---
author: justinucd
comments: false
date: 2016-09-28 16:16:38+00:00
layout: post
link: https://launchdarkly.com/blog/launched-enterprise-feature-flag-management/
slug: launched-enterprise-feature-flag-management
title: 'Launched: Enterprise Feature Flag Management'
wordpress_id: 1120
categories:
- Product Updates
tags:
- descriptions
- Enterprise
- feature flag management
- maintainer
- tags
---

Before using LaunchDarkly, many of our customers were already feature flagging using internal tools or open source products. They used feature flags to mitigate risk, manage releases, and deploy better software, faster. However, they learned that creating a handful of feature flags was easy, but managing them at scale was extremely hard. Flags would go stale, accrue technical debt, and become neglected. It was hard to know who was responsible for maintaining and cleaning up a flag or to know which flags were temporary and which were permanent.

Flags inherently need some form of organization. You can have multiple flags that control different parts of a single feature, flags that control configurations, and flags that should only be managed by certain people. This was very difficult to implement in internal systems.

[![LaunchDarkly Enterprise Feature Flag Management](https://blog.launchdarkly.com/wp-content/uploads/2016/09/managementgraph.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/managementgraph.png)



To improve [feature flag management](http://docs.launchdarkly.com/docs/managing-a-feature-flag) for teams, we’re excited to launch some new management features:  [flag maintainer](http://docs.launchdarkly.com/docs/managing-a-feature-flag#flag-settings), [flag tagging](http://docs.launchdarkly.com/docs/managing-a-feature-flag#flag-settings), [flag descriptions](http://docs.launchdarkly.com/docs/managing-a-feature-flag#flag-settings), and [rich flag variations](http://docs.launchdarkly.com/docs/creating-a-feature-flag).  These new features complement our existing management tools like [flag statuses](http://docs.launchdarkly.com/docs/managing-a-feature-flag#flag-status), [custom roles](http://docs.launchdarkly.com/docs/custom-roles), and the [flag dashboard](http://docs.launchdarkly.com/docs/managing-a-feature-flag#dashboard).

You can find most of these new features in the Settings tab of your feature flag.

[![LaunchDarkly Feature Flag Management Settings](https://blog.launchdarkly.com/wp-content/uploads/2016/09/ld_checkoutflow.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/ld_checkoutflow.png)


### Flag Maintainer


This feature allows you to assign responsible for the flag to any team member. It allows you to know who to contact if a flag needs to be cleaned up or who to contact for help. By default, the maintainer will be the individual who created the flag. You can assign any member of your team as the maintainer for a particular flag.

[![LaunchDarkly Feature Flag Maintainer](https://blog.launchdarkly.com/wp-content/uploads/2016/09/ld_maintainer.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/ld_maintainer.png)


### Flag Descriptions


You can now create custom descriptions for each feature flag. These human-readable descriptions help you identify the flag and its functionality in-depth. This is critical for effective feature flag management, organizing flags, and communicating the flag’s purpose to your team members.

[![LaunchDarkly Feature Flag Descriptions](https://blog.launchdarkly.com/wp-content/uploads/2016/09/flagdescriptions.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/flagdescriptions.png)


### Flag Tags


Adding tags to your flags (like Front-End, Ops, Marketing, Restricted) helps you categorize flags and manage custom permissions.

Here, we have added the tags “mobile”, “marketing”, and “unrestricted” to a feature flag.

[![LaunchDarkly Feature Flag/Toggles Management Tags](https://blog.launchdarkly.com/wp-content/uploads/2016/09/tags.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/tags.png)


### Rich Flag Variations


When creating a feature flag, you can specify a name, description, and value for each variation. This allows you to explicitly describe the purpose of each flag variation, especially if you are using multivariate flags returning numbers, strings, JSON objects, or JSON arrays. For example, you can have a flag that returns numbers and then add a name and description to describe each variation.

[![LaunchDarkly Multivariate Feature Flag / Toggles Names and Descriptions](https://blog.launchdarkly.com/wp-content/uploads/2016/09/checkout.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/checkout.png)

We hope these new features are able to improve your team’s ability to manage feature flags and mitigate technical debt. If you have any questions or feedback, we would love to hear from you at [support@launchdarkly.com](mailto:support@launchdarkly.com) .


