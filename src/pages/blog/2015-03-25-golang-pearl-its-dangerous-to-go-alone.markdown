---
author: johnkodumal
comments: false
date: 2015-03-25 19:52:05+00:00
layout: post
link: https://launchdarkly.com/blog/golang-pearl-its-dangerous-to-go-alone/
slug: golang-pearl-its-dangerous-to-go-alone
title: 'Golang pearl: It''s dangerous to go alone!'
wordpress_id: 70
categories:
- Continuous Delivery
- DevOps
---

[![its-dangerous-to-go-alone-take-this](https://blog.launchdarkly.com//wp-content/uploads/2015/09/its-dangerous-to-go-alone-take-this.jpg)](https://blog.launchdarkly.com//wp-content/uploads/2015/09/its-dangerous-to-go-alone-take-this.jpg)

In Go, the `panic` function behaves somewhat like an unrecoverable exception: `panic` propagates up the call stack until it reaches the topmost function in the current goroutine, at which point the program crashes.

This is reasonable behavior in some environments, but programs that are structured as asynchronous handler functions (like daemons and servers) need to continue processing requests even if individual handlers panic. This is what `recover` is for, and if you inspect the [source](https://sourcegraph.com/github.com/golang/go@ac452349e4f40c30d50f9922bf2c4592e748ce5e/.tree/src/net/http/server.go#startline=1175&endline=1188) you'll see that Go's built-in HTTP server package recovers from panics for you, meaning that bugs in your handler code will never take down your entire HTTP server.

Unless, of course, your handler code spawns a goroutine that panics. Then your server is screwed. Let's demonstrate with a trivial example:

    
    package main
    
    import (
      "io"
      "net/http"
    )
    
    func hello(w http.ResponseWriter, r *http.Request) {
      panic("hi")
    }
    
    func main() {
      http.HandleFunc("/", hello)
      http.ListenAndServe(":8000", nil)
    }


This server will happily chug along, panicking every time the root resource is hit, but never crashing.

But if `hello` panics in a goroutine, the entire server goes down:

    
    func hello(w http.ResponseWriter, r *http.Request) {
      go panic("hi")
    }


In our web services, we can never really trust a naked use of `go`. We wrap all our goroutine creation in a utility function we call `GoSafely`:

    
    import (
      "github.com/launchdarkly/foundation/logger"
      "runtime"
    )
    
    func GoSafely(fn func()) {
      go func() {
    
        defer func() {
          if err := recover(); err != nil {
            stack := make([]byte, 1024*8)
            stack = stack[:runtime.Stack(stack, false)]
    
            f := "PANIC: %s\n%s"
            logger.Logger.Error().Printf(f, err, stack)
          }
        }()
    
        fn()
      }()
    }


Here's how we use it:

    
    func hello(w http.ResponseWriter, r *http.Request) {
      GoSafely(func() {
        panic("hi")  
      });
    }


Not as syntactically sweet as a naked `go` routine, but it does the trick. The unfortunate thing (which we don't really have a solution for) is that any third-party code that spawns a `go` routine could potentially panic-- and we have no way of protecting ourselves from that.



* * *





###### _LaunchDarkly helps you build better software faster with feature flags as a service. Start your free trial [now](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._
