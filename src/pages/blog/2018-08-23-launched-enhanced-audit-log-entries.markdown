---
author: sagarwal
comments: false
date: 2018-08-23 19:50:58+00:00
layout: post
link: https://launchdarkly.com/blog/launched-enhanced-audit-log-entries/
slug: launched-enhanced-audit-log-entries
title: 'Launched: Enhanced Audit Log Entries'
wordpress_id: 193290
categories:
- Product Updates
tags:
- audit log
- custom targeting rules
- feature flag
---

Creating a feature flag is just the start of using feature flags throughout your application. Both temporary ("control") flags and permanent flags live in a lifecycle. Over time they can change, especially as you use the tenets of [Progressive Delivery ](https://launchdarkly.com/blog/progressive-delivery-a-history-condensed/)to expose your flagged features to more users and customers.

To give you more visible insight into how your flags change over time, we've released enhanced audit log entries for your flags. Now, in your audit log you can see details of the following changes to your flags:



 	
  * Adding, deleting, or reordering rules on a flag

 	
  * Changes to existing rules

 	
    * Changes or additions to flag values, such as the criteria you're using to define with users you're targeting a flag at

 	
    * Changes to a rule with multiple clauses, such as "the users are in the `country` defined as `United States` AND the user's `firstName` is one of  `Nick, Billy"`, so that you have more fine-grained control over the precise targeting you want

 	
    * Changes to rollouts for both boolean and multivariate flags, such as changing from serving a single variation for the rule, to serving a different percentage rollout to each variation





You can find these enhanced entries now in your audit log. And if you have the [LaunchDarkly / Slack integration](https://docs.launchdarkly.com/docs/slack) installed, we've also made the audit logs available in Slack more detailed as well.
