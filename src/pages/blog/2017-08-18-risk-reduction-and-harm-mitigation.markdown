---
author: heidiw
comments: false
date: 2017-08-18 20:04:18+00:00
layout: post
link: https://launchdarkly.com/blog/risk-reduction-and-harm-mitigation/
slug: risk-reduction-and-harm-mitigation
title: Risk Reduction and Harm Mitigation
wordpress_id: 1784
categories:
- DevOps
- Feature Management
tags:
- DevOps
- feature flags
- harm
- infrastructure
- product
- risk
- SDLC
---

_Risk Reduction_ is trying to make sure bad things happen as rarely as possible. It is anti-lock brakes, vaccinations, clothing irons that turn off by themselves, and all sorts of things that we think of as safety modifications in our life. We are trying to build lives where bad things happen less often.

_Harm Mitigation_ is what we do to make sure that when bad things _do_ happen, they are less catastrophic. Fire sprinklers in buildings, seat belts, and needle exchanges are all about making the consequences of something bad less terrible.

What does that mean for a DevOps world where our risks and harms are very different? [Charity Majors](https://twitter.com/mipsytipsy) says we shouldn't split the world into developers and operations, but into product and infrastructure—and I think that's a useful way to think about risk too.

Product risk is problems that users experience. We can usually predict and mitigate the danger by testing and being aware of common failings. For example, we can expect and plan for users that may be on a flaky connection, or that they may try to exit a page without saving information. We can work around these problems because we know they're out there. But our deployments are not something they should see until we're ready for prime time. For this kind of risk, we use feature flags to control what content is delivered.

Infrastructure risk is more about the inherent fragility of delivering software. CDNs, fiber, servers, switches, towers...the whole system of getting data to people has failure zones. When we are trying to reduce infrastructure risk, we assume that latency is ever-present, networks are intermittent, and we won't always be able to count on everything working right the first time. We try to build in robust and flexible ways than can route around failures. This is the place we might use feature flags to control failovers or to create circuit breakers to prevent flooding a fragile sector.

Product harm reduction is about making sure that users can have a positive experience, even if something happens that makes it less than ideal. We want to preserve their blog drafts, keep them from committing errors, only show them things they are allowed to change, and above all, avoid giving them a blank page. Something has gone wrong in the trip to the user, but they shouldn't have to suffer for it.

Infrastructure harm reduction is the ability to pull back breaking fixes, shunt users away from vulnerabilities, and respond near-immediately to things that have gone very wrong. Harm reduction at this level is the kind of action a pager-responder can take to get things back on track before doing more intensive repairs and investigations in the morning.

In my first week, I spent a lot of time thinking about how to summarize our product for a variety of audiences. "Feature flags as a service" is short and pithy, but only works if you can bring your own definition of "feature flag" and a business understanding of why you would use them. What about "Feature flags allow you to make changes in near real-time instead of waiting for a deployment, and LaunchDarkly helps you manage and track flags across an organization"? 

Well, that works, but it still doesn't get to the core of why an organization would want to use feature flags. What I've come up with so far is this:


<blockquote>Feature flags segment the risk of creating a product into manageable parts.</blockquote>


Creating and deploying software is risky. We can accidentally build in errors, we can deliver it badly, or to the wrong people, and it can interact in unfortunate ways with existing software or hardware. As organizations, we want to do our best to do no harm and provide benefit. Using feature flags lets us wrap our features in decision points that we can then use to make life easier for our users.

Here are some types of risks that are reduced by using feature flags:



 	
  * Server falls over from too much traffic

 	
  * Canary launch is not well-tracked, problems are missed

 	
  * Old features and workarounds are invisible and get left in place

 	
  * Feature with vulnerable content is deployed

 	
  * API endpoints are exposed to unauthorized users


Managing your feature flags is a post for another day—today I ask that you take a few minutes and think about how you can reduce risk and minimize harm in your organization, your project, or your code. How can you make things robust enough to resist failure, instrumented sufficiently to identify a failure spot, and flexible enough to reduce harmful consequences on the fly?
