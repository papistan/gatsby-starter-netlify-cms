---
author: edithharbaugh
comments: false
date: 2017-02-16 18:00:58+00:00
layout: post
link: https://launchdarkly.com/blog/net-promoter-score-feature-flags-for-canary-releases/
slug: net-promoter-score-feature-flags-for-canary-releases
title: Net Promoter Score + Feature Flags for canary releases
wordpress_id: 1416
categories:
- Feature Management
tags:
- canary release
- feature flags
- Net PromoterScore
- people.ai
---

Canary releases are a DevOps best practice of pushing new features to a subset of your customers. By pushing to a subset, this group can provide early feedback, verify functionality, and act as “canaries” to your entire population. Originally, canary had a negative connotation - miners took canaries down into mines, as canaries were more sensitive to bad air. If the canary stopped singing, the miners knew it was time to skedaddle. 

Surprisingly, being a canary can actually make your customers even bigger fans! I heard a great use case from a LaunchDarkly customer [People.ai](https://people.ai/),  [AI for managing sales teams](https://people.ai/product/), who would automatically push new features out to users who had an NPS of over a certain threshold. Net Promoter Score (NPS) rates how strongly would a customer recommend your solution, so initially, this seemed bizarre.  Why risk showing your best advocates functionality that might be unstable, early, or fragile? However, the people who are happiest users (likely to recommend) are actually very excited about being the first to see new functionality. They love feeling plugged-in to new development. And in addition, with LaunchDarkly [feature flag management](https://blog.launchdarkly.com/launched-enterprise-feature-flag-management/), if a feature isn’t doing well, the team can instantly turn it off, reverting to the old, stable experience. 

I love hearing stories about how customers are using LaunchDarkly’s segmentation capabilities to release better software, quicker. 


