---
author: johnkodumal
comments: false
date: 2015-06-01 19:19:15+00:00
layout: post
link: https://launchdarkly.com/blog/launched-cors-support/
slug: launched-cors-support
title: 'Launched: CORS support'
wordpress_id: 90
categories:
- Product Updates
---

We've upgraded our [REST APIs](https://apidocs.launchdarkly.com) to support [CORS](http://www.w3.org/TR/cors/). This lets anyone build web pages that call LaunchDarkly's APIs directly-- no need to proxy through a server.

You can make authenticated CORS calls just as you would make same-origin calls, using either [token or session-based authentication](http://apidocs.launchdarkly.com/v1.0/docs/authentication). If you're using session auth, you should set the `withCredentials` property for your `xhr` request to `true`.

One last thing-- for security reasons, all `POST`, `PATCH`, and `PUT` calls to our API require a `Content-Type` of `application/json`.

Happy launching!





* * *





###### _LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER WITH FEATURE FLAGS AS A SERVICE. START YOUR FREE TRIAL [NOW](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._
