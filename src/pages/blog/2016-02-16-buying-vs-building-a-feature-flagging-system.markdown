---
author: justinucd
comments: false
date: 2016-02-16 08:01:10+00:00
layout: post
link: https://launchdarkly.com/blog/buying-vs-building-a-feature-flagging-system/
slug: buying-vs-building-a-feature-flagging-system
title: Buying vs. Building A Feature Flagging System
wordpress_id: 446
categories:
- Continuous Delivery
- DevOps
- Feature Management
tags:
- build
- buy
- feature flag driven development
- feature flags
---

### How to use feature flag driven development effectively at your company


**Before the Decision**

As an engineering or product manager, your mission is to deliver quality software on time. You are looking to make your team fast, productive, and and more coordinated. Most importantly, you want your customers to love your product.

Professional developer tools are both the foundation and scaffolding for building successful products. Without team collaboration tools, issue tracking tools, IDEs, and version control systems, your team would find it challenging to release timely, high-quality software. To facilitate and improve product development, managers must inevitably decide whether to build developer tools in-house, purchase a platform, or maintain the status-quo.

<!-- more -->

The tradeoffs for each option depend on your resources, time, and internal expertise. Sometimes it's better to build in-house, other times it's more resource-efficient to purchase existing solutions. When it comes to feature flag driven development, companies who try to build internal platforms tend to face the following challenges:



 	
  * **Total cost of ownership: ** Homegrown tools are built to exist and serve a particular function, but with new business demands comes the cost of upgrades. There is a high cost to ongoing maintenance, both in time and money. Technical debt accrues over time due to engineer turn-over, product neglect, and evolving product demands.

 	
  * **Unknown And Evolving Scope:** Developing an internal product requires planning, resource allocation, and preparing for the unknown. Because feature flagging platforms are relatively new, it can be difficult to accurately define the scope and construct a solution for needs across not only engineering but also product groups.

 	
  * **Minimum Viable Functionality:** Internal developer tools are generally not built for usability, scalability, or cross-team support. They are built to solve an immediate pain point or provide minimum viable functionality as quickly as possible.

 	
  * **Polyglot Language Support:** Companies typically use multiple languages in their stacks and might adopt new languages in the future. This requires an adaptive feature flagging system that can handle the nuances of each language without compromising performance and stability.

 	
  * **Compliance: ** Company-wide internal tools require access controls, audit logs, and potentially custom permissions to ensure that functionality is controlled at an appropriate level.


**Starting to Feature Flag is Easy, Managing It is Hard**

Feature flagging is a straightforward concept that becomes difficult to manage on an enterprise scale. It's easy to manage one feature flag by modifying a configuration file, but when you have multiple feature flags across different environments, it's harder to keep everyone in sync in a compliant fashion. Facebook has a feature flagging system called Gatekeeper that took years to build, using limitless engineering resources. Wrapping one feature with an if/else is just the start, an enterprise-grade feature flagging systems require:



 	
  * An intuitive dashboard that an entire organization can use

 	
  * Access Control Levels to allow different functions (Developers, QA, Product) separate rights

 	
  * Auditing for who changed a flag when

 	
  * Performance & Targeting Analytics

 	
  * Speed in Microseconds

 	
  * Scale to Handle Millions/Billions of Events

 	
  * 100% Uptime and Redundancy


Companies that have built internal feature flagging tools (e.g. Google, Facebook, and Amazon) dedicated large teams of engineers and DevOps experts to build the platform, and continue to use full-time engineers to maintain and scale their systems.

[![Feature flag driven development build vs buy](https://blog.launchdarkly.com/wp-content/uploads/2016/02/BuildVsBuy.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/02/BuildVsBuy.jpg)

**Value Analysis**

Let’s look at the required inputs and expected outputs for an enterprise feature flagging platform.

_Inputs_



 	
  * Software Engineering

 	
  * User Interface Design

 	
  * Feature Flag Expertise

 	
  * Time (Months, Years)

 	
  * Money

 	
  * Infrastructure


_Outputs_



 	
  * Managed Continuous Delivery

 	
  * Risk Mitigation

 	
  * Feature Lifecycle Management

 	
  * Faster Release Cycles

 	
  * Percentage/Incremental Rollouts

 	
  * User & Group Targeting via Attributes

 	
  * Developer Coordination

 	
  * Visibility for Non-Developers

 	
  * Cross-Team Support


_When making the build versus buy decision, it’s important to ask the following questions:_



 	
  1. Can I divert my engineers from building the core product to building an internal tool?

 	
  2. What are the actual and opportunity costs of devoting engineering time?

 	
  3. How will I maintain the system in the long-run? Will I need to devote engineers full-time to managing the platform?

 	
  4. What infrastructure will I need to ensure system reliability?

 	
  5. What redundancies will I need to build?

 	
  6. Once it’s built, will it actually work at an enterprise level (speed, uptime, scale)?

 	
  7. How long will it take to build, test, and integrate the system into our continuous delivery process?


**Buying an Enterprise Feature Flagging Platform**

When purchasing a feature flagging platform, you want to make sure that you are integrating a well-tested and proven solution. You want to ensure that the feature flagging platform is:



 	
  * Stable

 	
  * Multi-language Compatible

 	
  * Scalable

 	
  * Intuitive

 	
  * Well-Supported


The platform should also allow you the flexibility to integrate feature flag driven development across teams and across products (web and mobile), either through an on-premise/private instance or managed cloud platform.

**LaunchDarkly**

[_LaunchDarkly_](https://launchdarkly.com/?utm_source=launchdarkly_blog&utm_medium=organic) is an [_enterprise-grade _](https://launchdarkly.com/how-it-works/?utm_source=launchdarkly_blog&utm_medium=organic)feature flagging platform. It is currently used by both small and large development teams at companies like AppDirect, Auction.com, CircleCI, and Apiary.

On a daily basis, the platform serves billions of feature flags in [_microseconds_](https://launchdarkly.com/how-it-works/?utm_source=launchdarkly_blog&utm_medium=organic). Led by former Atlassian engineers, LaunchDarkly was specifically built and tested to accommodate large, diverse development teams who are responsible for products that support millions of customers.

LaunchDarkly provides [comprehensive value](https://blog.launchdarkly.com/risk-elimination-and-the-launchdarkly-value-add/) right from the start, including:



 	
  * Feature Management Dashboard

 	
  * Team Support

 	
  * REST API

 	
  * SDKs for All Major Languages

 	
  * Audit Log

 	
  * Access Controls

 	
  * Percentage Rollouts

 	
  * Advanced User Targeting

 	
  * A/B Testing

 	
  * Integration Assistance & Personalized Support


[![launchdarkly build vs buy feature flagging platform](https://blog.launchdarkly.com/wp-content/uploads/2016/02/build-vs-buy-feature-flagging-platform.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/02/build-vs-buy-feature-flagging-platform.jpg)

**The Decision**

If you’re looking to build your own platform, [this page](https://launchdarkly.com/use-cases/?utm_source=launchdarkly_blog&utm_medium=organic) provides a list of feature flag libraries for every programming language. This can act as a nice starting point to understand the scope of the undertaking.

For a feature flagging service, **LaunchDarkly offers **[**_a free 30 day trial and demo_**](https://launchdarkly.com/?utm_source=launchdarkly_blog&utm_medium=organic). Feel free to contact [_sales@launchdarkly.com_](mailto:sales@launchdarkly.com) (or call 415-579-3275) to request a demo and ask any questions.

---------
_Resources for Further Information_

[_Video - LaunchDarkly Feature Flags_](https://www.youtube.com/watch?v=Fj3TvaovPe0)

[_Feature Flag Driven Development_](https://blog.launchdarkly.com/feature-flag-driven-development/)

[_Feature Flags for Product Managers_](https://blog.launchdarkly.com/the-product-managers-guide-to-feature-flags/)

[_Benefits of Feature Flags_](https://launchdarkly.com/use-cases/?utm_source=launchdarkly_blog&utm_medium=organic)

[_Feature Flag Fundamentals_](http://martinfowler.com/articles/feature-toggles.html)
