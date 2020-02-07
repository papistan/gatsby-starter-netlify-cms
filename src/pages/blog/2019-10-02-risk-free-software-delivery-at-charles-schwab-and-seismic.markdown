---
author: mattdel
comments: false
date: 2019-10-02 16:52:45+00:00
layout: post
link: https://launchdarkly.com/blog/risk-free-software-delivery-at-charles-schwab-and-seismic/
slug: risk-free-software-delivery-at-charles-schwab-and-seismic
title: Risk-Free Software Delivery at Charles Schwab and Seismic
wordpress_id: 194331
categories:
- Feature Management
tags:
- continuous delivery
- custom targeting rules
- feature management
- progressive delivery
- user targeting
---

## Recapping LaunchDarkly’s Lunch & Learn Chicago panel discussion on feature management


Feature management, a new category of software anchored in the use of feature flags, is transforming the way top companies deliver software. That much came to light in a recent panel discussion we hosted between LaunchDarkly CTO and Co-Founder John Kodumal and LaunchDarkly customers Bala Mukund, Director of Technology at Charles Schwab, and Brian Issleb, Senior Engineering Manager at Seismic.

Among other things, the panelists shared about how they’re shipping software faster and with less risk thanks to LaunchDarkly’s [feature management platform](https://launchdarkly.com/product/). They touched on themes such as:



 	
  * **Targeted rollouts (a key part of [Progressive Delivery](https://launchdarkly.com/blog/the-daughter-mother-in-law-challenge-a-case-for-progressive-delivery/)).** Seismic, for example, uses LaunchDarkly to customize the way in which it releases new features. Those hungry for the latest and greatest software see new functionality right away. But more conservative customers can adopt new features at a slower pace, allowing their users and processes more time to adapt.

 	
  * **Managing feature flags at scale.** [Feature flags](https://launchdarkly.com/features/feature-flags/) are a powerful tool that accelerates code deployments and reduces risk. But as flags proliferate, it becomes an ordeal to manage them. A feature management platform helps you control all your flags in a simple, scalable manner.

 	
  * **Rapid, "risk-free" delivery.** The ability to quickly shut off a feature if it's causing problems in production – and do so on a broad scale – has been a boon to Charles Schwab and Seismic. It has dramatically cut down on risk and enabled teams to achieve continuous integration and continuous delivery.


Here are more highlights from the event.


### Charles Schwab: Turning the _tanker_ around


_Bala Mukund, Director of Technology at Charles Schwab_

Bala discussed Schwab’s historical approach to software deployment, his plans for improving that process, and the pivotal role feature management plays in driving those improvements.

“Schwab is a large organization, and we are highly regulated. Every change has to go through many levels before it actually hits the client... Having said that, two years ago, we embarked on a digital transformation process in digital advice...We used to release once every six weeks, and it was a big party. And then, you start the process again. But over the course of the past two years, we've reduced that considerably to actually once a month. Now there are no parties. We don't have a manual component of quality. We've automated quality. And as a part of that entire process, we also built our whole feature flagging system.

...Our goal is to release every day if it's possible. Change management is a tough one for us because of the regulations that we go through, but, at the same time, reducing the risk of deployment allows change management to fuel the content of our recent products so we can turn features on and off and things like that. But before we get there, as John explained, we have to go through this rigorous process of documentation and getting all this approved.

It takes a lot. We are a big tanker. Turning that around is a lot of effort, but over the course of two years, we've made progress. We use different technologies for our automation, and LaunchDarkly is going to play a lead part to release software in a much more risk-free fashion. It's not about the quantity of releases, it's the quality and the ability to move back to a stable state from where we were – this is the metric that we track in each case.”


### Seismic: Tailoring feature rollouts to each customer


_Brian Issleb, Senior Engineering Manager at Seismic_

Brian, responding to the question of _how do you control the rate of change that goes out to your customers?_, explained:

“Seismic builds enterprise software for large companies. We have a lot of Fortune 100 companies, including those in the financial services industry. Those companies are culturally very averse to risk. As an engineer or software developer, you typically have this model in your head of, _everybody wants the latest cool stuff_. And that's what we as engineers and project managers get excited about: building new stuff and releasing it. But a lot of customers want the opposite. If you could just freeze it [the software application] and put it on a CD and hand it to them, that's really what they want.

We actually use feature flagging for coordinating releases to our tenants. Some tenants really don’t want a new feature. Maybe they want it eventually, but they need to do some internal rollouts first. They need to update their documentation, they need to educate their partners that work with them on this change. And so we can use feature flags to release features on a tenant-by-tenant basis. We can roll it out to this group of tenants while holding back the features from another group of tenants. So that can get sticky, and we're going to be talking a little bit later about some of the downsides of that; you don't want it [the new features wrapped in a feature flag] sitting on there for two years. But the ability to coordinate those releases based on not just our needs but the needs of our customers is one of the key features that we love.”

To learn more about feature management, check out a recording of our recent [“Intro to LaunchDarkly” webinar](https://launchdarkly.com/webinars/intro-to-launchdarkly).
