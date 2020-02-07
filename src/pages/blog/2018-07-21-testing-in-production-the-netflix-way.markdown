---
author: andreaech
comments: false
date: 2018-07-21 00:12:18+00:00
layout: post
link: https://launchdarkly.com/blog/testing-in-production-the-netflix-way/
slug: testing-in-production-the-netflix-way
title: Testing in Production the Netflix Way
wordpress_id: 193224
categories:
- DevOps
tags:
- chaos automation platform
- chaos engineering
- Netflix
- Nora Jones
- test in production
---

In June we focused our Test in Production Meetup around chaos engineering. Nora Jones, Senior Software Engineer at Netflix, kicked off the evening with a talk about how Netflix tests in production.




"Chaos engineering...is the discipline of experimenting on production to find vulnerabilities in the system before they render it unusable for your customers. We do this at Netflix through a tool that we call ChAP...[It] can catch vulnerabilities, and allows users to inject failures into services and prod that validate their assumptions about those services before they become full-blown outages."




Watch her talk (or read the transcript) below to learn more about how her team helps engineers across Netflix to safely test in production and proactively catch vulnerabilities within their systems. If you're interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/).

[embed]https://www.youtube.com/watch?v=3WRVgC8SiGc[/embed]

TRANSCRIPT

I'm super excited to be here today. Netflix is a huge fan of testing in production. We do it through chaos engineering, and we've recently renamed our team to Resilience Engineering because while we go chaos engineering still, chaos engineering is one means to an end to get you to that overall resilience story. I'm going to talk a little bit about that today.

Our goal as a team is to improve availability by proactively finding vulnerabilities in services, and we do that by experimenting on the production system. Our team has an active belief that is a certain class of vulnerabilities and issues that you can only find with live production traffic. I'm going to talk to you a little bit about how we do that today.

First and foremost, our focuses with testing in production are safety and monitoring. You really can't have great testing and production unless you have these things in place. And testing in production can seem really scary, and if it does seem scary in your company, you should listen to that voice and figure out why it seems scary. It might be because you don't have a good safety story. It might be because you don't have a good observability story. We really focus on these two worlds within Netflix and within our tools.

To define chaos engineering just in a simple sentence, it's the discipline of experimenting on production to find vulnerabilities in the system before they render it unusable for your customers. We do this at Netflix through a tool that we call ChAP, which stands for Chaos Automation Platform. ChAP can catch vulnerabilities, and it allows users to inject failures into services and prod that validate their assumptions about those services before they become full-blown outages.

I'm going to take you through how it works at a high level. This is a hypothetical set of microservice dependencies. There's a proxy. It sends request to service A, which fans out to service B, C, and D, and then there's also a persistence layer. Service D talks to Cassandra, and then service B talks to a cache.

I went ahead and condensed this, because it's about to get busy in a second. We want to see if service D is resilient to the failure of a cache. The user goes into the ChAP interface, and they select service D as a service that will observe the failures in a cache as a service that fails. ChAP will actually go ahead and clone service B into two replicas. We refer to them as the control in the experiment clusters, and it kind of works like AB testing or like a sticky canary. These are much smaller in size than service B. We only route a very, very small percentage of customers into these clusters because obviously we want to contain the blast radius. We calculate that percentage based on the current number of users currently streaming, currently using the service.

It will then instruct our failure injection testing to tag these requests that match our criteria. It does this by adding information to the header of that request. It creates two sets of tags. One set will have instructions to both fail and be routed to the canary, and then the other will have instructions just to be routed to the control.

When the RPC client and service A sees in the instructions that it needs to route a request, it will actually send them to the control or the experiment cluster. And then once failure injection testing in the RPC layer of the experiment cluster sees that the request has been tagged for failure, it will then return the failed response. As before, the experiment cluster will see that as a failed response from the cache it will execute the code to then handle a failure. We're doing this with the assumption that this is resilient to failure, right? But what we see sometimes is that that's not always the case. From the point of view of service A, it looks like everything is actually behaving normally.

How do we monitor this while these chaos experiments are running because it has the potential to go very poorly. When Netflix started our chaos engineering story, we didn't have good gates in place. We would run a failure experiment, cross our fingers, and then all sit in a war room watching the grass and making sure that nothing actually went incorrectly. Now, we have much more of a safety focus.

We look at a lot of our key business metrics at Netflix. One of our key business metrics is what we SPS, or stream starts per second. If you think about what is the most important thing to the business of Netflix, it's that a customer can watch Friends or The Office or whatever they want to watch whenever they want to watch it.

What you see in these graphs here are an actual experiment, and it shows the SPS difference between the experiment and control during a chaos experiment. You can see here that these are deviating a lot from each other, which shouldn't be the case because there's the same percentage of traffic routed to both clusters.

Because of that, the experiment will use automated canary analysis and see wow, these deviated really far from each other. I'm going to short the experiment. I'm going to stop failing these requests for the customer, and they'll have a normal experience. From a customer perspective, it's more seen as a blip when something like this happens.

We have a bunch of other protections in place as well. We limit the amount of traffic that's impacted in each region so we're not just only doing experiments in U.S. West 2. We're doing them all over the place and limiting the amount of experiments that can run in a region at a time. We're only running during business hours so we're not paging engineers and waking them up if something goes wrong. If a test fails, it can actually not be automatically run again or picked up by anyone until someone actually explicitly manually resolves it and acknowledges hey, I know this failed, but I fixed whatever needed to be fixed.

We also have the ability to apply custom fast properties to clusters, which is helpful if your service is sharded, which a lot of services are at Netflix. Additionally, and I don't have this as a bullet point, we also have the ability to fail based on device. If we're assuming that Apple or a certain type of television is having a bunch of issues, we can limit it to that device specifically and see if that issue is widespread across that device.

ChAP has found a lot of vulnerabilities. Here's some examples. This is one of my favorite ones. The user says, "We ran a ChAP experiment which verifies the service's fallback path works, which was crucial for our availability, and it successfully caught an issue in the fallback path and the issue was resolved before it resulted in availability incident." This is a really interesting one, because this fallback path wasn't getting executed a lot, so the user didn't actually know if it was working properly, and we were able to simulate. We were able to actually make it fail and see if it went to the fallback path and the fallback path worked properly. In this case, the user thought their service was noncritical or tier two or whatever you label it as, but really it actually was a critical service.

Here's another example. We ran an experiment to reproduce a signup flow fallback issue that happened with certain deploys intermittently at night. Something kind of weird was happening with their service. We were able to reproduce the issue by injecting 500 milliseconds of latency. By doing the experiment, we were able to find the issues in the log file that was uploaded to the Big Data Portal. This helped build context into why Signup fallback experiences served during certain pushes. That fallback experience kept happening, but these users didn't know why. And they actually ran a ChAP experiment to see when it was happening and to see why it was happening.

To set up ChAP experiments, there's a lot of things the user needs to go through. They need to figure out what injection points they can use. Our teams had to decide if they wanted failure or latency. These are all of our injection points. You can fail Cassandra, Hystrix which is our fallback layer, RPC Service, RPC Client, S3, SQS, or our cache, or they can add latency. Or you can add both. And you can actually come up with combos of different experiments.

What would happen is we would meet with service teams and we'd sit in a room together, and we'd try to come up with a good experiment. It would take a really long time. When we were setting up the experiment too you have to decide your ACA configurations, or your automatic canary configurations.

We had some canned ACAs set up. We had a ChAP SPS one. We had one that looked at system metrics. We had one that looked at RPS successes and failures. We had one that looked at whether our service was actually working properly and injecting failures, and we learned that experiment creation can be really, really time consuming, and it was. Not a lot of experiments were getting created. It was hard for a human to actually hold all the things in their head that made a good experiment. We decided to automate some of this from ChAP. We were looking at things like, who was calling who? We were looking at timeout files. We were looking at retries, and we figured out that all of that information was in a lot of different places. We decided to aggregate it.

We zoomed into ChAP, and we got cute and we gave it a monocle, and the Monocle provides crucial optics on services. This is what Monocle looks like. It has the ability for someone to look up their app and their cluster and they can see all this information in one place. Each row represents a dependency, and this dependency is what feeds into chaos experiments.

We were using this to come up with experiments, but what we didn't realize was this information was actually useful to just have in one place as well, so that was an interesting side effect. Users can come here and actually see if there are anti-patterns associated with their service like if they had a dependency that was not supposed to be critical but didn't have a fallback. Obviously it was critical now. People could see timeout discrepancies. People could see retry discrepancies. We use this information to score a certain type of experiment's criticality and fed that into an algorithm that determined prioritization.

Each row represents a dependency, and they can actually expand the rows. Here's an interesting example. That blue line represents someone's timeout, and the purple line represents how much time it was actually taking most of the time. You can see it is very, very far away from the timeout. But a lot of this information wasn't readily accessible. What would happen if we did a chaos experiment just under the timeout. You know? Is that going to pass? It never executes that high. It's an interesting question. We're trying to provide this level of detail to users before these chaos experiments get run to give them the opportunity to say, "Wait, this doesn't look right."

I'm going to play a little game. I know a lot of you don't have contacts on the Netflix ecosystem, but there's a vulnerability in this service, and I want to see if you can spot it. Take a second to look at it. To give you some context, sample remote Hystrix command wraps both the sample-rest-client and the sample-rest-client.GET. The Hystrix timeout is set to 500 milliseconds. Sample-rest-client.GET has a timeout of 200 with one retry, and this is fine because it's a total of 400 milliseconds with exponential backoff, which is within that Hystrix limit. The sample retry client has timeouts of 100 and 600 with one retry.

In this case, the retry might not have a chance to complete given the surrounding Hystrix wrapper timeout, which means that Hystrix abandons the request before the RPC has a chance to return. That's where the vulnerability lies. We're actually providing this information to users, and what's interesting is a lot of this logic lies in different places. They weren't able to have this level of insight before. Those were okay, and this is where the vulnerability lies.

Why did this happen? It's easy for a team to go in and look at their conflict file and just change this surround, right? But we want to figure out why this happened. We can change the timeout, but who's to say this won't happen again? We also help with figuring out why these things happen. Engineers weren't making bad choices, it was just a lot of things to update at once. That's something to be learned as well.

We use Monocle for automatic experiment creation as well. A user creates an experiment based on infactorial types of inputs. We take all these things, and we're working to automate the create of running these experiments so that users don't have to. We're automatically creating and prioritizing latency failure and latency-causing failure RPC and Hystrix experiments. ACA configs are added by default. The deviation configurations. We have SPC, system metrics, request statistics, and experiments are automatically run as well. Prioritizing experiments are also created. I'll go through the algorithm for that a high level. We use an RPS stats range bucket. We use a number of retries and the number of Hystrix commands associated with it. These are all weighted appropriately.

Something else we've also taken into account is the number of commands without fallbacks and any curated impacts that a customers adds to their dependency. Curated impacts is this has a known impact on login. This has a known impact on signup. This has a known impact on SPS. And we actually weigh these negatively and don't run the experiments if the score is negative. Test cases are then ranked and run according to their criticality score. The higher the score, the sooner it's run, the more often it's run.

Ironically enough, Monocle has given us some feedback that allows us to run less experiments in production. Right? It's ended up as a feedback loop because we've been running so many experiments we've seen patterns in between them where we can look at certain configuration files now and see certain anti-patterns and know that that's actually going to cause a failure, whereas we didn't know that information before.

It has led to new safety. Before if an experiment failed, it needed to be marked as resolved. Currently, it needs to be marked as resolved before it can run again. But now we can explicitly add curated impacts to a dependency. A user can go into their Monocle and actually add this has a known login impact. This has a known SPC impact. And we're working on a feedback loop to where it fails, it will add a curated impact as well. The runner will not run experiments with known impacts.

In summary, ChAP's Monocle is crucial optics in one place, automatically generated experiments, automatically prioritized experiments, and finding vulnerabilities before they become full-blown outages. If I can leave you with one tangent, one side piece of advice, it's to remember why you're doing chaos experiments and why you're testing in production. It's to understand how customers are using your service and not lose sight of them. You want them to have the best experience possible. So, monitoring and safety are of utmost importance in these situations. Like at Netflix, not being able to stream a video. Thank you. Appreciate it.
