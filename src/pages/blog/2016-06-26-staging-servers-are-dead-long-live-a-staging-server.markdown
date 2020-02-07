---
author: edithharbaugh
comments: false
date: 2016-06-26 17:34:46+00:00
layout: post
link: https://launchdarkly.com/blog/staging-servers-are-dead-long-live-a-staging-server/
slug: staging-servers-are-dead-long-live-a-staging-server
title: Staging Servers are Dead! Long Live a Staging Server
wordpress_id: 937
categories:
- DevOps
tags:
- continuous delivery
- DevOps
- microservices
- software development
- staging environment
- staging server
---

Earlier this year, I wrote about why [staging servers should die](http://readwrite.com/2016/01/22/staging-servers/) - that they actually increase risk and time and decrease quality. I’ve been very pleased with the thoughtful comments and feedback I’ve gotten about why effective continuous delivery and DevOps means no staging server. The one that made me the happiest was [“Dreams exist to become reality. Here is one I'd like to achieve at work.”](https://twitter.com/nicomputing/status/692044904931987456)

Here I’ll address the feedback I received, and what’s standing in the way of achieving this dream. 



First, there was a large agreement that “waterfall deployment” with a staging server added time and risk to the launch process. 



 	
  * Rapportive founder Sam Stokes agreed, saying [“Staging environments are an evolutionary dead end. They get out of sync, slow you down, just get neglected.”](https://twitter.com/samstokes/status/690689667306369024)

 	
  * [Christian Deger](https://twitter.com/cdeger?lang=en), Autoscout Software Architect  said “staging environment, even in a completely automated cloud setup, requires constant effort and produces costs.” 

 	
  * Dave Nolan gave [a talk at Pipeline London](https://vimeo.com/162633462) on #nostaging. 




Here are the questions and concerns about the practicality and validity of the “#noStaging” Dream. 



“Don’t we need to test major infrastructure changes in Staging?”

I’m not advocating pushing untested code willy nilly into production. I am advocating for through and complete automation, continuous integration and feature flagging, with the goal to get as quickly as possible to production. The reason to kill staging servers was said very well by [Joseph Ruscio](https://twitter.com/josephruscio?lang=en), Librato CTO & co-founder  “You think of everything in advance of how a user will use a feature, and you still miss half of them.” The purpose of DevOps is to move as fast as possible from code on a developers box to customer. 



One great case study is [Librato](https://www.librato.com/). Librato uses feature flags to wrap features, deploying their code and then ramping volume up and down, [controlling risk](https://blog.launchdarkly.com/powering-continuous-delivery-with-feature-flags/). The allure of a staging server is that all systems can be thoroughly tested there, “guaranteeing” a painless final deployment. However, the moment where you push code to the real world is the scariest, because the real world NEVER matches staging. By using feature flagging, Librato could de-risk a new infrastructure project. They used [“Branch-by-abstraction”](http://paulhammant.com/blog/branch_by_abstraction.html) to ramp on and off a new infrastructure. The old way would have been to push the entire new infrastructure at a slow time like 3 am, then when something went wrong, scramble to fix, precisely when memories and tempers are short due to sleep deprivation and key people might be asleep. With feature flags, Librato could ramp up volume in the real world, with real data. Ruscio says of their rollout with feature flags, “We never got paged at night for an issue with the new system, as we were only introducing it during the day when we were available. So all issues could be addressed while we were available. With feature flags, we could even dial back risk during lunch hour.”



“But we need a staging server for contractual reasons” 

Having a staging server for contractual reasons is arguing for an artificial artifact. As Dave Farley, co-author of Continuous Delivery” says “it’s not done until it’s delivered to users”. Lamont Lucas, [FastRobot](http://www.fastrobot.com/) co-founder, says “media and advertising companies want final approval before a feature goes live, generally from non-technical approvers. Flagging all users coming from a gateway lets you fulfill the contractual obligation (of showing a feature to them for approval) while preventing you from having an entire legacy/pointless staging setup.” 



“What about performance testing?” 

[Sean Byrnes](https://twitter.com/sbyrnes?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor), CEO/Founder of [Outlier](http://outlier.ai/) and the Founder of [Flurry](https://twitter.com/FlurryMobile), often had to “test that new features work in a production-like environment and don't compromise the integrity of our systems", as Flurry had millions of users worldwide.  However, Byrnes continued, “You don't have to load test EVERY feature to failure”.

The failure of most features is lack of load as there’s no customer interest. However for features where you do really need to know the failure rate, an alternate server other than production can be spun up ephemerally for that reason. Just don’t call it “the staging server” - it’s a production-like load system spun up for a specific reason - to test load - and then shut down after its purpose is complete. 



“Feature flags are only good for shallow UE changes, not for Microservices”.

Actually, [microservices make using staging servers even more painful](https://blog.launchdarkly.com/why-microservices-need-feature-flags/) as many versions of different microservices might be running across staging and production. Deger says,  “In a microservices architecture with lot of independent deployments going on, using a single staging environment would inadvertently test integrations with services in different versions, than what is currently in production. This gives a false sense of security. So we decided to not have a staging environment at all and find different ways to release features with confidence while only integrating into production.

We are constantly learning new techniques to deploy into production without a staging environment. There are many different ways of integrations that we need to care of, but overall it makes us faster and the testing and release experience is better."”



“Harbaugh is biased” 

I advise that instead of a confusing, time consuming, expensive, redundant and ultimately unsuccessful staging server; development teams should use feature flags to move features to production and do their feature validation as quickly as possible on production. I’m not unbiased - I’m CEO of a feature flagging management platform, LaunchDarkly. However, I founded LaunchDarkly the same reason I [publish articles](http://firstround.com/review/startups-software-development-and-the-art-of-bicycle-maintenance/), [podcasts](https://www.heavybit.com/library/podcasts/to-be-continuous/), and [give talks on DevOps](https://www.youtube.com/watch?v=28ZAoStv-Xw): because I care deeply about the power of feature flagging to create better quality software and reduce risk. You don’t need LaunchDarkly to feature flag - it’s easy to get started with a simple config file or open source library. Deger, is the contributor to an open source framework for feature flagging and huge proponent of no staging servers. 



“Let’s talk when you want to do serious software development”. 

Just as waterfall development once seemed the only way to guarantee success, so did waterfall deployment until recently. The most innovative and fast moving companies like Netflix, Google, and Amazon have found that they can move faster if they’re more agile. And serious? I think of software development as fun, as exciting, as liberating, transforming - with software people are connected worldwide, interacting in incredible ways, and their lives are better. I hope software never becomes too serious for me. 
