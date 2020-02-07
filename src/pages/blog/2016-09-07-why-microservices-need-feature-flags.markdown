---
author: edithharbaugh
comments: false
date: 2016-09-07 17:24:46+00:00
layout: post
link: https://launchdarkly.com/blog/why-microservices-need-feature-flags/
slug: why-microservices-need-feature-flags
title: Why microservices need feature flags
wordpress_id: 1063
categories:
- Feature Management
tags:
- feature flags
- Martin Fowler
- microdeployments
- microservices
---

Microservices is the practice of breaking up a huge, monolithic release where all components are tested and released as a whole, into many discrete services that can go on independent release schedules. The benefits of[ microservices were popularized by Martin Fowler](http://martinfowler.com/articles/microservices.html), and put into practice by Amazon and Netflix. However, with microservices, releases become more complicated, by n-factorial. Instead of one monolith that can tested as a whole, if there are even as few as nine different services, each needs to be tested with every other component. Suddenly there are nine potential friction points.

Feature flags to the rescue! With feature flags, engineering teams can have [complete control over their various microservices](https://blog.launchdarkly.com/feature-flagging-for-back-end-and-microservices/). First, wrap the microservice with a feature flag, with all traffic going to the old version. Then, release a new version. With a feature flag, gradually put whatever traffic you want to the new version, verifying functionality in all the other micro services. The new traffic and be cordoned off however suits your business. A feature flag at it’s simplest can be an “on” “off” switch to quickly flip between versions, similar to a blue green deployment. However, feature flags can serve arbitrarily complex (or simple) variations of traffic to the new microservice. Some example of how to test the new micro service are
- percentage rollout
- by IP address of service
- by version number of other services
or whatever other information. Feature flags allow users to do “microdeployments” of microservices. A microdeployment is breaking a deployment into smaller components of who exactly receives the new service.

Using feature flags and microservices together allows engineering teams to truly unlock the value of decoupling. You can read more about how we use microservices and feature flags at LaunchDarkly [here](https://blog.launchdarkly.com/feature-flagging-for-back-end-and-microservices/).



_LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER BY HELPING MANAGE FEATURE FLAGS AT SCALE. START YOUR FREE TRIAL [NOW](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._


