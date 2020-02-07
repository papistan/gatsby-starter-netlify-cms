---
author: justinucd
comments: false
date: 2016-04-23 07:16:19+00:00
layout: post
link: https://launchdarkly.com/blog/is-it-a-feature-flag-or-a-feature-toggle/
slug: is-it-a-feature-flag-or-a-feature-toggle
title: Is it a feature flag or a feature toggle?
wordpress_id: 556
categories:
- Continuous Delivery
- Feature Management
tags:
- continuous delivery
- dark launch
- feature flags
- feature toggles
---

### The evolution of feature toggles to feature flags and what it holds for the future of software development.


**History of the Toggle**

[Jez Humble](http://continuousdelivery.com/) and [Martin Fowler](http://www.martinfowler.com/) are best known for promoting the separation of feature rollout from code deployment.  Within the context of continuous delivery, they provided the foundation for a framework that would allow developers to release software faster and with less risk.

Fowler is well-known for championing the notion of [feature toggles](http://martinfowler.com/articles/feature-toggles.html), which are ways to wrap features in conditionals that allow you to _toggle_ features on and off for users.  This would enable developers to [take full control of their feature rollouts, dark launch, and roll back poorly performing features](https://launchdarkly.com/use-cases/?utm_source=launchdarkly_blog&utm_medium=organic).

<!-- more -->

This led to the rise of open source feature toggle libraries tailored for specific languages, like [Java](http://featureflags.io/java-feature-flags/) and [PHP](http://featureflags.io/php-feature-flags/).  The main purpose of these initial libraries was to allow the quick and easy implementation of basic feature toggling functionality - a boolean value of true or false that would determine the visibility of a code snippet.  Moreover, early feature toggle developers had to address the issues of runtime performance, technical debt management, toggle management, and polyglot stacks. 

As feature toggles increased in popularity, developers started to explore advanced functionality like incremental percentage rollouts, granular user targeting, and long term feature management.  With full control of feature releases, developers saw the power of releasing features to beta testers, specific user groups, and gradually ramp up a feature release from 1% to 5% to 100% of users.

Feature toggles, therefore, became less about simply turning a feature on or off.  They became more about full feature lifecycle management - managing the feature from development, to release, to sunset.

With this new emphasis on management came the rise of the feature flag.

**The Rise of the Flag**

Although feature _toggles_ and _flags_ are used quite interchangeably today, [feature flags](https://blog.launchdarkly.com/feature-flag-driven-development/) may be growing into the more appropriate term.  A toggle implies that something has two states: on and off.  Many new frameworks are switching to the nomenclature of flag because they are supporting long term control, percentage rollouts, and multivariate states.

Feature flags do not have to be binary.  A flag can return multiple values like blue, red, green, and purple which your code can interpret to display different variants of a feature.  You could also potentially use flags to release features using date ranges and numbers.  In other words, the feature itself can have more than two states and these states do not necessarily need to be on or off.  The off variation for a feature flag could hide the code completely, whereas the blue or red variations will serve different variants.

A feature flag can be considered a way to manage the [full lifecycle](https://blog.launchdarkly.com/enterprise-requirements-for-managing-feature-flags/) of a feature, tracking the matriculation of a feature from development, to QA, and to production.  It can also be a way for you to aggregate performance analytics and test the impact of a feature on your system’s architecture.

[![LaunchDarkly Feature Flags or Feature Toggles](https://blog.launchdarkly.com/wp-content/uploads/2016/04/flags-or-toggles.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/04/flags-or-toggles.jpg)

**Looking Forward**

There is no wrong way to categorize a feature toggle or feature flag.  What is important is that companies are starting to realize the importance of separating feature rollout from code deployment.  This separation enables software to be more adaptive to user needs while also contributing to platform stability.

The future of software development and continuous delivery highlights the significance of feature release management.  Feature release is now no longer an afterthought.  It is something that must be built into the development of a feature from its inception to its rollout.

[Feature flags and toggles](https://launchdarkly.com/use-cases/?utm_source=launchdarkly_blog&utm_medium=organic) are now becoming integral to running a business, not just a best practice for the continuous delivery of software.
