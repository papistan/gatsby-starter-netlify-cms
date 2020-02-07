---
author: matkins
comments: false
date: 2019-05-24 16:35:48+00:00
layout: post
link: https://launchdarkly.com/blog/this-one-weird-trick-to-trace-your-application-at-scale-for-free/
slug: this-one-weird-trick-to-trace-your-application-at-scale-for-free
title: This One Weird Trick to Trace Your Application at Scale for Free
wordpress_id: 193940
categories:
- DevOps
- Feature Management
tags:
- debugging
- feature flags
- tracing
- user attributes
- user targeting
---

Detailed execution traces are incredibly helpful when debugging applications, however sometimes recording these traces is more expensive than you’d like. Recently, we added detailed tracing to our streaming API servers. Unfortunately, the memory needed to store these detailed traces was more than we expected and our application was soon running perilously low on memory.

Instead of removing tracing from the code, we put a feature flag in our instrumentation. This flag allows us to decide whether or not to allocate memory to store each part of a trace. **We can use a feature flag to turn on detailed tracing at a 200ms notice and save our memory when the flag is off.**

One of the most powerful things about feature flags is that they allow you to tweak the experience for each user of your application through [targeting rules](https://docs.launchdarkly.com/docs/targeting-users). We can apply this idea to tracing as well. However, instead of tweaking the experience of a user, we'll be doing that for a trace, so the experience is just whether or not we store the trace. All of our traces have several identifying attributes. By putting all of these attributes into LaunchDarkly's 'user', we're able to use that information in our feature flag rules to target very specifically what is traced.



 	
  * serviceName – the service that is being traced

 	
  * operationName – the name of the operation that we’re tracing

 	
  * account – the LaunchDarkly account associated with the trace

 	
  * project – the LaunchDarkly project associated with the trace

 	
  * environment – the LaunchDarkly environment associated with the trace

 	
  * key – the request id associated with the trace


With these custom attributes available to us, we're able to do some pretty useful things on the fly. Some of the things we've done so far:

 	
  * store complete traces for 10% of all requests

 	
  * store complete traces for everything a single customer is doing

 	
  * exclude a repeated operation from traces


For example, the following configuration makes it so that we only trace the initialization code path in our streaming API servers.

[![LaunchDarkly instrumentation tracer implementation](https://blog.launchdarkly.com/wp-content/uploads/2019/05/Screen-Shot-2019-02-01-at-4.08.25-PM-1024x652.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/05/Screen-Shot-2019-02-01-at-4.08.25-PM.png)

Here, we've got two targeting rules. One that stores traces that contain the `stream init`, `stream finish`and `nats init` operations in [Honeycomb](https://www.honeycomb.io/), and another that ignores traces from the `streamer-sdk` and `streamer-msdk` services. Since targeting rules are applied in order from top to bottom, this makes it so that our stream initialization operations are stored in Honeycomb and that all other operations from the streaming services are ignored.

Generally, I've found these not-a-user users very useful for making tweaks to the behavior of our applications while they're running. There is a caveat though: the users must be **anonymous**. Otherwise, you'll flood your users page with traces and you won't be able to distinguish your human users from traces.

Ready to try powerfully customizable and incredibly efficient tracing in your app? [Give LaunchDarkly a try for free](https://launchdarkly.com/#free-trial) to feature flag your tracing and speed up your application.
