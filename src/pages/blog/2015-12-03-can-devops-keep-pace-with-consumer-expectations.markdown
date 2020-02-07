---
author: justinucd
comments: false
date: 2015-12-03 07:33:19+00:00
layout: post
link: https://launchdarkly.com/blog/can-devops-keep-pace-with-consumer-expectations/
slug: can-devops-keep-pace-with-consumer-expectations
title: In 2016, can DevOps keep pace with consumer expectations?
wordpress_id: 258
categories:
- Continuous Delivery
- DevOps
tags:
- canary launches
- canary release
- continuous delivery
- dark launches
- feature flags
- rollouts
---

## Consumer Expectations


Every morning, I roll out of bed at 8:01am and lazily reach for my phone to check my Apple News feed.   Sometimes, the app has the audacity to make me wait 2 full seconds before it refreshes my feed with 100 articles from dozens of sources around the web.

Unacceptable!  I want my news feed instantly.  I want it now.  I can feel myself get frustrated and I can feel my patience evaporate in a flash.  Then I take a step back: since when do I take personal offense to an application that doesn't load instantly?  Why do I get flustered as if I was rear-ended by a car?

This is just a microcosm of current consumer expectations.   An iOS bug becomes a TechCrunch headline, a bad Facebook feature makes CNN's front page, and an app that drains 0.1% more battery life becomes a human rights violation.

As a developer, imagine trying to adapt to these expectations.  Consumers want things to work instantly, smoothly, and intelligently.  They want everything to be perfect and work seamlessly or else they get frustrated, offended, and vocally upset.  "Ugh, why do I have to click TWO buttons to see this?"


## INCREMENTAL ROLLOUTS


Moving into 2016, what can developers do to meet or even exceed these expectations? Simply releasing software faster will not necessarily [mitigate risk](https://blog.launchdarkly.com/risk-elimination-and-the-launchdarkly-value-add/), nor will it necessarily lead to a better product.  The key question to address is "how can I adapt my development process to exceed consumer expectations?"

It doesn't matter how wonderful your new feature is if it degrades your application's performance.  Product-market fit no longer means that your product merely serves a market, but that it must meet that market's expectations for performance.

**How you release a feature becomes as important as the feature itself.  ** [DevOps in 2016](https://blog.launchdarkly.com/devops2/) should be the year of the incremental rollout, whereby assessing your application's response to a new feature becomes a prerequisite for a launch.  I am not strictly referring to local or staged testing, but actual testing in production.

I recently published a piece on [feature flag driven development](https://dzone.com/articles/feature-flag-driven-development) and I feel that this practice of compartmentalized release is essential for managing risk and meeting consumer expectations.  By flagging a feature (i.e wrapping it in a condition), you can deploy it off and then incrementally turn it on for particular users, assessing performance feedback along the way.

[![LaunchDarkly Feature Flag Rollouts](https://blog.launchdarkly.com/wp-content/uploads/2015/12/iterative_rollout2.png)](https://blog.launchdarkly.com/wp-content/uploads/2015/12/iterative_rollout2.png)


## Managing Scalability with Rollouts


Let's look at an example.  You are a developer launching a new feature that will require you to process hundreds of additional requests per second.  A few hundred more?  That's no problem - you've built the infrastructure to scale and handle that load.  But, what if all your users fall in love with the new feature?  Bombarding you with thousands of requests.  How do you manage this?

Imagine that you were able to [roll out your feature](https://blog.launchdarkly.com/soft-launches-using-feature-flags/) live to 10% of your users and then 20%... 30%....  Each step becomes a testing benchmark where you assess performance feedback and can scale accordingly.

More importantly, you mitigate unanticipated performance degradation and meet the consumer expectation of seamless application performance.


## implementing rollouts


Of course, feature flagged rollouts are not the saving grace for every feature launch or app update, but they're fast becoming essential for DevOps as consumer expectations continue to raise the bar for performance.

Managing risk does not need to be a transformative operational process.  It can be easily achieved by flagging your features and gradually releasing them to your users.  After all, there's no better way to get genuine feedback than testing in a real environment.
