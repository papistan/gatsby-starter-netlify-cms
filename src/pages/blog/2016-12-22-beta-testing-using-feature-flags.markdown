---
author: justinucd
comments: false
date: 2016-12-22 17:07:22+00:00
layout: post
link: https://launchdarkly.com/blog/beta-testing-using-feature-flags/
slug: beta-testing-using-feature-flags
title: Beta Testing using Feature Flags
wordpress_id: 1270
categories:
- Continuous Delivery
- Feature Management
tags:
- beta test
- beta testing
- feature flags
- feature toggle
- feature toggles
- percentage rollouts
- Pokemon Go
---

It’s best practice for products to have some sort of beta - a way to collect customer feedback and test performance before releasing to everyone. In an era of continuous delivery, we are delivering new features and experiences more frequently and with less time to gather thorough customer and performance feedback. With this increased cadence, product teams are having to make betas shorter, [forego them altogether](https://blog.launchdarkly.com/running-usability-tests-in-production/), or slow down their release cadence to gather adequate customer feedback.


### Challenges of traditional betas:





 	
  * Coordinating Opt-Ins: It sometimes takes weeks or months to gather customer opt-ins to test new betas. You also have to organize the distribution of beta keys (ex. for early access to games) and reminder emails.

 	
  * Organizing Focus Groups: Getting feedback from focus groups is often time consuming and expensive, creating a long feedback loop that lengthens the release process.

 	
  * Opt-Out: If customers opt-in to a beta and don’t like the experience, then they will want a simple mechanism to switch back to the production version.

 	
  * Granular Betas: It is very difficult to do targeted betas based on user attributes or to perform incremental percentage rollouts of new beta features.




### Feature toggles


To overcome these challenges, smart product teams are beginning to run betas with feature flags/toggles. These are mechanisms for granularly controlling software releases, allowing you to control the timing and visibility of a beta release.

Currently, many betas are tied to code releases and are managed by a config file or database.  This approach requires engineering time or custom mechanisms to opt-in users.

With feature toggles, you can empower product, marketing, sales, and even customers (themselves) to opt-in new to a new beta experience.

![Feature Toggle Beta Test LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2016/12/toggle1.png)

In this simple example, you can use a toggle to control the visibility of a new beta feature. Ideally, this toggle would be part of a user interface that could be controlled by a non-technical team member. The code, itself, could be deployed off and then turned on via the toggle.

[![Beta Test Percentage Rollout with Feature Toggle LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2016/12/toggle2.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/12/toggle2.png)

Moreover, you can also use the toggle to control the percentage of users who get the beta experience. For instance, you could release the new beta experience and have it rolled out to 0% of users. You could gradually increase the rollout percentage from 1% to 5% to 20% and more, collecting customer and performance feedback along the way.

Surfacing this beta control functionality in a user interface is critical for giving non-technical team members access to release controls.


### Regional betas


For a recent example of a targeted rollout, we can look at how Pokémon GO released their product country by country: first to the United States and then abroad.

[![](https://blog.launchdarkly.com/wp-content/uploads/2016/12/toggle3.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/12/toggle3.png)

This is a great use case for feature toggles because you can create [targeting rules](https://blog.launchdarkly.com/launched-custom-targeting-rules/) to determine which users receive the feature first. For example, I could create a toggle that is governed by the rule: “If users live in San Francisco, then serve the new Nearby Pokémon feature”. This allows you to maintain different regional feature sets without having to deploy different versions of the application. It also allowed Pokémon GO to refine their algorithms and assess customer feedback before rolling out the new feature to a wider audience.


### Benefits of beta testing with feature toggles





 	
  * Empowered non-technical users: Allow the sales, marketing, product, design, and business teams to turn features on for specific users, collect feedback, and control the business logic. This also substantially cuts down on engineering time.

 	
  * [Production feedback for your beta tests](https://blog.launchdarkly.com/flexible-infrastructure-with-continuous-integration-and-feature-flagging/): Test features in production with limited user segments to collect customer and performance feedback.

 	
  * Incremental percentage rollouts: Gradually roll out features to incrementally test performance and mitigate risk. If the feature is bad, toggle it off.

 	
  * Real-time opt-in / opt-out: Allow users to opt in and out of beta tests in real time, controlled via the feature toggle. Skylight provides a nice [article](http://featureflags.io/2016/12/14/feature-toggles-at-skylight/) on this.




### Getting started with toggles


Conceptually, a feature toggle is relatively simple. You create a conditional in your code that controls the visibility of a code snippet. There are many [open source libraries](http://featureflags.io) that will allow you to get started.  However, these libraries become cumbersome when you try to feature toggle at scale or restrict access to particular toggles. Depending on your needs, you could consider a [feature toggle management](https://launchdarkly.com/?utm_source=launchdarkly_blog&utm_medium=organic) platform to provide a system for access control and mitigating technical debt.
