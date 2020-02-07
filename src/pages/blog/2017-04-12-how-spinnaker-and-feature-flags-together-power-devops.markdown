---
author: edithharbaugh
comments: false
date: 2017-04-12 16:28:48+00:00
layout: post
link: https://launchdarkly.com/blog/how-spinnaker-and-feature-flags-together-power-devops/
slug: how-spinnaker-and-feature-flags-together-power-devops
title: How Spinnaker and Feature Flags Together Power DevOps
wordpress_id: 1524
categories:
- Continuous Delivery
- DevOps
- Feature Management
tags:
- canary release
- continuous delivery
- feature flag
- feature flagging
- Netflix
- Spinnaker
---

It’s very common for customers to be excited about both [Spinnaker](http://www.spinnaker.io/) (continuous delivery platform) as well as feature flags. But wait? Aren’t they both continuous delivery platforms? Yes, they are both trying to solve the same pain points - the ability to quickly get code in a repeatable, non-breaking fashion, from the hands of the developers into the arms of hopefully excited end users, with a minimal amount of pain and heartache for everyone along the toolchain. But they solve different pain points:



 	
  * Spinnaker helps you deploy functionality to clusters of machines. 

 	
  * Feature Flags help you connect those functionality to clusters of USERS.  


Spinnaker helps with “_cluster management_ and _deployment management_”. With Spinnaker, it is possible to push out code changes rapidly, sometimes hundreds (if not thousands) of times a day. As Keanu Reeves would say “Whoa.” That’s great! All code is live in production! Spinnaker even has handy tools to run black/red deployments where traffic can be shunted from cluster to cluster based on benchmarks. Dude! For those who remember the “Release to Manufacturing” days where binaries had to be put on an FTP server (and hope that someone would install and download in the next quarter or so), code being live within a few minutes of being written is amazing. For those who remember “master disks” and packaged software, this is even more amazing. 

Nevertheless, with dazzling speed comes another set of problems. All code can be pushed anytime. However, many times you do not want everyone to have access to the code - you want to run a [canary release on actual users](http://featureflags.io/canary-release/), not just machines. You might want [QA to try your code in production, instead of a test server with partial data](http://readwrite.com/2016/01/22/staging-servers/). If you’re a SaaS product, you might want your [best customers to get access first to get their feedback](https://blog.launchdarkly.com/net-promoter-score-feature-flags-for-canary-releases/). For call center software, you want to have an opportunity to test in a few call centers. You might want to have a marketing push in a certain country days (or weeks or months) after another country. You might want to fine-tune the feature with some power users, or see how new users react to a complicated use case. All of these scenarios can not be done at a server level. This is where feature flags come in. By feature flagging, you can gate off a code path, deploy using Spinnaker, and then use a feature flag to control actual access. 

Together, Spinnaker and feature flagging make an amazing combination. You can quickly get code to “production”, and from there decide who gets it, when. 
