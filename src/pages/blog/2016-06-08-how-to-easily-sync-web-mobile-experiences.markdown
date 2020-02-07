---
author: justinucd
comments: false
date: 2016-06-08 19:37:19+00:00
layout: post
link: https://launchdarkly.com/blog/how-to-easily-sync-web-mobile-experiences/
slug: how-to-easily-sync-web-mobile-experiences
title: How to Easily Sync Web & Mobile Experiences
wordpress_id: 880
categories:
- DevOps
- Feature Management
tags:
- cross platform sync
- feature flags
- mobile
- sync
- user experience
- web
---

### _Using feature flags to sync user experiences across multiple platforms_





#### Becoming a VIP


Imagine you just signed up for Amazon’s VIP checkout experience.  In this hypothetical experience, you can click a VIP button that allows you to shop for brand new items not yet available to normal Amazon customers.  “This is awesome!” you say to yourself, as you view the VIP item list in your laptop’s browser.  

But now, you have to head to the bus and go to work, but you still want to browse for items using the Amazon app.  Because Amazon uses feature flags, your mobile experience is automatically personalized to include the VIP experience.  Cool!  Now, your web and mobile experiences are synced instantly.


#### Cross-Platform Personalization with Feature Flags


[Feature flagging](http://featureflags.io/feature-flags/) is a way to wrap features in conditionals (If/else statements) so that you can control the visibility of those features over time.  In other words, you can deploy a feature as ‘off’ and then turn it ‘on’ at a later time or you can gradually roll out a feature to select users.  

So, imagine you feature flag the VIP checkout.  You can create a rule that says: “Any user who opts into the VIP program will get TRUE for the feature and everyone else will get FALSE.”  Those users who are assigned the TRUE variation will see the VIP feature and those who are assigned the FALSE variation will not. 

[![Mobile Web Feature Flags Feature Toggles LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2016/06/mobile_flags.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/06/mobile_flags.jpg)

What is great about this method is that you can use this same feature flag to control the VIP checkout for both the web and mobile versions of an application.  

Some more benefits of cross-platform feature flagging include:



 	
  * The ability to decide whether to release a cross-platform feature simultaneously or separately, with full control over who gets to see that feature. For example, web users might get access to a new search bar before mobile users do.

 	
  * Real time personalization that allows users to opt-in to new features on one platform (like mobile) and have that personalization sync with another platform (like web)

 	
  * Percentage rollouts that allow you to gradually release a feature to targeted users on different platforms, allowing you to assess user and performance feedback for each platform

 	
  * A kill switch that lets you turn off poorly performing features for web and mobile, without having to redeploy

 	
  * Subscription plan management using feature flags to bundle cross-platform features into different tiers (ex. to create Bronze, Gold, and VIP plans). 




#### Summary


Cross-platform feature flagging is an easy way to deliver personalized and synchronized user experiences across different platforms.  Overall, it is paving a way for a [new genre of user experience personalization](http://featureflags.io/multivariate-feature-flags/), where companies can harness real time user feedback to customize features across different platforms.  This could usher in an era where users do not have to adapt their behavior to an app… the app will adapt to them.
