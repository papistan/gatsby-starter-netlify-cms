---
author: edithharbaugh
comments: false
date: 2015-08-24 18:28:33+00:00
layout: post
link: https://launchdarkly.com/blog/secret-to-googles-engineering-culture/
slug: secret-to-googles-engineering-culture
title: Secret to Google's Engineering Culture
wordpress_id: 127
categories:
- Continuous Delivery
- DevOps
tags:
- canary release
- Google
- NewRelic
---

Google is known for rock solid stability and iterating quickly on user feedback. One of Google's secrets is canary releases to ensure stable, high quality products. A canary release is releasing features to some users (but not all). If the features aren’t successful, they are reverted to be fixed or removed. Google has an extremely sophisticated canary release process. Google has extensive unit tests that allow them to continuously integrate. After continuous integration, for major products like Google Mail, Google has a weekly release cycle.

Google’s first canary is google.com itself, as it has over 50,000 employees. Starting Monday and through the week, Google gradually rolls the new release internally to it’s own users, monitoring hundreds of different metrics on scalability and stability. Google’s employees act as canaries - squawking about any issues that come up. If core metrics are impacted significantly, the release is rolled back entirely. However, usually fixes are put in for critical issues and the release goes to the entire Google employee base.

On the next Monday, Google will take the release that had been rolled out to Google employees and canary release externally. Google will start showing more users the new release. Google continues to monitor for scalability and stability - using the external users as the true “staging” environment. Google’s products have a large enough base that they can even do sentiment analysis for keywords like “Gmail Sucks” on twitter. If there are spikes, Google will stop or roll back the new release. But usually by the end of the week, the entire release has been rolled out, and it's time for the new new release.

The advantages of Google's canary release approach is



	
  * stability - there's always a release to roll back to

	
  * feedback - real world users give real world reactions


Google is large enough that they can never simulate or test all situations internally on an artificial staging server. By pushing releases to real users as canaries, Google ensures that they're designing for the real world, not a laboratory. What enables Google to roll releases to real users is a deployment system that allows them to easily control who sees what features, and roll back easily. Want to be as smart and stable as Google? You could build your own canary deployment system - or you could use LaunchDarkly, which allows you to roll out features to your own users. LaunchDarkly even integrates with [NewRelic](https://blog.newrelic.com/2015/06/24/launchdarkly-features-performance/) so it's easy to see metrics on your features.



* * *





###### _LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER WITH FEATURE FLAGS AS A SERVICE. START YOUR FREE TRIAL [NOW](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._
