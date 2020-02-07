---
author: justinucd
comments: false
date: 2016-03-04 17:43:31+00:00
layout: post
link: https://launchdarkly.com/blog/enterprise-requirements-for-managing-feature-flags/
slug: enterprise-requirements-for-managing-feature-flags
title: Enterprise Requirements for Managing Feature Flags
wordpress_id: 495
categories:
- Continuous Delivery
- Feature Management
tags:
- Enterprise
- feature flag management
- feature flags
- feature toggles
- LaunchDarkly
- SDK
---

### Harnessing LaunchDarkly to manage feature flags at scale


The process of [_feature flagging_](https://blog.launchdarkly.com/feature-flag-driven-development/) is fairly straightforward: you wrap your features in conditionals that determine who can see your features and when. At an enterprise scale, organizations must confront the complexities of mitigating [_technical debt_](https://dzone.com/articles/feature-toggles-are-one-worst), managing developer workflows, compliance, and controlling the lifecycle of feature flags. To meet these challenges, LaunchDarkly provides an enterprise-grade feature flag platform built specifically for development teams.

<!-- more -->


#### Feature Flag Lifecycle Management


A feature flag is a [powerful tool](https://launchdarkly.com/use-cases/?utm_source=launchdarkly_blog&utm_medium=organic), but with that power comes great responsibility. A feature flag’s lifecycle includes its progression through multiple development stages: local, QA, staging, and production. These phases require extensive lifecycle management where developers can manage the flag’s creation, changes, requests, rollouts, and sunsetting.

Typically, home-grown feature flagging systems provide a minimum viable level of functionality for lifecycle management. In other words, these systems enable features to be toggled on or off, but they do not have extensive support for audit logging, change tracking, or team access controls.

This leads to the accrual of technical debt, which refers to feature flag implementation that seems quick and easy in the short-term (i.e using a config file), but may cause more long-term problems if not maintained or scaled correctly. Feature flags become technical debt due to complications with:



 	
  * Flag Implementation & Consistency - Feature flags need to be carefully crafted and consistently implemented within your application to prevent performance degradation and ensure that they function correctly. Often times, organizations will use conflicting methods like managing multiple config files or using in-line toggling.

 	
  * Flag Scalability - Adding more feature flags makes testing and management exponentially more difficult over time. It becomes very hard to tell which flags are necessary or obsolete.

 	
  * Flag Management - Maintaining feature flags across multiple development environments (local, QA, staging, production) becomes arduous and time-consuming. It becomes increasingly difficult to track who created the flag, the flag’s intended use, and changes made to the flag’s rollout.


As more flags are added, application testing becomes harder and more expensive. Technical debt festers over time, where it leads to development, performance, and scalability issues.

Sometimes, time constraints and resource limitations force developers to implement code quickly without proper due diligence. While this is a natural byproduct of software development, it is something that can be mitigated by a robust feature flag management platform.

**Feature Flag Statuses**

LaunchDarkly’s feature flag platform enables teams to take full control of their feature flags and mitigate technical debt. To do this, the platform provides an intuitive user interface that aggregates all feature flags, displays rich data, and provides real-time statuses.

These flag statuses allow teams to manage both short and long-term flags, and know when flags are safe to remove. LaunchDarkly shows you when the flag was added, when it was last requested, the current state of the flag, and the rollout percentage. This gives teams full visibility into their feature flag lifecycles, the ability to clean up flags that are obsolete, and know which features are rolled out.

[![Feature Flag Rollouts and Statuses LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2016/03/rollout_statuses.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/03/rollout_statuses.jpg)

**Audit Log**

Foundational to effective feature flag management is the ability to track changes and control access to feature flags. LaunchDarkly provides an [_audit log_](https://blog.launchdarkly.com/launched-audit-log/) that contains a record of all changes made to each feature flag, including who made those changes and when.  The audit log is also critical for organizations that have compliance obligations, giving managers full visibility into the who, what, and when of feature flag changes.

[![launchdarkly build vs buy feature flagging platform](https://blog.launchdarkly.com/wp-content/uploads/2016/02/build-vs-buy-feature-flagging-platform.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/02/build-vs-buy-feature-flagging-platform.jpg)


#### 




#### Team Management


When implemented at scale, feature flags become instrumental to a company’s development workflow. Feature flagging is a team effort and often requires coordination amongst diverse teams, like engineering, QA, and marketing. This substantiates the need for custom development environments and access controls.

**Cross Functional Team Support**

With LaunchDarkly’s team support, you can invite team members, manage their roles, and customize permissions. This empowers team collaboration by centralizing information and allowing teams to add or remove individual members.

At an enterprise level, managers can create different teams to oversee targeted organizational goals, like conversion rates, performance management, and sales metrics.

Other use cases include:



 	
  * Marketing teams harnessing A/B testing data to increase conversions

 	
  * Design teams testing usability and experimenting with new features

 	
  * DevOps teams managing application performance

 	
  * Engineering teams decoupling feature rollouts from code deployments


[![Feature Flags Custom Roles LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2016/01/customroles3.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/01/customroles3.png)

**Development Environments**

LaunchDarkly allows teams to create custom development environments for local, staging, QA, and production (with no limit on the number of environments). This enables developers to manage features across multiple testing environments and manage developer access to those environments.

[![Feature Flag Development Environments LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2016/03/dev_cycle.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/03/dev_cycle.jpg)

**Access Controls**

LaunchDarkly’s [_fine-grained access controls_](https://blog.launchdarkly.com/launched-custom-roles/) allow teams to manage permissions for everything in the system, from feature flags to A/B testing.  Managers can assign one or multiple custom roles to each team member using a policy system modeled after [_AWS_](https://aws.amazon.com/iam/).
A few powerful examples of access controls include the ability to:



 	
  * Lock your production environment down to a small set of trusted users

 	
  * Distinguish infrastructure-level feature flags (controlled by your DevOps team) from experiments (controlled by product management or marketing)

 	
  * Allow QA members to control feature flags on designated QA environments only




#### 




#### Analytics & Extensibility


A powerful benefit of feature flags is the ability to assess feature performance and get [_genuine user feedback_](https://blog.launchdarkly.com/the-product-managers-guide-to-feature-flags/) from customers. Organizations will typically already harness a suite of analytics and feedback tools, like MixPanel, Segment, Slack, HipChat, and New Relic. For a feature flagging system to provide analytical value, it must be able to integrate with these existing tools and allow for customized integrations tailored for an organization’s evolving needs.

**Platform Analytics & API**

In addition to advanced feature flag controls, LaunchDarkly provides integrated support for A/B testing, performance monitoring, and [_a REST API_](http://apidocs.launchdarkly.com/). These integrations enable teams to connect LaunchDarkly to existing team tools (like Optimizely and New Relic) and create their own custom integrations.

**SDK Support for All Languages**

It is not uncommon for organizations to maintain a stack that utilizes multiple development languages and frameworks. LaunchDarkly provides [_SDKs_](https://launchdarkly.com/how-it-works/?utm_source=launchdarkly_blog&utm_medium=organic) for iOS, Java, JavaScript, PHP, Go, Node.JS, .NET, Ruby, Python, and Python Twisted. This ensures that LaunchDarkly can support an evolving polyglot stack, both in terms of language composition and mobile/web support.


#### Next Steps


LaunchDarkly acts as a feature flag control center, where teams can easily integrate feature flags into their short and long-term development cycles. If your team is considering building or buying a feature flagging solution, [_this article_](https://blog.launchdarkly.com/buying-vs-building-a-feature-flagging-system/) analyzes the benefits and costs of a managed feature flagging system versus a home-grown platform.

LaunchDarkly offers a [_free 30 day trial and demo_](https://launchdarkly.com/?utm_source=launchdarkly_blog&utm_medium=organic) for prospective teams. Contact [_sales@launchdarkly.com_](mailto:sales@launchdarkly.com) or call (415) 579-3275 to schedule a demo and discuss your questions.
