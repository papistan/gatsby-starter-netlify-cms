---
author: justinucd
comments: false
date: 2016-11-01 17:19:53+00:00
layout: post
link: https://launchdarkly.com/blog/launched-android-feature-flags-sdk/
slug: launched-android-feature-flags-sdk
title: 'Launched: Android Feature Flags SDK'
wordpress_id: 1117
categories:
- Product Updates
tags:
- android
- controlled rollouts
- feature flags
- feature toggles
- mobile
---

LaunchDarkly’s mission is to be your complete solution for enterprise feature flag management. We wanted to provide SDKs for every major language and platform, both web and mobile -- allowing our customers to manage features and synchronize rollouts across multiple platforms.

Now, we are excited to announce the launch of our [Android SDK (beta)](http://docs.launchdarkly.com/docs/android-sdk-reference). This SDK supports both boolean and [multivariate ](https://blog.launchdarkly.com/launched-multivariate-feature-flags/)feature flags, allowing you to take full control over any feature or configuration in your release.

![LaunchDarkly Android Mobile SDK for Feature Flags / Feature Toggles](https://blog.launchdarkly.com/wp-content/uploads/2016/09/android.png)

Additionally, we wanted to ensure that the SDK always served the latest stored flag rules for each user, even if the app was backgrounded or if the app had multiple users on the same device.

To do this, we integrated some neat features: _(these features are also available in our [iOS SDK](http://docs.launchdarkly.com/docs/ios-sdk-reference))_

**Android SDK Features**



 	
  * [Simple User Construction](http://docs.launchdarkly.com/docs/android-sdk-reference#users)

 	
    * Easily construct users by using a builder pattern.  This makes it easy to use our targeting rules to perform [custom rollouts](http://docs.launchdarkly.com/docs/targeting-users) by user key or any attribute.




 	
  * [Multiple User Contexts on One Device](http://docs.launchdarkly.com/docs/android-sdk-reference#changing-the-user-context)

 	
    * If your app is used by multiple users on a single device, you may want to change users and have separate flag settings for each user. To achieve this, the SDK will store the last 5 user contexts on a single device, with support for switching between different user contexts.




 	
  * [Real-Time Updates](http://docs.launchdarkly.com/docs/android-sdk-reference#real-time-updates)

 	
    * You can immediately kill bad features and have granular control over the timing of flag updates.  LaunchDarkly manages all flags for a user context in real-time by polling flags based on a real-time event stream. When a flag is modified via the LaunchDarkly dashboard, the flag values for the current user will update almost immediately.




 	
  * [Offline Mode](http://docs.launchdarkly.com/docs/android-sdk-reference#offline-mode) & [Background Fetch](http://docs.launchdarkly.com/docs/android-sdk-reference#background-fetch)

 	
    * We wanted to make sure that developers had full control over the offline and backgrounded behavior of LaunchDarkly.  If a user's device is in airplane/flight mode or if they are not connected to a network, LaunchDarkly will use the latest stored flag settings in memory.  Additionally, when the app is backgrounded, the Android SDK does not receive real-time events. However, a battery-conscious Android Alarm is set to poll for updates once every 5 minutes.





We’re really excited to see what our customers are able to do with the new Android SDK. If you have any questions or feedback, we would love to hear from you at [support@launchdarkly.com](mailto:support@launchdarkly.com).
