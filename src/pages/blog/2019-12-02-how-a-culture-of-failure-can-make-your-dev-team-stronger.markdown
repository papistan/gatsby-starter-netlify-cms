---
author: Kimh
comments: false
date: 2019-12-02 16:00:39+00:00
layout: post
link: https://launchdarkly.com/blog/how-a-culture-of-failure-can-make-your-dev-team-stronger/
slug: how-a-culture-of-failure-can-make-your-dev-team-stronger
title: How a Culture of Failure Can Make Your Dev Team Stronger
wordpress_id: 194573
categories:
- Continuous Delivery
tags:
- engineering culture
- failure
- software development
---

_Originally published on [Toolbox](https://it.toolbox.com/guest-article/how-a-culture-of-failure-can-make-your-dev-team-stronger) on September 25, 2019._


#### What is the first thing your team does during an incident? The alert goes out. A ticket has been filed. You start to search for the root cause. What's the priority—are you searching for the person at fault, or working as a team to find a fix and restore functionality to your customers?


Failure is inevitable. No matter how prepared we think we are, failure can happen to any of us at any time. In a recent talk at the Bay Area Test in Production Meetup, Ben Woskow, Engineering Manager at LaunchDarkly, reminds us that nothing we do in software development will ever be perfect or invulnerable:

“Do our developers occasionally make mistakes? Yeah. They’re human. Are we dependent on third-party services, the libraries that might have some sort of instability or vulnerabilities? Yeah, absolutely. Even if all of your software, all your dependencies are perfect, is there always a chance that a natural disaster, a power outage, or some other widespread event will knock out your underlying infrastructure making your cloud application completely inaccessible? Yeah, it’s happened to several of us, I’m sure.”

Teams that recognize this inevitability, and devote time and energy to thinking about how failure affects them, can grow stronger for it. In thinking about how to prevent, recover from, and learn from failure, they are turning these challenges into valuable learning opportunities. And as a result, they are reducing costly outages and recovering from incidents faster. This proactive approach is commonly referred to as a culture of failure, or a blameless culture.


### Casting the first stone


Blameless is well-established and industry-recognized. This approach enables teams and organizations to learn productively instead of reactively. Woskow points out:

“It’s all about working together and trusting each other…You’re all collectively at fault, in the same way that when you have a huge success, you’re all collectively successful. When you start thinking about working together as a team, it helps in your incidents, but then it also helps just generally working together in all ways.”

The Google SRE Team (Site Reliability Engineering) is one of the biggest proponents of blameless culture, and [write about it extensively](https://landing.google.com/sre/sre-book/chapters/postmortem-culture/) in their book that outlines their own processes. Netflix, Facebook, PagerDuty, and Etsy have practices in place that support a culture of failure. Startups like Gremlin, Honeycomb, and FireHydrant have even built businesses and products around this concept.

Some teams have gone so far as to normalize and gamify failure. Through events like chaos engineering game days, organizations are helping their teams learn how to mitigate mistakes so that in an actual emergency, they follow a well-practiced and tested routine rather than make snap decisions under stress. This way of thinking about failure allows teams to recover faster, learn more, and ultimately reduce incidents altogether.


### Designing for failure


We can see how a blameless culture empowers teams to work more effectively together—when you’re not afraid of hiding mistakes and near misses, then everyone benefits from shared knowledge. But what are the processes and infrastructure that help teams recover from failure, learn from failure, and ultimately avoid failure?

Designing for failure reduces the inherent risks associated with building and delivering software. Having known failure modes and well-understood processes in place are fundamental. This includes:


#### Monitoring, observability, alerting


Knowing when a failure has happened is key. Make sure you put the appropriate monitoring/observability and alerting tools in place so your team knows when a failure is happening.


#### Response and recovery


Once your team knows a failure is occurring, having a process in place around escalation and response is important. Also, while you are focused on recovery, have you considered customer impact? Having a plan in place for communicating incidents to users is important, and known reduced modes that you can fall back on are even better.


#### Teams, not individuals


Having a blameless culture means remembering that incidents happen to all of us. When individuals are not worried about blaming or being blamed, they will be more open to sharing the knowledge they have about systems so the team can respond more quickly and effectively.


#### Continuously improving


Once you’ve found the root cause, you naturally want to fix it. But also be careful to identify proximal causes as well. Make sure you learn from the incident and make changes to processes as well as systems that will prevent the same incident from happening again.


### Failure, not disaster


Failure happens. It’s not a question of if, but when. And we all know sometimes this is our own doing, and sometimes it’s contributing factors outside of our control. The question is how will you respond? How will you prevent failures from becoming disasters? And how can you empower your team to learn from failure, so they can become stronger and more resilient?


