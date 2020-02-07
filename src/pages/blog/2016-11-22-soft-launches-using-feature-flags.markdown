---
author: justinucd
comments: false
date: 2016-11-22 18:16:06+00:00
layout: post
link: https://launchdarkly.com/blog/soft-launches-using-feature-flags/
slug: soft-launches-using-feature-flags
title: Soft Launches Using Feature Flags
wordpress_id: 1209
categories:
- Feature Management
tags:
- feature flags
- feature toggles
- soft launch
---

#### Getting granular, real-time control over your feature releases


Let’s imagine your team wants to launch a new one-click checkout feature.  You’ve been working on it for months: designing, iterating, and developing.  Now, you’re ready to release it into the wild.  

In the old days, we would just release the new feature via a code deployment.  It would be live for everyone. If something crashed, we would need to do a code deployment to roll back the changes.  Since everything would be live all at once, every customer would feel the pain.  Even if the feature didn’t break, it would take days or weeks to truly measure customer satisfaction.  Was the new feature increasing sales?  Are people enjoying it? Is it hurting engagement? 

**A feature flag**

[A feature flagged soft launch changes this](https://blog.launchdarkly.com/how-launchdarkly-improves-your-customer-experience/). It allows you to mitigate the risk of feature releases and incrementally roll out a feature to your users.

Some benefits include:



 	
  * Releasing a feature ‘off’ in production and then slowly rolling it out

 	
  * Allowing only particular users to see the feature

 	
  * Performing randomized percentage rollouts that target small segments of users

 	
  * Killing a feature instantly without redeploying

 	
  * Adjusting the rollout percentage to test infrastructure performance and scalability

 	
  * Syncing PR and advertising with feature releases


**How it works**

By definition, a soft launch is a way to [release a new product or service to a segment of your audience in advance of a full launch](https://blog.launchdarkly.com/feature-flag-driven-releases/).  Traditionally, we would think of these as alpha or beta opt-in releases.  These would be managed at the database or configuration level, where you would specify users who would receive the beta feature in a very manual way.

[![Feature Flag / Toggle Soft Launch](https://blog.launchdarkly.com/wp-content/uploads/2016/11/featureflagged_soft_launch.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/11/featureflagged_soft_launch.png)

With feature flags, you can practice intelligent soft launches.  A feature flag is a way to control the progression of a feature throughout its lifecycle, from design and development to release and rollback.  It also allows you to granularly target segments of your users for beta tests and incremental percentage rollouts.

**Soft launching with a feature flag**

Let’s use our one-click checkout feature from above as an example.  The goal of this new feature is to make it easier for our customers to purchase an item by removing the friction of multiple checkout steps.  However, we cannot truly know how our customers will enjoy this feature until they have tried it. 

Here are some of our release uncertainties that cannot just be tested in a staging environment:



 	
  * Can will it handle a production-level load?

 	
  * How will it impact support costs?

 	
  * Does it work well on all versions of all browsers?

 	
  * What edge cases will create stability, security, and performance issues?

 	
  * Will customers actually like it?


Of course, we will have tested this feature on our development environments and performed a closed beta.  But, these modes of testing cannot simulate our fully-scaled production environment that encompasses a whole range of users, from our early adopters to our laggards.

So, what we’ll do is wrap our one-click checkout in a flag:

[![Anatomy of a feature flag for a soft launch](https://blog.launchdarkly.com/wp-content/uploads/2016/11/anatomy_feature_flag.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/11/anatomy_feature_flag.png)

Basically, we can pass a series of user attributes to a flag, like “name, email, age, group, beta”, and then the flag’s targeting rules determine whether the feature is on or off for that user.

Here, we have rolled out our one-click checkout feature to 20% of users, while 80% still receive the old checkout:

[![Feature Toggle Roll Out for Soft Launch](https://blog.launchdarkly.com/wp-content/uploads/2016/11/toggle_rollout.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/11/toggle_rollout.png)

Using a slider, we can easily control a feature’s release in real-time without having to redeploy.  The percentage can be increased or decreased depending on the feature’s performance.

**Soft launching best practices**

For an introduction to the benefits of soft launches, Mobilize provides a nice [overview](http://www.gdcvault.com/play/1023099/Soft-Launch-Best-Practices-How) using the example of a mobile game launch. You should also reference this guide to [feature flagging best practices](http://featureflags.io/feature-flag-introduction/?utm_source=launchdarkly_blog&utm_medium=organic) to learn how to incorporate feature flagging into your soft launch.
