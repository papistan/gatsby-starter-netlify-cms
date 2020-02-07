---
author: KevinG
comments: false
date: 2018-04-02 22:35:24+00:00
layout: post
link: https://launchdarkly.com/blog/targeting-users-with-feature-flags/
slug: targeting-users-with-feature-flags
title: Targeting Users with Feature Flags
wordpress_id: 2463
categories:
- Feature Management
tags:
- best practices
- beta testing
- feature flag
- PII
- security
- segments
- sensitive data
- targeting
- testing in production
---

Companies exploring feature management are looking for control over their releases. A common theme is using feature flags to rollout a feature to a small percentage of users, or quickly roll a feature back if it is not working properly. These future flaggers also seek to control a feature further by limiting its visibility to individual users or a group of users. In this piece, we'll explore how LaunchDarkly lets you control your releases in these ways.

When launching a new feature, or simply updating an existing feature, you may not always want everyone to receive the same experience. When working with a new front-end marketing design, a back-end improvement to search, or anything in between, targeting specific users can help ensure the best experience for all of your customers. Below are a few common scenarios where targeting can come into play. We’d love to hear your thoughts on other targeting best practices—let us know what you come up with![![](https://blog.launchdarkly.com/wp-content/uploads/2018/03/Animated-GIF-source.gif)](https://blog.launchdarkly.com/wp-content/uploads/2018/03/Animated-GIF-source.gif)[![](https://blog.launchdarkly.com/wp-content/uploads/2018/03/Animated-GIF-source.gif)](https://blog.launchdarkly.com/wp-content/uploads/2018/03/Animated-GIF-source.gif)


![](https://media.giphy.com/media/82VaVtYtzFZL62V1wQ/giphy.gif)_Targeting users within LaunchDarkly’s UI._





### Internal QA


Perhaps the most common use case for _individual_ user targeting is internal QA. Testing in production is a scary thought, but so is launching to production without knowing how the rollout will go. Feature flags enable safe testing in production. By targeting only your internal QA teams to receive the new feature, you can experience how it will function in a production environment without exposing the untested feature to your customers.


### Beta Releases


When releasing a feature or product in beta, you can target users in your beta group to receive this update while not releasing it to anyone else. Essentially, you would set the flag to “true” for all beta users to enable the new feature. Everyone else would have the flag set to “false”. When Kevin from LaunchDarkly asks to be part of your beta group, it’s as easy as adding that user to the true variation to enable the new feature.


### Attribute-Based Targeting


Sometimes, you’ll want to target users, but may not want to dive into as many specifics as we just visited. Perhaps you are constrained by regulations, and need to deliver a different experience to customers from different states. Or, maybe your marketing team is launching a campaign specifically to Gmail users. You can place the email domain “[gmail.com](http://gmail.com/)” in your targeting rules to deliver an experience only to that group.


### Targeting in a Canary Launch


Many companies are seeking to slowly rollout their releases to before releasing to everybody. Rolling a new feature out to 10% of users, for example, is a great way to gain validation before a complete launch. You can target your internal QA team to be a part of the 10% initial rollout, or specifically include members from a beta group to see the new feature first. Conversely, you can target specific users or groups to exclude from the launch, and give them the new feature only when it is rolled out to everybody.

A common challenge with canary launches is delivering a consistent experience to users from the same group, especially in B2B applications. LaunchDarkly’s platform provides a bucketing feature that solves this problem. By bucketing users, you are ensuring that all users from the same group receive the same variation for the duration of a canary launch.


### Other Considerations


The examples we have covered so far are typically used for short-term flags, either upon initial rollout or for a shorter-lived feature. As your company's feature flag use continues to mature, wrapping a feature or set of features in a long-term or permanent flag is a logical next step. A common use case here applies to entitlements. For example, if you have Basic, Pro, and Elite versions of your product, user targeting helps manage these tiers effectively across your organization. Many products with different account tiers already have a way of controlling functionality, but with a feature management platform, this can be easily managed by anyone on your team. Customer success team members can quickly dial functionality up or down without the need to go to engineering for support. When a customer upgrades from Pro to Elite, a user simply flips the appropriate flags on.


Managing targeting rules at scale is an important consideration, especially as the amount of feature flags you are managing continues to grow. We introduced a new feature we call Segments to help tackle this very topic. Segments enables you to build reusable targeting rules to make this practice quick and scalable. Borrowing from a few of my examples above, you may want to flip a feature on for everyone with an Elite subscription, but also include all beta members as well. Because this is an important feature, you may want to also target internal users to ensure rollouts go smoothly. This same rollout strategy will likely apply to future features and you can simply target your Segment to receive the true or false variation. We'll be featuring Segments in a future post, so stay tuned for more.




[![](https://blog.launchdarkly.com/wp-content/uploads/2018/03/image2018-3-26_14-54-36-1024x587.png)_Build reusable targeting rules with Segments_](https://blog.launchdarkly.com/wp-content/uploads/2018/03/image2018-3-26_14-54-36.png)





### Data Privacy and Targeting


Targeting often involves customer data, and we [launched Private Attributes in January](https://blog.launchdarkly.com/launched-private-user-attributes/) to add an additional layer of protection. Private Attributes allows you to shield your customer data from LaunchDarkly while still enabling targeting rules on the shielded data. One thing I’d like to point out is that you never need to upload a database of users into LaunchDarkly to enable targeting. LaunchDarkly simply stores your targeting rules, which are evaluated based on the user objects that you provide. Ben Nadel wrote a wonderful piece describing InVision’s use of targeting and Private Attributes: [Using LaunchDarkly To Target Personally Identifiable Information (PII) During Feature Flag Evaluation Without Leaking Sensitive Data.](https://www.bennadel.com/blog/3425-using-launchdarkly-to-target-personally-identifiable-information-pii-during-feature-flag-evaluation-without-leaking-sensitive-data.htm)

To wrap things up, there are a number of different ways targeting users can deliver a more valuable experience. We visited just a few above, but the opportunities here are endless. At the end of the day, you’ll target users based on what makes the most sense for your product. We’d love to hear your thoughts and how you think user targeting can help. Until then and for more pointers, you can visit our documentation [here](https://docs.launchdarkly.com/docs/targeting-users).
