---
author: edithharbaugh
comments: false
date: 2016-08-22 23:55:44+00:00
layout: post
link: https://launchdarkly.com/blog/feature-flagging-and-testing/
slug: feature-flagging-and-testing
title: Feature flagging and testing
wordpress_id: 1010
categories:
- Feature Management
tags:
- feature flag
- feature flag tip
- Feature flagging tip
---

[Sam Stokes](https://twitter.com/samstokes), Rapportive co-founder, has this tip on testing and feature flagging:

"I've found that explicitly testing both sides of the flag can help with managing the increased complexity a flag introduces.  It helps you catch changes down the line that would have broken the old, forgotten code path that 10% of customers are still on.  It provides reminders to clean up the old code and delete the flag (via occasionally breaking the tests).  And it provides some pushback against having too many interacting flags (if you had to write 8 tests for one function because it depended on three separate feature flags, maybe it's time to refactor that function, or retire some flags)."

Sam Stokes regularly blogs [here](http://blog.samstokes.co.uk).
