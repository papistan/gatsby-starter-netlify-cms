---
author: pgoyanes
comments: false
date: 2018-09-25 22:30:46+00:00
layout: post
link: https://launchdarkly.com/blog/launched-require-comments-for-flag-changes-and-confirmations-for-environment-changes/
slug: launched-require-comments-for-flag-changes-and-confirmations-for-environment-changes
title: 'Launched: Require Comments for Flag Changes and Confirmations for Environment
  Changes'
wordpress_id: 193333
categories:
- Product Updates
tags:
- comments
- deleting flags
- feature flagging
- feature management
- flag changes
---







As teams get larger, it becomes harder for everyone to understand all of the changes made to a system. LaunchDarkly helps you communicate the _why_ of every change with optional [comments when making flag changes](https://launchdarkly.com/blog/launched-comments-adding-context-to-your-actions/).







Since the initial release of comments, we have gotten great feedback on how having a little more information about flag changes helps teams stay in sync. This feature has been so helpful that some teams have asked to _require_ comments on every flag change.






















Today, we are introducing two new controls for LaunchDarkly teams built on comments. The first is the ability for administrators to make comments required when users change a flag or a segment within certain environments. You can set up required comments when you create a new environment, or you can add them as a requirement to existing environments. For new projects, we've turned on the require comments option for the pre-generated production environments. (You can, of course, turn this off.)













The second new control is a new safety net for flag changes to critical environments—you now can set an option to have users type an extra confirmation when making changes to flags in that environment. This new control helps reduce the possibility of accidentally changing a flag in your production or another critical environment.
















These new capabilities give your team extra control and confidence using flags. As you scale LaunchDarkly across more projects and even more teams, these confirmations help reduce the likelihood of incorrect changes and help your teams ship faster.











[![](https://blog.launchdarkly.com/wp-content/uploads/2018/09/Screen-Shot-2018-09-21-at-10.59.11-AM-1024x503.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/09/Screen-Shot-2018-09-21-at-10.59.11-AM.png)

[![](https://blog.launchdarkly.com/wp-content/uploads/2018/09/with-comment-1024x634.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/09/with-comment.png)

Check out our [documentation](https://docs.launchdarkly.com/docs/environments#section-require-commentshttps://docs.launchdarkly.com/docs/environments#section-require-comments) for more details on requiring comments and environment confirmations. For further questions, please email support@launchdarkly.com.
