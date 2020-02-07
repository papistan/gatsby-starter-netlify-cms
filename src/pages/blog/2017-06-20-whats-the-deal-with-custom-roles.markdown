---
author: arnold
comments: false
date: 2017-06-20 16:47:15+00:00
layout: post
link: https://launchdarkly.com/blog/whats-the-deal-with-custom-roles/
slug: whats-the-deal-with-custom-roles
title: What's the deal with Custom Roles?
wordpress_id: 1679
categories:
- Feature Management
tags:
- custom roles
- RBAC
---

At LaunchDarkly we believe that the ability to finely tune access controls in the fast-paced developer space is mission critical. We've introduced [custom roles](https://docs.launchdarkly.com/v1.0/docs/custom-roles), modeled after Amazon Web Services' [IAM service](http://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html), to all of LaunchDarkly's enterprise customers, allowing admins to control permissions at a granular level. Yet [custom roles are more powerful than plain access control restrictions](https://blog.launchdarkly.com/launched-custom-roles/) in that they allow you to extend functions inherently reserved for engineering teams to other stakeholders in your organization.

Let's assume your organization has the following teams: Engineering, Customer Support, Sales, and Marketing. We'll define policies for each that allow the organization to become more efficient and less dependent on the engineering team.

[![](https://blog.launchdarkly.com/wp-content/uploads/2017/06/roles-diagram.png)](https://blog.launchdarkly.com/wp-content/uploads/2017/06/roles-diagram.png)


### Customer Success


The value of custom roles is demonstrated quite well in the case of the customer support team, so we'll start there.

Let's say a team member has received a support request where a specific user has reported broken functionality on a new feature that is impacting other core features and the team is scrambling to investigate. In an organization without LaunchDarkly the customer support team would have to provide the engineering team with steps to reproduce the bug and wait for them to implement a fix. With LaunchDarkly and custom roles, the support team member can disable the problematic feature for that particular user to temporarily resolve the issue, and depending on the prevalence of the issue elect to kill switch (turn off) that feature for all users.

The support team member is empowered to remedy issues in-real time. Moreover, the engineering team is no longer launched into emergency response mode; features toggled off can be resolved at a later time.

Here is a simple custom role to support that new value:

[![](https://blog.launchdarkly.com/wp-content/uploads/2017/06/update-flags-role.png)](https://blog.launchdarkly.com/wp-content/uploads/2017/06/update-flags-role.png)

This custom role would also be useful to sales team member, allowing that stakeholder to turn a feature on or off for a specific user based on customer plan selection. It's less likely that the sales team would need access to the kill switch, so we would remove that in this case:



[![](https://blog.launchdarkly.com/wp-content/uploads/2017/06/update-targets-role.png)](https://blog.launchdarkly.com/wp-content/uploads/2017/06/update-targets-role.png)


### Marketing


The marketing team can also benefit from custom roles. Let's say the team wants to [A/B test ](https://blog.launchdarkly.com/tag/ab-testing/) a new logo or design assets. Without LaunchDarkly and custom roles, the marketing team would have to coordinate this process with engineering releases. With LaunchDarkly and custom roles, engineering could implement flagged features to allow them to do this on their own schedule and tag the features with a marketing tag. This tag could be used to identify marketing features and also double as a custom role requirement.

When the marketing team is ready to run the A/B tests, it has full control over the features and goals with that marketing tag, relieving the engineering team of the burden of supporting marketing once it has implemented the features. The engineering team can move on to exciting new features while the marketing team tests and analyzes its theories.

This marketing role is also very easy to create:

[![](https://blog.launchdarkly.com/wp-content/uploads/2017/06/marketing-role.png)](https://blog.launchdarkly.com/wp-content/uploads/2017/06/marketing-role.png)


### Engineering


Defining custom roles for the engineering team is probably the least interesting topic in that custom roles don't quite offer this group anything it didn't have before. Nevertheless, we can use roles to avoid destructive operations that might affect other team members or end-users.

Imagine a scenario where a flagged feature exists in a production environment and a developer accidentally deletes that flag. An action like this would disable the feature for all end-users. Ideally we would restrict this permission to designated decision-makers.

For this purpose, we've created a slightly modified version of the built-in “Writer” role which does not allow for deletion of resources:

[![](https://blog.launchdarkly.com/wp-content/uploads/2017/06/dev-role.png)](https://blog.launchdarkly.com/wp-content/uploads/2017/06/dev-role.png)

For a full list of resources and actions, and more details about the policy creation process, check out our [custom roles documentation](http://docs.launchdarkly.com/v2.0/docs/custom-roles).
