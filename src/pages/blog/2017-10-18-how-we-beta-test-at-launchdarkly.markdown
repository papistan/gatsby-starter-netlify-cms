---
author: Kimh
comments: false
date: 2017-10-18 21:36:36+00:00
layout: post
link: https://launchdarkly.com/blog/how-we-beta-test-at-launchdarkly/
slug: how-we-beta-test-at-launchdarkly
title: How We Beta Test at LaunchDarkly
wordpress_id: 2062
categories:
- Continuous Delivery
- DevOps
- Feature Management
tags:
- beta test
- beta testing
- continuous delivery
- feature flags
- test in production
---

We recently looked at how some well-known companies beta test. Specifically we looked at groups that [test in production](https://blog.launchdarkly.com/tag/beta-testing/), and do it well. As you know, testing in production is one of the best ways to find bugs and get solid feedback from your users. While some may shy away from this because of the risks involved, there are ways to mitigate risk and [do it right](https://opensource.com/article/17/8/testing-production). So this time we want to share how we beta at LaunchDarkly. 

It’s no surprise that we dogfood at LaunchDarkly. Using feature flags within our development cycle is a straightforward process. We often push features directly into our production environment and safely test prior to allowing user access. When it’s time to beta test with users we can update the setting on the appropriate flag and get user feedback quickly. And of course, if we ever need to we can instantly turn features off.


### **Deciding Which Things to Build**


When we’re thinking about new features to implement, we have our own ideas of which direction our product should go, but we also consider inbound requests. This can be from support tickets, questions from potential customers, or conversations with existing customers. Bottom line is we want to build a product that serves our customers, and so we do our best to listen to what they want.

Once we identify a feature we’d like to build—whether it was our own idea or a customer request—we’ll share it out to see if other customers are also interested. This is an important part of our beta testing process, because once the feature is in production and we’re ready to test it, these are the people we want to circle back with for beta testing.


### **Testing in Production**


When it’s time to test, we test with actual end users in production. Our feature management platform allows us to turn features on for specific users. We can specify individual users, or we can expose users by attribute, like region (everyone in Denver)—and we can instantly turn them off at any time.

Because we’re testing in production, we don’t have to have an isolated environment or separate account. For those customers who showed interest, and agreed to participate in beta testing, we turn the features on in their production accounts.

![](https://media.giphy.com/media/kNTAHtqCfu6nm/giphy.gif)

Typically we beta for two weeks, sometimes as long as a month. As mentioned before, since we know which customers are interested in the feature, we can go back to them and have them test it. These are the users who already know they want this functionality, so we want to be sure it fits (or exceeds!) their expectations. And of course we want to make the most of this time, so it’s important we actually get feedback. We find that those who have asked for the feature are eager to let us know how things are working. We make a point of also following up with those who don’t proactively offer feedback—we want to hear from everyone!

While we’re testing and getting feedback, we’re taking all this information in and improving the feature before rolling it out to everyone else. When we feel confident we have something that’s ready to be shared, we’ll begin a percentage rollout to the rest of our users. 


### **Embracing Failure**


Using feature flags around features within our development cycles allows us to mitigate risk by pushing out small, incremental changes at a time. As you can see, this also enables us to beta test quickly and safely. If there are major bugs, we’re more likely to identify them early on before affecting our all of our customers. 


<blockquote>“Embrace failure. Chaos and failure are your friends. The issue is not if you will fail, it is when you will fail, and whether you will notice.” [-Charity Majors](https://opensource.com/article/17/8/testing-production)</blockquote>


Right now we’re currently in beta for scoped access tokens and a new faster .net SDK. Let us know if you’d like to take a look at it early, we’d love to hear what you think.
