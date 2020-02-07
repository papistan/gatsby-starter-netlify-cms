---
author: rgulati
comments: false
date: 2018-06-14 21:21:10+00:00
layout: post
link: https://launchdarkly.com/blog/launched-put-a-tag-on-it/
slug: launched-put-a-tag-on-it
title: 'Launched: Put a Tag on It'
wordpress_id: 193133
categories:
- Product Updates
tags:
- development environments
- feature management
- Projects
- tags
---

Tags are a useful way of grouping flags together, as well as leveraging the power of custom roles and webhooks. As a LaunchDarkly customer, you may have been using tags since it was first launched in 2016. For example, many LaunchDarkly teams add an “ops” tag to flags as a way of quickly assigning permission and providing visibility to particular flags.

We’ve noticed some teams have many projects and environments, and need ways to group those together too. So we thought about how we could make custom roles and webhook filters that group together multiple environments (e.g. development environments) or projects at a time—with similar ease as they already group flags using tags. Today we’re launching tagging for Projects and Environments.





[![](https://blog.launchdarkly.com/wp-content/uploads/2018/06/Screen-Shot-2018-05-17-at-10.44.48-AM-1024x889.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/06/Screen-Shot-2018-05-17-at-10.44.48-AM.png)







### Project and Environment Tags + Custom Roles


With tags, you now have control and easy management across your resources by expanding tags to additional areas of our feature management platform. With this, you can facilitate the management of individual features and groups of features quickly and consistently.

Tagging enhances custom roles so you can give granular access control to specific team members. For example, you may have junior developers on your team that need less expansive control of a few features. You can create a resource that allows them to perform only certain actions on all feature flags, for all projects, in all environments tagged `dev` and `ops`.

This defined control helps teams collaborate and move forward in their software development process with less risk of an accidental change.





[![](https://blog.launchdarkly.com/wp-content/uploads/2018/06/Screen-Shot-2018-05-17-at-10.43.54-AM-1024x890.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/06/Screen-Shot-2018-05-17-at-10.43.54-AM.png)







### How Do I Get Started?


If you are ready to dive in, you can find this feature in your Account Settings panel. Read our official documentation [here](https://docs.launchdarkly.com/docs/other-flag-settings#section-tags). If you are new to tags, check out this [post](https://blog.launchdarkly.com/launched-enterprise-feature-flag-management/).
