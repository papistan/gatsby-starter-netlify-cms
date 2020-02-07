---
author: justinucd
comments: false
date: 2016-09-14 17:14:46+00:00
layout: post
link: https://launchdarkly.com/blog/launched-custom-targeting-rules/
slug: launched-custom-targeting-rules
title: 'Launched: Custom Targeting Rules'
wordpress_id: 1087
categories:
- Product Updates
tags:
- conditional rules
- custom targeting rules
- feature flags
- percentage rollouts
---

A goal of LaunchDarkly is to provide our customers with the ability to target your users to meet the needs of your unique use cases.  We have always allowed you to target individual users or groups by any attribute that you define: name, e-mail, group, ID, country, age, etc.  However, we did not let you perform granular percentage rollouts for each attribute, nor did we allow you to construct conditional targeting rules. Many of you have asked for this!

Now, we are excited to launch [custom targeting rules](http://docs.launchdarkly.com/docs/targeting-users#targeting-rules-based-on-user-attributes), allowing you to construct a conditional rule using a user attribute, operator, and value.


## Use Cases


Using both boolean and [multivariate](https://blog.launchdarkly.com/launched-multivariate-feature-flags) feature flags, you can perform extremely powerful and granular user targeting:



 	
  * Roll out a new feature to users who registered before a certain date

 	
  * Perform a percentage rollout for all of your users who live in Canada and the United States

 	
  * Release a feature to your beta testers whose e-mail address ends with gmail.com

 	
  * Turn on a VIP checkout system for all users who spend more than $100 per month

 	
  * Release a new feature to 10% of users who belong to your Gold Plan and who signed up before August 1st, 2016

 	
  * Target all of your users above age 35, and show the one-click checkout to 30%, the two-click checkout to 20%, and the original checkout to 50%.




## Custom Targeting Rule


For a more concrete example, let’s say we have a feature flag that controls our app’s checkout flow.  This multivariate flag has three variations: one click checkout, two click checkout, and original checkout.  Here, we are performing a percentage rollout that targets all users whose email ends with gmail.com or yahoo.com:

[![LaunchDarkly feature flags and toggles using custom conditional targeting rules](https://blog.launchdarkly.com/wp-content/uploads/2016/09/user_targeting.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/user_targeting.jpg)


## Constructing a Rule


Let’s now build a rule using LaunchDarkly.  Here is a rule that serves the ‘true’ variation to all users whose e-mail address ends with gmail.com:

[![LaunchDarkly Custom Targeting Rule](https://blog.launchdarkly.com/wp-content/uploads/2016/09/customtargetingrule.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/customtargetingrule.jpg)

You can target users by using any attributes that you send to LaunchDarkly, like group, country, age, and device.  For each feature flag, you can create as many custom targeting rules as you would like.

Additionally, you can add multiple conditions to a rule.  Users must meet all the conditions in a rule to match the rule. If any of the conditions are not met, the user will not match the rule.

Here, we've created a custom rule with two conditions. This rule serves true to all users whose e-mail address ends with “gmail.com” and whose country is either “USA” or “Canada”.

[![LaunchDarkly feature flags / toggles custom rule with multiple conditions](https://blog.launchdarkly.com/wp-content/uploads/2016/09/customrulesconditions.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/customrulesconditions.jpg)

If we want to do a percentage rollout instead, we can select "percentage rollout" from the dropdown and allocate users accordingly.  Here, we have are serving “true” to 25% of users whose ‘groups’ attribute is “beta_testers”.

[![LaunchDarkly feature flags / toggles percentage rollouts using attributes](https://blog.launchdarkly.com/wp-content/uploads/2016/09/custompercentagerollout.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/custompercentagerollout.jpg)

There are many exciting ways to use custom rules, especially when you take full advantage of our multivariate feature flags.  If you have any questions or feedback, please send them to [support@launchdarkly.com](mailto:support@launchdarkly.com) and we’ll be happy to help!
