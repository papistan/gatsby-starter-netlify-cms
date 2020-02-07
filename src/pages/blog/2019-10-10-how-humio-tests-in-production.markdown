---
author: mattdel
comments: false
date: 2019-10-10 02:01:49+00:00
layout: post
link: https://launchdarkly.com/blog/how-humio-tests-in-production/
slug: how-humio-tests-in-production
title: How Humio Tests in Production
wordpress_id: 194343
categories:
- Feature Management
tags:
- software development
- test in production
---

## Eating your own dog food without even knowing it


Another Test in Production Meetup is behind us. Heidi Waterhouse, a Senior Developer Advocate at LaunchDarkly, emceed the September event held at the Microsoft Reactor in San Francisco. In the first session of the night, Craig Vitter, Solution Architect at Humio, discussed how Humio uses its own product, a log management platform, to test in production.


<blockquote>"...as a developer, remember, just because it (a new feature) works on your machine, doesn't mean it's going to work in production. Customers always find interesting and new ways to break whatever it is you release to them. There's always some edge case you haven't anticipated." – Craig Vitter, Solution Architect, [Humio](https://www.humio.com/)</blockquote>


Watch to learn how Humio's developers mitigate risk by pushing new features through multiple "levels of production" and building observability into their application. If you’re interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/).

[embed]https://youtu.be/-Xf-pl5ELOw[/embed]

TRANSCRIPT:

Heidi Waterhouse: Hey, folks, welcome to Testing in Production. We are super excited to have you here. I give really high odds that I fall in that crack and fall off the stage, which is usually my standard for, did the talks exceed? Did I fall off the stage? No, talk succeeded, excellent. So, I'm not the one giving a talk today. We have three exciting speakers who are going to talk to you about different aspects of Testing in Production, and I'm really happy to introduce them to you.

Before I start, I need to say thank you to the Microsoft Reactor for hosting us. We really appreciate the space. LaunchDarkly is sponsoring this, but this is a Meetup for the community, and not just for LaunchDarkly. So, our first speaker, are you ready, Craig? There he is. Our first speaker is Craig from Humio, thank you. He's going to talk to us about how Humio tests in production, eating your own dog food without even knowing it. I'm really looking forward to hearing this. Let's give him a little round of applause.

Craig Vitter: Thank you. Can everybody hear me? Make sure I turn this thing on.

Heidi: You're good.

Craig: All right, thank you. First a confession, I don't know what I'm doing, and I'm just going to admit that. The product of this presentation really comes out of conversations with my entire team, but two people really stand out. Thomas and Morten who are core engineers from way back in the beginning in the Humio product, which was two and a half years ago, really a long time in internet years. These guys really know what they're doing and they helped me a lot with this presentation, so I just wanted to admit that.

Just quickly, Humio is a log aggregation platform. The job of Humio is to take all of your log data and make it somehow meaningful to you. I just want to explain that in the terms of when we're testing in production, it's all about delivering a better product. This presentation isn't really about selling you on Humio, it's telling you how we test Humio to sell it to you. When I started thinking about this presentation, I went to the team and I asked them, "How do we test in production?"

There were a lot of blank faces and they said, "Wait a second, do we test in production?" They were like, "I guess when you put it that way, we do." And so, this is going to be a little bit of a talk about how we also discovered how we're actually using our own product, to test our product in production. Also, for those of you who are not in the space where you have millions of users to do feature flag AB-type testing, I'll tell you about how we do it, because we actually are pretty small.

Our product, although we do have a hosted version, we primarily focus on selling software to customers who host in their own infrastructure and when you do that, it's really hard to test in production because they don't like you to look over their shoulders when they're running your system in their environment. We do have hosted customers, it's just a very small number. We don't have millions of users and we can't do AB testing and generate large volumes of data, but we do absolutely test features in production.

When we talk about production, for Humio there are levels of production. Every developer obviously has their own environment when they're releasing their engineering code through the pipeline, but then we have this system called [ops.humio.com](http://ops.humio.com/). That's where we actually monitor all of the Humio clusters that we're running somewhere, whether it's for customers or our cloud infrastructure, and that's our first line of testing in production. Because that system is super important to our daily business, but that's the first place that really gets all of our new features.

So, it's our system and if it goes down, it's a big problem for us because then we have no idea what's happening with all our other systems that are out there. Yet, we still do test in production on that and some days, it's a little hair raising. But the nice thing to note is if it ever were to completely fail, we might lose many, many, many terabytes of data, but we wouldn't actually go out of business. We would just have a blind spot for a few days.

If it passes in that environment, that's usually when we do one or two things. We'll cut a release candidate that we might give to customers that are running on-premise that we trust and like to live on the edge. Specifically, those who may have asked for a new feature that was in that release. The other thing we do is, we might release it to cloud.huimo, and that's where our customers who are on the hosted environment live. Sometimes we do it and let them know that there are features that they're getting that didn't exist before, and other times we just wait to see how they respond whether or not they notice they got some new features.

Then obviously we go to release and release, that can be direct on-prem, etc. But because we don't have a lot of users in that cloud environment, we don't do AB feature flag type of testing in an automated way and we don't sit and study data about it. But, we do have a couple of cool features. In fact, there's even more for on-premises customers. We do feature flags, and we build them into our UI.

Little secret trick, if you do Control Shift F, it'll open the panel on the left. That'll give you a list of all the things that we're currently testing in the UI side of things and you can actually try them out for yourself. I took the snapshot of this screenshot a couple of weeks ago. Some of those things don't actually work. Like if you were to hit Dark Syntax Theme, nothing would happen. We tested the dark theme, nobody liked it and it was disabled. We just haven't removed it from that control panel.

The other interesting thing we do is if you hit Control Shift D and again, if you happen to try Humio, you can try this yourself, you'll get this dev panel. It's another undocumented feature, but what it actually allows us to do is watch the real-time execution of queries that people are running and see what's happening. That's really powerful for us because when we release this platform, we can't always anticipate edge cases. We don't know what people are actually going to do.

We have a guy that says, "Here's how you write a query to query your data," but we don't really know at the end of the day how a power user like you might write that query, and what would actually happen to the system. So, we put a profiler in and if you hit that Control Shift D, that'll come up and you can actually watch your queries executing and how the profiler is dealing with them. That's kind of fun.

So, that's how we're doing testing on the UI side of things. It's not a huge scaling feature, but it's something that you can do on your end if you don't have millions of users, but you want to try things out in a production environment and give your customers that ability to say, "Yeah, I want to try that dark theme. Let me try that out." As long as you're letting them now, and you can still slip things in on them.

Now here's where we'll talk about data. We are a data platform and we're designed to ingest very large volumes of data, up to hundreds of terabytes a day. The benefit is on the back end, we can really use our platform to test how our platform is doing what we want it to do, ingesting all that data, and here's an example. One of the features is that you can archive your data off of the platform to an S3 bucket. At one point, it was limited to 2.3 terabytes a day, and so the engineer who worked on this feature said, "How can I improve that?"

One of the things that we have in the platform, which is written in Scala and runs on the JVM, is that we're doing thread dumps. So, if you go into Humio, you actually can see that there's a constant update in Humio, of thread dumps coming from Humio itself, so Humio is monitoring Humio. In this screenshot, what you see is a thread dump, specifically for the S3 archiving job and for the segment source class that's handling those features that are archiving data.

So, you took a look at what the thread dump was saying, and this is really important. If you're going to do this, then I highly recommend any application you write has this capability of doing this thread dump so you can watch your app in real-time. The only problem is, you really need to understand your app to understand what the thread dumps are telling you. So, it's important to name functions and classes something that makes sense to you, because otherwise your thread dump data is pretty useless, right?

Fortunately, this engineer having written the code and named everything understood what these thread dumps were telling him, and figured out that the bottom four minus the last one actually were meaningful. And so, he went back and worked specifically on those functions and was able to get it up to 3.3 terabytes a day. And, we can monitor that because after he put that code into production, on the left-hand side you can see right in the middle of the graph, the throughput went up.

Now, the right-hand side is CPU. You want to increase throughput, but you don't want to increase CPU utilization. Ignoring the spikes which are unrelated to the code he released, you can see that CPU utilization was straight across the board. That's a classic example of building your application so that you can actually monitor the application and see what's happening with it.

We do that on the cloud version as well in release because one of the things you find is just because it works for you on your machine, doesn't mean it will continue to work when you give it to customers. So, it's really important to make sure that goes throughout the whole lifecycle. Another example, we compress data as it comes in. We're continuously working on trying to improve that level of compression so we can get more data stored in the same amount of space.

We wrote a new algorithm, dropped the algorithm and you can see we monitor the level of compression we get, the overall. Just after 12 o'clock on the 27th of August, we released that new code and you can see the compression doubled. That's another great example of being able to monitor. It's not just the thread dumps, now it's the actual output of the product and how much stuff is getting compressed.

If I'm going to leave you with a takeaway is, build your application to actually make it observable. That goes back to just basic observability principles. It's not even like, "I want to know all the things." Start to think about it like, "What do my users care about?" In our case, they care about, how much data can I get out? How much data can I get in? And then, how can I monitor that? Or, how can I just watch the entire lifecycle of the application so that I can actually see what's happening once I've released it into production?

And as a developer, remember, just because it works on your machine doesn't mean it's going to work in production. Customers always find interesting and new ways to break whatever it is you release to them. There's always some edge case you haven't anticipated. So, as long as you can watch these things happen throughout the full lifecycle, then you're going to hopefully be able to give them what they need in the long term and they'll buy your product.

If you want to know more about that last part, when I started talking to Morten about this and I said, "Testing in production," Morten said, "Oh my God, that's a really good idea for a blog post," and he went and wrote a blog post about all of this stuff. It's really interesting and although you probably don't want to remember that Bitly, if you just go to the Humio blog, you'll find it out there.

Thank you. That's my talk and hopefully if you have any questions, feel free now. I think there's a couple of minutes, or after.

Heidi: Yup, thank you Craig. First of all, first question, Are you hiring?

Craig : We absolutely are hiring and I will tell you, the big selling point is we are a Danish company. We were founded in Denmark out of the city of Aarhus, and so we're really big on hygge. If you know anything about Scandinavian culture, that means we're really nice, and we like candles and warm, fuzzy stuff.

Heidi: Cozy sweaters. That's a culture.

Craig: It's always worth a good trip. I just came back from an engineering meetup in Sweden, which was amazing and I've been Aarhus. So big selling point, you get to travel internationally and build really cool software.

Heidi: Excellent. Thank you so much. Round of applause for Craig. Wait, don't go away Craig, you're not off the hook yet. People have questions.

Audience: You mentioned when you build an app, you should make sure that the app is observable. Do you have any more examples? Can you elaborate on that?

Craig: Yeah, a couple of things about observability. I mean, you have to think about the entire lifecycle. It's not just end-users, but if there are other applications that are looking to receive data, think about your users, whatever is consuming the product of that application. From just an engineering perspective, it's being able to do things like thread dumps so that you can just monitor everything that happens.

But if you're going to do that again, remember, naming conventions matter because six months from now, you won't remember what that function did if it's not really obvious. So, make sure that when you're looking at those thread dumps, you're writing data that's meaningful so you can actually understand where the errors are happening, or where things are sitting, waiting idle, for work to be done.

The other thing is as far as errors, if you're going to output errors, same thing. Don't just say error, you need to give some context around the error so whoever is going to be dealing with the error is not spending an hour trying to figure out how to remediate, tell them how to remediate. Like, if this is happening, clearly this has happened and you should do this to fix it. Right?

Observability is about making sure you understand what's going on and when things break, that you can fix them quicker, especially at scale. When these things get big, it's just really hard to understand all the moving pieces. And when you got a big team of engineers, you start to have specialists and not everyone will understand what's happening on the other side of the wall so to speak.

Heidi: Any other questions? Well, you'll be able to find him when we take a break, but thank you Craig.

Craig: Thank you.
