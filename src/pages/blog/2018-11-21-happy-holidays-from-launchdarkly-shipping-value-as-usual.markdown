---
author: zachdavis
comments: false
date: 2018-11-21 17:35:31+00:00
layout: post
link: https://launchdarkly.com/blog/happy-holidays-from-launchdarkly-shipping-value-as-usual/
slug: happy-holidays-from-launchdarkly-shipping-value-as-usual
title: Happy Holidays from LaunchDarkly - Shipping Value as Usual
wordpress_id: 193542
categories:
- Continuous Delivery
- Product Updates
tags:
- code deployments
- code freeze
- feature flagging
- risk
---

This week, many software teams across the U.S. will invoke a "deploy freeze" in an effort to minimize the risk of something going wrong at an inopportune time—such as mid-meal on Thanksgiving day. Here at LaunchDarkly we're still deploying at will, leveraging feature flags to eliminate risk and reclaim peace of mind.

Many teams find themselves short-handed this week, with people traveling and spending time with their families around the Thanksgiving holiday. At first glance it seems logical to avoid shipping in the run-up to a holiday weekend, because it just feels too risky. However, that mind-set doesn't get rid of the risk, it just kicks it down the road a bit. Next week's deploy gets larger and scarier. Also, for many teams not shipping isn't an option with Black Friday and Cyber Monday just around the corner.

We deliver over 30 billion flags a day for our customers and we know we're critical to many teams who won't or can't take time off this week. But because we use feature flags to control the release of new features and as a way to nearly instantaneously respond to unexpected problems, it's less risky for us to deploy as normal than to accumulate a bunch of un-deployed code.

Last week, we ran an internal exercise we call "focus week." It's an opportunity for everyone on the engineering team to focus on something that might not always get the roadmap time it deserves—tech debt, dev speed, performance.

Some of the things our engineers accomplished include:



 	
  * Cross-service tracing using [opentracing](https://opentracing.io/)

 	
  * Internal reporting and metrics collection

 	
  * Upgrading our ElasticSearch Clusters

 	
  * Improving the experience and documentation for new users

 	
  * Documenting elements of our design language


It's important work, and a lot of it will get deployed this week. For instance, the two newest members of our team collaborated on updating our application to be more friendly to screen readers and those who have [color vision deficiency](https://www.aoa.org/patients-and-public/eye-and-vision-problems/glossary-of-eye-and-vision-conditions/color-deficiency).

Come Thanksgiving, I'll have plenty of things to stress out about—I'm smoking a turkey for a mishmash of family and friends—but code, deployed or un-deployed, won't be one of them.
