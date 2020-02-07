---
author: andreaech
comments: false
date: 2017-09-14 18:41:47+00:00
layout: post
link: https://launchdarkly.com/blog/beta-testing-with-feature-toggles-testing-in-production-like-a-pro/
slug: beta-testing-with-feature-toggles-testing-in-production-like-a-pro
title: 'Beta Testing with Feature Toggles: Testing in Production Like a Pro'
wordpress_id: 2016
categories:
- Continuous Delivery
- Feature Management
tags:
- beta testing
- canary launch
- continuous delivery
- dark launch
- permission toggles
---

We all know beta testing is important—not just for understanding your customers’ needs, but also for stability and security. Every time you do a launch you are essentially asking: “Are there bugs? Is there feedback?” Both with the goal of making your product better. 

[Testing in production](https://opensource.com/article/17/8/testing-production) will give you the most information about the success of your new functionality. And because feature flags help separate deployment from release, they make such testing safe and easy. When it comes to beta testing, a lot of the top companies tend to adhere to a similar paradigm—test early, test often, and do it in your production environment. 

So how do companies have smooth and simple transitions from alpha to beta testing, and then to full rollout? Read on to learn how top companies are approaching their beta testing using deployment tools with feature flags providing links out to more in-depth descriptions. 

But before we get started, here’s a quick terminology review. Pete Hodgson refers to this use of feature flags for betas as “[permissioning toggles](https://martinfowler.com/articles/feature-toggles.html).” Also known as a “canary launch,” this is often random like a percentage rollout. A set group, or “champagne brunch,” releases to internal users or another section or group.

[![](https://blog.launchdarkly.com/wp-content/uploads/2017/09/betatesting-1024x491.jpg)
](https://blog.launchdarkly.com/wp-content/uploads/2017/09/betatesting.jpg)


### 6 Approaches to Product Launching


**#1 ****Facebook** is the prime example of dark launching. Their release management has to be impeccable to operate at such massive scale. Their betas are often up to  million users or more.

___“Although we push to production only once a week, it's still important to test the code early in real-world settings so that engineers can get quick feedback. We make mobile release candidates available every day for canary users, including 1 million or so Android beta testers.”___

Read their article on [Rapid Release at Massive Scale](https://code.facebook.com/posts/270314900139291/rapid-release-at-massive-scale/) to learn more about how they do continuous delivery at scale.

**#2 ****Hootsuite** gives a typical rollout pattern for its features—starting internally and then slowly exposing to a larger audience.


Typical
Push new code then:
- Dark launch to yourself or your team to test
- Launch to the whole Hootsuite organization
- 10% of all users
- Watch graphs
- 50%
- 100%
- Simple means of rollback if necessary


Check out Bill Monkman’s [full deck on dark launching](https://www.slideshare.net/datawire/dark-launching-with-consul-at-hootsuite-bill-monkman) here.

**#3 Etsy** calls feature flags “config flags,” and gives a lot of credit for their process to [Flickr](http://code.flickr.net/2009/12/02/flipping-out/).

_“Key system-level and business level metrics (like checkout/listing/registration/sign-in rates) are projected on _[_screens in the office_](http://www.flickr.com/photos/chad/5144084512/)___ and we have a number of internal dashboards that the team uses (we mainly use Ganglia and Graphite). We also have lots of switches and knobs to help us roll features out to percentages of users and ramp them up slowly, or quickly. Features are used and tested by us here at Etsy for some period of time before they are rolled out publicly.”___

They have custom built a feature flagging API, “Feature API” to enable this. Some of the bucketing they use include: admin, internal, users, groups.Read more about [Etsy’s deployment practices](https://codeascraft.com/2011/02/04/how-does-etsy-manage-development-and-operations/) and check out their [Feature API on GitHub.](https://github.com/etsy/feature)

**#4** Beta can also apply to back-end rollouts. **Instagram** does canary deployments to a subset of servers, using feature flags as a continuous delivery tool. It’s important for continuous delivery to perform these tests, which are key in helping them avoid failed deployments.

But Instagram hasn’t always had this system. Read here to [learn how they evolved](https://www.infoq.com/news/2016/04/continuous-deployment-instagram) from a “mish-mash of manual steps and scripts” to a system they could depend on. And check this out if you want more recipes for [database migration with feature flags](https://blog.launchdarkly.com/feature-flagging-to-mitigate-risk-in-database-migration/).

**#5 Niantic’s** Pokemon Go betas are well known and rabidly tracked by its fans. They famously roll out by region—a field test in Japan here, a limited beta in Australia, and then something in New Zealand. Sometimes these betas for features are invite-only. Here’s a write up of [how they approached the rollout](https://www.reddit.com/r/TheSilphRoad/comments/4e3skg/beta_means_beta_and_for_niantic_its_game_is/) of the game Ingress.

**#6 GoPro** released their GoPro Plus product early using feature flags. By breaking the larger release into smaller features with their own testing timelines, they were able to iterate and improve continuously. The video below walks through the technology they used and the timeline from dogfood to a “big bang” marketing announcement.

__“At GoPro you can kind of tell we don’t things lightly. We want to do big announcements and we want to come out with great products...we actually had smaller features that would go out, and then go for alpha testing and beta testing along the way. Shortly after March, we actually had most of the applications done from a core feature standpoint, but we kept iterating and improving those core features that we knew we were going to launch with.”__

[embed]https://www.youtube.com/watch?v=mJEZ8-PfTjk[/embed]




### Controlling Your Rollout Like a Boss


Did you notice some trends there? These larger companies are using beta testing to do one of the following:



 	
  * Testing in production with feature flags

 	
  * Ability to release early and test small functionalities before a broader release

 	
  * Internal tests that easily become external canaries

 	
  * Regional rollouts


As more companies start to use feature management, these incremental rollouts are not the headaches they once were. Companies can be safer and smarter with how and when they expose features to their end users. 

If you want to get started with feature flagging, check out [featureflags.io](http://featureflags.io/) a resource we made for the community to learn best practices.  
