---
author: Kimh
comments: false
date: 2017-10-03 00:10:44+00:00
layout: post
link: https://launchdarkly.com/blog/removing-risk-from-product-launches-a-webinar-with-gopro/
slug: removing-risk-from-product-launches-a-webinar-with-gopro
title: 'Removing Risk from Product Launches: A webinar with LaunchDarkly, CircleCI,
  and GoPro'
wordpress_id: 2047
categories:
- Continuous Delivery
- DevOps
- Feature Management
tags:
- CircleCI
- continuous integration
- feature flags
- GoPro
---

We recently sat down with one of GoPro’s Senior Engineering Managers, Andrew Maxwell, and the CTO of CircleCI to discuss reducing risk in product launches. Andrew talked about how his team delivered their code two weeks early, tested in production, and had an overall successful product launch. He goes into detail, sharing how his team uses continuous integration and feature flags to make product launches like that possible.


### **The Big Launch**


Andrew’s team is responsible for web applications. Last September his team was focused on a big initiative around a product launch called GoPro Plus, which allows users to access and share content wherever they are. This launch included both mobile and desktop apps, and promoted two new cameras in the GoPro line.  


### **Two Weeks**


The team delivered their code and pushed it into production two weeks early: 


“...we used LaunchDarkly to push our code to production, turn the apps off -- off by default—and then make sure that we had everything pushed out, deployed, and the infrastructure running live without customers actually seeing it.”


Two weeks gave them time to do a full integration test their features. They tested both in-house and in production—slowly opening up who had access—so they could get valuable feedback, find bugs, and make continuous improvements in the weeks leading up to the big launch. On the day-of, they were confident in their work and simply turned on 12 feature flags.

Check out the full webinar below to learn more about how the team used CircleCI and LaunchDarkly, their planning strategies, and best practices for their continuous integration pipeline.

[embed]https://www.youtube.com/watch?v=mJEZ8-PfTjk&feature;=youtu.be[/embed]
