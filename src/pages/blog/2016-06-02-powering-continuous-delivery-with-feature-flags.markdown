---
author: justinucd
comments: false
date: 2016-06-02 18:55:57+00:00
layout: post
link: https://launchdarkly.com/blog/powering-continuous-delivery-with-feature-flags/
slug: powering-continuous-delivery-with-feature-flags
title: Powering Continuous Delivery With Feature Flags
wordpress_id: 866
categories:
- Continuous Delivery
tags:
- continuous delivery
- continuous integration
- DevOps
- feature flags
- risk mitigation
---

### Separating feature rollout from code deployment to mitigate risk in continuous delivery


We are in the [era of continuous delivery](https://blog.launchdarkly.com/why-leading-companies-dark-launch/), where we are expected to quickly deliver software that is stable and performant.  We see development teams embracing a suite of continuous integration/delivery tools to automate their testing and QA, all while deploying at an accelerated cadence.

However, no matter how hard we try to mitigate the risk of software delivery, almost all end-user software releases are strictly coupled with some form of code deployment. This means that companies must rely on testing and QA to identify all issues before a release hits production. It also means that companies primarily rely on version control systems or scraped together config files to control feature releases and mitigate risk.  For instance, many homegrown feature release systems rely on hard coded values read from config files.  These systems can work with a handful of configuration values, but accrue massive [technical debt ](https://dzone.com/articles/feature-toggles-are-one-worst)at scale and may require a full redeploy for any updates.

Once a release is in production, it is basically out in the wild.  Without proper controls, rolling back to previous versions becomes a code deployment exercise, requiring engineering expertise and increasing the potential for downtime.<!-- more -->

One way to mitigate risk in feature releases is to introduce [feature flags](https://blog.launchdarkly.com/feature-flag-driven-development/) (feature toggles) into the continuous delivery process.  These flags allow features (or any code segment) to be turned on or off for particular users.  

First, let’s explore software delivery from a systemic perspective.

[![Continuous Delivery and Feature Flags LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2016/06/software_dev_graph.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/06/software_dev_graph.jpg)

Admittedly, there are many ways to frame the software delivery process, but this diagram provides a more segmented overview.  It demonstrates that most teams who harness continuous integration and continuous delivery do so up to the software’s release.  By using feature flags in the continuous delivery process, teams are able to efficiently integrate release, deployment, and operational management into the software development cycle.

[![Benefits of Continuous Delivery and Continuous Integration with Feature Flags LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2016/06/cd_graph.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/06/cd_graph.jpg)

Adding feature flags into the continuous delivery cycle enables the separation of feature rollout from code deployment.  This allows teams to conduct percentage rollouts, user-targeted releases, and instant feature rollbacks.  You can essentially get real world user and performance feedback without the risk of widespread user backlash and degraded performance.

This is why companies like Google, LinkedIn, and Facebook have supplemented their continuous delivery processes with their own feature flagging systems.  Facebook, for instance, uses a system called Gatekeeper that controls feature rollouts and targeted releases.  It also enables them to roll back features that users do not like and assess how their infrastructure performs under new releases.

The new age of continuous delivery, therefore, harnesses release management as a way to mitigate risk, but also as a way to adapt to shifting consumer preferences and market conditions.







* * *





###### _LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER WITH FEATURE FLAGS AS A SERVICE. START YOUR FREE TRIAL [NOW](https://launchdarkly.com/#signup/?utm_source=launchdarkly_blog&utm_medium=organic)._
