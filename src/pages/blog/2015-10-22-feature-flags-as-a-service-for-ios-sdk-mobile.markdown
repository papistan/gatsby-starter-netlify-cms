---
author: edithharbaugh
comments: false
date: 2015-10-22 21:42:20+00:00
layout: post
link: https://launchdarkly.com/blog/feature-flags-as-a-service-for-ios-sdk-mobile/
slug: feature-flags-as-a-service-for-ios-sdk-mobile
title: LaunchDarkly now has feature flags for mobile with iOS SDK
wordpress_id: 183
categories:
- Product Updates
tags:
- feature control
- feature flags
- iOS
- iOS sdk
- mobile
---

#  [![mobiledarkly](https://blog.launchdarkly.com/wp-content/uploads/2015/10/mobiledarkly1.png)](https://blog.launchdarkly.com/wp-content/uploads/2015/10/mobiledarkly1.png)




[View the SDK Documentation](http://docs.launchdarkly.com/v1.0/docs/ios-sdk-reference)  and [GitHub Repo](https://github.com/launchdarkly/ios-client)


[Mobile feature flagging](https://blog.launchdarkly.com/how-to-easily-sync-web-mobile-experiences/) has always been the next step for LaunchDarkly. In fact, I’ve heard a drumbeat of questions of “when mobile, when mobile, when mobile?” We’re pleased [to announce that yes, LaunchDarkly mobile iOS SDK is now in beta](http://www.businesswire.com/news/home/20151022005487/en)! Mobile feature flagging is perhaps even MORE useful than web feature flagging.

When I was at TripIt, we’d have to make our best possible guess about what features users wanted. We’d build an app version that would get shipped to Apple for review, a process that could take 1-3 weeks. Then, once a version was available for download, it was out of our hands (literally). We couldn’t make any changes to it, hence our concern for making sure that features were exactly right. The absolute worse was when something would break. Once we inadvertently shipped a version that treated all of our paying users as people who’d illegally broken our pay logic. We flashed up a cheeky message of “Ahoy you Scurvy Pirates” to the very people who were actually paying us! And, what’s worse, it took us multiple days for Apple to approve a fix. I said at the time “You could laugh or cry - or do both.” Laugh, because we could fix the bug in literally five minutes. Cry, because it took us days to go through the Apple review process and get the fixed version into end user hands and stop abusing them as pirates. Meanwhile, "0 star" app reviews built up, even though we had a fix ready to go.

With LaunchDarkly feature flags for mobile, “0 star” app store review pain goes away. Mobile developers can build the features they want, and ship them enabled for the people they want, independent of an App Store release. If a feature is doing well, the developer can amp up the volume. If the feature is doing poorly, the developer can turn it off in the live version so no users see it.

And rollout with a kill switch is just the beginning. With feature flags, mobile developers can do a surprising amount of interesting things - like rollout to a bigger number of users than TestFlight, gate features for paywalls, and [more](https://blog.launchdarkly.com/5-surprising-ways-your-neighbors-use-feature-flags/).

I want to give a huge thanks to [Mike Rollins](https://twitter.com/rollinsio?lang=en) for helping us with our iOS mobile SDK alpha testing. Mike says “I’m excited for what LaunchDarkly is bringing to mobile. Feature management via flags is something of a holy grail that I’ve heard about for many years but is something I’ve never seen anyone successfully implement. I know that I’ll be using it in my own apps!" Thank YOU Mike for helping us with feedback.

We’re happy to hear from more early users like Mike - anyone who starts using our mobile OS SDK will automatically get a stylish LaunchDarkly T. We ship anywhere in the world.
