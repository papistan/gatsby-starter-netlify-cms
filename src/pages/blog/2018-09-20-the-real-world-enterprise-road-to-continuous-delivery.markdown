---
author: Guest
comments: false
date: 2018-09-20 16:35:38+00:00
layout: post
link: https://launchdarkly.com/blog/the-real-world-enterprise-road-to-continuous-delivery/
slug: the-real-world-enterprise-road-to-continuous-delivery
title: The Real World, Enterprise Road to Continuous Delivery
wordpress_id: 193374
categories:
- DevOps
tags:
- CI/CD
- DevOps
- feature management
---

_Guest post by [Jason Bloomberg](https://intellyx.com/author/jbloomberg/), of [Intellyx LLC](https://intellyx.com/)._

For many large enterprises, the promise of DevOps seems like pie-in-the-sky wishful thinking. Small, collaborative teams iterating quickly on modular bits of code, leveraging the latest in automation tooling, deploying to production perhaps several times a day?

At a web-scale company or some cloud-native startup, perhaps, but not here.

For such skeptics, the enterprise context is diametrically opposite to the DevOps ideal: an intensive waterfall methodology, or perhaps the regimented Agile, which is only a little better. Massive legacy assets and the technical debt to match. And a rigidly siloed organizational structure that draws more on executive empire-building than a concern with customer needs.

The good news: many large companies – even some that have historically been resistant to change – have jumped on the DevOps bandwagon, with a good measure of success. True, the road to continuous integration and continuous delivery (CI/CD), DevOps’ core processes, can be a long one. Here are how some organizations made the journey.

**Watchful Bank Before its Transformation**

Watchful Bank is a fictitious company whose journey is the combination of true stories. This midsize US-based bank had grown via numerous acquisitions over the years, bringing together a complex mishmash of legacy assets and processes, and siloed organizations that had grown around them.

Given the dynamic competitive environment, executive management decided to undergo a broad, corporate digital transformation, including a ‘digital rejuvenation’ of its consumer bank – while continuing the steady pace of acquisition.

The first step in this rejuvenation for the software team: _recognizing it had a problem_. Its codebase struggled under massive technical debt from years of disparate projects at most of Watchful’s acquisitions.

This technical debt impacted its technical architecture, or lack thereof. For example, the mere act of logging into the online banking app required over 200 network hops across two data centers in order to access the account page.

Unplanned outages were unacceptably common, and all mitigation efforts were reactive, fire-fighting exercises that never addressed the underlying issues.

**The Road to CD for Watchful Bank**

The Watchful team initially focused on understanding its software value chain – how it currently handled its software pipeline and where the pipeline would have to change. It decided to move from a difficult, ‘big bang’ quarterly release cycle to cycles in hours or days depending upon the task at hand.

To achieve this acceleration, Watchful focused on three areas: containers, automated testing, and CD. Before changing its use of tooling, however, it needed to rework its organizational structure.

Watchful reorganized its dev/security/ops silos, instead moving to a cross-functional team structure consisting of small, autonomous teams. Each team had a technical lead, two developers, a project manager, and a designer.

Technical leads were truly technical as well as product-focused, and they facilitated interactions with other teams to keep the overall product roadmap on track. Furthermore, each team was ‘full stack,’ that is, equally conversant with front-end and back-end development, in order to reduce dependencies on other teams or individuals.

In fact, each team’s autonomy was critically important, as it lowered communication overhead (i.e., fewer meetings). Each team owned a functional part of the product, and management chartered each team to make meaningful progress for customers. And if something broke in production – the team owned the fix.

Watchful also implemented a CD pipeline for automating the entire software process. This process included numerous feedback loops, including usability testing, customer interactions, usage tracking, as well as interactions with other stakeholders within the broader Watchful organization.

In other words, automation sped up the process, but human interaction – especially with the users of the software – became critical to the success of each team’s efforts.

Early results of this move to CD included a reduced mean time to resolve issues as part of an overall increase in quality. The automation tooling also facilitated a data-driven approach, enabling Watchful to report quantitative successes that soon got the CIO on board with the effort.

**The Role of Containers**

Before beginning its DevOps journey, it would take Watchful up to four months to stand up an individual server. Furthermore, each team required its own servers, even in cases where the servers would serve a similar or overlapping purpose.

Virtualization partially addressed this situation, but it wasn’t until Watchful implemented containers that it was able to deploy builds as rapidly as it liked.

Once Watchful had Docker up and running, it was able to implement daily preview builds and more than 70 developer builds per day – fully self-service on the part of developers. In addition, Watchful no longer needed a separate patching or upgrade regimen, as it simply rolled such changes into normal deployments.

Because containers allowed Watchful to deploy thousands of independent units, the new container-based architecture aligned with clear team ownership and rapid iterations.

This architecture facilitated the acceleration of test automation from days to a matter of minutes, with full test runs for each build across as many as 200 scenarios – adding up to over 7,000 automated tests per day.

As a result, Watchful was able to achieve four or more releases to production per day with no adverse impact on either customer experience or back-office functions.

**Dealing with Legacy Risk**

In some cases, teams worked on greenfield products or other products with little to no legacy debt, for example, websites with little to no system of record transactionality.

The larger part of Watchful’s work, however, dealt with legacy applications and technologies. Sometimes the software development effort focused on updating legacy assets directly, while in other cases, code would integrate with one or more legacy endpoints.

In either case, Watchful had to manage the risks inherent with such legacy – risks that essentially amounted to the technical debt the company accrued over the years via poor coding practices, use of now-obsolete products, or simply via the acquisition of different companies with different approaches to building software.

One key to managing such risks was the extensive use of feature flags that enabled each team to roll out new functionality to different audiences over time. As each feature progressed, the team would merge it into the master code trunk in stages – from the developer to the team to perhaps a beta group of customers and then to general availability.

As a result, developers merged code branches into the trunk whenever they were ready, instead of having to wait for a complex, ‘big bang’ deployment event, while minimizing the risk of issues cropping up in production.

**The Intellyx Take**

There is more to Watchful’s story than fits into this article, of course. The next phase for the company involved scaling the effort to over 700 applications, including both greenfield and legacy codebases.

At that level, deployment cadence became a critical consideration, as even the most independent of DevOps projects still require some coordination. However, even at the broadest scale and most rapid of CI/CD implementations, Watchful depended on its DevOps team structure, containers, and feature flagging to reduce risks while ensuring an optimal customer experience.


*  *  *


_Originally published on September 10, 2018 [here](https://intellyx.com/2018/09/10/the-real-world-enterprise-road-to-continuous-delivery/). Copyright © _[Intellyx LLC](http://www.intellyx.com/)_. LaunchDarkly is an Intellyx client. At the time of writing, none of the other organizations mentioned in this article are Intellyx clients. Intellyx retains full editorial control over the content of this paper. Image credit: _[Nick Goodrum](https://www.flickr.com/photos/nrgoodrum/)_._
