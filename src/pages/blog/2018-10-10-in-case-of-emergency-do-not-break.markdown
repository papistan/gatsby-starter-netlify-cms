---
author: heidiw
comments: false
date: 2018-10-10 21:20:01+00:00
layout: post
link: https://launchdarkly.com/blog/in-case-of-emergency-do-not-break/
slug: in-case-of-emergency-do-not-break
title: In Case of Emergency, Do Not Break
wordpress_id: 193429
categories:
- DevOps
- Feature Management
tags:
- fail safe
- failure
- feature flagging
---

What happens to your application when your feature flagging system goes down? There are two possibilities: fail-safe or fail-broken.

The first possibility is that nothing happens. This is the fail-safe mode. No updates to flag states are made, but everything continues to operate the way it has all along. And when the feature flagging system comes back up, there’s no changes from the user point of view. This kind of system works because flag state is set and then maintained on the client side—the flag evaluations are already made.

For example, if you are doing A/B testing in a fail-safe feature flagging system and the system goes down, everyone getting the ‘B’ variant will continue to receive the ‘B’ variant. They have already been evaluated and sorted into that bucket, and their identifier is used to retrieve the ‘B’ variant from the application servers.

In a fail-broken system, it’s a little more complicated. Fail-broken systems are often more tightly-coupled and have the weaknesses of their strengths. When the client calls back to the flag evaluation on the unresponsive system, the call can fail, timeout, or return an error message. If it fails, the user may not see the feature controlled by a flag. If it times out, the user may experience it as general slowness. If there’s an error, it may get passed through to the user.

In an A/B test that is running in a fail-broken environment, users who should get the B variant may get an empty element or an error message. The application page would need to be designed to catch errors from the flagging system and smooth them out for the users.

There are reasons to use a system that fails broken. You may need indications that it’s broken, or it may be dangerous to assume that you can continue to serve the same state without checking back in with the application. For most applications, however, it’s better to [fail safe](https://launchdarkly.com/blog/designing-for-failure-to-avoid-disaster/) than to present users with errors.

Thinking about failure states is a type of testing and an essential part of making sure your application will behave in the way you expect it to, even in the face of [unknown-unknown failure states](https://launchdarkly.com/blog/what-makes-a-failure-a-disaster/).
