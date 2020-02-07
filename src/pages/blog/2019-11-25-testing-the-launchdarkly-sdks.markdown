---
author: bwoskow
comments: false
date: 2019-11-25 16:00:29+00:00
layout: post
link: https://launchdarkly.com/blog/testing-the-launchdarkly-sdks/
slug: testing-the-launchdarkly-sdks
title: Testing the LaunchDarkly SDKs
wordpress_id: 194594
categories:
- DevOps
tags:
- roku
- SDKs
- testing SDKs
---

## Extending our testing strategy for the Roku SDK




### LaunchDarkly's testing strategy


At LaunchDarkly, we take testing very seriously. To be the top feature management platform, we need to validate that our platform can handle anything thrown at it. We need to ensure that our SDKs, which are intended to operate within our customers' applications, are performant and resilient across all of our supported platforms. This includes applications built with some of the industry's most popular server-side technologies, desktop applications, mobile apps, and more.

This post focuses on how we test our SDKs.

To ensure reliable product delivery, each SDK utilizes a couple of continuous integration workflows:



 	
  1. Unit tests for a quick feedback loop

 	
  2. Integration tests for a more thorough and complete examination


After the unit testing workflow completes, the latest source code is deployed to our integration testing infrastructure. This infrastructure contains a suite of long-running applications across all of our supported platforms - Java, .NET, Node.js, Android, iOS, and more. These applications are _long-lived_ for a realistic simulation of customers' environments. Traditionally, testing environments are thrown away after each workflow, however, this does not result in a realistic simulation; production environments are typically long-lived.

These long-running applications "wrap" (embed) our SDKs and expose the core SDK functionality through a consistently-defined REST API. We call these applications "restwrappers." Our restwrappers' APIs allow tests to be specified consistently across many different languages and platforms.

For each SDK and respective language or platform, there are multiple restwrappers with differing configurations. For example, we have one Node.js restwrapper operating streaming connections, another operating polling connections, yet another operating streaming connections while connected to a Redis-backed feature store, and more. Across nearly 20 SDKs, there are over 60 restwrappers that run continuously. Each depends on LaunchDarkly for feature flagging.

Once the restwrappers are deployed to the integration testing infrastructure, our centralized test harness connects to LaunchDarkly's REST API and to each restwrapper. The test harness proceeds to run a suite of tests. These tests cover each method in the SDK and verify that flag evaluation, event sending, stream re-connection, and other aspects of the SDK all behave correctly. This approach gives us the ability to test for consistency across SDKs, as well as test networking behavior in a long-running application. Each SDK can be monitored for memory usage and other potential resource leaks that might become apparent over time.

The test suite is scheduled to run continuously and operates against both our internal staging and production environments. This also serves as a full end-to-end integration test for the core services of our entire product.


### Integrating with Roku




[![puzzle-1](https://blog.launchdarkly.com/wp-content/uploads/2019/11/Integrations-1.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/11/Integrations-1.png)Prior to launching a new SDK, we always implement a restwrapper(s) with the testing framework as described above. When we [launched the LaunchDarkly SDK for Roku](https://launchdarkly.com/blog/launched-roku-sdk/), we found that integrating the Roku SDK (written in BrightScript) into this infrastructure required a couple slight yet significant deviations:






 	
  1. Typically, for reasons of convenience, our restwrappers operate within virtualized environments. However, existing BrightScript interpreters and Roku emulators are not officially supported and do not offer full compatibility with physical devices. To integrate our new Roku restwrapper into our testing infrastructure, we built a local Roku device farm and then ran an on-premise bridge server to offer a secure connection point from our AWS resources to our device farm.

 	
  2. Our restwrapper technical design allows the SDK to be controlled over a REST API, meaning that the restwrapper needs to run an HTTP server. Most languages and platforms have package ecosystems that would already provide such functionality. However, Roku lacks this ecosystem, and the platform itself was designed for media consumption – not serving a web API. To work around this, we implemented a BrightScript HTTP server from scratch.


Generally, we attempt to utilize cloud and SaaS technologies to their furthest potential, allowing us the ability to focus on what we do best. Sometimes things just have to be done in-house.

Implementing and testing the Roku SDK required more work than most of our other SDKs. But in doing so, we gained even more confidence that our SDKs and testing infrastructure are reliable, performant, consistent, and constantly improving.
