---
author: johnkodumal
comments: false
date: 2015-08-03 22:51:11+00:00
layout: post
link: https://launchdarkly.com/blog/launched-environments/
slug: launched-environments
title: 'Launched: Environments'
wordpress_id: 109
categories:
- Product Updates
---

LaunchDarkly now supports multiple environments!

Environments let you manage your feature flags throughout your entire continuous delivery pipeline, from local development to QA, staging and production. When you create your LaunchDarkly account, we'll provide you with two environments, called Test and Production. Out of the box, you can use Test to set up feature flags for your non-production environments, while keeping your rules and data separate from your Production environment.

It's incredibly easy to switch environments— just select your environment from the dropdown on the sidebar. When you create a flag, you'll get a copy of that flag in every environment. Each flag can have different targeting and rollout rules for each environment. So you can roll a flag out to 100% of your traffic in staging, while keeping it 'off' in production.

[![switch](https://blog.launchdarkly.com//wp-content/uploads/2015/09/switch.gif)](https://blog.launchdarkly.com//wp-content/uploads/2015/09/switch.gif)

Each environment has its own API key— use your Test key in your SDK for local development, staging, and QA, and reserve your Production API key for your production environment.

Environments are also completely customizable— you can create new environments, rename them, or delete them. You can even change the sidebar swatch color for your environment— make your Production environment red, for example, to give yourself a visual reminder that you're modifying the rules for your live customer base.


[![color](https://blog.launchdarkly.com//wp-content/uploads/2015/09/color.gif)](https://blog.launchdarkly.com//wp-content/uploads/2015/09/color.gif)


Check out our [documentation](http://docs.launchdarkly.com/docs/environments) to learn more!



* * *





###### _LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER WITH FEATURE FLAGS AS A SERVICE. START YOUR FREE TRIAL [NOW](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._



