---
author: justinucd
comments: false
date: 2016-04-19 17:48:12+00:00
layout: post
link: https://launchdarkly.com/blog/why-leading-companies-dark-launch/
slug: why-leading-companies-dark-launch
title: Why Leading Companies Dark Launch
wordpress_id: 550
categories:
- Continuous Delivery
tags:
- canary launch
- dark launch
- feature flags
- feature rollouts
- feature toggles
---

When it comes to releasing new features, there is nothing worse than deploying a feature that cripples your application, degrades performance, and turns away customers. 

With the rise of [continuous delivery](https://blog.launchdarkly.com/powering-continuous-delivery-with-feature-flags/), software teams are embracing faster, more iterative feature releases.  It’s now imperative for teams to ensure their features will be well-received by customers and maintain their application’s performance.

This is why companies like Google, Facebook, and Amazon have embraced [dark launching](https://blog.launchdarkly.com/secret-to-facebooks-hacker-engineering-culture/) to ensure the efficacy of their feature releases and the stability of their app infrastructure.

<!-- more -->


### The Dark Launch


Dark launching is the process of releasing production-ready features to a subset of your users prior to a full release.   This enables you to decouple deployment from release, get real user feedback, test for bugs, and assess infrastructure performance.

Scenario A - “I want to release an experimental _One Click Checkout_ to my users to see if it increases sales.”



 	
  * To dark launch this feature, you would enable it for 1% of your users, then to 5%, and 10%.. and assess performance along the way.  If you see that the checkout is increasing sales, then you can gradually increase the rollout percentage.  However, if you see that sales are worse, customers are confused, or that it degrades your app’s performance, then you can simply roll back the feature for further evaluation and refinement.


Scenario B - “I want to test new application infrastructure without switching all of my traffic.”

 	
  * Before switching all of your traffic to a new system architecture, you can dark launch new infrastructure by routing traffic via a toggle/flag specifically geared for configuration management.  For instance, suppose you want to stop maintaining your own queuing system and switch to a managed service. You might create a flag that sends some jobs to the new managed service, while still sending most to the old queuing system (and you have workers set up to listen on both). Then, you can gradually transition to an all-managed service as you monitor performance and other metrics. For another example, you can ramp traffic up and down during the daytime hours (when your DevOps team is awake), rather than perform a hard cutover during the midnight hours.


Scenario C - “I want to specifically release a feature for beta testing.”

 	
  * Also referred to as a [canary launch](https://blog.launchdarkly.com/canary-launches-how-and-why-to-canary-release/), this type of dark launch specifically target users in your ‘beta’ group or target users via an ID (like email or UID).  This will enable the new feature for these particular users, while all of your other users receive the current feature set.  At any time, you can add or remove beta users, get feedback, and assess system performance.


Scenario D - “I want to release a new feature to my VIP users first.”

 	
  * Dark launching via feature flags and toggles will allow you to roll out a new feature to your VIP users before doing a widespread release. You can also allow your users to opt-in and out of dark launched features, similar to a self-selected beta.




### Implementation


The easiest way to dark launch is by utilizing [feature flags or feature toggles](https://blog.launchdarkly.com/feature-flag-driven-development/) to wrap code in logical chunks, thereby separating your feature rollout from code deployment.  However, too many feature flags may lead to technical debt if they are not managed properly over time.  It is very important to have full visibility into your [feature flag lifecycle management](https://blog.launchdarkly.com/tag/feature-flag-management/) and allow your development teams to coordinate efficiently.

Successful dark launches require developer due diligence and benefit from adopting [feature flag driven development](https://blog.launchdarkly.com/feature-flag-driven-development/).  This style of development institutionalizes dark launching as a core part of your continuous delivery process.  Basically, every new feature is dark launchable because it will be wrapped in a feature flag or toggle to separate its rollout from code deployment.


### Getting Started with Dark Launching


To learn how dark launching gets implemented at enterprise scale, you can read about [Facebook’s Gatekeeper system](https://www.facebook.com/notes/facebook-engineering/building-and-testing-at-facebook/10151004157328920).  To test your own system, you can utilize any of these [open source libraries](https://launchdarkly.com/use-cases/?utm_source=launchdarkly_blog&utm_medium=organic) or [trial a managed feature flagging service](https://launchdarkly.com/?utm_source=launchdarkly_blog&utm_medium=organic). 
