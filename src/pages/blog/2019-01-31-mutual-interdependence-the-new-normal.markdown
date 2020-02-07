---
author: heidiw
comments: false
date: 2019-01-31 22:00:32+00:00
layout: post
link: https://launchdarkly.com/blog/mutual-interdependence-the-new-normal/
slug: mutual-interdependence-the-new-normal
title: 'Mutual Interdependence: The New Normal'
wordpress_id: 193695
categories:
- DevOps
tags:
- Agile
- continuous delivery
- continuous integration
- DevOps
- SDLC
---

Originally published in [DZone's _Guide to DevOps: Implementing Cultural Change_](https://dzone.com/guides/devops-implementing-cultural-change), in January 2019.

DevOps is a culture, not a process or a tool. It’s a way of structuring teams and thinking about projects so organizations can ship faster and more often. DevOps asks organizations: ‘What does ready mean?’ Ready used to mean a complete product, perfect, ready to ship. Now, smaller teams using DevOps methodologies are shipping smaller releases more frequently. And they’re comfortable with the fact that those releases may not be perfect and may require updates. Let’s take a look at the ramifications of this cultural shift, and how it changes the way teams approach their role and processes.


### Moving Fast, Trying Not to Break Things


As customers, we hope someone has made the app we need so that it’s ready the moment we realize our need. The speed and agile delivery of software has changed our expectations about how often releases and updates happen, and we want them to happen even faster. How are organizations speeding up their development process while releasing more often, faster, and avoiding the inherent risks involved? 

Part of it is that the tools available to create software are powerful and continue to evolve in both reach and usability. Consider how far automation has come — from hand-built scripts and Jenkins to the automation and compliance of Habitat. Now instead of reading log files, we’re using Splunk and New Relic and Honeycomb to delve into the connections between services and trace messages through complex architectures. But that’s just one part of the puzzle. No matter what tools we have in-hand, if we don’t change how teams operate, we will still have bottlenecks. Before many of these tools even became mainstream, teams began adopting practices that would help them deliver faster. 

One of the earlier methodologies was Agile. The most basic goal of Agile getting rapid feedback and incorporating that information at the point of change. Taking that a step further, Continuous Integration and Continuous Delivery (CI/CD) exponentially decrease the time to delivery by making very small incremental changes every few days or even minutes. Specifically, Continuous Delivery is a set of practices that ensure your code is always in a deployable state. You accomplish this by increasing the frequency at which code is committed, built, tested, and deployed—steps that used to happen at the end of a project when it was ‘code complete.’ Because your team is delivering frequently, every change is smaller, and those changes are more isolated and less risky. Problems are identified more readily, and bugs are fixed more easily because they are discovered immediately. 


### You Got Ops in My Dev


Teams are taking Agile and CI/CD practices and rethinking how their collaboration habits. When development and operations are siloed from each other, one person builds, another QAs, and a third releases. It can take several transfers of ownership and considerable time to fix an issue after it is discovered. 

Working in an Agile or CI/CD framework, teams find value in holding development accountable for their code up until the point of release. Maybe that person should be more involved in testing, validating, and releasing the feature they worked so hard to build. After all, this could help processes move along even faster. This blurring of rigid job identities became known as DevOps. And DevOps is more than a title or a collection of tools—it’s about how teams are structured, organized, and ultimately empowered to collaborate with each other.


<blockquote>“[DevOps] is a firm handshake between development and operations that emphasizes a shift in mindset, better collaboration, and tighter integration. It unites agile, continuous delivery, automation, and much more, to help development and operations teams be more efficient, innovate faster, and deliver higher value to businesses and customers.” - [Atlassian](https://www.atlassian.com/devops)</blockquote>


With a more collaborative outlook, DevOps teams leverage Agile and CI/CD methods to move even faster. Individuals are no longer focused on their one piece of the puzzle, but see the whole picture and understand how they can make an impact on it. When a developer begins to build, they are thinking about the entire development and release process. They are either setting up the tests themselves, or working closely with their QA team to make sure that feature is delivered without delay. 


### Checkpoints, Control Points, and Points of Interest 


As DevOps practices have become more widely adopted, tooling has been developed to support these collaborative workflows. Most recently, feature management platforms offer more control of elements in the release process. Instead of a release manager coordinating things at the moment of release, features can be deployed, tested, and then handed off to the release or business teams for full activation.

Moving fast seems risky if you are coming from a model where releases are large and involve many parts. Even a simple product update can turn into a complete disaster that takes hours or days to repair, and having to roll back code makes the process even more painful. However, as Forsgren, Humble, and Kim argue in their book [_Accelerate_](https://www.amazon.com/Accelerate-Software-Performing-Technology-Organizations/dp/1942788339), moving fast is the way to make DevOps work more effectively. 

Feature management platforms let teams determine how users will experience their products, and can configure different experiences for different user groups using the same code. These teams are using feature flags to separate the act of deploying code from releasing a feature. This means they decide when a feature is turned on, who will experience it, and how to precisely target it. 

With these control points and safety valves in place, DevOps is empowered to function collaboratively. Teams can check their code in early to reduce long-lived branches, they can test their code and validate their ideas, and they can protect their services and their users as they roll out new features. They can even instrument microservices with circuit breaker flags that will prevent cascade failures. Moving fast is not as risky anymore—if something goes wrong, you can simply turn the flag off. 

While DevOps teams are enriching their development and release processes with stronger controls, they often find this level of control makes it easier to include other teams within their organizations in critical points of the processes. Once a feature flag is in the codebase, a feature management platform allows anyone to control it without needing to directly access the code. DevOps can invite Product or Marketing to participate in releasing a feature. 

Engineering no longer needs to operate on strict timelines dictated by external business calendars. They can deliver code when it’s complete, and share the controls for releasing that feature. This means Marketing can release when they’re ready to launch their campaign, Sales can share new features with prospects, and Customer Success can quickly and easily assist customers.


### Seize the Means of Release!


This is where collaboration between Engineering and other business teams only begins. When these business teams are given control over these features, they can do more than just turn them on/off, they can also become more involved in testing and validation processes. 

Business teams like Product, Design, or Marketing can now be an integral part of running a beta test—from determining who will be involved, to actively collecting feedback and validation. Suddenly they can become actively involved in building new features, helping to garnish valuable feedback and making sure it’s what the user base really needs. 

With the controls found in DevOps tooling—like feature management platforms—team members across organizations are now becoming active participants in the development and release processes. What would change in your workflow if you could choose when and how to deliver a feature?
