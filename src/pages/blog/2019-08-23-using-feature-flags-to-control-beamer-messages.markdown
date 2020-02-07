---
author: mcho
comments: false
date: 2019-08-23 16:32:26+00:00
layout: post
link: https://launchdarkly.com/blog/using-feature-flags-to-control-beamer-messages/
slug: using-feature-flags-to-control-beamer-messages
title: Using Feature Flags to Control Beamer Messages
wordpress_id: 194225
categories:
- Feature Management
- Product Updates
tags:
- Beamer
- custom segments
- targeted announcements
---

### Using Beamer with LaunchDarkly to Send Targeted Announcements


We're going to show you how to use feature flags to tailor in-app messages to specific user groups.

Feature flagging introduces experiences that are different for various user groups. Using exactly the same flag you use to target, you can also make in-app announcements for the same audience your feature is rolled out to!


### In-product announcements


We use feature flags extensively- to roll features out gradually, to selected accounts for beta testing, or some combination of those things.

We also use in-app notifications to announce news and product changes. Sometimes we have challenges with notifying only the customers who will see the changes. We use Beamer to send in-app announcements about new features, and we have user segments that we want to notify without alerting the rest of the user base. You may have seen our messages, which look like this.

[![Announcements in LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2019/08/image2019-8-15_10-25-8-1024x667.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/08/image2019-8-15_10-25-8.png)


### Connect your flagged feature to Beamer’s segments feature


After noticing that Beamer supports configurable Advanced Segments, we integrated our flags with their filter functionality, which allowed us to create Custom Segments based on the target users of a feature flag.

From Beamer's Segment screen, this allowed us to select a flag from the Filter dropdown and designate it as a Custom Segment.

[![Creating a custom segment in LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2019/08/image2019-8-15_10-22-42-1024x661.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/08/image2019-8-15_10-22-42.png)

After creating the Custom Segment, we were able to make in-app announcements to just the target group by selecting the right Segment filter from the dropdown when creating a post.

[![Targeting groups with announcements in LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2019/08/image2019-8-15_10-27-22-1024x657.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/08/image2019-8-15_10-27-22.png)

We're always excited to have supporting functionality that helps us release more incrementally, and release faster. Connect your flagged feature to Beamer’s segments feature to do the same thing, and only make announcements where relevant!

For more information contact [sales@launchdarkly.com](mailto:sales@launchdarkly.com) or start a free trial to try out LaunchDarkly today.
