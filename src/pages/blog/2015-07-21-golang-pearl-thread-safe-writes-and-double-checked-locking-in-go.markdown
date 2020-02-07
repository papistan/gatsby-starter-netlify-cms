---
author: johnkodumal
comments: false
date: 2015-07-21 19:02:55+00:00
layout: post
link: https://launchdarkly.com/blog/golang-pearl-thread-safe-writes-and-double-checked-locking-in-go/
slug: golang-pearl-thread-safe-writes-and-double-checked-locking-in-go
title: 'Golang pearl: Thread-safe writes and double-checked locking in Go'
wordpress_id: 104
categories:
- Continuous Delivery
- DevOps
tags:
- Golang
---

Channels should be your first choice for structuring concurrent programs in Go. Remember the Go concurrency credo-- "do not communicate by sharing memory; instead, share memory by communicating." That said, sometimes you just need to roll up your sleeves and share some memory. Lock-based concurrency is pretty old-school stuff, and battle-hardened Java veterans switching to Go will undoubtedly feel nostalgic reading this. Still, many brand-new Go converts probably haven't encountered low-level concurrency primitives before. So let's sit down and program like it's 1999.

To start, let's set up a simple lazy initialization problem. Imagine that we have a resource that is expensive to construct- it's read often but only written once. Our first attempt at lazy initialization will be completely broken:

    
    type Expensive struct {
      Data int
    }
    
    var instance *Expensive
    
    func GetInstance() *Expensive {
      if instance == nil {
        time.Sleep(5 * time.Second) // Simulate an expensive initialization step
        instance = &Expensive{42} 
      }
      return instance
    }
    
    func Broken() {
      go GetInstance()
      go GetInstance() // may also take 5+ seconds
    }


This doesn't work, as both goroutines in `Broken` may race in `GetInstance`. There are many incorrect (or semantically correct but inefficient) solutions to this problem, but let's focus on two approaches that work. Here's one using read/write locks:

    
    var mutex = &sync.RWMutex{}
    
    func GetInstance() *Expensive {
      mutex.RLock()
      if instance == nil {
        mutex.RUnlock()
        mutex.Lock()
        defer mutex.Unlock()
        if instance == nil {
          time.Sleep(5 * time.Second)
          instance = &Expensive{42}       
        }
        return instance
      } else {
        defer mutex.RUnlock()
        return instance
      }
    }


If you're a Java developer you might recognize this as a safe approach to [double-checked locking](https://en.wikipedia.org/wiki/Double-checked_locking). In Java, the `volatile` keyword is typically used on `instance` instead of using a read/write lock, but since Go does not have a volatile keyword (there is `sync.atomic`, and we'll get to that) we've gone with a read lock.

The reason for the additional synchronization around the first read is the same in Go as it is in Java. The [go memory model](https://golang.org/ref/mem) does not otherwise guarantee that the initialization of `instance` is visible to other threads unless there is a happens-before relation that makes the write visible. The read lock ensures this.

Now back to `sync.atomic`. Among other things, the `sync.atomic` package provides utilities for atomically visible writes. We can use this to achieve the same effect as the `volatile` keyword in Java, and eliminate the read/write lock. The cost is one of readability-- we have to change `instance` to an `unsafe.Pointer` to make this work, which is aesthetically displeasing. But hey, it's Go-- we're not here for aesthetics (I'm looking at you `interface{}`):

    
    var instance unsafe.Pointer
    
    var mutex = &sync.Mutex{}
    
    func GetInstance() *Expensive {
    	if inst := (*Expensive)(atomic.LoadPointer(&instance)); inst != nil {
    		return inst
    	} else {
    		mutex.Lock()
    		defer mutex.Unlock()
    		if instance == nil {
    			time.Sleep(5 * time.Second)
    			inst = &Expensive{42}
    			atomic.StorePointer(&instance, (unsafe.Pointer)(inst))
    		}
    		return (*Expensive)(instance)
    	}
    
    }


Astute Gophers might recognize that we've re-derived a utility in the `sync` package called `Once`. `Once` encapsulates all of the locking logic for us so we can simply write:

    
    var once sync.Once
    
    func GetInstance() *Expensive {
      once.Do(func(){
        time.Sleep(5 * time.Second)
        instance = &Expensive{42}
      })
      return instance
    }


Lazy initialization is a fairly basic pattern, but once we understand how it works, we can build safe variations like a [resettable `Once`](https://github.com/matryer/resync). Remember though-- this is all last-resort stuff. Prefer channels to using any of these low-level synchronization primitives.



* * *





###### _LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER WITH FEATURE FLAGS AS A SERVICE. START YOUR FREE TRIAL [NOW](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._
