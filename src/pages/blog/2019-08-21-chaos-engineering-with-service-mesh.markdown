---
author: andreaech
comments: false
date: 2019-08-21 16:05:56+00:00
layout: post
link: https://launchdarkly.com/blog/chaos-engineering-with-service-mesh/
slug: chaos-engineering-with-service-mesh
title: Chaos Engineering with Service Mesh
wordpress_id: 194219
categories:
- DevOps
---

At our July session of Test in Production, we invited Christian Posta, Global Field CTO of Solo.io, to give a talk about chaos engineering and service meshes.


<blockquote>"Now the idea at least of Chaos injection and Chaos analysis is that we know that with our distributed systems there are going to be things we can't find deterministically and in lower environment testing. With Chaos injection we say we've built our system to be resilient in for these cases. Let's go prove it, let's inject the cases that would trigger this supposedly resiliency and observe that it really does happen." - Christian Posta, Global Field CTO of [Solo.io](http://Solo.io)</blockquote>


Watch to learn more about why his team built a chaos injection tool on a service mesh. If you’re interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/events/254964628/).

[embed]https://youtu.be/bfBVpYL0EEA[/embed]

TRANSCRIPT:

Christian: Thank you LaunchDarkly and Heavybit. I am going to be talking about chaos experimentation. A lot of my background is in helping enterprises actually make the move to more modern architectures, modern infrastructure, and actually getting value out of it, not just replacing the current crap that they have with the new stuff, expecting different results. Right? Because that doesn't usually turn out very well.

I spent a long time at Red Hat, where I focus deeply on containers and building application architectures on top of containers. I've spent a lot of time in open source communities working on messaging and integration and all these different types of technologies and more recently I've been working on something called service mesh more specifically Istio. How many people have heard of Istio? How many people are using containers or a service mesh? Just some kind of, okay, awesome. Well let's get going.

As we go to award these types of application architectures, while we're breaking things up into loosely coupled services and we're expecting them to interact with each other and deliver some kind of business result, things get a lot more complicated. Right? We're doing this for a reason, or at least that's what we tell ourselves when we see other people do it, we tell ourselves that's it's for the right reason. We want to go faster.

When our application architecture becomes a bottleneck, then we want to adopt architectures that allow us to spin up new functionality outside of that bottleneck or take out some of those pieces from outside of that bottleneck and build them so that they can go independently and you can rev and add new features more quickly. But when you do that, like I said, "Things become a lot more complicated."

When you have a monolith and you've deployed that and people are using it, it's bringing in lots of revenue and something goes wrong. You know where to look. It's the one thing or the one thing plus a database, right? When you break things out into a services architecture, now you have multiple services potentially written in different languages, potentially using different frameworks, maybe different data back-ends talking over unreliable networks.

When we go to cloud infrastructure, things are more ephemeral and so on. Now when we get into an environment like this where there's potentially tens, hundreds, maybe even thousands of these services interacting with each other and things start to go wrong, we end up not being able to go to our existing tooling because it doesn't fit that same model. It doesn't fit that application architecture model. So the current tools that at least I see at our enterprise customers are not sufficient.

Either they are built with the premise that the architecture is static - and what I mean by that is you have a couple of VMs there got a long lift IP addresses, maybe static IP addresses, and you just... You treat them as you probably heard the pets and cuddle analogy. You treat them as pets and these things aren't going away and you build your architecture with the assumption that none of this stuff is going to fail, right?

But then when it does, then you're not prepared. Some of the tooling for doing debugging and verification of your system are very language specific and have to be embedded inside the application. So not only does this require you to bring on all the libraries and transitive dependencies and all that stuff into your application and manage that as they rev their versions and so on, but you actually have to go in and instrument your code, which is not a bad thing. You got it, you've got to do that. But you do it in some cases to the detriment of being able to understand what the application is doing.

So at Solo we are building a open source tools to help solve this problem. In a couple more slides I'll talk a little bit bit more about how, but some of these tools are premised on the idea of having a set of interceptors or proxies deployed along with your application that provide the points of control that enable these types of tools to be successful.

So the first one, the one we'll look at today is called Gloo shot is a chaos experimentation engine for a distributed distributed application architecture. A second one is called loop, LOOP and that is a record and replay framework. So as traffic is flowing through your system, when things start to fail, we can record the requests, we can record the requests across multiple hops in your request path and understand exactly what order they happened and then take them and replay them in a lower environment.

Then once we replay them, we can attach a distributed debugger. So that's what squash is, open source, multi-language distributed debugger. So that means if you can run in containers or Kubernetes and it could be a Node.js, it could be Java, it could be Go, you just attached squash up to your services and bring and connect to up your IDE to the different services and you can get step by step debugging across multiple services and even across multiple languages.

So when we talk about chaos engineering, especially when I talk with our enterprise customers, the term chaos is kind of scary. Just kind of curious how many people are doing some sort of chaos experimentation with their production systems today. Just kind of get an idea of where we are. Okay.

Now the idea at least of Chaos injection and Chaos analysis is that we know that with our distributed systems there are going to be things we can't find deterministically and in lower environment testing. Just because the system is very complex, the interactions are not deterministic and little gremlins are hiding in the shadows that we need to try to fader out. With Chaos injection we say we've built our system to be resilient in for these cases. Let's go prove it, let's inject the cases that would trigger this supposedly resiliency and observe that it really does happen.

We do this in a controlled way and in a way that we could define the experiment and be very explicit about what we're trying to prove upfront. Then as we've run it, we can observe that it does actually validate what we think of is supposed to do or that we roll back because we observed that it's disturbing the steady state of the system too much.

So we build this and the open source project that I'll talk about today. We're building on top of the concept of a service mesh. I say concept of the service mesh, because at Solo we want to build value on top of service mesh. We think service mesh is supposed to be boring. You shouldn't have to worry, it should be there, but you shouldn't have to be too fanatical about it. The real value is on driving the capabilities of a service mesh.

Things like traffic control, things like policy enforcement, things like fault injection, driving those capabilities with higher level services. For example, a chaos experimentation engine or a Canary analysis engine or a debugging engine. That's where we start to deliver value. That's where we start to be able to bring our applications out to production faster and safely.

So we chose service mesh because it is inherently built for this type of application architecture. So it solves some of these, some of the drawbacks of our existing tooling. It is language agnostic. So with the service mesh, when we have the operational control proxies, we're a big fan of Envoy proxy at Solo. When we have these proxies deployed alongside our applications, we can do fault injection, we can do traffic control, we can do timeouts, circuit breaking, retry that kind of thing without having to worry about what language is being used inside the application itself.

So it runs out of process from the application. So it's language agnostic. You don't have to import libraries and frameworks and transitive dependencies and extra code into your applications. The project that I'll be looking at tonight is called Gloo shot. So Glooshot.Solo.Io is where you can get a documentation. I'll show that in a second. We are looking at a couple of pieces of functionality from the service mesh that we're going to orchestrate to achieve this capability.

So again, I'll say that the service mesh exposes a handful of very powerful capabilities as APIs. And the stuff that's valuable isn't the service mesh itself. It's how we build tooling on top of it to drive those APIs. And in the case of Gloo shot, we're going to drive the APIs in a service mesh that can do things like fault injection, things like latency, inject latency or inject bad returned messages or failed requests.

We're also going to look at the telemetry that the service mesh can give us. Because on the request path are going through the mesh and going through these proxies, we can capture very detailed information about how many requests we're seeing and what the latency is and how many failures we're seeing and so on.

So with a project specifically Gloo shot, we're going to watch the telemetry generated by the service mesh as requests are going through the system, and we're going to inject the the failures that we want to see. Then lastly, we want to define exactly what our boundary is for or our thresholds are for the experiment that we want to run. So if we say this service is supposed to be resilient, when it's dependency service fails, then let's go prove that.

Let's specify that we have a minimum latency we want to see and we don't want to see throughput drop below a certain number. Then if we run this experiment and it does do any of those gets out of out of those boundaries, then let's roll the experiment back. So let's take a look at a quick demo. All right?

The first thing that we're going to do is we're going to look at what an experiment definition, how you actually realize a definition for this experiment. So the first thing we're going to do is we're going to specify what would constitute this experiment going wrong. So we put this out there. Specifically, what we're going to do is we're going to fail requests to the rating service. Let me give you a visual diagram of exactly what this architecture is.

Requests are coming into a initial landing page. And then that's calling a review service, which in turn is calling a reading service. With our fault injection experiment, what we're going to do is we're going to take down or effectively take down the reading service, but we shouldn't see the reviews service completely fail. We should see it fall back to it's alternative behavior.

So if we come to our book info page here and refresh, we can see everything is looking good right here. We're going to take this definition which says if we hit... I forgot this was 10 failed requests in a minute, then or more than 10 failed requests in a minute, then we should trigger a rollback or stop the experiment after aborting these requests. So let's actually create that.

And now we'll give it some low. Let's just do it from the browser. If we refresh, oh, that is actually giving us a error from the review service. So reviews is calling ratings, ratings we took down, but reviews is now throwing failures. Oh, so we actually, that went pretty fast. If we come over here and take a look at what Gloo shot did, we can see that it's failed. The experiment is actually faster than 10 and one minute. It failed the experiment and rolled it back to the correctly behaving behavior that we wanted from the application. Thank you.
