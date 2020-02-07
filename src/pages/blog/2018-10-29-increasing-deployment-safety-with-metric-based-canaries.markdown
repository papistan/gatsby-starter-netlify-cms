---
author: andreaech
comments: false
date: 2018-10-29 16:34:15+00:00
layout: post
link: https://launchdarkly.com/blog/increasing-deployment-safety-with-metric-based-canaries/
slug: increasing-deployment-safety-with-metric-based-canaries
title: Increasing Deployment Safety with Metric Based Canaries
wordpress_id: 193484
categories:
- DevOps
tags:
- Armory
- automated canary deployment
- canary launch
- deployment
- kayenta
- Lookout
- Spinnaker
- test in production
---

In September, Brandon Leach, Sr Engineering Manager at Lookout, gave a talk at our Test in Production Meetup on Increasing Deployment Safety with Metric Based Canaries.


<blockquote>“You can configure a canary to watch any metric you want, like here we're watching system metrics and application-based metrics. You can see we're watching for response codes, other application metrics, and other system-level metrics like memory utilization and CPU.”</blockquote>


Watch Brandon’s talk below to learn more about how Lookout moved towards continuous deployment using canaries in production. If you’re interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/events/254964628/).

[embed]https://www.youtube.com/watch?v=Q-A0fumiXXU[/embed]

TRANSCRIPT:

Yeah, my name's Brandon. I manage Platform Engineering at Lookout. Today I'm gonna talk about Lookout's path to continuous delivery, and how we ended up moving towards continuous deployment using canaries in production.

First, a little bit about Lookout. We were founded with the mission of making the world more secure as the world becomes more connected by mobile devices. Our main focus is mobile end-point security. We have a personal and enterprise product on Android and iOS.

A little bit about our scale, just to set context. We have over 100 million devices registered. We acquire and analyze over 90,000 mobile applications daily through our security analysis pipeline, and we have about 120 services in production.

We recently rebuilt our service delivery tooling for continuous delivery. We had many disparate in-house built tools that had many problems and were a huge drag on engineering efficiency and service stability. I'm gonna go over some of this transition briefly to give you some context about how we got to where we are today.

About a year ago we kicked off an effort to build what we call SDP, our service delivery platform. We ended up consolidating all of our service deployment on Spinnaker. Spinnaker's a service delivery platform created by Netflix.

Here's a brief look at the impact that we had moving to Spinnaker and continuous delivery. Steps to deploy service to production went from about 25 steps to about one to three steps depending on the pipeline. Engineer time to deploy, that's the time actually spent on the engineer doing a deployment, went from about an hour to less than a minute. The automation time deploy, that's just the deploy end-to-end, went from about an hour to 31 minutes. The engineer's time to patch a service went from about five days to zero, and onboarding time, which is the time that it would take an engineer to get comfortable deploying a service, went from about three days to about 30 minutes.

We had already achieved continuous delivery, and that left us with the question of, "How do we achieve continuous deployment?"

Let's look briefly at the difference between continuous delivery and continuous deployment. Continuous delivery is a series of best practices designed to ensure code can be rapidly deployed and safely, delivering every change from production-like environment, and ensuring business applications and services function as expected through rigorous automated testing. That's what we achieved.

Then we look at continuous deployment. Continuous deployment's the next step of continuous delivery. That means that every change ... Every change that passes automatic tests is automatically deployed to production.

To get to continuous deployment we knew we needed to test in production. We began looking for ways to automate metric-based deployments in Spinnaker, so I this context what is a canary? A canary is a deployment process in which change is partially rolled out then evaluated against the current deployment, which is the baseline, to ensure that the new deployment is operating at least as good as the old deployment. This evaluation is done using key metrics that are chosen when the canary's configured.

We already knew that Netflix had already achieved this internally with Spinnaker, and we were kind of looking like, "Hey, we want to do this, too," so we turned to our partners at Armory. Armory, we had partnered with Armory to do continuous delivery. They had partnered with us and gotten us to that point, and so we came to them. We were like, "Look, we want to do canaries in Spinnaker."

Armory actually put together a hack-a-thon where they brought Lookout, us, as a customer, together. We spent three days together to try to solve this problem. We brought our services, our use cases, our requirements, and we kind of laid the foundation for an automated metric-based canary platform in Spinnaker.

The eventual outcome of this was Armory's Barometer Service, so Barometer is a service that integrates with Spinnaker that uses time series data from your monitoring platform, which is in our case Data Dog, to allow for the orchestration of metric-based canaries in Spinnaker.

Let's look at how this works in more detail. What you see here is a deployment pipeline for one of our services. You can see the production canary stage right before the production deployment. The canary stage starts by deploying two new server groups, a baseline and a canary. The baseline service group is deployed with the same AMI as the current release, and then you have another server group which is deployed with the release candidate. Both the baseline and the canary are configured to take production traffic, and the canaries emit metrics to DataDog using the tag specific to the canary deployment.

The Barometer service compares the metrics of the baseline and the canary. If the metrics fall outside a defined deviation, the canary fails. Once the canary stage is completed, both the canary and the baseline server groups are destroyed, and the pipeline continues either as a success or a failure.

You can configure a canary to watch any metric you want, like here we're watching system metrics and application-based metrics. You can see we're watching for response codes, other application metrics, and other system-level metrics like memory utilization and CPU.

Here's an example of a pipeline that passed, so it goes on to do the staging deployment, and here's one that failed. Notice the link on the bottom to the DataDog dashboard, which is actually really useful. If the deployment fails, it actually shows you a DataDog dashboard of the metrics that caused the failure.

We're still pretty early into our journey into continuous deployment, but here's some things we've learned so far. It takes time to dial in what metrics you want to use. We first started out, we were like, "Let's look at all of our RCA's, let's look at all of our incidents. Let's try to dive into the metrics that would have shown this incident coming before." It was funny. None of those things ended up being what we used, so it takes time to actually identify these things.

Too many metrics will cause too much noise and false failures. Another thing we tried, we're like, "Look. Let's throw 100 metrics in there. Let's watch that." That was actually interesting. We got a lot of interesting data points, but we ended up with too many false positives.

The last thing is it slows down your deployment, like in our case by hours, but it actually ends us saving time. Funny story here is an engineer came to me and he was like, "My god. This canary's taking so long. It's like three hours." My answer to him was, "Dude, stop watching it. The whole point. Go on and do something useful." He was like, "What?" He was so trained to sitting there, and watching the deployment, and waiting for it to succeed so he could see if it failed. I was like, "The service is actually doing that for you."

One more note. Barometer filled the need for us for a while, but Netflix and Google, who are both very active in the Spinnaker community, recently collaborated and shared their knowledge of how to do metric-based canary deployments, and built a platform in Spinnaker for automated canary analysis called Kayenta. Kayenta's awesome, and we're currently in the process of migrating all of our canary deployments from Barometer to Kayenta.

This is actually one of the great things about the Spinnaker community, is that you can leverage all the community contributions from great companies like Netflix and Google, and here's the release that came out not that long about about that.

I also want to mention Bhavik. Bhavik was actually the person that should have been here giving this talk. He actually did all the technical work. He's awesome, and yeah, he's just in Boston so he couldn't give the talk.
