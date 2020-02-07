---
author: justinucd
comments: false
date: 2016-02-15 23:15:35+00:00
layout: post
link: https://launchdarkly.com/blog/launched-audit-log/
slug: launched-audit-log
title: 'Launched: Audit Log'
wordpress_id: 441
categories:
- Product Updates
tags:
- audit log
- diff
- Enterprise
- LaunchDarkly
- patch
- team support
---

#### The audit log gives LaunchDarkly customers fine-grained visibility into changes to their feature flags.


[fruitful_sep]

We're excited to announce the launch of an audit log for LaunchDarkly teams! The audit log gives teams full visibility into their [feature flag management](https://blog.launchdarkly.com/launched-enterprise-feature-flag-management/) -- the who, what, and when of all [feature flag](http://featureflags.io/feature-flags/) changes.

The [audit log](http://docs.launchdarkly.com/docs/the-audit-log) contains a record of all the changes made to each feature flag in the system. You can filter the audit log by timestamps, or do prefix searches on feature flag names and keys.<!-- more -->

The audit log always shows entries for a single [environment](https://docs.launchdarkly.com/v1.0/docs/environments)-- to see the entries for other environments, use the environment switcher.

This initial release of the audit log provides a solid foundation for more robust integrations.  In the near future, you'll be able to push audit log entries to Slack, HipChat, or set up custom webhooks to receive audit log events.

**Screenshots**

[![Audit log](https://blog.launchdarkly.com/wp-content/uploads/2016/02/Audit-log.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/02/Audit-log.png)The audit log dashboard allows you to see a history of all changes to your feature flags. Clicking "Details" will give you visibility into the patch and diff for that change.

[fruitful_sep]

[![Audit log 2](https://blog.launchdarkly.com/wp-content/uploads/2016/02/Audit-log-2.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/02/Audit-log-2.png)

View the patch for each change.

[fruitful_sep]

[![LaunchDarkly Audit Log](https://blog.launchdarkly.com/wp-content/uploads/2016/02/68caa6a0219d5cb752b50bb40f649619.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/02/68caa6a0219d5cb752b50bb40f649619.png)

View the diff to see the differences between the old and new JSON.
