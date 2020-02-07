---
author: edithharbaugh
comments: false
date: 2016-08-27 00:40:32+00:00
layout: post
link: https://launchdarkly.com/blog/3-ways-to-avoid-technical-debt-when-feature-flagging/
slug: 3-ways-to-avoid-technical-debt-when-feature-flagging
title: 3 Ways to Avoid Technical Debt when Feature Flagging
wordpress_id: 1019
categories:
- Continuous Delivery
- DevOps
- Feature Management
tags:
- feature flag
- feature flag driven development
- feature flag management
- feature flags
- feature toggle
- feature toggles
- technical debt
---

Feature flags are a valuable technique of separating out release (deployment) from visibility. Feature flags allow a software organization to turn features on and off at a high level, as well as segment out their base to allow different users different levels of access. However, feature flags have an (ill-deserved) reputation of “Technical Debt”. Used incorrectly, feature flags can accumulate, add complexity, and even break your system. Used correctly, feature flags can help you move faster. Here’s three easy ways you can [avoid technical debt when using feature flags](https://blog.launchdarkly.com/how-to-use-feature-flags-without-technical-debt/).



 	
  1. **Create a central repository for feature flags**


Using config files for feature flags is “the junk drawer” of technical debt. If you have seven config files with different flags for different parts of the system, it’s hard to know what flags exist, or how they interact. Have one place where you manage all of your feature flags. 



 	
  2. ** Avoid ambiguously named flags**


Give your flags easy to understand, intuitive names. Assume that someone other than you and your flag could potentially be using this flag days, months, and years into the future. Don’t have a name that could cause someone to turn it on when they mean off, or vice versa. For example “FilterUser”, when it’s off - does this mean users are filtered? or not? 



 	
  3. ** Have a plan for flag remova**l 


Some flags are meant for permanent control, for example for an entitlements system. Other flags are temporary, meant for the purpose of a release only. If a flag can be removed (because it’s serving 100% or 0% of traffic), it should be removed, as quickly as possible. To enforce this rigor, when you write the flag, also write the pull request to remove it. That way, when it’s time to remove the flag, it’s a two second task.
