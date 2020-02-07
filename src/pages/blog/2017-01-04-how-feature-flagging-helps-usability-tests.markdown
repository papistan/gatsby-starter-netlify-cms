---
author: justinucd
comments: false
date: 2017-01-04 19:02:09+00:00
layout: post
link: https://launchdarkly.com/blog/how-feature-flagging-helps-usability-tests/
slug: how-feature-flagging-helps-usability-tests
title: How Feature Flagging Helps Usability Tests
wordpress_id: 1292
categories:
- Feature Management
tags:
- feature flags
- feature toggles
- production testing
- test in production
- usability testing
- UX
---

Usability testing in a real-world environment (aka [production environment](https://www.techopedia.com/definition/8989/production-environment)) gives us insight into how users actually use our product in their day to day lives. It is one thing to run a test in a lab setting, but it is another to have users try features while they are walking, running to the airport, stressed, and sleepy.

But, no matter how hard we try, it is very difficult to truly simulate how our apps behave in our production environment. We can run focus groups, beta tests on a beta environment, and test things internally, but how can we truly mimic the real world in an artificial context? In other words, how do we test a feature while also simulating the environment it’s meant to be used in?

[![LaunchDarkly Usability Testing In Production - Feature Flags and Feature Toggles - Context](https://blog.launchdarkly.com/wp-content/uploads/2017/01/usability_context.png)](https://blog.launchdarkly.com/wp-content/uploads/2017/01/usability_context.png)

A good [real-world usability test](https://blog.launchdarkly.com/the-new-way-to-conduct-real-time-user-research/) analyzes features efficiently and accurately collects user feedback to improve the user experience. But, when we test anything in a non-production environment, we are inherently biasing our tests. In a lab-based usability test:



 	
  1. Users are overly cognizant of the feature they are testing.

 	
  2. Users are unnaturally focused on testing that new feature.

 	
  3. Users are using fake data or incomplete data, and don’t sufficiently utilize actual use cases.

 	
  4. It is very hard to test discoverability (i.e can a user find the feature on their own?).

 	
  5. Users tend to ignore distractions, like external notifications (Facebook, Skype, texts) and just focus on the task at hand.

 	
  6. Users are in an overly analytical mode, typically looking to give feedback.

 	
  7. Users are overly forgiving, looking to please!


Does this mean that running usability tests in non-production environments is a waste of time? Not at all! This is absolutely necessary to identify bugs, check for general usability, and solicit feedback quickly.

However, it should just be one of the steps in a comprehensive usability testing process, one that involves internal, staging, and production usability testing.


### Benefits of usability testing in production:


The primary purpose of usability testing in production is to gather real-world user behavior while minimizing bias and performance risk. Some more benefits include:



 	
  1. Genuine user feedback in a real-world environment

 	
    * Quantitative insight into your feature’s performance. How well is it scaling? Are users using it? How is it impacting your system? How are your levels of engagement?

 	
    * Contextual insight into your feature’s efficacy. Do users see the new feature? How is it meshing within the context on your existing feature set? Are people using it as intended? Are people using it once and then not using it again?

 	
    * Qualitative feedback. Are users complaining? Are they happy? Are they neutral?




 	
  2. No opt-in bias - users test the feature without knowing they are part of the test. You can assess how well they use it by using a product like Full Story to record the session or by tracking metrics. You therefore get a more representative sample testing the feature, rather than just early adopters.

 	
  3. Measuring actual system performance - there is nothing quite like your production environment, where you can have a complex array of nodes, clusters, CDNs, etc allowing your app to scale. As people start to use the new feature, you can see how it is impacting your actual system (load times, discoverability, caching issues).




### Managing a usability test in production:


Of course, testing anything in your production environment is inherently risky and has real-world consequences. If you launch something to everyone just to get feedback and they hate it, then you risk permanently losing those users. Equally bad, you can cripple your entire application with unforeseen scaling and performance issues.

To mitigate this, companies like Facebook, Amazon, and Google collect [production feedback](http://tech.co/the-dark-launch-how-googlefacebook-release-new-features-2016-04) by releasing features behind feature flags. While we won’t go into to the specific anatomy of a feature flag, we can go through the methodology behind the release.

[![LaunchDarkly - Usability Testing Using Feature Flags and Toggles - Betas and Feedback](https://blog.launchdarkly.com/wp-content/uploads/2017/01/usabilitytest.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2017/01/usabilitytest.jpg)

If a feature is wrapped in a feature flag, then it gives you control over who sees the feature and when. This means that you can perform targeted and controlled releases using a percentage rollout, whereby you can incrementally increase a feature’s visibility to 1%, 5%, and to 100% of your users.

Hence, you can collect production level feedback because you control the level of risk. If a new feature is performing well, then you can keep increasing the percentage rollout. If it is tanking or hurting performance, you can reduce the rollout or kill it completely.

Therefore, [feature flags](https://launchdarkly.com/use-cases/?utm_source=launchdarkly_blog&utm_medium=organic) (aka feature toggles) give you full control over the risk of your production releases. You can gather real-world user feedback by separating your feature rollout from your code deployment.
