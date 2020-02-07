---
author: Kimh
comments: false
date: 2018-05-30 22:41:27+00:00
layout: post
link: https://launchdarkly.com/blog/debug-a-kubernetes-cluster-in-prod-with-the-conduit-service-mesh/
slug: debug-a-kubernetes-cluster-in-prod-with-the-conduit-service-mesh
title: Debug a Kubernetes Cluster in Prod with the Conduit Service Mesh
wordpress_id: 193088
categories:
- DevOps
tags:
- Conduit
- debug
- DevOps
- Kubernetes
- service mesh
- test in production
- visibility
---

The second guest speaker at our April Test in Production Meetup was Andrew Seigner, Software Engineer at Buoyant. Buoyant develops open source service mesh software. In his talk, he focused on visibility and debuggability.

[tweet_box design="default" float="none"]“Service mesh is a bit of a buzzword of late for…it’s really a piece of software that runs on top of something like Kubernetes to provide security reliability, debuggability, and visibility into your cluster in a really uniform way."[/tweet_box]

Watch his talk below and follow along as he goes through some of the steps of deploying an app and layering a service mesh on top of it. If you’re interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/).

[embed]https://youtu.be/ZcyCvJhJVXk[/embed]

TRANSCRIPT

My name's Andrew Seigner, I work at a place call Buoyant, we develop open source service mesh software. Just kind of stepping back really quick, service mesh is a bit of a buzzword of late for ... A quick review of what it is. It's really a piece of software that runs on top of something like Kubernetes to provide security reliability, debuggability, and visibility into your cluster in a really uniform way. Today, in the talk, we're gonna mostly focus on visibility and debuggability. We're gonna go through some of those steps.

Most service meshes are split into a control plane and a data plane. The control plane is something that kind of manages routing policy, handles telemetry and observability, all that, allows you to interact with your cluster in an administrative way. The data plane is often a small proxy that runs next to your application. That stuff's in the hot path, so it's stuff that's actually routing the data between your microservices.

A little bit about Conduit, what we work on. The design goals of Conduit are really solving production problems, being super lightweight, and having zero configuration, making it super dead simple to set up. Those are kind of lofty, handwavy goals, but we'll get into some of the demos for a little more concrete examples of how that stuff works. A little bit about Conduit specifically, talking about a data plane and a control plane. The technologies we picked for the data plane, we chose Rust. For the control plane, we chose Go. Rust was a bit of a gamble. We picked it almost a year ago, maybe six months ago. What we were really looking for was native performance and memory safety, and it seems to have fit the bill. We found the community to be super enthusiastic about it. So far, so good. It's paid off.

For the control plane, we wanted performance, but we didn't quite need the performance of Rust. Since we're integrating with Kubernetes, Go seemed like a really natural language to choose. That's also paid off really well. You'll see in a little bit how the tooling integrates with the Kubernetes environment. Using the libraries that the Kubernetes folks have provided for us has been super helpful.

We're gonna jump back and forth a little bit. If I make you all dizzy, just tell me and I'll slow down. So, what we're gonna do is we're just gonna deploy an app, and it's gonna be kind of broken, and then we're gonna layer on some service mesh into it. Right now, I've got a Kubernetes cluster running on my laptop. I've just got one demo app YAML here. So, I'm just gonna cat that into kubectl. I should ask, can you all read that? Should I make it bigger? Make it, maybe, a little bigger? Okay. Cool.

Okay, so now I've got an app deployed. I'm gonna start up a tunnel to it just so we can play with it just to give you an idea of what it looks like. It's a simple little toy app. It's for voting on your favorite emoji. When you click on one, it tells you how things are going, what emojis are voted on the most. There's also a bot that runs so it should be creating some additional traffic, maybe eventually. We'll see. What we'll notice is that if we click on some of these, we're getting failures. Something's broken. We don't really know what, we just know that if we click on some of the emojis at the top of the page, they seem to be okay, but if we click on emojis near the bottom of the page, they fail.

The website's broken. What do we do? From a plain vanilla Kubernetes perspective. Oh. Let's just click on all the unsafe things to get into here. Let's see. Sorry, bear with me for a second. There we go. Everything's green. From the plain Kubernetes perspective, that's true. All the pods are running. As far as that layer is concerned, the app's working. The services are throwing 500s at each other, but we don't quite have that level of visibility in here yet. So, what we're gonna do next is I'm gonna go through and layer on this service mesh and see what that looks like to install it and then how we use that to debug what's going on.

I'm just gonna give a quick spoiler on what's actually wrong. So, this is the app that we just deployed and there's a few different services going on. You can see we're here at the browser. Spoiler, the voting service is what's broken. It's broken when it's talking to the emoji service. I'm just telling you this because I'm gonna be at the command line typing between all these services. Just to give an idea of like ... We have to kind of explore this topology to figure out what's wrong with our app.

We're gonna do two things. We're gonna install the control plane, which is ... We provide this binary, you can download it or build it yourself, that installs all of those Go packages that allows you to administer the service mesh on your Kubernetes cluster. It just generates some YAML and you pipe it into kubectl and that's it. The next thing that we're gonna do is enable our emoji test app with the Conduit data plane. This is all it is. You take the YAML you already have, you pipe it into our inject command, and it's going to inject a bunch of proxies next to each one of your containers, and then we send that out to Kubernetes again. We don't have to change anything in our app, we don't even have to take down the app. We just redeploy it as is. Let's go through that part now.

First thing we'll do is install the control plane. Okay, so now we've got a control plane up and running. To confirm that everything's doing what we want, we provide a little... Oh. Give me a minute. We provide a little dashboard that tells you that things are up and running. So, this is just kind of a welcome screen. We don't have any interesting data in it yet. We know the control plane's up. If we look at our deployments, here's our sample app. Conduit's already talking to Kubernetes and it knows they're there, but we don't have any information on what's going on.

The next step we're going to do is inject those data plane Rust proxies into our application. I'll go back to the tab where I deployed my emoji app and instead of just deploying it like this, I'm gonna inject Conduit into it. You'll see ... A lot of these, your services don't change, but your deployments do and they get redeployed with a new proxy in them. If we switch back to our control plane, if everything worked, we should start seeing these things activated as part of the service mesh. We can go here. You can start to see metrics rolling in. We've got success rate, request rate, and latencies across the things that we just enabled. It'll take a minute to get all of the data collected, but you get the idea.

Already, we can see things are bad. Our success rates are not good across all the services. It's hard to know which piece is broken right now. Now, we're gonna use the Conduit tooling to dig into these numbers to pinpoint where that failure is. We're gonna use two commands, stat and tap. Stat is something that gives us metrics about our services, and then tap actually lets us tap in and see requests as they happen. Let's just get an overview of the whole cluster.

If you've used kubectl, Conduit is a lot like that. It's kind of the same patterns of resources. That dashboard we just saw on the webpage, it's exactly the same data as we're seeing here. We can see that our success rates are not good. Let's limit what we're looking at just to our demo app to kind of zero in on what's going on. Okay, so we can see we have three apps that all have failure rates. What we're gonna do is let's start at the top. We know stuff is broken when we're on the webpage, so let's zero in on the web service and look at all the calls that are going out from the web service. So, we're already looking at deployments, but let's do all deployments but filtered from the web deployment.

Okay, now we're getting somewhere. Turns out the web deployment calls two other services and one is showing 100% success rate, the other is showing 44%. We're already on the right track on where in our call graph are things breaking. Let's dig a little bit farther in and look at, is it the voting service in particular that's failing or is it calling something downstream from itself that's causing failures? We'll do the same command, but we'll do it from the voting service. Okay, now we see that voting is calling another service and that service is showing bad success rate. We're kind of zeroing in, again, on there's something between these two, but it's not clear. Is it that lower level service that's bad or is it the one upstream from it?

What we can do from here is say, let's filter by all requests to that lower level service. It turns out that this lower level service is getting called from two different places, and when it gets called from one, success rate's great, and when it gets called from another, success rate's 52%. At this point, we've pretty much identified the edge in our call graph where things are broken. Now, this is where we transition into using our tap command to actually see what the requests are doing and why they're failing. Let's just zero in on the voting service and we're gonna switch this from a stat command to a tap command.

I don't expect anybody to read this, but these are live requests coming in that are transiting through the proxy right now. To be clear, this is not like tailing a log. The proxies are not doing any work until you run this tap command. You can activate it for as many proxies as you want at a time, and you can also throttle how many requests you want to see. It establishes a persistent JRPC connection with each proxy and you get data as it's streamed.

If we just kill this for a second, try to get a handle on the failures that we're seeing. Let's see. Okay, so I see a status 500. That's interesting. We can see the URL that's causing it, and it's true. The bacon emoji seems to be failing for some reason. Now, if we want to try to get a sense of like, "Well, why is that one failing and something else is working," Let's see. Voting. Let's look at requests to the same requests going from the web service to the emoji service. So, this was the good edge. This is the one that we knew ... Oops. I typed something wrong. Find. Deploy. Bear with me. Emoji.

These are requests that we knew were working. Let's see. Sorry, live demos. What we'll notice now is we can compare the successful requests versus the bad ones. I don't expect anybody to recognize what's going on, but as a service owner, you would note that we've got two APIs, they're both called FindByShortcode, and one is a gRPC endpoint and one is an older, broken HTTP1 endpoint. Turned out that that team rolled out a new API. The voting service team didn't get the memo, they didn't upgrade their service, and they're failing.

What this is really demonstrating is like, you've got a bunch of services, they're calling each other. These tools allow you a way to very quickly drill in and see where the failures are happening. We've got these stats and you can really dig in and see what's going on, but that dashboard we were looking at earlier, you saw, these are very high level summary metrics. But you can click on any of these and it'll still take you to an automatically generated Grafana dashboard that allows you to browse all of your services, all of your deployments, by all of the same metrics.

You get all, again, all of this for free. We didn't instrument our demo app at all. This is a normal Kubernetes app, they're just talking to each other via HTTP and gRPC. We get all of this data for free because we're running this low Rust proxy right next to your app and it allows you to browse by all your namespaces and your deployments and you can look at things across pods and resource controllers and all of that.

I should add, these commands I'm running, they don't necessarily need to be on deployments. They can be on pods. Let me do a stat command on that. Any Kubernetes resource, if you're familiar with kubectl, allows you to do this kind of thing. So, if you wanted to do stats from a namespace to a pod, or a particular deployment to a replication controller over here, or all the replication controllers in a namespace, these commands allow you to do it. This stuff just hit master a day or two ago. A lot of these features are already in our last release, but we're doing another release tomorrow. Please take a crack at it and give us feedback.

Just as kind of a quick review of what we all did. We ran a Conduit install command that deployed Conduit its own namespace. We injected into our app, which didn't change ... We didn't have to change the app code at all. We used stat to get all the metrics, and then we used tap to see actual requests between all of our services. On top of that, you get this nice Grafana monitoring system. So, again, please send us feedback, send us issues, PRs are the best. Check out [Conduit.io](http://Conduit.io) and play with it. Thanks a lot. Cheers.
