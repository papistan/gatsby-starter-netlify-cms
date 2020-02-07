---
author: patrickkaeding
comments: false
date: 2015-08-13 17:17:43+00:00
layout: post
link: https://launchdarkly.com/blog/5-surprising-ways-your-neighbors-use-feature-flags/
slug: 5-surprising-ways-your-neighbors-use-feature-flags
title: 5 surprising ways your neighbors use feature flags
wordpress_id: 120
categories:
- Continuous Delivery
- Feature Management
tags:
- feature flags
- rollout
- software releases
---

Recently I handled a support request asking for clarification about what problems can be solved with a system like LaunchDarkly, and how it's different from every other analytics/event-tracking service. I realized that we actually have a wide range of things that customers are doing with our service--many of them are not obvious use cases for feature flags, but it turns out they work pretty well. I'm trying to beware of [seeing everything as a nail](https://en.wiktionary.org/wiki/if_all_you_have_is_a_hammer,_everything_looks_like_a_nail), but I think these are all good fits for feature flags.

LaunchDarkly allows you to control your software releases, by separating the deployment and rollout processes. Many people think of deployment and rollout as the same thing, but it is incredibly powerful if you can separate them. Deployment is actually pushing the code to your production servers, and rollout is exposing the new features to your users. With LaunchDarkly, you can:



	
  * Roll out a new feature to a [subset of your users](http://docs.launchdarkly.com/docs/targeting-users) (like a group of users who opt-in to a beta tester group), gathering feedback and bug reports from real-world use cases.

	
  * Gradually roll out a feature to a percentage of users, and [track the effect](http://docs.launchdarkly.com/docs/running-an-ab-test) that the feature has on key metrics (for instance, how likely is a user to complete a purchase if they have feature A versus feature B?).

	
  * [Turn off a feature](http://launchdarkly.com/blog/canary-launches-how-and-why-canary-deployment-canary-release/) that you realize is causing performance problems in production, without needing to re-deploy, or even restart the application with a changed configuration file.

	
  * Grant access to certain features based on user attributes, like payment plan (eg: users on the 'gold' plan get access to more features than users in the 'silver' plan).

	
  * Disable parts of your application to [facilitate maintenance](http://launchdarkly.com/blog/how-launchdarkly-uses-feature-flags-for-rolling-maintenance-modes/), without taking everything offline.


This is just a brief sample of some of the use cases that some of our customers are using right now. So, while tracking events is an important part of powering these use-cases (especially for A/B testing and canary launching), it is not the main focus.

Take a look at our [blog](http://launchdarkly.com/blog/) and [docs](http://docs.launchdarkly.com/) (I linked to a few relevant pages above, but there is more there), and of course, we're happy to [answer any other questions](mailto:support@launchdarkly.com) that you might have, or help you get started.



* * *





###### _LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER WITH FEATURE FLAGS AS A SERVICE. START YOUR FREE TRIAL [NOW](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._



