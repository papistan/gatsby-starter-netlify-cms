---
author: adamcockell
comments: false
date: 2017-03-14 17:35:54+00:00
layout: post
link: https://launchdarkly.com/blog/my-agile-launch/
slug: my-agile-launch
title: My Agile Launch
wordpress_id: 1469
categories:
- Continuous Delivery
- Feature Management
tags:
- agile development
- Behavior-Driven Development
- Cucumber.io
- feature flagging
- HBO
---

Starting at a company that helps software teams release faster with less risk has reminded me of my first foray into agile development.

One of my earliest professional experiences was as an intern at HBO, where I reported directly to the VP of Emerging Technologies.  Over the course of the summer, it became clear that there were more promising new technologies to explore than there were engineers.  The undaunted college student that I was, I convinced my boss that I should own one of these projects.  Every day I would demo my work on a screen in his office, and he would provide feedback.  A few weeks later the VP presented to senior management and the company officially green-lit the project.  Though we didn’t refer to it as such, that cycle was my introduction to Agile.  Yet more importantly, it was a daily routine where a non-technical business stakeholder provided direct feedback to a technical resource; an arrangement that I’ve come to realize is quite uncommon.

Working at large and small companies in a variety of engineering roles, there are two overall trends that I’ve identified:



 	
  1. Companies often separate engineering from the business side.

 	
  2. Most development-related failures (e.g. missed deadline, bad or buggy feature, release causing a security vulnerability, etc.) are a result of miscommunication.


Neither of these statements are profound in isolation but when coupled genuinely pique my curiosity.

Over time the broader engineering community has developed numerous tools and processes to mitigate risk.  Missing deadlines?  Use story points to measure team output (velocity) over time.  Releasing buggy features?  Try test-driven development.  Want to avoid downtime during a release?  Setup application performance monitoring in your staging environment.  While these “quality assurance” measures are not guarantees of perfection, they make development more predictable.

Problems arise when we cut corners in response to misaligned expectations.  Let’s say there’s a feature request for a relatively straightforward user enhancement.  The development team has done everything right to this point (features properly designed and scoped), but towards the end of the sprint the team finds a scalability issue with no clear path forward.  Engineering management notifies the business side of this issue and insists that there should be resolution within five business days.  Five days pass and the developers have made no progress.  Engineering rushes to fix the issue through a refactor but skips unit testing to release earlier.  Two new bugs slip into production.  Instead of working on the next sprint the development team now works to get a hotfix release out.  One unexpected event can change everything.

The separation of the business side from its engineering counterpart sets the stage for frustration and missed opportunities.  Any tool that can bridge the gap between these two groups offers immense value to an organization or a working relationship.  [Cucumber](https://cucumber.io/), a Behavior-Driven Development test tool, [empowers non-technical stakeholders](https://confidentqa.wordpress.com/2013/12/21/effective-engineering-collaboration-for-the-non-technical/) to define requirements, in plain English, that double as executable test guidelines for engineers.  By regularly reviewing Cucumber test results, a business stakeholder could easily assess the current status of a project.  Nevertheless, Cucumber facilitates one-way communication and offers no clear guidance on iteration or state.

The daily iterations I had at HBO were extremely effective in moving the project forward quickly. In a perfect world we could repeat this process as often as possible with senior management to win their approval as early as possible.  What if we schedule a daily meeting with the entire senior management team and show up with a buggy build?  It would quickly become apparent that our good intentions are far less valuable than executive time.  Instead, what if we gave each one of the senior managers a version of the technology that we could push updates to over time?  What if I could focus on building features and my boss could choose and deploy the ones that he thought were ready?  What if after realizing that there was a problem with a deployed feature he could hide that feature without involving me?  LaunchDarkly does all of this at the enterprise level.

To me LaunchDarkly is about much more than feature flagging or even quality assurance; the platform empowers companies to reconnect the technical and non-technical departments in order to shorten feedback cycles with customers and make better decisions.

This mission is a game changer.

That its founders and team are all extraordinary yet humble makes the opportunity twice as appealing.
