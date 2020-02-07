---
author: matkins
comments: false
date: 2018-03-23 20:05:42+00:00
layout: post
link: https://launchdarkly.com/blog/the-first-week-of-a-wild-ride/
slug: the-first-week-of-a-wild-ride
title: The First Week of a Wild Ride
wordpress_id: 2442
categories:
- DevOps
- Team &amp; News
tags:
- event data
- feature flag
- operational feature flags
- RabbitMQ
- startup
---

My first week on the job, we raised [series B funding](https://blog.launchdarkly.com/launchdarkly-1-feature-management-platform-gets-21m-in-series-b-funding/) and celebrated with a trip to a local tiki bar. After that big milestone, I've split my time learning a new programming language, learning a new deployment toolchain, getting acquainted with all my great new colleagues, and realizing that there's so much more for me to learn. A few things, however, have been familiar.

At my last job, we used LaunchDarkly for feature management. Engineers would create feature flags and then ship features behind those flags. We kept those features hidden to customers until we had tested them out internally. Once a feature was ready, we’d let our customer success team communicate the change to our customer and enable the feature.

Something that brings me pangs of nostalgia is operational issues with recording event data. At my last gig, we had an outage because of a bug (I introduced) that created a channel in RabbitMQ every time that we published an event. This bug went undetected for a while. Then, one day we had a load spike that caused our RabbitMQ server to run out of memory and prevent us from accepting all writes (because we tried to publish before the transaction was committed). Since the bug went undetected for so long, reverting recent deploys didn’t have an effect, and so we had an outage until we were able to find the root cause of the issue. Once we knew the root cause, the fix was easy, but while we were investigating, our application was essentially read only. If we had the ability to disable publishing for the one customer that was sending us the spike in traffic, we’d have been able to isolate and reduce the severity of this outage.

At LaunchDarkly, luckily, we use feature flags for those operational scenarios. Just recently we were getting a dramatic spike of events from one customer, to the point it was causing increased latency in our message broker. Once we noticed that, we disabled publishing events for that customer since they were already over their usage limit. By doing that we were able to isolated degraded service and prevent issues cascading to anyone else. Once we flipped the feature flag in LaunchDarkly, in real-time, the traffic was diverted and the outage was averted.

Building resilient systems like this is something that I'm really excited to be doing. I've got a lot to learn and [the company is growing fast](https://launchdarkly.com/careers/), so I think this wild ride is gonna continue for a while.
