---
author: Jwin
comments: false
date: 2018-11-28 23:01:40+00:00
layout: post
link: https://launchdarkly.com/blog/best-practices-for-testing-code-under-feature-flags/
slug: best-practices-for-testing-code-under-feature-flags
title: Best Practices for Testing Code Under Feature Flags
wordpress_id: 193560
categories:
- Feature Management
tags:
- feature flags
- SDKs
- testing
---

<blockquote>**“What is the best practice for testing code under various flags? For example, is there a specific configuration that should be used when writing unit tests? Any stub method that we can use to set a specific value when running our tests. Any other considerations/samples?"**</blockquote>


Testing is a difficult subject, there is no written standard. The two things customers want from testing with the SDK is the ability to control which variations the SDK serves, and preventing the SDK from polluting an important environment with a bunch of garbage test users. There are some SDK specific tricks that can be used, but generally speaking there are five main approaches:

**Create a LaunchDarkly environment dedicated to testing.**
By having a single environment dedicated to testing, you can use the API to configure the environment before each test so the SDK will behave how you need it to. You also can leave events enabled so you can confirm tests are generating events the way you expect them to. Although if ensuring events are sending correctly is not a priority, then this approach offers little advantage over other approaches. The biggest problem with this approach is scalability. Running multiple tests concurrently can be difficult, since the environment can only be in one configured state at a time.

**Set the SDK to offline mode.**
This forces the SDK to evaluate all flags as their fallback values. This has the effect of being able to predict what the SDK will respond with, prevents the SDK from needlessly opening a streaming connection out to LaunchDarkly, and prevents users from being created since the SDK will send no event data back to LaunchDarkly. The disadvantage of this is that you cannot test your code using different configurations, since the SDK will only respond with fallback values.

**Use a Redis cache and enable LaunchDarkly Daemon (LDD) mode on the SDK.**
A more complicated but incredibly effective option is to populate a Redis cache with your desired flag configurations, then initialize the SDK in LDD mode when testing. This will result in the SDK not opening a streaming connection, and it will initialize immediately. Feature flags will be served from the Redis cache, and the SDK can still send analytic events to a testing environment. If the analytic events are not necessary, then sendEvents can be disabled, which will result in the SDK making no network requests at all to LaunchDarkly.

**Engineer a mock SDK for testing.**
Our SDK’s API is rather simple, and creating a mock which behaves similarly to the SDK is trivial. With a mock you can easily serve any value you wish when testing, but requires the resources and commitment to build and maintain it.

**Build a custom feature store for testing.**
Our SDKs support the ability customize the feature store. This feature exists so that you can use a Redis feature store, but you can build a custom feature store which responds with the values you provide it. When you initialize the SDK for testing, you simply configure the SDK to use this feature store instead of the default.
