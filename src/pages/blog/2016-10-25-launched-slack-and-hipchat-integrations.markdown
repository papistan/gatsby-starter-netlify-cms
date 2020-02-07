---
author: justinucd
comments: false
date: 2016-10-25 20:33:00+00:00
layout: post
link: https://launchdarkly.com/blog/launched-slack-and-hipchat-integrations/
slug: launched-slack-and-hipchat-integrations
title: 'Launched: Slack and HipChat Integrations'
wordpress_id: 1165
categories:
- Product Updates
tags:
- chat integrations
- HipChat
- LaunchDarkly
- notifications
- Slack
---

Feature flag driven development encourages communication between product, engineering, and business for faster, more coordinated releases. To help facilitate this, we are excited to announce a [Slack](http://docs.launchdarkly.com/docs/slack) and [HipChat ](http://docs.launchdarkly.com/docs/hipchat)integrations to sync LaunchDarkly notifications with your team’s messaging platform.


#### Benefits





 	
  * Know when feature flags are turned on / off or rolled out to users

 	
  * Get notified when flags are created or deleted

 	
  * Know which team members have modified flags

 	
  * Create custom policies to stream changes to individual chat rooms

 	
  * Coordinate releases and know when changes go live


[![LaunchDarkly Atlassian HipChat and Slack Feature Flag Notifications / Integrations](https://blog.launchdarkly.com/wp-content/uploads/2016/10/ld_integrations.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/10/ld_integrations.jpg)


#### Rich Notifications


Each notification contains a rich description of the who, what, and when of any activity in LaunchDarkly, including activities is triggered via our [API](http://apidocs.launchdarkly.com/).

[![LaunchDarkly Feature Flag Slack Notifications](https://blog.launchdarkly.com/wp-content/uploads/2016/10/slack_notifications.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/10/slack_notifications.png)

[![LaunchDarkly Feature Flag HipChat Notifications](https://blog.launchdarkly.com/wp-content/uploads/2016/10/hipchat_notifications.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/10/hipchat_notifications.png)


#### Chat Integrations


LaunchDarkly's Slack and HipChat integrations allow you to set up incoming webhooks to receive any activities in LaunchDarkly. When something is changed (e.g. when a feature flag is updated, when a new team member is invited to LaunchDarkly, and more) we'll send an incoming webhook to Slack or HipChat, or both.

[![LaunchDarkly Slack and HipChat Chat Notifications - Feature Flags and Feature Toggles](https://blog.launchdarkly.com/wp-content/uploads/2016/10/chat_integrations.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/10/chat_integrations.png)

You can also create custom policies for granular control over what types of notifications are sent to each room. For example, you can have changes to rollouts and targeting rules streamed to your Product room, while having team management notifications streamed to your Team room.  Custom policies are available for both [Slack](http://docs.launchdarkly.com/docs/slack#adding-a-policy-filter) and [HipChat](http://docs.launchdarkly.com/docs/hipchat#adding-a-policy-filter).

We’d love to hear from you at [support@launchdarkly.com](mailto:support@launchdarkly.com) with any questions or feedback!
