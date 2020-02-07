---
author: justinucd
comments: false
date: 2017-03-03 20:56:51+00:00
layout: post
link: https://launchdarkly.com/blog/launched-feature-flag-variation-editing/
slug: launched-feature-flag-variation-editing
title: 'Launched: Feature Flag Variation Editing'
wordpress_id: 1459
categories:
- Product Updates
tags:
- edit variations
- feature flags
- LaunchDarkly
---

Feature flags are powerful when serving variations like true and false. However, they are even more powerful when you can serve variations that are strings, numbers, JSON objects, and JSON arrays -- which we call multivariate feature flags.

Previously, we allowed you to create multivariate feature flags with defined variations, but we did not let you add, edit, or delete variations once they were created. Now, you can!

With support for [edit variations](http://docs.launchdarkly.com/docs/managing-a-feature-flag#section-editing-variations), you can now edit feature flags after they are created.

You can now:



 	
  * Manage pricing in an e-commerce app by serving number variations

 	
  * Dynamically control configuration values

 	
  * Serve hex values to control CSS styles

 	
  * Sunset variations that are no longer necessary




## Editing Variations


When you navigate to any feature flag, you will notice a new Variations tab. This is where you will be able to edit your flag’s variations.

For boolean flags, you can edit a variation’s name and description, but not the value. This is because boolean flags can only serve true and false values.

[![LaunchDarkly Feature Flag Variation Editor](https://blog.launchdarkly.com/wp-content/uploads/2017/03/editvar1.png)](https://blog.launchdarkly.com/wp-content/uploads/2017/03/editvar1.png)

For multivariate flags, you can now add, edit, and delete variations even after the flag is created. Moreover, you can edit any variation’s value, name, and description. Keep in mind that you cannot change the “type” of variation being served after the flag is created.

[![LaunchDarkly feature flag variation editor](https://blog.launchdarkly.com/wp-content/uploads/2017/03/editvar2.png)](https://blog.launchdarkly.com/wp-content/uploads/2017/03/editvar2.png)

When you add, edit, or delete a variation for a multivariate flag, the change will apply to all environments within that project. For example, if you have a feature flag called “Checkout Flow” with 4 variations: A, B, C, D and you deleted variation D, then every environment will only have 3 variations (A, B, C) for the “Checkout Flow” feature flag.

We’re excited to deliver this new feature to you and would love to hear your feedback at [support@launchdarkly.com](mailto:support@launchdarkly.com).  You can reference our [docs ](http://docs.launchdarkly.com/docs/managing-a-feature-flag#section-editing-variations)for more info.
