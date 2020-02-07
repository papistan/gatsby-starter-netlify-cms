---
author: Kimh
comments: false
date: 2018-09-13 20:30:01+00:00
layout: post
link: https://launchdarkly.com/blog/performing-automated-canary-analysis-across-a-diverse-set-of-cloud-platforms-with-kayenta-and-spinnaker/
slug: performing-automated-canary-analysis-across-a-diverse-set-of-cloud-platforms-with-kayenta-and-spinnaker
title: Performing Automated Canary Analysis Across a Diverse Set of Cloud Platforms
  with Kayenta and Spinnaker
wordpress_id: 193352
categories:
- DevOps
tags:
- automated canary deployment
- automated testing
- canary deployment
- Google
- kayenta
- Netflix
- Spinnaker
- test in production
---

At our Meetup in July, we focused on testing in production with systems and processes at scale. Matt Duftler, Senior Software Engineer at Google, and Michael Graff, Senior Software Engineer at Netflix, gave a talk about automated canary deployments.


<blockquote>“So what's canary deployment? …the idea was to mitigate risk before you sent the valuable humans down there. [And] it's the same kind of thing with what we're doing, right? Try to mitigate the risk, make for safer deployments. Concretely, it almost always means exposing a small number of your users to a change. And that can be a binary change, config change, infrastructure change. So expose it to a smaller blast radius. And then once you have an increased confidence, then roll it out to a broader audience.”</blockquote>


Watch their talk below to learn more about what an Automated Canary Deployment consists of and how Spinnaker and Kayenta make this possible. If you're interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/).

[embed]https://www.youtube.com/watch?v=3xQm7CsR0ww[/embed]

TRANSCRIPT

[![](https://blog.launchdarkly.com/wp-content/uploads/2018/09/Matt-Dufler-1024x683.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2018/09/Matt-Dufler.jpg)

**Matt Duftler:**

I'm Matt, I work at Google. Michael will be up in a minute. He works at Netflix. We've been working together on this for a year and a half, maybe more. More generally, I work full time on the Spinnaker Project, but I dedicate a lot of time to this over that period of time.

All right. This is what we're going to talk about, a little bit about how we got here, what projects led to the creation of Kayenta, why we did this, what a Canary Release is, what an Automated Canary Deployment consists of and how Spinnaker and Kayenta make this possible. And then a bunch of practical things to keep in mind if you want to employ Canary Releases for your own deployments. Most of what we're saying, I mean we're going to talk about Spinnaker and Kayenta do, but it's really general information about Canaries. It's not specifically tied to using Spinnaker or Kayenta.

Netflix has internally a system called ACA. They've used it for a bunch of years. It's quite battle tested at this point. Basically everybody uses it. If you use Spinnaker, you almost certainly use it inside of Netflix. Google has several internal canary systems, but there's one big dominant one. There are lots of ways to deploy, to push changes into production at Google internally. The one that the vast majority of deployments use, you get canary analysis for free, so you don't have to enable it or configure it. It just kind of happens.

Nevertheless, both companies use automated canary analysis techniques internally. This system Kayenta that we built over that recent period of time is really like an evolution of Netflix's internal ACA system. And then we put our heads together and said, what would we do if we started over? Then we rebuilt the thing, made it open, extensible, support some advanced use cases that neither of our internal system supported in the past. Did all this out in the open in open source. And it supports like an extensible set of metric services and judges and cloud platforms and everything else. It's a service, it's part of Spinnaker. It has a full rest API. You can use it without Spinnaker. And we'll explain how all that works in a moment.

So internally, Netflix canaries, lots of different things, not just microservices, I think, like binary pushes to microservices are the dominant use case, but it's not the only use case inside of Google. We canary everything as well. And then future work is to expand the set of things you can canary, make it easier, like more consumable, enable faster canary, so you don't have to run things for hours or days or whatever.

Also we have lots of ideas about how to build more smarts into it. So right now you can make it work, but you have to know a lot and have a pretty mature release workflow. We'd like to make it easier. One example we talk about a lot is if you have a discipline, rollout procedure, and then something goes bad and you roll it back, and that thing that you were pushing out was publishing metrics, you now have a time window within which you've hopefully captured the metrics that indicate something went wrong. So why can't you just point the system like this at it and say, tell me what I should have been canarying on, what would have been a strong indicator that this was a risky deployment? But that's one example, but we have lots of ideas like that.

So what's canary deployment? The term comes from, and I think everybody probably knows this at this point, but miners used to send birds down into mines before they sent the humans down, see if there was a buildup of poisonous gases. The idea was to mitigate risk before you sent the valuable humans down there. It's the same kind of thing with what we're doing, right? Try to mitigate the risk, make for safer deployments. Concretely, it almost always means expose a small number of your users to a change. And that can be a binary change, config change, infrastructure change. So expose it to a smaller blast radius. And then once you have an increased confidence, then roll it out to a broader audience.

But looking at this diagram, this is again, it's an example, but this is a pretty typical deployment pattern for say a microservice. So you have something running that service, so they could be VMs or containers, something distributing traffic, so incoming requests, let's say, to all those backend systems. And then hopefully all of those things are publishing metrics somewhere. And in this case we have a change which is that red box and it has a smaller number of servers running that change, running that new version of your service.

So you have the bulk of traffic being handled by the thing that was already running in production and then a small percentage running the new thing, all publishing metrics. And then typically what would happen, if you're doing a canary deployment, is you'd run that thing for some period of time. It doesn't really matter what that period of time is. And then a human would try to look at some dashboards and say, was this a good push or not? Is this safe? Can I roll it out to a broader audience? Hopefully you're publishing metrics. Those metrics have to be tagged in some way that you can tease them apart later. It's no good publishing them if you can't figure out what you've published later, so you should be able to easily figure out later which metrics were from the production version, which are from the experiment or the Canary version.

But then you know, it's a human looking at graphs. It's kind of tedious. It's manual. Everybody looks at these things differently. I mean it might look one way to one person a different way to another person. Like this looks like an issue to me, but it might look different to somebody else. Chris Sanden, who's a senior data scientist at Netflix that works with Michael a lot and did a huge amount of this work, he calls it spot the difference game. Remember this when you're a kid and I see a couple of differences. But that's the idea, try to get away from doing that. But this is quite typical. And then if the one person who's really good at figuring out if things were safe or not is on vacation or tired or off that day, you may have have issues.

So we try to automate this, right? And the idea is to automate as much of that as possible. I mean, if you know how you do roll outs, you're publishing metrics, you know what metrics to look for, you can tease apart those published metrics. The idea is to just have the computers do this for you, so you're not relying on humans trying to tease apart this information later.

So here's that same conceptual overview of what a typical canary deployment for microservice looks like. We built it out a little bit and said, well, how does Spinnaker and Kayenta weigh into this. So same thing, traffic, load balancer, distributing it to your back ends. There's one big distinction to the right of it in this diagram though. So instead of just having that production group and then the Canary Group, there's an additional baseline group and we consider this a best practice, but obviously do what works for your environment.

But we typically recommend that when you want to compare what's running in production to a change or something you want to canary, that you provision a new baseline group, running exactly what's already running in production, but at the same time you provision the canary. And the goal is to have as much of an apples to apples comparison as possible. So same infrastructure, same size baseline in Canary Group, provisioned at the same point in time, taking the same traffic, at the same load, in the same conditions. As much of an apples to apples comparison as possible. If you don't do this, the things that you're working off of might be false signals, they might be noise, might be wrong. We outlined that with Spinnaker, but the ideas in this diagram, Spinnaker, which is like a, gives us a continuous delivery platform, it has a bunch of services where you can build pipelines and it can orchestrate your deployments and manage traffic and things like that.

Spinnaker would have orchestrated the rollout of the baseline and the Canary Server groups, whether they're containers or VMs, and then directed traffic there. Those services themselves, republishing metrics, and then Kayenta, which is this automated Canary Analysis service that we released a few months back, that thing is also a stage in Spinnaker and it would go off and scrape for those metrics from your metric service and it works with a whole bunch of different metrics services. And then use the configuration you provide to try to make that automated judgment. So you would say this metric is significant, or these metrics are significant. I give this much weight to these metrics, this one is critical. This one I just want to hear about but shouldn't fail. So those are the kinds of configuration you provide to it. And you can say this metric can go up. It's not a failure. This one can go down. It's not a failure. Or this one if it deviates at all in any statistically significant way, that's a failure. So you give that kind of configuration, then it automates those steps we talked about. Provisions everything, wait for it to run for some period of time, wait for metrics to collect and then make your judgment and that judgment is a gate in your deployment.

So I'm gonna hand it over to Michael and he'll give you hopefully some war stories from Netflix.

[![](https://blog.launchdarkly.com/wp-content/uploads/2018/09/Michael-Graf-1024x683.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2018/09/Michael-Graf.jpg)

**Michael Graff:**

Hello, I'm Michael Graff from Netflix. And I've been working on the Spinnaker team now for about three months, but I've been working on Canary Analysis for about two years. So I followed the project from the Spinnaker team, which is great.

One of the problems with the scenario analysis at Netflix right now is that you still have to pick all the metrics. So if you choose bad metrics, or your metrics are bad, you're going to get really bad results. And a lot of times you don't even know they're garbage until you actually start looking at them in a very analytical way, because humans ignore things like spikes. They go, oh, that's just an aberration. We can ignore that whenever we look at the graph. But our analysis has to actually take all that stuff into consideration.

And this is the graph we had before, is this good? Is this bad? It depends entirely on what your application is doing. So you also have to have a lot of domain knowledge about what your individual metrics are. And this is something we're trying to address at Netflix in the future, but right now it still requires a lot of configuration. As Matt mentioned, we're gonna be doing some sort of something to be able to look at all the metrics that you currently have and figure out what your application looks like when it's healthy and when it's bad, and get it down to the smallest number of metrics possible to indicate what a failure looks like in the common case.

Another issue are the types of metrics. In some cases you end up with metrics that are very spiky and those are much harder for our current algorithm to classify versus the nice continuous one on the right. Continuous ones look wonderful for us, but whenever they're sparse, we have to try to guess, is data missing or is zero or what's going on there. It's also bursty workloads tend to be very bursty, and you can't really actually judge exactly what's going to happen. You can't really compare apples to apples and you have a lot of false positives.

And one way to actually solve this when you're trying to select the metrics is to do an AA analysis, which is really just running the same version against the same version and if you get bad results, if your canary fails, which it shouldn't, that means either your code is already broken, you just don't know about it yet, or more likely your metrics are not really indicative of a actual problem or indicative of an actual success.

The other issue is how long do you run a canary for and when do you start? As Matt mentioned again, we have the baseline cluster that we spin up to try to minimize the effect of a brand new application, which is the canary starting up with a older application or running with an older application, which is why we spin up the baseline cluster running the old code as well. But your application may be very random in behavior at the first five minutes, 10 minutes, 15 minutes, depending on what you're doing. Caches have to be filled. Maybe you're loading something from databases or such before you actually start serving traffic. So it's up to you to decide when you do that, when you actually start looking at the metrics from the Canary analysis, actually starts looking at that to determine what health looks like.

And the other issue is how long do you run the Canary? If your granularity of data is every minute, the current algorithm that we use really wants about 45 data samples, which means you're already exposing users to 45 minutes, plus the warmup period, before you can actually get the first judgment to say, is this good or bad? So that's a window of risk that we really are trying to get down.

So one thing we're doing and once again at Netflix is trying to get that down so we get five second or ten second granularity data, so we can actually get a Canary analysis within the first 45 times whatever step size we use, which should help a lot. This is especially effective on larger scale Canaries where people actually, our customer service team is very aware when we run Canaries, because they oftentimes are the people who get the first call and they are able to look into our database and say that Canary is running. Let's see if that's the issue or not.

And along that line, the size of your original cluster really matters. In this case, this is a microservice and there's a simple load balancer in front of it. That may not be sufficient for some applications. If you have a small number of servers that actually handle a lot of traffic, you may have to actually adjust the way you get the traffic to those individual servers. In this case, we have the production cluster running six instances. We have the baseline running three, which means the Canary itself is 25 percent of the effect, so 25 percent of users, if this canary is bad, could get a very bad response.

In the microservice world, we also expect this to be very homogeneous, where the application itself does everything. The application does a small number of things, but every server is the same. You can't really Canary something that's running a different type of service against another one, but we get that request once in a while, especially whenever you roll out a new feature. So ideally when you first do the Canary, all the features are identical across the board and then you'd flip the switch later, which could be a second Canary, because you can also Canary the feature flag to turn that on.

So keep in mind, Canaries aren't magic. They are a tool that help you protect against mistakes that you were about to deploy. Without Canary analysis, you would have already deployed this code. This isn't a test suite, it's a thing that says, okay, now that area, all the testing has been done, all the work has been done to make certain it's safe, it's a final check. If you can't determine how it works, we're not going to have a magic bullet that determines what healthy is for your application.

And so you have to know how to measure your application as being successful or not. You have to know what it means for it to be unhealthy and be able to find that and program that into the system. And you have to have data come into some common place that we can fetch that from. And the higher granularity, the better. In our case we have something called Atlas which is very similar to other things you've seen that has tags for everything. So we can actually slice and dice as much as we need to.
