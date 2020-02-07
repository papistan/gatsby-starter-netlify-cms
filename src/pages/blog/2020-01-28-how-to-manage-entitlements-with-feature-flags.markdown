---
author: dparzych
comments: false
date: 2020-01-28 17:35:11+00:00
layout: post
link: https://launchdarkly.com/blog/how-to-manage-entitlements-with-feature-flags/
slug: how-to-manage-entitlements-with-feature-flags
title: How to Manage Entitlements with Feature Flags
wordpress_id: 194882
categories:
- Feature Management
tags:
- entitlements
- feature flags
- feature management
---

In software, _entitlement_ refers to the right to use services, products, or features. Entitlements can provide fine-grained controls over how an individual or organization can use software. For example, software as a service (SaaS) solutions typically offer different membership plans. Entitlements define the features each plan can access. Entitlements are sometimes referred to as paywalls, as features are only available to paid subscribers.

Feature flags, in the context of a feature management platform, can streamline the process of managing entitlements. This results in better customer experiences and greater operational efficiency. In this post, we'll cover best practices when using feature flags for entitlements.

[caption id="attachment_194884" align="alignnone" width="696"][![Listing of free, bronze, silver, gold, SaaS packages](https://blog.launchdarkly.com/wp-content/uploads/2020/01/Packages-1024x314.png)](https://blog.launchdarkly.com/wp-content/uploads/2020/01/Packages.png) This sample SaaS application offers four membership plans. In addition to the basic features, bronze customers receive email support, silver customers get email and chat support, and gold customers get email and chat support, plus a guaranteed SLA.[/caption]


## Feature flags and entitlements


Managing entitlements is time-consuming and continuously in flux.



 	
  * When new features are released, you need to decide which plans have access to it.

 	
  * As the competitive landscape changes, a feature that was only available to higher tiers may be made available to everybody.

 	
  * The sales team wants to run a limited-time promotion offering the feature to a lower plan to entice them to upgrade.

 	
  * Customer Success wants to give certain features to a customer that was recently impacted by an incident as a gesture of goodwill.


Many companies use feature flags to mitigate risks, but they can also generate additional revenue when used for entitlements. Instead of creating a custom build for a customer requesting a specific feature, wrap a flag around the feature and release it to that particular customer. Managing entitlements with feature flags allows you to unlock additional value for customers, manage technical debt, and minimize risk.


## Get your feet wet


There are many different use cases for feature flags, such as [release management](https://launchdarkly.com/blog/release-management-flags-best-practices/), [operational support](https://launchdarkly.com/blog/operational-flags-best-practices/), and [experimentation](https://launchdarkly.com/blog/nine-experimentation-best-practices/) (all of these have been covered in the best practices series). We deliberately ended the series with entitlements because it’s an advanced feature flagging use case. If you’re new to feature flags, start with release management or operational use cases. These frequently only involve a single team and are limited to a subset of features. Entitlements, on the other hand, often include coordination across many teams and involve multiple features. Start small and work your way up to using feature flags for entitlements.


## Empower the right individuals to manage entitlements


Engineering teams should not focus on managing entitlements. They should focus on creating new features. Entitlements are often a part of pricing and packaging; the teams and individuals responsible for these tasks should manage entitlements (Product, Customer Success, Sales, etc). Give these teams the ability to control entitlements for individual features via feature management. Identify people within your organization who should change entitlements and provide them with the ability to toggle the flags.

With LaunchDarkly, [custom roles ](https://docs.launchdarkly.com/docs/custom-roles)and [tags](https://docs.launchdarkly.com/docs/tags-in-custom-roles) help you empower teams to manage entitlements. Flags related to entitlements are tagged and associated with a custom role for Customer Success or whoever has the authority to manage entitlements. Only employees in the customer success organization can target and edit those flags.


## Maintain a single source of truth for entitlements


Information on entitlements can exist in many places—your feature management software, your website, or services like Zuora, Recurly, and Salesforce. When multiple systems are used and each one has a different configuration, how do you know which one is accurate?  A single source of truth is required. This ensures that everyone in the organization has the same information and is basing decisions off the same data. For example, Sales, Customer Service, and Product Management all know the features included in each plan resulting in less confusion and finger-pointing over misconfigured customer accounts. In today’s world of data-driven decision-making, everybody needs the same data to make good decisions.

Determine which system is your single source of truth. Pull settings from the single source of truth into all other systems for consistency and accuracy. If Zuora is your single source of truth for entitlements, when a feature is allocated to a plan, this should trigger a workflow to make necessary changes to feature flag settings.


## Change at a predictable cadence


Having the flexibility to change entitlements on the fly is appealing, but modifying them too frequently can have negative consequences like incorrectly billing a customer. If you’re making changes across the board, determine a cadence that is acceptable for your customers—monthly, quarterly, or semi-annually.

Changing entitlements as a gesture of goodwill for a specific customer can be done on an ad-hoc basis, but schedule changes impacting large numbers of customers.


## Audit changes


To avoid unhappy customers or billing nightmares, track who makes changes to entitlements, why they were made, and when. For audit logs to be useful, when a feature flag changes, include a comment with relevant details and links to supporting documentation.

If you have learned and implemented operational and release feature flags, consider expanding your usage to entitlements to help your organization hit their business objectives.

Are you looking for other best practices? Check out the other blog posts in the series:

[Long-term and short-term flags best practices ](https://launchdarkly.com/blog/best-practices-short-term-permanent-flags/)

[Operational flags best practices](https://launchdarkly.com/blog/operational-flags-best-practices/)

[Release management flags best practices](https://launchdarkly.com/blog/release-management-flags-best-practices/)

[9 experimentation best practices](https://launchdarkly.com/blog/nine-experimentation-best-practices/)
