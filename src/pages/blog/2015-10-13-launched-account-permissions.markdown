---
author: johnkodumal
comments: false
date: 2015-10-13 17:25:30+00:00
layout: post
link: https://launchdarkly.com/blog/launched-account-permissions/
slug: launched-account-permissions
title: 'Launched: Account Permissions'
wordpress_id: 177
categories:
- Product Updates
tags:
- permissions
- qa test
---

We've just launched account permissions! Team members can now be assigned more restrictive roles on your [team management page](https://app.launchdarkly.com/settings#/team). There are several roles:



	
  * Readers— readers can see anything in LaunchDarkly, but can't modify any data. This role is perfect for members of your organization that need visibility into your feature flags, but shouldn't be able to modify rollout rules, or administer the system.

	
  * Writers— writers can modify feature flags, goals, environments and more. They can't add new team members to the account, or manage your payment method or plans.

	
  * Admins / owners— admins and owners can do pretty much everything on the site. Owners can't be removed from the account.




[![Account Permissions](https://blog.launchdarkly.com/wp-content/uploads/2015/10/Account-Permissions.png)](https://blog.launchdarkly.com/wp-content/uploads/2015/10/Account-Permissions.png)


Over time, we'll be making our permissions model more powerful. It'll be possible to put even finer-grained controls on your users, so you can lock down your production environment, or restrict your Test environment to QA engineers if necessary.
