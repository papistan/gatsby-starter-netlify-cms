---
author: andreaech
comments: false
date: 2018-03-08 18:00:34+00:00
layout: post
link: https://launchdarkly.com/blog/testing-and-debugging-in-production-with-distributed-tracing/
slug: testing-and-debugging-in-production-with-distributed-tracing
title: Testing and Debugging in Production with Distributed Tracing
wordpress_id: 2224
categories:
- DevOps
- Feature Management
tags:
- distributed tracing
- lightstep
- monitoring
- observability
- test in production
- tracing
---

At LaunchDarkly we host a monthly Meetup for anyone interested in testing in production. At our Meetup in February, we focused on monitoring and observability while testing in production. If you’re interested in joining this Meetup, [sign up here](https://www.meetup.com/Test-in-Production/).

Priyanka Sharma, Product Marketing, Partnerships & Open Source at LightStep, kicked off the event with a discussion around how she sees tracing as an essential tool for testing in production. She pointed out how software systems have become more complex in recent years, especially with the rise of CI/CD and microservices.

“There's an explosion of data. The more services there are, the more touchpoints there are, and the more data you have to collect about what's happening in your system. It's very hard to manage all of this.”

Watch her talk to see how distributed tracing can help teams get a better understanding of their systems and the responses they’re seeing when testing in production.



TRANSCRIPT

Hi, everybody. How's everyone doing?

Awesome, awesome. I love Heavybit, just like Andrea. LightStep also was here until a few months ago and we miss the space and the community. And today, I'll be talking about tracing being an essential tool for testing in production. So before we deep dive in to tracing, let's take a brief overview of what are the big challenges in production, especially around debugging and performance.

As people here probably know better anybody else, software is changing. Software workflows are changing, especially with the event of CICD and also microservices. Things are done completely different now. This diagram you see here, the first one, is what a monolithic architecture would look like where it's one giant box and a request from start to finish and its lifecycle goes through various parts of this box, which, while it's huge and has a lot inside it is at least contained and viewing something through it was much easier.

But now as systems are breaking up into fragments whether they're microservices or larger services, however you call your service or you call it core projects, whatever, the point is that there's more and more complexity introduced in today's software systems.

What also happens with this is that there's an explosion of data. The more services there are, the more touchpoints there are, and the more data you have to collect about what's happening in your system. It's very hard to manage all of this.

This is where distributed tracing can help. So if you have anomalies or outliers that you want to detect, it gets very challenging in that very fragmented system over here because is it in that corner, on this corner here? Where is the actual problem? With distributed tracing, you can examine the exact edge case and see what happened end to end in that request lifecycle. If you're running a distributed system, out of curiosity, how many people here have a distributed system with at least two services? All right. A bunch of you. So you know what I'm talking about where that observability can be really lost the minute there is any fragmentation. So with tracing, you can get a full picture off your system from the plans all the way to the back end and the responses that come out.

How many of you here run CICD? All right. A bunch here too. So when you're running CICD, it's great that you can ship faster, but also there can be problems with your bills and you need to understand what is the issue. Often times, it's not the code, but actually the resources being utilized. And with tracing, you can pinpoint that as the issue if it is the case.

Andrea mentioned gradual software rollouts with feature flags, things like that. If you're doing that, you want to analyze the full transaction data off each rollout to look at the performance, see what errors were there, and make informed choices about the next rollout that happens and that is, again, something that distributed tracing can provide you.

So just to make sure we're all on the same page, before deep diving further, I'd like to do a quick intro of distributed tracing as I'm defining it in this context and make sure we're all aligned. So what is distributed tracing? So tracing as a technology has actually been around since the 70s. But what's brought it mainstream into industry is the coming of distributed systems into the internet age.

So then you need to know the lifecycle of a request and to end in a distributed system, you use distributed tracing. It's a view of the request as it travels across multiple parts of the systems and come back out with the response. This here is an example of a relatively simple request going through a small system. So you can imagine if you 10x it how big this will be and how complicated it'll be to follow the path of a request.

So what's a trace exactly? A trace is the entering life cycle of a request and its composed of parts that are called spans. Now a span is a named timed operation that represents a piece of workflow. So think of it as Point A to Point B and then there's a jump in the context to a different span and then Point C to D and it goes from there. This diagram here, it should give you a little bit of a sense of how a trace is structured where there'll be the parent span that starts a lot and there can be child spans or logs, etc. in here. So you can add in a lot of information that is important to you and your system. So there's a lot of flexibility. Ultimately though, the TL;DR of this all is that the trace is a collection of spans.

So here, I've tried to visualize what a request looks like in a very simple architecture and then the trace view. So on, I guess your left, my right, your left, there's a very simple service. There's a client then a rep server that talks to an Auth service, billing, and a database. If you're looking at the trace we offered, which is my left, your right, that's on the time continuum. And the top you see over there, the client, or the root span is the top most thing because that is the beginning and end of the request. And these dashes that you see are all spans of work that happened within this whole trace. So this can be quite useful when you're debugging a problem because you can deep dive exactly is the problem and the process workflow or in the art in the DP, client, whatever.

So that's great, right? You can deep dive into things, you can append information and logs and baggage. There's so much you can do with tracing and systems of fragmenting so much as changing. So then why is tracing not ubiquitous? The key reason here is that tracing instrumentation has just been too hard. Until recently, most of the instrumentation libraries were vendor specific. And so if you went through all the work of instrumenting each part of your code base, you were connected to this vendor and you didn't really have a choice to change options should this one not work out for you.

Then monkey patching is insufficient. So an automated agent can do so much, but you need instrumentation by humans who understand the system and the problems that they run into for it to be a comprehensive system.

Then there's the problem of inconsistent APIs. Today's systems... How many of you use more than one language in your code base? A bunch of you. So the minute there's more than one API, if you have to transfer between different APIs or different languages, which don't work nice together, you have a problem because you're only seeing a snapshot of your system. And the same applies to open source projects. So most people's code is a ton of open source projects with Glue code, that's your application code, right? And so in that situation, if you're not seeing anything through those project, then you're, again, flying in the dark. And tracing libraries for different projects if they're not the same ... You have the same problem that you had with different language APIs that don't play nice with each other. So all this is a lot of difficulty and dissuaded most developers from going into tracing.

And this where open tracing, the project I work on is your ticket to omniscience. So the open tracing API is a vendor-neutral open standard for distributed tracing. It's open source and part of the Cloud Native Foundation, as I mentioned.

It enables developers to instrument their existing code for tracing functionality without committing to an implementation in the start. So you could use any tracer and visualization system such as LightStep, Zipkin, Jaeger, New Relic, Datadog. Whatever choice you have, if they have a binding for open tracing, you can go ahead and swap out with just a change in the main function.

And this standard has been doing really well and part of the reason why I that it's backed by folks who've been around the tracing landscape since it became mainstream industry. So Google release this project called Dapper, which it's in production tracing system that was created by Ben Sigelman and a few of his colleagues. And they released a paper about it in the 2000s sometime. Inspired by that, Twitter built Zipkin, which it open sourced around 2009. And then now these people who've worked on these project including Ben Sigelman, including other folks from industry like Yuri Shkuro from Uber, other folks came together to build the open tracing spec in 2016 and it was built by people who had solved these problems before, had lived these problems multiple times, and the result is there for others to see.

So let's look at the open tracing architecture. This is it. Jk. So there's the open tracing API. It speaks to the application logic, the frameworks, the RPC libraries, you name it and they all connection to open tracing. And open tracing talks to the tracing visualizer off choice. Here, the examples listed like Zipkin, Lightstep, Jaeger, very, very few. As I mentioned just before, multiple vendors such as New Relic, Datadog, Dynatrace, and [inaudible 00:09:57] have created bindings for open tracing. So the options for the end user community are very many.

A lot of end user companies are finding this very useful in production. So this logo wall is by no means complete. It's all kinds of companies from hipster engineering cultures to large scale enterprises to somewhere in between. You see the Under Armors of the world. You also see the Lyfts and the CockroachDB, etc.

Along the way, the open source site has really pushed the project along too. The open source project maintainers have adopted open tracing and accepted PRs for it because this an opportunity for them to allow their users to have visibility through the system without having to build the whole thing themselves. Some notable ones will be Spring by Pivotal, GRPC, and there's a bunch of language libraries fueled by this open source and end user adoption vendors have been jumping onboard.

So that all sounds great. Clearly there's some social proof, people seem to like it, but what does this really mean? Let's look at open tracing in action with some traces. So I'm now presenting the next unicorn of Silicon Valley, Donut zone, which is a DaaS, Donuts as a Service. It's the latest innovation, it's donut delivery at its very best, it's backed by Yummy Tummy Capital with a lot of money. This is the beautiful application we've built and through this, you can order donuts. Now I'm going to be asking you guys for help very soon to help me create a success disaster on donut zone.

Before that, I quickly want to explain the DaaS architecture, which is built to move fast in big things so that you know when we look at traces, what we're really looking at. So we have bootstrapped with a single donut mixer for our topper, start up life. But the good news is that we've built with open tracing. There's an open tracing of our Mutex wrapper that's included in this. So it will hopefully help us debug any issues that may come up. But who knows?

So now we are going to get on to the success disaster part of the piece. So if you can please pull out your mobile phones or laptop, whatever you may have and go to donut.zone. I'm going to do this too. And then once you're there at donut.zone, just start ordering a bunch of donuts, as many as you would like in a dream world where there are no calories in donuts and they were just like water but tasted like they do. So let's get started. Click away because if you don't do this, there will be no good traces to see and so this is all on you. Okay, so tap, tap, tap. Click, click, click. Okay, let's just do a little more for good measure. Don't be shy. Click a lot. Okay, great. So thank you so much.

Now let's look at some traces. I have a bunch of traces here. Now you'll see that this is a full trace and the yellow line that you see here ... Can people see the yellow line? The yellow line is the critical path, which means the things that ... the blocker, so to speak, for the process to be completed. So here you see that the donut browser is taking up in this specific trace, which is 10.2 seconds long. Seven seconds are gone just by the browser and client interaction. What does that tell us? Something that's not every surprising, which is that the internet's a little slow. So nothing moved beyond the client until seven seconds in. Then you see here this is like the payment is being processed because you paid fake money for your donuts.

Then here is an interesting one. Here we see that from 7.6 seconds to 9 second was taken up by the donut fryer. But, the interesting point here is that the Mutex acquire says that that itself took close to about, I would say, two and a half seconds, which mean ... And here in the tags, you will see that I was waiting on six other donut requests. This is where you created the success disaster by clicking so many times. So this request was just waiting for its chance to be fried and that took up the most time. So that should tell you that if you were debugging over here, that it's a resource allocation issue as opposed to an issue in your code. The code that worked just took this tiny amount of time. So you'll be better off optimizing by adding a fryer. And this is something you knew right away because you had this distributed trace available and you could debug on the moment to figure out why is it so slow to get these donuts from donut.zone.

So I hope you found this useful. For those of you who are interested in seeing those kinds of traces for your system and debugging efficiently and quickly, I recommend going to open [tracing.io](http://tracing.io/) to learn about the project. We have documentation, we have links to all our GitHub Repos, and lots of advice, etc. But if you're interested more in the community aspect, you want to talk to people, hear their experience, then I'd recommend the Gitter community where we all hang out. It's [gitter.im/opentracing](http://gitter.im/opentracing). This is where people help each other and you can get good advice on how to get started. I hope you found this useful. If you have any questions, feel free to reach out to me, [priyanka at lightstep.com](mailto:priyanka@lightstep.com). I am also on Twitter at @pritianka. Reply really quickly. So please reach out, check out distributed tracing, and let me know if I can help in any way. Thank you so much.
