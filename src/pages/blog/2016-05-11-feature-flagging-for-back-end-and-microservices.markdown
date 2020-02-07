---
author: andreaech
comments: false
date: 2016-05-11 16:28:58+00:00
layout: post
link: https://launchdarkly.com/blog/feature-flagging-for-back-end-and-microservices/
slug: feature-flagging-for-back-end-and-microservices
title: Feature Flagging for Back-End & Microservices
wordpress_id: 701
categories:
- Feature Management
tags:
- back-end
- DeployHub
- feature flagging
- microservices
- mongo
- New Relic
---

I sat down with LaunchDarkly Lead Software Engineer [Patrick Kaeding](https://twitter.com/pkaeding?lang=en) to get his take on feature flags for the back-end and how feature flagging works with [microservices](https://blog.launchdarkly.com/why-microservices-need-feature-flags/).

**Andrea: How does feature flagging help in back-end projects?**

Patrick: It helps in general to be able to rollout to a small set of canary users and see if things go wrong. You can gather feedback from performance metrics or error logs. You can give a smaller customer access to the new feature or even a group of customers who know they are testing out something bleeding edge. Then you can make changes and react to the feedback and then roll it out to all users or roll it back. This helps mitigate risk and lets everyone sleep better at night.

**Andrea: What was it like before you used feature flags?**

Patrick: You would have to make a change - and test it of course, that part hasn’t changed - but then you would release it out to all of your users. You’d be watching everything to make sure nothing went wrong - and it would be a lot more stressful. You might have to time your deploy for a low traffic time, which meant staying up late on the weekend to be able to do the deploy at that time. And if something went wrong, you’d have to rollback the deploy. And if there’s any sort of data model change, sometimes rolling back to the old code is easier said than done. You might have to make sure you have a reverse migration in place and that adds a whole lot of complexity. Of course with feature flagging you still need to make sure both code paths still work in the data model. That’s still something you have to think about.   

<!-- more -->

**Andrea: Tell me about how microservices comes into the picture.**

Patrick: Microservices are great in how they help you split up your application into more manageable pieces. But sometimes, if you have a feature flag, it affects some big cross-cutting concern that would affect multiple microservices. It’s important that you keep those feature flags values in sync.  And that can be tricky with some of the open source options out there - especially if these microservices are written in different languages on different platforms. And being able to write different parts of your application in different languages or using different platforms is one of the huge wins of microservices! But if you were then going to feature flag across those different systems using some open source solution that is restricted to one language, you’re going to have a bad time. So something like LaunchDarkly that has the polyglot SDKs with consistent results is going to be incredibly helpful for that...to make sure your user gets the same feature flag value on one microservice as another.

**Andrea: Wow that could really be a big deal for certain users. **

Patrick: It’s really an orthogonal change to microservices.  Certainly you can use microservices just fine without LaunchDarkly. It’s really when you want to start using feature flags in microservices that you need to come up with something to manage them.  

**Andrea: To use all these different libraries together doesn’t even seem possible?**

Patrick: Yeah, especially if they are different languages.  If you have them all in the same language but they’re just different services, maybe you could get away with using some shared database.  But that still means that you have to make a call to the database to lookup a feature flag value.  For low volume that might be perfectly fine, but if you’re getting into high volume site you’re not going to make be able to make that make database calls and still serve the requests in a reasonable time. So, being able to evaluate that feature flag in-memory on each service means that you can do what you need to do much more quickly while still having control of the feature flag.

**Andrea: Do you have any stories about feature flagging in one of your back-end projects?**

Patrick: [The Mongo migration](https://blog.launchdarkly.com/feature-flagging-to-mitigate-risk-in-database-migration/) is probably the most interesting story.  Another pretty cool thing that I think is underrated, is [our New Relic integration](https://blog.newrelic.com/2015/06/24/launchdarkly-features-performance/) so you can see how performance metrics are affected by feature flags.  Measuring the impact of a new feature on KPI business metrics is one thing, but it is also critical to be able to monitor the operational impact. Does the new feature slow down the request serving? Or cause memory usage to balloon out of control? You need to be able to keep an eye on these things.

**Andrea: Are there other tools you like using with LaunchDarkly?**

Patrick: One cool one is [DeployHub](https://deployhub.io/).  So feature flagging lets you separate your deploy from your rollout, and LaunchDarkly gives you the view of what’s rolled out and how all that works.  We also use a tool called DeployHub to track what’s deployed and when, what code is on what server; it’s immensely helpful for that.  

_LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER BY HELPING MANAGE FEATURE FLAGS AT SCALE. START YOUR FREE TRIAL [NOW](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._
