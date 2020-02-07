---
author: edithharbaugh
comments: false
date: 2015-12-05 03:35:53+00:00
layout: post
link: https://launchdarkly.com/blog/featureflagasservice/
slug: featureflagasservice
title: Why smart companies choose LaunchDarkly for feature flags as a service
wordpress_id: 274
categories:
- Continuous Delivery
tags:
- continuous delivery
- feature flag
---

[Feature flags](http://featureflags.io/feature-flags/) are a key part of successful continuous delivery that the most successful companies like [Heroku](https://www.heroku.com/) and [CircleCI](https://circleci.com/) use to supercharge their development. Feature flags power software teams to release features faster to the users they want. The biggest companies maintain their own feature flagging framework - but the smartest ones are using feature flags as a service, from LaunchDarkly.

Feature flags start off simple, but can quickly become a quagmire when you need to [maintain them](http://featureflags.io/management/). At the beginning, it’s easy enough to create a feature flag as a database table that an engineer can manually use to turn a user on or off. Next, you’ll want to start doing more sophisticated rules like “20% of traffic,” “everyone on our beta email list” or “no one with a TechCrunch email address.” At this point, usually a rough UI is made so that non-technical people can also control. Then, the bright idea comes of using the same framework for a/b testing. This works, until it doesn’t. That's when the smart companies switch to LaunchDarkly for their feature flags support, for ROI, reuse, maintenance and sophistication.

**ROI** [Auction.com](https://www.auction.com/) chose LaunchDarkly because they didn't want to dedicate multiple engineers to build a feature flagging system from scratch. They wanted their engineers to work on differentiating features for Auction.com. Lawrence Yuan, Senior Director Web and Mobile Engineering at Auction.com, LLC says “LaunchDarkly has been easy to on-board and integrate into our existing development cycle, which has helped us move faster with less risk."

**Reuse** One large LaunchDarkly customer had built a custom feature flagging structure for their one product. When they acquired another company, they found that they couldn’t reuse the functionality for any acquisitions, as it had been intertwined with their own functionality. Another customer recently rebuilt from Ruby to Node.js. When they rebuilt, their existing feature flagging infrastructure was obsolete. In both cases they found it prudent to move to a more stable system.

**Maintenance costs** CircleCI had built and maintained their own feature flagging system, as it was a critical part of the release process they used for canary releases and dark launch. However, they wanted to spend their time on continuous integration, not on their feature flagging system. Mark Pundsack, VP Product CircleCI, made the decision to move to LaunchDarkly, saying “I really like LaunchDarkly, and I’m glad we’re using it. I believe that feature flags is a critical piece of modern development, and LaunchDarkly brings this part of continuous delivery to the masses."

**Flexibility & sophistication ** LaunchDarkly facilitates both simple and complex feature flagging. We have both per feature views as well as per user views, so you can easily see who has what features. We allow you to see how long a feature flag is in use so you know when to remove it. Other developer tools companies use LaunchDarkly, saying “We like that you think about nothing but feature flags.”

The smartest companies are choosing to have LaunchDarkly handle their feature flagging. Are you ready to join them? Click [here ](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)to start your free trial.
