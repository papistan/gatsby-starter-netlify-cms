---
author: justinucd
comments: false
date: 2015-11-08 06:12:42+00:00
layout: post
link: https://launchdarkly.com/blog/feature-flag-driven-development/
slug: feature-flag-driven-development
title: Feature Flag-Driven Development
wordpress_id: 195
categories:
- Continuous Delivery
- DevOps
- Feature Management
tags:
- a/b test
- canary launch
- continuous delivery
- feature flag
- feature toggle
- test-driven development
---

_This article provides a broad and comprehensive overview of feature flag-driven development, from gradual rollouts to A/B testing._


### A Typical Afternoon


It's an uneventful Friday afternoon. You're ready to head home, hit the gym, and spend time with the family. The last thing you'd want to do is deploy some new features to your users, right? That would be crazy talk. "Let's just wait for Monday...it's too risky...what if things break?" Deploying on Friday would inevitably mean working the weekend, but you're brave, you're the Zeus of the programming world, and you deploy it anyway.

In fact, you're smiling and cranking up the music as you confidently stroll out of the office to the bus stop. "Naive!" some would say, but you keep up the pace with a hop in your step.

A few hours later, you're lounging on the couch, proudly sunk into the cushy leather. "Bzz Bzz" as your phone rattles in your pocket. You ignore it, but the Bzzing won't stop. With an irksome look, you begrudgingly grab your phone and see a slew of error messages from your tracker. Oh no! This is it. The deploy failed. The gamble has turned into a nightmare... Right? Nope.

Without much thought and a timid roll of the eyes, you pull up LaunchDarkly and flip a switch. The errors stop and your only annoyance is the 30 seconds missed of your show.

This is the power of feature flags. On that Friday afternoon, you used LaunchDarkly to deploy a feature to 1% of your users, warmly wrapped in a feature flag. You wanted to test to see how it performed. If something bad happened, no problem. You knew you could just flip the switch and the feature would be rolled back with only 1% of your users experiencing a few seconds of inconvenience. This is just one of hundreds of use cases showcasing the power of feature flags.


### Feature Flags Explained


Feature flags/toggles/controls are basically ways to control the full lifecycle of your features. They allow you to manage components and compartmentalize risk.  You can do pretty cool things like roll out features to certain users, exclude groups from seeing a feature, A/B test, and [much more](https://launchdarkly.com/use-cases/?utm_source=launchdarkly_blog&utm_medium=organic). Check out this [video on canary launching](https://www.youtube.com/watch?v=oqSuzU3cCfA) to see the benefits of dark launching features.


#### How They Work


When a user loads a page, your application will use that user's attributes to determine what features to show. For example, if I am a BETA user and I log in to myexamplesite.com, I will see the brand new BETA feature. However, all non-BETA users will just see the old feature. The reason I see the BETA feature is that my user is grouped as BETA.

[![ld_overview2](https://blog.launchdarkly.com/wp-content/uploads/2015/10/ld_overview2.png)](https://blog.launchdarkly.com/wp-content/uploads/2015/10/ld_overview2.png)

While there are many [open source solutions](http://featureflags.io/resources/), we can dig deeper into LaunchDarkly's SAAS platform for feature flags.

In this example below, you will see an explanation of multivariate feature flags. Multivariate means that you can serve multiple variations of a feature to different user segments. For example, let's say I have a purple, orange, and green landing page. I can select which individual users or groups of users I would like to see each variation.

[![LaunchDarkly Multivariate Feature Flags](https://blog.launchdarkly.com/wp-content/uploads/2015/10/ld_multivariate.png)](https://blog.launchdarkly.com/wp-content/uploads/2015/10/ld_multivariate.png)

On the LaunchDarkly side of things, you would do the following:



 	
  1. Create a feature flag called "Landing Page"

 	
  2. Name three variations "Purple" "Orange" "Green"

 	
  3. Select which users you want receive each variation (you can also serve to percentages: _'60% of all users get the purple variation'_)


On your side of things, you would do the following:

 	
  1. Add the [LaunchDarkly SDK](http://docs.launchdarkly.com/docs/sdk-setup) to your platform

 	
  2. Wrap your feature in a [feature flag](http://docs.launchdarkly.com/docs/getting-started)

 	
  3. Call the SDK method to receive the value for that flag


It's as simple as that.   You can check out the full documentation [here](http://docs.launchdarkly.com/docs/getting-started).


#### Targeting Users


Above, we briefly covered how to target individual users and groups. Let's take a deeper look into why this is important. Targeting gives you the power to personalize a user's experience.

Imagine the ability to create a customized and rewarding experience for every user. Here are a few notable use cases:



 	
  * **Plan Management** (normal vs. premium) – You can launch targeted features to users on different plans. Want to add a new feature for a premium user? Sure! Just wrap the new feature in a flag and turn it on for premium users. Want to extend that feature to normal users eventually? No problem! Just add normal users when you're ready.

 	
  * **Early Access** – Allow only opt-in or power users to experience the latest features.

 	
  * **Block Users** – Exclude users or groups who you do not want to see a new feature.

 	
  * And [many more](https://launchdarkly.com/use-cases/?utm_source=launchdarkly_blog&utm_medium=organic).




#### Managing Rollouts


If you're deploying a brand new set of features, launching them to 100% of your users at once is a risky business. In fact, testing things by giving all of your users access isn't really a test. A test should be the process of receiving incremental feedback from your users, making improvements, and gradually expanding your release to everyone. This is where LaunchDarkly's rollouts come in. If you want to launch a new feature, you can start by rolling it out to 1% of your users.. then 5%.. then 20%.. then 50%.. then 100%. If something goes wrong at the 1% rollout, you can instantly roll it back, make the improvements, and test it again.

[![launchdarkly-rollout-2x](https://blog.launchdarkly.com/wp-content/uploads/2015/10/launchdarkly-rollout-2x.png)](https://blog.launchdarkly.com/wp-content/uploads/2015/10/launchdarkly-rollout-2x.png)

This is the process of canary launching, whereby you test the efficacy of a new set of features before releasing it to everyone. It also allows you to test how your features behave at different levels of traffic and incrementally refine your infrastructure to support the deployment.


### Flag-Driven Development


Feature flags/toggles/controls harness the power of [test-driven development](https://en.wikipedia.org/wiki/Test-driven_development) (TDD). This is the process of releasing and iterating features quickly, testing those features, and making improvements. Think of it as Lean UX methodology. You release light features to receive market feedback. You iterate on that feedback, make improvements, and redeploy.

Think of feature flag-driven development as a way to receive iterative market feedback on your product, rather than solely depend on isolated customer feedback. It's a way to test how your features perform in the real world and not just in an artificial test environment.

[![Feature Flag Driven Development - Waterfall Agile](https://blog.launchdarkly.com/wp-content/uploads/2015/10/ld_ffdd.png)](https://blog.launchdarkly.com/wp-content/uploads/2015/10/ld_ffdd.png)

In the world of Waterfall development, you will typically see one continuous build that culminates in a single deploy. After this deploy, you'll receive feedback and fix some bugs, but you will likely need to restart the process for any major feature releases.

Agile is a bit more forgiving. You can iteratively test small releases to your users, but this is best performed in a staging environment. You typically will not release your product to market throughout the agile development process, as most of your testing will be internal and controlled.

Finally, lean UX codifies the process of releasing features to market throughout the development process. These releases will likely be smaller in scale, but you'll receive immediate market feedback. When you introduce feature flags into the equation, the process becomes even more efficient.


#### Continuous Delivery via Feature Flag-Driven Development


Feature flags allow you to substantially mitigate the risk of releasing immature functionality. If a release is having a negative impact, roll it back. If it's doing well, keep rolling it out. This is like having a persistent undo button and a means to recalibrate and improve functionality.

More importantly, you can institutionalize this process within your development cycle. Your team will develop a cadence for lean releases, where all new components and functionality are wrapped in feature flags. You can easily test features, cultivate creativity, and reward bold advances – all without compromising the integrity of your platform.

[![ld_ffdriven](https://blog.launchdarkly.com/wp-content/uploads/2015/10/ld_ffdriven1.png)](https://blog.launchdarkly.com/wp-content/uploads/2015/10/ld_ffdriven1.png)

This new development methodology also allows your marketing, design, and engineering teams to collaborate more frequently and more effectively. With an agile approach, you will typically have one large planning cycle that will launch you into development. You will then test your iterations on local groups or in a local environment that tries to simulate production. However, you cannot substitute real market feedback.

Feature flag-driven development allows you to quickly release iterations of your features to market, receive feedback, improve, and redeploy. It allows you to roll out features to small segments of your users in order to mitigate risk all while receiving valuable feedback. More importantly, your team will converge and collaborate based on real market feedback and make the necessary improvements to drive the product forward.


#### Feature Flag-Driven A/B Testing


A/B testing is the practice of comparing different versions of a page to see which one performs better. In the traditional sense, A/B testing has been used for mainly cosmetic changes. These include layouts, element position, colors, and copy. Typically, A/B testing is tied to a goal. For example, you want to increase sign up conversions, so you use tools like [Optimizely](https://www.optimizely.com/ab-testing/), [Visual Web Optimizer](https://vwo.com/lp/ab-testing-tool/), and [Apptimize](http://apptimize.com/product/ab-testing/) to test different layouts, buttons, and call to action language. These tools work great, but what if you wanted to test backend-level functionality, completely new features, and sign-up flows?

This is where feature flag-driven A/B testing comes into play.

[![LaunchDarkly Feature Flag A/B Testing](https://blog.launchdarkly.com/wp-content/uploads/2015/10/ld_abtesting.png)](https://blog.launchdarkly.com/wp-content/uploads/2015/10/ld_abtesting.png)

Because feature flags are implemented at the code level, you can control deep functional features and then target user segments. For example, let's say I want to test a new sign-up flow and welcome tutorial (see above). I can flag the new functional components so that only certain users will receive the new flow.

With a suite like LaunchDarkly, you can then analyze these feature tests using your Optimizely or New Relic goals. This will allow you to see, for example, which sign up flow is generating better conversions or which check out flow is generating more revenue.

All in all, feature flag-driven A/B testing enables companies to test robust functionality instead of just cosmetic changes.





* * *





###### _LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER WITH FEATURE FLAGS AS A SERVICE. START YOUR FREE TRIAL [NOW](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._
