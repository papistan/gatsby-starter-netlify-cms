---
author: edithharbaugh
comments: false
date: 2015-07-08 21:46:38+00:00
layout: post
link: https://launchdarkly.com/blog/dark-launching-meetup-lessons-learned/
slug: dark-launching-meetup-lessons-learned
title: 'Dark Launching Meetup: Lessons Learned'
wordpress_id: 98
categories:
- Continuous Delivery
- DevOps
tags:
- dark launch
- dark launchers
- dark launches
- Facebook
- meetup
---

We hosted the first [Dark Launching meetup](http://www.meetup.com/San-Francisco-Dark-Launching-Meetup/) in May with a surprisingly large turnout. We’d originally planned the meetup to be a user group of our current LaunchDarkly users sharing how they were using LaunchDarkly for dark launches. We were very pleasantly surprised by how many people joined our meetup as they wanted to learn more about dark launching itself! Dark launching is a best practice used by Facebook to launch new features “dark”(off), then slowly light up (turn on) features for different users. A key component of dark launches is the ability to easily turn a feature off again if issues are found.

Why dark launch? Shouldn’t all releases always be throughly tested and production ready? No matter how good or thorough your QA and performance testing is, you will never find all issues before production. Dark launches are a recognition that the real world exists. Rather than exposing your release into the full light of day to get blasted, shouldn’t you control access yourself?

I started the Dark Launch meetup by asking for a show of hands from everyone who’d had a bad release. Every hand went up, way up. I then asked if anyone wanted to share their story of a bad release. Everyone put their hands back down. I think there’s too much shame attached to bad releases, when we should 1) admit that bad releases happen to good teams 2) learn from bad releases 3) put process like dark launches into place to help mitigate bad releases.

So I’ll share a tale of two releases - one where I used dark launching, and one where I should have used dark launching. At TripIt, our users emailed us their email travel confirmations. We’d parse the emails, extract the useful information like flight and hotel, and make them a beautiful trip itinerary. Our users loved us, we were the number #1 Travel app in the App Store. I was the product manager on a daring new feature - users would connect their gmail accounts directly to TripIt, skipping the step of manually forwarding itineraries. It was considered extremely risky to have people authorize us to scan their email inbox. So I found a group of frequent travelers who were willing to give us feedback. We pushed the feature “live” to production, but only granted the opted-in users access, as a dark launch.

Internally, we carefully monitored our speed scanning real world inboxes. I also followed up on all users on whether we were importing the right (or wrong) email items. Some early mistakes were being too aggressive with the word “ticket” and importing a Tiffany order, or a Turkish Airlines promotion. When we’d gotten enough real world feedback, we then truly launched, with a TechCrunch article. I was pretty excited both that we’d launched something to help our users as well as [my picture making it into TechCrunch](http://techcrunch.com/2010/08/10/with-new-auto-import-itinerary-feature-for-gmail-tripit-just-got-easier-to-use/)!

We didn’t dark launch another email feature at Tripit, with very bad results. A persistent user complaint to TripIt is we would import ALL travel confirmations, whether or not you were the actual traveler. We called this “Other People’s Travel” (OPT). For example, if my sister Margaret Harbaugh emailed me her flight information - bam! her trip would appear in my TripIt account. Our system recognized that there was a travel plan, but there was no way for our system to tell the difference between Margaret and Edith. Or was there? Our engineers implemented some logic to compare names on the account with names on the itinerary and if there wasn’t a close enough match, to not import the trip. Sounds easy - “Margaret” is clearly different than “Edith”, so let's ship it, right? However, we quickly had a flood of complaints. We had over a million users using auto-import (the largest gmail authorized company worldwide) . It turns out that email itineraries often had very odd concatenations like MsEdith or EdithMs, etc, which TripIt was rejecting as not the same as “Edith”. We were skipping too many emails and our users were very unhappy. They'd relied on us to “automagically” work, and they had tolerated some false positive imports. Now we were ignoring may emails they expected us to import. We had to do an emergency patch and quickly revert the change. If we’d done a dark launch, we could have tested the change with a smaller batch of users and monitor their reaction. It was a lesson learned to me that dark launching is a powerful tool to ensure user satisfaction.

We’re looking forward to our next dark launching meetup to share more stories and lessons learned. You can join the Dark Launch meetup group [here](http://www.meetup.com/San-Francisco-Dark-Launching-Meetup/), and we hope to see you soon!



* * *





###### _LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER WITH FEATURE FLAGS AS A SERVICE. START YOUR FREE TRIAL [NOW](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._



