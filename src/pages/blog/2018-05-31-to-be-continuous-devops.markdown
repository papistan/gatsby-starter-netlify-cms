---
author: andreaech
comments: false
date: 2018-05-31 19:00:23+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-devops/
slug: to-be-continuous-devops
title: 'To Be Continuous: DevOps'
wordpress_id: 193115
categories:
- To Be Continuous
tags:
- DevOps
- feedback loop
- product
- Sam Guckenheimer
- scale
- VSTS
---

In episode 45 of To Be Continuous, Paul and Edith meet with Sam Guckenheimer, Product Owner for Microsoft’s Visual Studio Team Services. They talk about how CI/CD has shaped the way teams approach DevOps today and how things might look in the not-so-distant future.

<!-- more -->

This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.

﻿﻿﻿<span data-mce-type="bookmark" style="display: inline-block; width: 0px; overflow: hidden; line-height: 0;" class="mce_SELRES_start">﻿</span>&lt;span data-mce-type="bookmark" style="display: inline-block; width: 0px; overflow: hidden; line-height: 0;" class="mce_SELRES_start"&gt;﻿&lt;/span&gt;&amp;lt;span data-mce-type="bookmark" style="display: inline-block; width: 0px; overflow: hidden; line-height: 0;" class="mce_SELRES_start"&amp;gt;﻿&amp;lt;/span&amp;gt;





ABOUT THE GUESTS







[Sam Guckenheimer](https://twitter.com/samguckenheimer) is Product Owner for Microsoft’s [Visual Studio Team Services](https://www.visualstudio.com/team-services/)(VSTS) where he supports and promotes agile software development and continuous delivery with the One Engineering System.






TRANSCRIPT
















**Edith Harbaugh:** So, what do you like about continuous delivery?

**Sam Guckenheimer:** You get to move faster, you get to experiment more, and you get to connect developers and users without all the waste and all the barriers in between.

**Edith:** Now would be a good time for you to introduce yourself.

**Sam:** I'm Sam Guckenheimer. I'm from Microsoft Visual Studio Team Services, which is a SaaS for continuous delivery and for posting Git and for agile planning. The basis of the One Engineering System in Microsoft.

**Edith:** So you must see a really broad spectrum of users. How do you see people starting to adopt continuous delivery in real life?

**Sam:** Well, you're right. It ranges from, for example, what we see internally with One Engineering System where we have 75,000 engineers in Microsoft as customers.

**Edith:** 75,000?

**Sam:** Yeah.

**Paul Biggar:** Is this the Gish migration thing that we all read about online?

**Sam:** That was part of it. The thing you read about online was the migration of Windows and Devices Group onto Git when we had this problem with the WDG.

They have a 270 gigabyte repo as their core repo. That's one of 400 repos. That with classic Git took 12 hours to clone. Now, that's if it was successful, meaning your laptop didn't go to sleep, your network didn't burp or the Wi-Fi didn't screw up. And if any of those things happened you had to start over.

We ended up having to fix Git for that and created the Git Virtual File System which gave us roughly 300x improvements in performance and has given us more since. So that's something that we announced and open-sourced, I think, not quite a year ago now. It's in our hosted service and it's on our on-prem offering as well. That's a part of it, hosted Git.

We also have CI/CD services part of it, and Agile work management, things like Kanban and dashboards and data analysis services as part of it. That's the weirdly named Visual Studio Team Services. It in fact works within the IDE, IntelliJ, Eclipse.

**Paul:** Right, all their ways you can write code.

**Sam:** Yeah, any way you can write code. That's the product group I'm in and that's what we use internally in One ES, the One Engineering System.

To your question, Edith, about the range of customers you see, we see everything from classic folks who are very aware that they move slowly and are highly regulated, and we'll say we're not really a technology company, to startups who say we're just a few people. And they can sign up for free. We love both, and we serve both.


<blockquote>One of the things I try to do is to share as much as I can about our own experience. </blockquote>


So I curate a website [DevOps at Microsoft](https://docs.microsoft.com/en-us/azure/devops/devops-at-microsoft/), AKA, .MS WAC DevOps, and share things like how we use Git and how we change our test portfolio.

An example is that [in my talk yesterday](https://www.youtube.com/watch?v=NlI0bkgdG7E) at [Index](https://developer.ibm.com/indexconf/) I was showing how we use our pull request policies to run 70,000 tests in about six minutes. And that's on every pull request uniquely. If any of them fail, we fail the pull request. And if the co-review doesn't happen within 12 hours, we fail the pull request.

So we get all changes reviewed, which we need to do for some of the compliance certifications, and we get a very high test reliability signal in the pull request, pre-CI. And then if all of those things pass, and security test passes, the pull request is squashed merged into master and triggers the CI build.

What it means is that in practice we will fail about one in four, one in five pull requests, but we'll only fail like one in 50, one in 100 of the CI builds. And then post-CI, we'll do a second round of testing through the REST APIs, with testing fake identities and so forth. And those we'll let on for an hour, and those all need to pass as well.

So by the time we hit production, we have had a very high confidence green signal on changes that are going out. And that really gives you the freedom to deploy frequently and it gives us the freedom to know that we can remediate quickly, in our case, across about 15 data centers worldwide.

**Paul:** One thing I find very interesting about this is that the way you're describing, it's a very integrated system. In my past life when I was at CircleCI we dealt with the GitHub ecosystem, lots of tools, very sharp tools that did one thing well. In my new startup, I'm very much more in the, "Let us make one tool that does everything and is awesome."

What's that experience like for your customers, for the people who are working on the system where you have that one holistic system? What can you do that you can't do the other way?

**Sam:** First of all, for us it's at both ends. We have 600-some marketplace partners. Edith's company LaunchDarkly is a great example of one of those.

**Paul:** I've heard of them.

**Edith:** Thanks for wearing the shirt.

**Sam:** You can think of this as a world with a whole bunch of coopetition. So if you want to use our hosted Git and then use CircleCI for the pipeline, that works. If you want to use GitHub and then use our CI/CD to deploy, that works great.

If you want to start a project called a DevOps project on Azure, it's VSTS underneath that's driving that. If you want to do our Kanban and then use GitHub or GitLab or anything else, and then our pipeline you can do all that mix and match.

The benefit of the mix and match is that if you have parts of the toolchain today, you don't need to switch. You can adopt the step-wise way. The benefit of offering both best of breed and highly integrated is that


<blockquote>for a customer who is new to a DevOps way of working, you can make one choice and try it, and you don't need to spend any time on stitching together your own toolchain. </blockquote>


**Edith:** This is definitely a shift from the Microsoft of the past.

**Sam:** Oh yeah. If you mean the Microsoft five years ago, it definitely is. I mean, one of the things I talked about yesterday at Index was our open source contributions. If you look at last year, 2017, the company with the highest number of contributors to open source on GitHub was Microsoft. And Google was a little bit behind, and then everyone else was way behind if you look at that.

So we're not just doing this in terms of sharing our own work internally. We're doing this in terms of sharing work with the community and GVFS, the Git Virtual File System, is a great example of something we open source.


<blockquote>If we're not the top, we're one of the top two contributors to Git, top three to Kubernetes and so forth. </blockquote>


**Edith:** You're pretty senior at Microsoft. I mean, I know you were, what led to this change of direction?

**Sam:** I think it's both top down and bottom up. For example, we had our "One ES Day" or One Engineering System Day internal conference last week.

**Edith:** So, by the way, this is such immense scale that 75,000 developers just using your own systems.

**Sam:** Yeah. I had a few VPs on this panel with me. One of them is Gabe Aul from Windows & Devices. He made a very clear point that the most important metric for them is engineering satisfaction with the engineering system. So in other words, how happy are you with the tools and process? And how much does it improve your work and is it better than three months ago? And so on.

That is for them the most important metric. He made the observation that not only is it going up, but it is also bimodal. And the younger or less tenured engineers are showing a much faster rise in stats than folks who've been around for a long time.

He said the folks who've been around for a long time are experiencing the "who moved my cheese?" Right? And the young ones are like, finally, you're working the way we thought we were supposed to work and this is what we want to do.


<blockquote>He pointed out, that's what we're optimizing for. We're optimizing for that next generation. </blockquote>


That's an example of the top-down leadership. The bottom is exactly that, this is how people want to work. They want to work with the new normal. The new normal is not that you click "File New" and get a website on your laptop. That was 20 years ago.

The new normal is that your "Hello World" includes a pipeline and is deploying, and that your next commit gets deployed. And that's how people start. So from day one, from the first few minutes, you want the pipeline as part of what you're doing.

**Paul:** It's really interesting, this way of viewing the world. Because the younger people vastly outnumber the older people. So the number of people who are coming into this industry now is at an all-time high.

I think I was reading recently the number of people who graduated boot camp last year. It was like 23,000. Where just typically about 50,000 people in the US graduate with CS in college.


<blockquote>We're maybe doubling the number of people who are roughly joining the industry every year. The people who had their cheese in the old place must be a tiny number. </blockquote>


I mean, it might be more that Microsoft is a tiny part of the industry relative to the immense people who are coming in now and who are familiar with the new way of doing things, they're being outbred almost.

**Sam:** Yeah, I think that's true, and that's true 10x if you look at it globally. In other words, if you look at the number of new CS graduates who are minted in China and countries that we used to call "emerging," they way outnumber the number who graduate in the US. And they expect to work this way too.

We can't myopically focus on the US or North America. We as a company have a majority of our business outside of the US. We need to play not just as a supplier but also as an employer and a contributor in all those markets. We hire there, we grow development centers there. We want to be the place where people want to be.

**Edith:** So your 75,000 developers, it just keeps coming back to us, that's a great quote, a great number. How do you then relate that? What works at Microsoft scale might not work for somebody smaller, or vice versa. Or I guess the bigger question is what do you see in amongst the base of how are people adopting continuous delivery in al these trends.

**Sam:** We have a principle we call "first party equals third party."


<blockquote>In other words, we try things on ourselves and make them work as part of our One Engineering System, and then take them to market through things like VSTS. </blockquote>


So I would not say that things that work for us don't work for people who are not at the same scale. There are some things we need to do because we're at bigger scale, that you don't need to do if you're five people.

**Edith:** Or even like 400.

**Sam:** Right, or 400. Absolutely true. But the case I always make is, look, we didn't start cloud-native. We have these long code lines. Including in my group, we started with an on-premise team foundation server, which was frankly written as a monolith. And we have been over years refactoring that into microservices.


<blockquote>It's slicing the elephant one piece at a time. And doing that forces us to have a certain discipline about picking the important problems first. </blockquote>


Now, I regularly meet with customers who are starting that journey, and I regularly make the point, "Look, here's what we did, and it wasn't all that unlike where you're starting now." And you don't need to say, "Oh, we can't get there."

I've heard all the skepticism, I've heard all the, "Throw it away and start over." We very much took an approach in our code base of saying, we're going to have one code base, develop cloud first, deliver continuously, have a sprintly release train that we publish.

We happen to do three-week sprints globally. We're in 131 now, and you can see everything we've done over the years and what's planned on the backlog in the docs. And you can see how our velocity is increasing with a sort of Moore's law effect.

The beauty of that is that I can say, look, our baby is ugly, too.


<blockquote>If you say your baby's ugly, you get the people to say, "Well, not really," right?</blockquote>


And you get to talk about your problems and you get to say, look, these things, here are some things that took years.

**Edith:** So you think having lived through this transformation yourself from monolith to microservices, from the legendary three-year Microsoft cycles, what you just said, you could have more empathy if it's not an overnight switch?

**Sam:** Right, it's not an overnight switch. I have a ton of empathy for folks who are doing this. I have a ton of empathy for the change agents in enterprises who are trying to get them to recognize that they are software companies and they need to behave like software companies.

I have a lot of visits from companies who do the West Coast tour and ask, "Well, how do you work? Show us what you do so we can learn from it." And a lot of empathy for customers who are saying, "We don't know where to start."

**Edith:** Yeah.

**Paul:** You hear people talk about the complexity of where the DevOps world has gotten to be. And you talked earlier about you're starting Hello World in this pipeline image. Versus maybe 20 years ago when you started Hello Worldt it was File New Project and you compiled that a minute later and it ran in your machine.

So how did those people, when they're doing their West Coast tour and we show them, "Well, all you need to do for this microservice world is set up Kubernetes and set up pipelines and set up all this complexity." I suppose, how do we tell them in a straight face that it's a better way to be?

**Sam:** Well, let's go to the Hello World part of the question first, okay? So today, I can't demo this on a podcast, but you can literally start at the Azure portal, click the plus sign for "create a new resource," click DevOps Project, and you then choose what technology do you want to work with, Java, Node, .NET, Python, etc.

Based on that, then what framework do you want, if it's Java you got to pick Spring or something else. If it's Node you get to pick Express or something else, or whatever. And then do you want this on, do you want this containerized on Linux, do you want this on straight Windows VM? And then you identify which account, and you click Start, and in four minutes you have a Hello World site that is deployed in the cloud running.

**Paul:** With end-to-end everything.

**Sam:** With code in front of you. Editable if you edit the code and make a new commit, you'll see it when you refresh the website. That we think is the new normal Hello World.

**Edith:** And it stands in some ways that's best better than what we did 20 years ago when we might have had built something in Visual Basic but we didn't know how to build an installer.

**Sam:** Right.

**Edith:** Like, you might have something that could run locally but you still had to do all those steps just to get it off your machine that were actually pretty hard.

**Paul:** To get this to another human.

**Sam:** Right. Well, there's this thing in the theory of constraints about attacking the next bottleneck, "elevate the constraint as a legal route." And 20 years ago, the constraint was getting the hardware. And getting it set up, and getting the networking set up and all this other crap.

**Edith:** Yeah.

**Sam:** So the fact that it took a while to package the app for deployment was not the big deal, okay? Today the infrastructure is available, it's flexible, it's instant. Right? That constraint is gone.

**Edith:** Well, I remember we used to just have the installer team.

**Sam:** Yeah.

**Edith:** Like, you had a team who would build the nice installer.

**Sam:** Yeah. What a ridiculous thing.

**Edith:** I mean, yeah. And it's like, well yes, it is harder to get it a Hello World going, but like to have somebody else see it you've already felt that that pain is gone.

**Sam:** Yeah. I mean, the more you get out of the cruft of these handoffs of specializations that are there to overcome the ways of the process, the more you get that direct contact between developer and end user.

And that really is what is, I think, driving this industry, I think that's what's so exciting about the new generation that we're bringing in to this industry, because what they are experiencing is the chance to make a difference now.

**Paul:** Put something in front of a customer.

**Sam:** Right, yeah. Do something in minutes, do more in hours. Whereas, in the past, months just to get a deployment. I thought it was ridiculous.

**Edith:** Because you had to worry about somebody going and getting your ZIP or your TAR file. And you hope that they could install it, if they had to put on their own database or they're in a hardware you had to worry about all that getting configured too.

**Sam:** Right. And so what happened in the old days is you basically had developers discovering that they wanted to work faster. In 2001 we have Agile Manifesto, but we still had ITIL which basically was how you prevent change in operations.

Then maybe 2007 or something like that, we started having agile admin and then that morphed into DevOps. And so we're now with DevOps maybe where we were with Agile in 2010.

**Edith:** I agree.

**Sam:** And if you think about it from a technology lifecycle adoption perspective, at the point where the early majority is saying, "Wait a minute, this obviously works. And we can obviously derive benefit from this and we will disrupt or be disrupted."

**Edith:** Yeah.

**Sam:** And they see that. The other thing that they see correctly is that this acceleration in the world is leading to a shortening of the value of any particular choice you make today.


<blockquote>The lifecycle of your product or your service today is a lot shorter than it was a decade ago. </blockquote>


**Edith:** Yeah.

**Sam:** The business consequence of that is you need to be able to make decisions about whether to persevere or pivot, much, much, more frequently.

So effectively, the pace at which you can get the feedback from what's really performing, performing in the sense of people are using and liking and recommending, and performing in the sense of the quality of service you're delivering,


<blockquote>the more quickly you can get that feedback loop and act on that feedback loop, the more opportunities you have to learn or succeed. </blockquote>


**Paul:** Let me ask you about that. We've been talking about this and One Engineering System or whatever, set of 8 or 10 tools which sort of together form the set of things you need to do to iterate rapidly and to go to market faster. And my question is, are we done?

What I mean by that is, are there some sort of complexity that comes from this knowing how to build the pipelines and Kubernetes and Kafka or whatever else you need to build the whole thing?

**Edith:** Did you say Kafka or Kafkan?

**Paul:** I said Kafka. But just the tools that are involved in bringing a product to market today, in an Agile way. And they've sprung up and gotten larger and so on over the last 10 years, but is that going to keep going?

Are we going to see more and more tools that we need to fit into that thing? If you have feature flags and you have CI and you have code hosting and you have Python and Django or whatever, are you kind of done?

Or, I'll tell you one tool that I saw today, it was launched on Hacker News or something, it was an edge delivery system for machine learning. Just one of the random dev tools that sort of launch every day.

Is this one of the tools that is eventually going to find its way into when you start a project you need an edge deployment tool for machine learning as part of your pipeline as well? And so are we going to see over the next 10 years a sort of an explosion in what we call or what we think of as the One System of what we need to build quickly?

**Sam:** I think the pace of innovation and disruption is going to continue to accelerate.

**Paul:** For dev teams too?

**Sam:** Yes.


<blockquote>I think that today's core that is differentiating, becomes tomorrow's context.And I think that that happens ever more quickly. </blockquote>


A great example, you talked about machine learning at the edge. Well, in fact what people are doing is they're trying to combine lightweight machine learning at the edge with deep learning at the service. The compute's becoming more available, so the amount of data is growing at exponential rates and the amount of learning that happens off of that is growing much more.

So people try to do things they never could do before, that kind of change, I think, is not going to slow down. Now, I do think on the principle of today's core becomes tomorrow's context, the things that you worry about in terms of where we need to differentiate, where we need to be better, where we need to pick up the best thing, that does change.

I basically think that people aren't going to be arguing about continuous delivery pipeline--

**Paul:** Sure, the need for CI, the need for feature flags.

**Edith:** Yeah, it'll just be assumed.

**Sam:** But the kinds of things they're going to be doing, horrifically larger volumes of data and the kinds of computing they're going to try to do where it's really the data that's determining what you're doing, that will be different.

**Paul:** So how are we going to manage this sort of complexity? Like, for a developer, if we just keep jamming in new services and new things that we need to be able to do but we're not, we're elevating the context or certain sense that, what was it, today's something is tomorrow's context?

**Sam:** Today's core is tomorrow's context.

**Paul:** Today's core is tomorrow's context. Well, tomorrow's core is the next day's context.

**Sam:** That's correct.

**Paul:** And now we've got so many things that we need to know in order to be able to deliver a service, are we sort of painting ourselves into a corner and how do we manage that complexity?

**Sam:** If you have to know a lot to do the basics, you're wasting your time learning the wrong stuff, okay? You asked about the toolchain thing. I think the time spent cobbling together a toolchain when you don't need to spend it on that is--

**Paul:** You still need to be aware of all the components in the toolchain.

**Edith:** Do you? I mean like--

**Paul:** Can you build feature flags if you don't first learn about a feature flag? Or what the elements of the pipeline are?

**Sam:** This is a great example. You talk about feature flags, how many people today know how to do meaningful metrics? So one of the learnings--

**Paul:** Far fewer than think they can.

**Sam:** Right. Exactly.


<blockquote>One of the significant learnings is that designing good metrics is as difficultas designing good features. </blockquote>


The metrics that you need to drive your business change and you need to be able to respond and adapt at that level of, frankly, business KPIs with this rapidity too.

Now, do I need to know that behind the feature flags there's a CDN that is giving me so many milliseconds of performance advantage, and allowing both code paths to coexist, and that that gets multiplied in this combinatorial metrics, and be able to keep all that in my head? No.

I do need to be able to capture the trace when there's a live site incident. I do need to be able to manage the feature flag in real-time. I do need to be good at formulating the hypothesis that motivate the things that I want to put behind those feature flags.

That is new learning, new muscle, new skills that we need to do. Those are moves in tomorrow's Olympics that you're not seeing on the slopes today.

**Edith:** That's a triple axel or that's the quintuple axel to today's triple lutz.

**Sam:** Right. I mean, you see these things that,


<blockquote>if you look at the Olympics today versus 20 years ago or what have you, you see people doing stuff that no one would've dreamed of. And I think in the case of our industry, it's more dramatic. </blockquote>


When people are able to talk about computational biology machine assisted medical diagnosis, when you have speech as a service, image recognition as a service, all these possibilities start opening up that we're not there before.

**Edith:** Yeah.

**Paul:** So do you see that, in like 10 years time, in the Visual Studio Team Services, is going to have those things as the core feature set?

**Sam:** I don't know what the product name will be.

**Paul:** Sure, sure.

**Sam:** Or I don't know what mix will be. I do think people will be using services in 10 years that we cannot imagine today. I think that the expectation for what computers will do in 10 years or, computers is a bad word, for what devices will do in 10 years, is wildly different.

I mean, 10 years ago, a mobile phone could do voice and maybe SMS messaging, today when people are saying, let me get my phone, what are they doing? They're ordering a ride on Lyft, they're sharing photos, they're using apps that if you talked about 10 years ago, people would've just thought you're nuts.

Then you get into the whole IoT transformation and what that will do to the computing model. And that's clearly breeding this intelligent edge and intelligent cloud combination and that will breed a whole new way of working. And the challenges we're going to deal with are not going to be stitching together our authentication credentials for these different tools--

**Paul:** I mean, we still need to do that.

**Sam:** We'll need to have secure authentication.

**Paul:** So you think we'll build better abstractions for the things that we have today?

**Edith:** Yes.

**Sam:** I think that the stuff today where you start by learning how to use SSH keys and how you deal with paths and all that kind of stuff.

**Paul:** Right.

**Sam:** It's like, we're going to get over that. We'll get the identity and authentication figured out. And I certainly hope we get down, in that world distinguishing humans from non-human identities.

**Edith:** Well, that's what you say as a human.

**Sam:** That's what I say as a human, you're right. I mean, there's stuff like the, what's the new Dan Brown book which essentially is about the AI emergence and the plot revolves around essentially the computer outsmarting its master?

**Edith:** Yeah. I mean, that's Terminator.

**Sam:** Yeah.

**Paul:** I felt like I've read a hundred of these books.

**Sam:** That's kind of the scary side of it.

**Paul:** I assume the AI is going to look at how to set up its SSH keys and the path and then start learning about Kubernetes and be like, "I'm actually not going to do this, this doesn't seem worth it."

**Sam:** It's going to become, it'll be plumbing taken care of for you.

**Edith:** Yeah, that's my theory. We talked about the way-off future, I love the way you framed it in terms of the early majority. What's your message to the people behind the early majority?

**Sam:** One of the things that put up on the web is [Devopsassessment.net](https://devopsassessment.net/), and it's a self-service tool to figure out how your performance is and where your bottlenecks are and where you might improve.

E- You have to care to even take this.

**Sam:** Agreed. Okay, so creative destruction is a fact of the way our economy works, right? It is, and I don't mean this as, I don't pretend to be a libertarian, I don't pretend to be a believer that regulation is bad or what have you. But if you take something like the Fortune 100 list or you take any other ranking of companies, the longevity of companies on that list goes down every year.

So they get replaced and value shifts to the innovators. Now, the folks who were trailing behind can say, "We're not bothered by this," or they can say, "We need to change because this is where value gets created."

Now, I think the dark underbelly of this is that a lot of people instead of saying we need to change and we have the power, say, "We see change and we feel threatened." And we get into the totally dysfunctional politics that we have today around the globe, because people feel threatened by the rate of change.


<blockquote>Again, I think there are many points of light in this, where instead of being a victim of change you can be an enabler of change. And my message to people,open your eyes, recognize what you don't know. </blockquote>


There was a great, great, great HBR article and then became a book called [The Real Reason People Won't Change](https://hbr.org/2001/11/the-real-reason-people-wont-change). Authors were Kegan and Lahey who were, I think, two Harvard professors in psychology or something like that. Just read the article form from HBR. You don't need the book.

Essentially, what they talk about is stages of maturity and self-awareness. And that people don't change because of a fear, and a fear that is not recognized. And their whole technique is to bring that fear to consciousness.

"What are you really afraid of? And what would be the worst thing that would happen?" You can think of it as the Toyota Five Whys, but instead the "Five What-ifs." And you confront, "What if you do nothing as opposed to what if you take action?"

**Edith:** Yeah, the lack of a decision is a decision.

**Sam:** Exactly.

**Edith:** The lack of a decision is just saying, "Hey, I'm just going to be doing this."

**Sam:** Yeah. This is the victim-enabler-triangle thing. Are you going to frame the world as a place that does stuff to you, or are you going to frame it as a place where you can do things? And if you just flip that perspective, you'll discover you can do things.

Other people have done things, you can learn from that. You can experiment,


<blockquote>you can treat experiments not as things from which you fail but things from which you learn. </blockquote>


**Edith:** I think that's such a great note to end on.

**Paul:** Yeah, that is wonderful.

**Edith:** Any final, final thoughts, Sam?

**Sam:** Thank you for having me.

**Edith:** It's so wonderful to have you.

**Sam:** You guys are really great. And it's so much fun to be here. It's been such a beautiful week here. Thank you.

**Edith:** It's great to have you.














