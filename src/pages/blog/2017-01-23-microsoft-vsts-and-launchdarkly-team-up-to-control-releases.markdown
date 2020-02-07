---
author: justinucd
comments: false
date: 2017-01-23 16:58:21+00:00
layout: post
link: https://launchdarkly.com/blog/microsoft-vsts-and-launchdarkly-team-up-to-control-releases/
slug: microsoft-vsts-and-launchdarkly-team-up-to-control-releases
title: Microsoft VSTS and LaunchDarkly Team Up to Control Releases
wordpress_id: 1318
categories:
- DevOps
tags:
- continuous delivery
- DevOps
- feature flag
- feature flags
- Microsoft
- release lifecycle management
- release process
- Visual Studio Team Services
- VSTS
---

It’s every project manager’s dream to get complete control over their software releases and have a way to continuously integrate and deliver new features, while also controlling the visibility of those features once they’re live.


### Microsoft Visual Studio Team Services


Microsoft’s [Visual Studio Team Services (VSTS)](https://www.visualstudio.com/team-services/) enables development teams to build, integrate, test, and release new software in a single platform. It has a centralized version control system that allows for continuous integration, package management, and release management. Together, these components enable agile teams to move faster in a more centralized manner while also minimizing the number of third party dependencies needed for deployment.

Traditionally, when you release new features into your Production environment, they are live for all of your users. You could provide code-level access control via a config file or modify database values to superficially control the visibility of your new features. However, these release controls are engineer-dependent, meaning they require a developer to make changes to who gets to see a feature and when. It makes it very difficult to target granular segments of users or perform incremental percentage rollouts to test performance and visibility.


### LaunchDarkly VSTS Extension


With LaunchDarkly, you can use feature flags to control the full release lifecycles of your features, perform percentage rollouts, and granularly target user segments. These controls are surfaced via a UI that can be used by non-developers, including designers, project managers, and the business team.

[![LaunchDarkly and Microsoft Visual Studio Team Services (VSTS) Feature Flags / Toggles for release management](https://blog.launchdarkly.com/wp-content/uploads/2017/01/vsts.png)](https://blog.launchdarkly.com/wp-content/uploads/2017/01/vsts.png)

To tie this feature flag UI into your VSTS workflow, the [LaunchDarkly Extension](http://featureflags.io/2016/03/30/introducing-feature-flag-toggle-support-for-visual-studio-team-services/?utm_source=launchdarkly_blog&utm_medium=organic)  allows you to associate feature flag rollouts with VSTS work items to get complete control over who sees what, and when. This allows teams to:



 	
  * Centralize feature and release lifecycle management

 	
  * Release confidently with less risk

 	
  * Incorporate feature flags into the release process

 	
  * Team support for superior project management

 	
  * Gain better visibility into features and outcomes

 	
  * Achieve next-level continuous delivery

 	
  * Empower your team to do better DevOps


Here’s some of the core functionality when you integrate VSTS and LaunchDarkly:

**Associate feature flags with work items**

Take full control of the release lifecycle of your work items and manage feature rollout

[![LaunchDarkly and Microsoft Visual Studio Team Services (VSTS) Feature Flags / Toggles for release management work items](https://blog.launchdarkly.com/wp-content/uploads/2017/01/vsts_workitem.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2017/01/vsts_workitem.jpg)

**Comprehensive Release Management**

Manage percentage rollouts and turn the feature flag on or off

[![LaunchDarkly and Microsoft Visual Studio Team Services (VSTS) Feature Flags / Toggles for release management controlled percentage rollouts](https://blog.launchdarkly.com/wp-content/uploads/2017/01/vsts_rollout.png)](https://blog.launchdarkly.com/wp-content/uploads/2017/01/vsts_rollout.png)



**Incorporate feature flags into your release definitions**

Tie feature flags to your Visual Studio Team Services release definitions and perform percentage rollouts:

[![LaunchDarkly and Microsoft Visual Studio Team Services (VSTS) Feature Flags / Toggles for release management work items and rollouts](https://blog.launchdarkly.com/wp-content/uploads/2017/01/vsts_release.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2017/01/vsts_release.jpg)


### Getting Started


If you already use [VSTS](https://www.visualstudio.com/team-services/) and have a LaunchDarkly account, then all you have to do is connect the[ LaunchDarkly extension](http://featureflags.io/2016/03/30/introducing-feature-flag-toggle-support-for-visual-studio-team-services/?utm_source=launchdarkly_blog&utm_medium=organic) and you’re ready to feature flag and take total control over your releases.

You can also check out the [documentation](http://docs.launchdarkly.com/docs/visual-studio-team-services-extension) to learn more about setup and integration. 
