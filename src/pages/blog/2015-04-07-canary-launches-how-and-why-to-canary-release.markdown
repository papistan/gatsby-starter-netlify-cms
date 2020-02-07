---
author: edithharbaugh
comments: false
date: 2015-04-07 19:00:52+00:00
layout: post
link: https://launchdarkly.com/blog/canary-launches-how-and-why-to-canary-release/
slug: canary-launches-how-and-why-to-canary-release
title: Canary launches - how and why to canary release
wordpress_id: 76
categories:
- Feature Management
---

A canary launch (aka canary deployment or [canary release](http://martinfowler.com/bliki/CanaryRelease.html)) is rolling features out to a small number of users to assess the reaction of the overall system. Are users happier? Is more money made? Does the new feature increase system load? A canary launch allows you to roll out a feature slowly, and measure the reaction from real user “canaries”, looking for early indicators of danger. If a feature is not good, it can rolled back. Canary launches are a best practice for agile development organizations practicing continuous delivery to move faster.

[![canary](https://blog.launchdarkly.com//wp-content/uploads/2015/09/canary.png)](https://blog.launchdarkly.com//wp-content/uploads/2015/09/canary.png)

Canary launches are named after the “canary in a coal mine” - miners would carry canaries into mines, as canaries were more sensitive to fatal gases like methane or carbon monoxide. If the canary stopped singing, miners knew to exit the mine immediately. Canary launches are different than internal betas (dog fooding), user testing, QA or performance testing in that all of those methods are done in controlled test environments. Canary launching is done on real users in a production environment, either in a randomized fashion or with users explicitly assigned or opted in to the early launch. For example, Google always releases new versions of Chrome as “Chrome Canary” to allow early adopters to try new features.

Traditional pre-launch activities to improve product quality like internal betas, user testing, QA and performance testing are all helpful, but they all lack the key component of testing a feature in actual usage. For example, recruiting people off Craigslist to look at your new user experience in a lab is extremely different than a harried traveler running for a plane seeing your new user experience. QA can try to run every test they can think of, but not be able to know or think of some real life test cases. With the explosion of devices and browsers, it’s difficult to test across platform. And for performance testing, running tests in a lab misses real world latencies and hiccups. I worked at an Internet of Things company where we’d test uploads of our data - sitting in our office with a high speed internet connection. Our real users sometimes had dial-up!

Traditionally, companies have “rolled-their-own” platforms to enable canary launches. The key issues with homegrown systems is whether the systems are effective and maintainable. If your framework fails, you’re in a bad state. In addition, maintenance can be a hassle. LaunchDarkly offers “canaries as a service” - we are a blazingly fast, completely scalable platform for you to roll out features, see the reaction on your users, and either continue rollout or completely shut off. Here's a [video demonstrating canary launching](https://www.youtube.com/watch?v=hj5PYsQpgck) with LaunchDarkly.

Now, you might be thinking - isn’t in bad to test potentially imperfect features on real users? Shouldn’t we do everything beforehand to prevent defects? Of course we should. Every good product development org will do their darndest to product high quality code. However, canary launches provide risk mitigation. If an issue IS to occur, do you want 100% of your users to encounter the issue, or 1%? And, if an issue is to be found, don’t you want a mechanism to quickly recover? To quote Sting of the Police “First to fall over when the atmosphere is less than perfect Your sensibilities are shaken by the slightest defect - you're a canary in a coal mine”. Canary launches allow you to quickly identify issues that might impact your entire user base, roll back easily to a known good version, and fix the issues in a controlled environment. The net result is a better product for all.



* * *





###### _LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER WITH FEATURE FLAGS AS A SERVICE. START YOUR FREE TRIAL [NOW](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._
