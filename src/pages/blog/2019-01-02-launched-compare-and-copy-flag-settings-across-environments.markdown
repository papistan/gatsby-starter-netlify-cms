---
author: alexisgeorges
comments: false
date: 2019-01-02 21:28:23+00:00
layout: post
link: https://launchdarkly.com/blog/launched-compare-and-copy-flag-settings-across-environments/
slug: launched-compare-and-copy-flag-settings-across-environments
title: 'Launched: Compare and Copy Flag Settings Across Environments'
wordpress_id: 193672
categories:
- Product Updates
tags:
- Environments
- feature flags
- feature management
---

As development teams grow with LaunchDarkly, it can become more difficult to maintain consistency for your flag evaluation rules across development, staging, and production environments.

We've now launched a new feature to compare your flag targeting rules across different environments in the same project.

At a glance, you can see if there are any differences between your local development environment and production. If you made a change to test out some new code, you can see that easily, and if you want to apply the targeting rules from your local environment to production, you can do that with a single click.

This new functionality also uses the [confirmation safety checks we released earlier](https://launchdarkly.com/blog/launched-require-comments-for-flag-changes-and-confirmations-for-environment-changes/) this year so that you don't have to worry about accidentally changing the flag targeting rules on any environment.

The compare and copy functionality is accessible from your main LaunchDarkly dashboard, and you can read more about this new feature [on our docs](https://docs.launchdarkly.com/v2.0/docs/compare-and-copy-flag-settings).
