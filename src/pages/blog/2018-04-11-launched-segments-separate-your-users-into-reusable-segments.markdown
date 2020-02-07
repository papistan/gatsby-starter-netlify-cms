---
author: Andrewb
comments: false
date: 2018-04-11 00:45:28+00:00
layout: post
link: https://launchdarkly.com/blog/launched-segments-separate-your-users-into-reusable-segments/
slug: launched-segments-separate-your-users-into-reusable-segments
title: 'Launched: Segments, Separate Your Users Into Reusable Segments'
wordpress_id: 2483
categories:
- Product Updates
tags:
- feature flag
- feature management
- segments
- user targeting
---

One of the core benefits of the LaunchDarkly feature management platform is the ability to [target](https://blog.launchdarkly.com/targeting-users-with-feature-flags/) end-users on a granular level. This means you not only have control over when a feature is 'on', but can decide who will see/experience it. Teams using LaunchDarkly use targeting rules to perform beta releases, canary launches, test in production, or even manage entitlements like tiered pricing structures.

We’ve gotten feedback that teams often want to target the same group of people for multiple different features. Unfortunately this meant building that list of targeting rules each time for each flag. So to make that process easier, we’ve introduced a new feature called **[Segments](https://docs.launchdarkly.com/docs/segmenting-users)** that allow you to build a list of targeting rules that can be used for different feature flags.

Segments are great for dark launchers who are targeting the same group of users for different features. This can be users of a particular technology (e.g. all of your Gmail users), a long-lived beta testing group, a particular department within your organization–you get the idea. Segments makes it easier to consistently reach particular groups that you work with over time. To use this new feature, existing LaunchDarkly customers should make sure you update your SDK (you can read more about that [here](https://docs.launchdarkly.com/docs/segmenting-users)).


### How does this work?


In this example, I describe a set of users called _Gmail Users_ with email addresses ending with _@gmail.com._[![](https://blog.launchdarkly.com/wp-content/uploads/2018/04/segments-img-1-1024x720.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/04/segments-img-1.png)

Then, in a feature flag called _Use Rich Formatting for Email_ I add a rule to include _Gmail Users_ in the list of users receiving this feature flag value.

[![](https://blog.launchdarkly.com/wp-content/uploads/2018/04/segments-img-2-1024x595.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/04/segments-img-2.png)

In another feature flag called _Encourage Users to Switch to Gmail_ I add a targeting rule to  exclude _Gmail Users_.[![](https://blog.launchdarkly.com/wp-content/uploads/2018/04/segments-img-3-1024x596.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/04/segments-img-3.png)

That’s all there is.


### How are Segments different than Prerequisites**?**


Our more advanced dark launchers might have noticed that segments appear very similar to **[prerequisites](https://docs.launchdarkly.com/docs/prerequisites)**. Just remember: segments allow you to target users by key or attributes, and prerequisites represent a dependency on a flag value served to a user.


### How do I get this new feature?


If you created an account starting March 1, 2018, you have already Segments. Congratulations! If you joined before that, then use of Segments requires that you update your server-side SDKs (you can read more about that [here](https://docs.launchdarkly.com/docs/segmenting-users)). For specific requirements, see our documentation for [building user segments](https://docs.launchdarkly.com/docs/segmenting-users). Contact us at [support@launchdarkly.com](mailto:support@launchdarkly.com) if you think your application is ready to handle Segments.
