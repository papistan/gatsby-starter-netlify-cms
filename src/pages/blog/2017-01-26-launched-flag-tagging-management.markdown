---
author: justinucd
comments: false
date: 2017-01-26 22:26:42+00:00
layout: post
link: https://launchdarkly.com/blog/launched-flag-tagging-management/
slug: launched-flag-tagging-management
title: 'Launched: Flag Tagging Management'
wordpress_id: 1331
categories:
- Product Updates
tags:
- DevOps
- feature flag management
- feature flags
- feature toggles
- tagging
---

For better feature flag management, LaunchDarkly allows you to create tags for organizing and grouping your feature flags.  Adding tags (like “Front-End”, “Ops”, “Marketing”, “Restricted”) helps you categorize flags and manage [custom permissions.](http://docs.launchdarkly.com/docs/custom-roles)

Here, we have added the tags “mobile”, “marketing”, and “unrestricted” on the Settings tab of our feature flag:

[![](https://blog.launchdarkly.com/wp-content/uploads/2017/01/flag_tagging.png)](https://blog.launchdarkly.com/wp-content/uploads/2017/01/flag_tagging.png)

After adding tags, you can filter by tag on the dashboard and link to filters for better feature flag management.

Here, we have clicked on the “marketing” tag, which has created a filter that shows all feature flags tagged “marketing.”

[![LaunchDarkly Feature Flag Tagging and Management Dashboard](https://blog.launchdarkly.com/wp-content/uploads/2017/01/featureflag_dash.png)](https://blog.launchdarkly.com/wp-content/uploads/2017/01/featureflag_dash.png)

Creating a filter also generates a URL that you can bookmark and share with your teammates.  For example, this URL will show all feature flags tagged “marketing”  [https://app.launchdarkly.com/default/production/features?tag=marketing](https://app.launchdarkly.com/default/production/features?tag=marketing) .

In the future, we will add more advanced filtering and sorting for even better flag management.  If you have any suggestions or questions, please feel free to contact us at [support@launchdarkly.com](mailto:support@launchdarkly.com)
