---
author: alexisgeorges
comments: false
date: 2016-11-15 18:39:33+00:00
layout: post
link: https://launchdarkly.com/blog/launched-bulk-user-targeting/
slug: launched-bulk-user-targeting
title: 'Launched: Bulk User Targeting'
wordpress_id: 1185
categories:
- Product Updates
tags:
- bulk user management
- feature flags
- segmentation
- user targeting
---

It's always been easy to target individual users when you create a feature flag in LaunchDarkly.  You simply enter a user's key, name, or email into the individual targeting field to serve to target that user. But, what if you want to target tens or even hundreds of users at once?

Our new [_bulk user targeting_ ](http://docs.launchdarkly.com/docs/targeting-users#bulk-user-targeting)feature allows you to add, remove, or replace entire user populations by entering lists of user keys or emails. Our app will resolve each user, and you can decide what to do with them.

With bulk user targeting, you can:



 	
  * Paste a CSV list that contains thousands of user keys or e-mails

 	
  * Create user segments locally, like a beta group, and then add them to a variation

 	
  * Look up multiple users at once and see which users currently exist and which do not


You can trigger Bulk User Targeting from the Bulk Edit button, or by using Ctrl-V to paste a list of users from your clipboard directly into the Add Users field:
[![LaunchDarkly Bulk User Management for Feature Flag / Toggle Targeting](https://blog.launchdarkly.com/wp-content/uploads/2016/11/bulk_targeting.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/11/bulk_targeting.jpg)
This will open a bulk targeting modal that will let you add, remove, or replace users.
[![LaunchDarkly Bulk User Targeting and Segments](https://blog.launchdarkly.com/wp-content/uploads/2016/11/bulkss.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/11/bulkss.png)

Check out our _[documentation](http://docs.launchdarkly.com/docs/targeting-users#bulk-user-targeting)_ to learn more about bulk user targeting and how users are resolved.

We’re really excited to bring you this new feature, as many of our customers have requested it. If you have any questions or feedback, we would love to hear from you at [support@launchdarkly.com](mailto:support@launchdarkly.com).
