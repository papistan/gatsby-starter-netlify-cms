---
author: justinucd
comments: false
date: 2016-02-05 08:01:34+00:00
layout: post
link: https://launchdarkly.com/blog/the-new-way-to-conduct-real-time-user-research/
slug: the-new-way-to-conduct-real-time-user-research
title: The New Way to Conduct Real-Time User Research
wordpress_id: 398
categories:
- Continuous Delivery
- DevOps
tags:
- feature flags
- Usability
---

### Overview


Conducting research [using your live product](https://blog.launchdarkly.com/a-new-way-to-beta-test/) sounds pretty crazy right? It seems almost backwards and counter-intuitive. Why would you go through all this trouble researching, designing, and building a new feature to just repeat step 1 (research) again?

This reason is contextual observation. [Contextual observation](http://www.usefulusability.com/tag/contextual-observation/) is the process of observing how your product meshes with the day-to-day lives of your users. There is absolutely no substitute for observing people [using your product in their own environment](https://blog.launchdarkly.com/soft-launches-using-feature-flags/). Think of this as an out-of-the-lab usability experiment using a production-ready feature.


### Benefits of Contextual Observation


Contextual observation is not meant to replace your initial research, nor should it be a 'bug-catcher' or a test of functional efficacy. Rather, it is used to assess user engagement with a new feature. Additional benefits of contextual observation include:



 	
  * Quantitative insight into your feature's performance. How well is it scaling? Are users using it? How is it impacting your system? How are your levels of engagement?

 	
  * Contextual insight into your feature's efficacy. Do users see the new feature? How is it meshing within the context on your existing feature set? Are people using it as intended? Are people using it once and then not using it again?

 	
  * Qualitative feedback. Are users complaining? Are they happy? Are they neutral?


There are two primary ways to approach contextual observation:

 	
  1. Launch the feature and observe

 	
    1. Use embedded analytics to asses engagement and performance.




 	
  2. Contextual inquiry

 	
    1. Use your real users as research participants. Select a few 'lucky ones' and ask for their feedback. It's important to ask users who are using the feature and users who are NOT using the feature. You can do this through Intercom-style messages, emails, or subtle feedback call-to-actions on your website.





[![LaunchDarkly Contextual Observation Usability Feature Flags](https://blog.launchdarkly.com/wp-content/uploads/2016/02/usability_context.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/02/usability_context.png)


### Caveats


As a developer or product manager, you may see live contextual observation as risky or just a semantic way to frame a normal launch. "Well, what if the feature breaks?" "How is this different than normally launching a feature?"

The answer is that normal feature release cycles do not let you:



 	
  * Gradually rollout a new feature to your users (1% -> 5% ... 20% and so forth)

 	
  * Target segments of your users or customize who gets to see the features

 	
  * Turn off the feature if it breaks without harming your product's performance

 	
  * Turn on the feature with one click




### Using Feature Flags


This is where [feature flag driven development](https://blog.launchdarkly.com/feature-flag-driven-development/) (FFDD) comes into play. FFDD lets you wrap your feature in a flag so you can control its life cycle from development to QA and production. This allow you to [control rollouts](https://blog.launchdarkly.com/case-study-modernizing-development-controlling-rollout-with-launchdarkly/), target users, and control your feature's visibility throughout development. More importantly, it mitigates risk by allowing you to continuously deliver features without worrying about user rejection and performance degradation. Everything you release gets placed in a flag, so you can toggle it on or off to whomever you want, when you want.

Imagine the power of flagging for contextual observation. For example, you can get real user feedback by gradually rolling out a new 'one click checkout screen' to 5% of your users. Let's say your users love the feature and you see sales increase by 20%. Cool! Now you can increase the rollout to 20%... 50%... 100% and measure impact along the way. However, let's say your users hate the feature. In fact, the new 'one click checkout' is drastically increasing accidental purchases which is hurting your bottom line and frustrating your users. No problem. Since you only had it rolled out to 5%, you can simply roll it back to 0% while you reassess the feature and try to improve the user experience.


### Conclusion


Contextual observation using feature flags is a practice that leading product teams use to launch features like Google, Facebook, Amazon, Quora, Asana...and many more. For modern UX, where users want the latest and greatest features instantly, contextual observation cultivates more usable software that can be delivered quickly and safely.

_Photo Credit: Periscope with GDS User Research Lead, Tara Land_
