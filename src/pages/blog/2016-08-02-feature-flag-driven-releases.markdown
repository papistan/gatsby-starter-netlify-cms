---
author: justinucd
comments: false
date: 2016-08-02 07:07:28+00:00
layout: post
link: https://launchdarkly.com/blog/feature-flag-driven-releases/
slug: feature-flag-driven-releases
title: Feature Flag-Driven Releases
wordpress_id: 982
categories:
- Continuous Delivery
- DevOps
- Feature Management
tags:
- DevOps
- feature flags
- feature rollouts
- feature toggles
- feedback loop
- release strategy
---

### Using feature flags to incorporate a release strategy into your development process





#### **The Old Way**


The "old way" of software releases is characterized by an explicit waterfall hand-off between teams - from Product (functional requirements) to Engineering (build and deploy). This old way did not explicitly promote release planning in the development process. The full release burden was shifted from one team to another without plans for a feedback loop or integrated release controls.  Hence, it was difficult for teams to continuously deliver software, gather feedback metrics, and take full control over software rollouts and rollbacks.

With the rise of continuous delivery, teams are integrating feature release and rollout controls into the product development process.  This is ushering in a new era of DevOps where teams collaborate on release strategies during the initial design phase in order to manage a release throughout the development cycle, from local, QA, staging, and to production.

How will the feature be released?  Who will be getting this feature first?  Will it be gradually rolled out? Who will alpha/beta test it?  What if something doesn’t go right?  All of these considerations (and more) are typically not discussed in initial planning meetings. [By codifying a release strategy from the start](https://blog.launchdarkly.com/feature-flag-driven-development/), you can ensure that your software release matriculates smoothly from build to release to sunset.


#### **Release Strategy**


Release strategy is a DevOps concept where teams integrate feature release planning into the development process.  Instead of pushing a new feature to production and being done with it, developers integrate feature flags into the development lifecycle to control their releases.  Broadly speaking, feature flagging is a way to control the visibility and on/off state of a particular feature by wrapping the code in a conditional.  The process of flagging encourages developers to plan for the initial feature rollout, feature improvements based on user feedback, and overall feature adoption.  It basically compels teams to incorporate a release strategy into the development process.

Josh Chu, Director of Engineering at [Upserve](https://upserve.com/), explains how his team incorporates release strategy:

“A lot of times people would say ‘let's roll this out’ and not think about how to actually get adoption. The fact that you have a feature flag story raises visibility. Engineers start thinking about how their feature is going to get rolled out rather than just ‘push it to production, it's done’. The product team is encouraged to take a more hands-on approach to pre-release feedback, which directly feeds into obtaining post-rollout traction.”



[![LaunchDarkly Rollout and Release Strategy Feature Flags and Feature Toggles](https://blog.launchdarkly.com/wp-content/uploads/2016/07/rollout_strategy_1.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/07/rollout_strategy_1.jpg)


#### **Strategic Rollouts Using Feature Flags**


In this section, we illustrate an example of how a release strategy can be incorporated into a traditional design, build, test, and release process.

**Stage 1 - Feature Design**



 	
  * Design the feature’s functionality, examine the target audience and use case, and develop a timeline for implementation.


**Stage 2 - Release Strategy**



 	
  * Collaborate on rollout and release strategy.  Should the feature flag be a front-end flag, back-end flag, or both? (Front-end flags are mainly used to control UI visibility, while back-end flags can control APIs, configurations, and even routing).  What should be behind the flag?  Is this a permanent or temporary flag? (ex. permanent = ‘maintenance mode’, temporary = ‘new signup form’) Who has rights to change the flag?  Is the flag intended to control a percentage rollout? How will we incorporate user feedback? How will we measure adoption and traction?


**Stage 3 - Build**



 	
  * Develop and integrate, using the feature flag to manage the feature’s progression through multiple development environments.


**Stage 4 - Test**



 	
  * Test the feature in QA and Staging, using the feature flag to control rollout and user targeting.


**Stage 5 - Release**



 	
  * Deploy the feature as ‘off’ in production and then implement your release and rollout strategy.  This could be an incremental percentage rollout, individual user targeting, or targeting groups of users.


[![LaunchDarkly Rollout and Release Strategy Using a Feedback Loop Feature Flags and Feature Toggles](https://blog.launchdarkly.com/wp-content/uploads/2016/07/rollout_strategy_2.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/07/rollout_strategy_2.jpg)

**Feedback Loop**

By adopting a release strategy, Engineering, Product, and Design teams can continuously collaborate on release and rollout plans, assessing user and performance feedback along the way.  Bryan Jowers, Product Manager at AppDirect, comments on the benefits of controlled rollouts, “It allows us to bring product to market faster, test, get data, and iterate… Engineering, Product, and leadership are all looking to deliver product with low risk… and we do that with tightly controlled rollouts.”

Instead of pushing a future to production and being done with it, teams should be designing release strategies that incorporate targeted/incremental rollouts with the intention of iterating based on feedback.  This creates a continuous [feedback loop](https://launchdarkly.com/use-cases/?utm_source=launchdarkly_blog&utm_medium=organic) because teams can synthesize performance metrics and transform those metrics into better, faster iterations.

**Take-Aways**

Release strategy incorporates release and rollout planning into the development process.  It forces teams to plan for feature rollouts and develop methods for aggregating user feedback, analyzing metrics, and assessing traction.  One of the proven ways to do this, as used by teams at Upserve and AppDirect, is to use [feature flags](https://blog.launchdarkly.com/feature-flag-driven-development/) to launch, control, and measure features from development to release.



_LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER BY HELPING MANAGE FEATURE FLAGS AT SCALE. START YOUR FREE TRIAL [NOW](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._


