---
author: ebishop
comments: false
date: 2018-10-02 21:08:49+00:00
layout: post
link: https://launchdarkly.com/blog/launched-redis-integration-for-launchdarkly-net-sdk/
slug: launched-redis-integration-for-launchdarkly-net-sdk
title: 'Launched: Redis Integration for LaunchDarkly .NET SDK'
wordpress_id: 193409
categories:
- Product Updates
tags:
- .NET SDK
- launchdarkly relay proxy
- redis
- redis integration
- SDKs
---

The LaunchDarkly service is built from the bottom up to be [highly available and highly resistant](https://launchdarkly.com/blog/designing-for-failure-to-avoid-disaster/) to multiple types of failures to ensure that our customers' applications are always able to serve their customers. One of these levels of redundancy is an optional [Redis](https://redis.io/) store.

Today, we've added native Redis feature store support to the .NET SDK, providing a persistent store of feature flag configurations. There are two ways to use the Redis feature store:



 	
  * With a regular connection to LaunchDarkly. In this configuration, when the SDK receives new feature flag data from LaunchDarkly, it stores the flags in Redis. When you ask the SDK to evaluate a feature flag, it retrieves the data from Redis (using an in-memory read-through cache to improve performance if the same flag is being queried repeatedly). If the LaunchDarkly connection is unavailable when your application starts up, the last known feature flag data can still be obtained from Redis.

 	
  * Or, with the [LaunchDarkly Relay Proxy in daemon mode](https://github.com/launchdarkly/ld-relay#daemon-mode). In this configuration, the relay proxy is responsible for putting the latest flag data into Redis; the SDK communicates only with Redis (again using a read-through cache) and does not connect directly to LaunchDarkly.


The Redis feature store is available as a separate NuGet package, `LaunchDarkly.Client.Redis`; the source code is published [here](https://github.com/launchdarkly/dotnet-client-redis).

Redis support for our .NET SDK joins the Redis support already available with all of our [other server-side SDKs](https://docs.launchdarkly.com/docs/java-sdk-reference).
