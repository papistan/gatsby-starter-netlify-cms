---
author: Guest
comments: false
date: 2018-05-01 20:38:34+00:00
layout: post
link: https://launchdarkly.com/blog/giving-sales-control-of-feature-flags/
slug: giving-sales-control-of-feature-flags
title: Giving Sales Control of Feature Flags
wordpress_id: 2510
categories:
- Feature Management
tags:
- beta testing
- DevOps
- feature management
- feature release
- sales
- test in production
---

_Guest post by Ian Dugas, Sales Manager at IOpipe._

I’ve worked for companies ranging from startups to one traded on the public market. In every one of those, I was largely—if not entirely—abstracted away from the product development and engineering teams. Now that I am at seed stage startup called [IOpipe](https://www.iopipe.com/), where I was the first sales hire, I engage directly with the product team. That’s right, I’m a salesperson.

So why am I, a salesperson, writing about a developer tool like LaunchDarkly? Well like most people (hopefully) who work in technology, I’m a fan of discovering efficiencies and applying them to processes and workflows. LaunchDarkly has uncovered new efficiencies for IOpipe and how we engage with our customers. The value here transcends product development.

IOpipe is obsessively focused on iterating the product at breakneck speeds. In other words, being efficient—as a company—is mission-critical for our success. It takes extreme focus for a small team to iterate as quickly as we’ve been able to and continue to.

I’ve already learned many things working in this paradigm. Chief among them are two closely related lessons:



 	
  1. Disrupting a developer mid-sprint breaks their flow, which can inhibit their ability to maintain extreme focus and ultimately execute with the right cadence.

 	
  2. Although Sales and Product are intimately aligned from a strategic perspective, Sales needs to be as operationally autonomous as possible to minimize developer disruption.


IOpipe provides powerful debugging, monitoring, and observability tools for enterprises. “Enterprises” is the operative word in the preceding sentence as our touches with prospects and customers are always deliberate and often strategic. For that reason, the release of beta and test features are not done en masse, and are instead done in a controlled and manual fashion. The problem, however, was that we had to find a way to open test features for specific users without Sales disrupting product sprints.

That’s when my developer colleagues introduced me to LaunchDarkly and feature flags—something we’ve been using on the Product side of the business for quite a while. With LaunchDarkly, once our company determines a feature or capability is ready for user testing, Sales can go in and directly unlock for a specific user.

So, with LaunchDarkly, our process went from:


**1) Sales identifies test user  →  2) Sales requests feature from Dev  →  3) Dev unlocks feature  →  4) Dev notifies Sales**


To:


**1) Sales identifies test user  →  2) Sales unlocks feature for test user**


LaunchDarkly essentially removes two steps from our process, and completely eliminates the need for developers to break flow in order to perform a simple but very important task. i.e. _Exactly what we were looking for._ It also took the time to implement a feature for a customer from 45 minutes plus a developer interruption, to ~1 minute.

Let me give you a real example… IOpipe recently GA’d support for Java. Prior to releasing this capability, we performed two rounds of tests (alpha, beta) with actual enterprise users. At the time, only a subset of our customers and prospects had requested Java support. They were of the larger variety. Within that subset, we could only have a few strategic users test for testing to be effective. I was responsible for engaging the users and qualifying strategic prospects and customers willing to partner with us for Java testing. With LaunchDarkly I was able to unlock the feature as I spoke with the target users. Without LaunchDarkly, unlocking Java would’ve become a “let me get back to you” type of exercise, which no one enjoys, and is also…well, inefficient.

To recap, since my sales team has begun using LaunchDarkly, we’ve been able to minimize developer distractions, so they can preserve focus, and we’ve been able to independently roll out beta features. This has allowed us to quickly deliver functionality without being a burden to engineering, and participate more actively in the feedback process with developers and product managers.


*  *  *


[_Ian Dugas_](http://www.linkedin.com/in/iandugas)_ has been in tech for the last 10 years in roles spanning Sales, Professional Services, Customer Success, Business Development, and Operations. He's sold, and delivered, cloud and on-premise solutions to companies and government entities big and small. He has an affinity for bulldogs, and can be found on Twitter _[_here_](http://iandugas/)_._
