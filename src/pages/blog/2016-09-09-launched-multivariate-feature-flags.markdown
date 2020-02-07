---
author: justinucd
comments: false
date: 2016-09-09 17:01:38+00:00
layout: post
link: https://launchdarkly.com/blog/launched-multivariate-feature-flags/
slug: launched-multivariate-feature-flags
title: 'Launched: Multivariate Feature Flags'
wordpress_id: 1071
categories:
- Product Updates
tags:
- multivariate feature flags
---

LaunchDarkly has always supported boolean feature flags, which came with two pre-defined variations: true and false. This satisfied our customer's use cases for [risk mitigation](https://blog.launchdarkly.com/risk-reduction-and-harm-mitigation/) and end user control.

As our platform grew, so too did our customers' requests for more powerful ways to harness feature flags, like managing user plans, app configurations, and multiple variations of a feature.

To meet these use cases, LaunchDarkly now provides support for multivariate feature flags. A multivariate flag allows you to define two or more custom variations. These variations can be strings, numbers, JSON objects, or JSON arrays.

[![ld_flags-1](https://blog.launchdarkly.com/wp-content/uploads/2016/09/ld_flags-1-1024x384.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/ld_flags-1.jpg)


## Creating a Multivariate Feature Flag


The next time you create a feature flag, you'll be able to specify which kind of flag you need: boolean or multivariate.

Here, we have created a multivariate flag that serves strings as variations. There is no limit to the number of variations you can add to a multivariate feature flag, making it very powerful for complex use cases and to manage two or more variations of a feature.

[![LaunchDarkly multivariate feature flags and toggles with multiple variations](https://blog.launchdarkly.com/wp-content/uploads/2016/09/cd14712-docs_multi.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/cd14712-docs_multi.jpg)


## Multivariate Percentage Rollouts


Now, you can easily perform percentage rollouts using multivariate feature flags. In this example, 10% of users will receive `one-click-checkout`, 10% will receive `two-click-checkout`, and 80% will receive `original-checkout`.

[![LaunchDarkly multivariate percentage rollouts for granular user targeting](https://blog.launchdarkly.com/wp-content/uploads/2016/09/precentagerollouts.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/precentagerollouts.png)


## Multivariate Individual User Targeting


We have also revamped our user targeting UI to support multivariate feature flag user targeting. This UI allows you to easily target individual users by key.

In this example, bob@example.com will get the `one-click-checkout` , john@example.com will get the `two-click-checkout`, and sarah@example.com will get the `original-checkout`.

[![LaunchDarkly multivariate individual user targeting](https://blog.launchdarkly.com/wp-content/uploads/2016/09/multivariatetargeting.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/multivariatetargeting.png)


## Multivariate Rollouts Using Custom Rules


You can also create [custom rules](https://blog.launchdarkly.com/launched-custom-targeting-rules/) to serve variations based on any user attributes you send us.

In this next example, we have two rules. The first rule serves `two-click-checkout` to all users whose `country` is `USA`. The second rule targets users whose email ends with `example.com` and serves `one-click-checkout` to 50% and `two-click-checkout` to 10% of those users.

[![LaunchDarkly multivariate feature flag / toggle rollouts using custom targeting rules and user attributes](https://blog.launchdarkly.com/wp-content/uploads/2016/09/customrules.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/customrules.png)

All users who have not been targeted in the custom rules or who have not been individually targeted will fall to the Default Rule.

In this next example, all users will receive `original-checkout` if they have not been individually targeted and have not matched any custom rules.

[![LaunchDarkly Default Rollout Rule](https://blog.launchdarkly.com/wp-content/uploads/2016/09/default.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/default.png)

We hope you find multivariate flags useful. Send us feedback at [support@launchdarkly.com](mailto:support@launchdarkly.com)
