---
author: edithharbaugh
comments: false
date: 2015-08-11 19:09:01+00:00
layout: post
link: https://launchdarkly.com/blog/secret-to-facebooks-hacker-engineering-culture/
slug: secret-to-facebooks-hacker-engineering-culture
title: Secret to Facebook's Hacker Engineering Culture
wordpress_id: 116
categories:
- Continuous Delivery
- DevOps
tags:
- canary launch
- canary launches
- dark launch
- dark launches
- Facebook
- Facebook engineers
---

Facebook's engineering is legendary for its speed and execution. You too can be as quick and smart as Facebook, if you know their hacker engineering secret. Originally they lived by "Move Fast and Break Things", which has now evolved with wisdom to "[Move Fast With Stable Infra](http://mashable.com/2014/04/30/facebooks-new-mantra-move-fast-with-stability/)." Speed is important, as is stability and providing a good experience to users.Facebook's engineering Kent Beck wrote a great Facebook Note on how Facebook embraces reversibility to scale up. I highly recommend you read his entire [post](https://www.facebook.com/notes/1000330413333156/).

Facebook has a secret sauce: an in-house system called Gatekeeper that allows them to get quick feature feedback and quickly iterate based on feedback. Engineering changes are wrapped with a feature flag and pushed live to production. However, the features are live but off, then turned on via Gatekeeper to different users . Facebook's seemingly simple system of separating deployment from rollout unlocks many powerful ways to move faster with more stability. All items in italics below are quotes from Kent Beck, followed by my analysis of how Facebook uses Gatekeeper.


<blockquote>_Internal usage. Engineers can make a change, get feedback from thousands of employees using the change, and roll it back in an hour._</blockquote>


Initially, the engineer uses Gatekeeper to turn the feature on to internal users (only) . Interestingly, I’ve heard that Facebook is too large for changes to be effectively communicated EXCEPT by actually making the change. Instead of flurries of emails or blasts in chat rooms notifying other groups, Facebook engineers makes the code change and waits for impacted parties to notify them that something is broken, or fix their own dependencies. Separating changes from bigger releases with feature flags mean that any change can be rolled back at any time.


<blockquote>_Staged rollout. We can begin deploying a change to a billion people and, if the metrics tank, take it back before problems affect most people using Facebook._</blockquote>


Staged rollout depends on feature flags to encapsulate a change and a feature flagging system (like Gatekeeper) to take it back.


<blockquote>_Dynamic configuration. If an engineer has planned for it in the code, we can turn off an offending feature in production in seconds. Alternatively, we can dial features up and down in tiny increments (i.e. only 0.1% of people see the feature) to discover and avoid non-linear effects._</blockquote>


The key to turning features off in seconds (rather than hours or in best case, minutes) is “if the engineer has planned for it in the code”. By using feature flags to separate code deployment from functionality, Facebook can quickly kill malignant features. Without feature flags and Gatekeeper, Facebook would have to do a full redeployment.


<blockquote>_Right hand side units. We can add a little bit of functionality to the website and turn it on and off in seconds, all without interfering with people's primary interaction with NewsFeed._</blockquote>


Facebook smartly uses micro services and avoids monolithic code. Small changes in functionality, wrapped in feature flags, can quickly be toggled on and off using Gatekeeper.


<blockquote>_Shadow production. We can experiment with new services under real load, from a tiny trickle to the whole flood, without affecting production._</blockquote>


Facebook pioneered [dark launches](https://www.facebook.com/notes/facebook-engineering/hammering-usernames/96390263919), the ability to expose features to load without exposing them to users. I've heard that it's impossible to simulate Facebook's production load as it's so large. Gatekeeper allows Facebook to control via feature flags load testing from user visibility.


<blockquote>_Data-informed decisions. Data-informed decisions are inherently reversible. "We expect this feature to affect this metric. If it doesn't, it's gone.”_</blockquote>


By wrapping a feature with a flag, it’s possible to isolate its effect on the system. Data-informed decision , tying an individual feature to metrics, is made possible by Gatekeeper and feature flags. Without feature flags, it’s impossible to see the impact of a change - if you release five features and twenty bug fixes at once, and engagement drops by 5%, what feature is to blame? Could one of the bug fixes actually have caused a 10% drop and one of the features a 15% gain? Only by separating out each change can true causation (not just correlation) be seen. Yammer also follows [data-informed](http://launchdarkly.com/blog/hypothesis-driven-development-yammer/) decision in its product development. Again, it’s necessary to have encapsulation of the feature to both have measurement as well as enable the rollback.


<blockquote>_Advance countries. We can roll a feature out to a whole country, generate accurate feedback, and roll it back without affecting most of the people using Facebook._</blockquote>


Gatekeeper and feature flags, are enabling [canary launches](http://launchdarkly.com/blog/canary-launches-how-and-why-canary-deployment-canary-release/) - using an entire country as “canary in a coal mine” to see if there are issues with a release. Rather than having a world-wide failure, Facebook can iterate quickly and rollback.


<blockquote>_Soft launches. When we roll out a feature or application with a minimum of fanfare it can be pulled back with a minimum of public attention._</blockquote>


Facebook, after many misfires like Facebook Beacon, now follows Eric Ries ([Don’t launch - separate out a marketing launch from a product launch](http://www.startuplessonslearned.com/2009/03/dont-launch.html)). With feature flags, Facebook can get feedback from their own users, and control the story. Facebook has avoided the flameouts of Google, which has had epic failures with Google Wave, Google Buzz, and most recently Google Plus - all expensively launched, then expensively decommissioned. With feature flags and Gatekeeper, Facebook is always in control of who sees what when.

Want to be as smart as Facebook for developing software? Want to integrate reversibility, dark launches, data-informed decisions into your own development cycle? The smartest companies like Facebook, Medium, DropBox, and LinkedIn have in-house feature-flagging systems custom built for them. You can build your own system, or simply use LaunchDarkly, “Gatekeeper for everyone else”.



* * *





###### _LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER WITH FEATURE FLAGS AS A SERVICE. START YOUR FREE TRIAL [NOW](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic?utm_source=launchdarkly_blog&utm_medium=organic)._



