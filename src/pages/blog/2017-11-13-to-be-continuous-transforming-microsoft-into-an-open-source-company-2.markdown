---
author: andreaech
comments: false
date: 2017-11-13 21:19:54+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-transforming-microsoft-into-an-open-source-company-2/
slug: to-be-continuous-transforming-microsoft-into-an-open-source-company-2
title: 'To Be Continuous: Getting Acquired, Founder Conviction, DevOps in Continuous
  Delivery'
wordpress_id: 2155
categories:
- To Be Continuous
tags:
- continuous delivery
- DevOps
- early stage founders
- Keith Ballinger
- Thomas Dohmke
- To Be Continuous
---



In this episode of To Be Continuous, Edith and Paul are joined by Keith Ballinger and Thomas Dohmke from Microsoft. They share their experience of being acquired by Microsoft and discuss the role of DevOps in the continuous delivery process. They then consider the importance of balancing founder convictions of product value and how the world is changing, with necessary market validation activities. Keith also shares his thoughts on why early-stage founders should ignore larger companies for as long as possible, focusing instead on building their business.




This is episode #40 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->

This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.

﻿<span data-mce-type="bookmark" style="display: inline-block; width: 0px; overflow: hidden; line-height: 0;" class="mce_SELRES_start">﻿</span>





**ABOUT THE GUESTS**







[**Keith Ballinger:**](https://twitter.com/KeithBa) is Director of Program Management at Microsoft. Keith manages teams building mobile cloud services including Visual Studio Mobile Center. Prior to Microsoft, Keith was VP of Product at Xamarin, a company that was aquired by Microsoft in 2016.

[**Thomas Dohmke:**](https://twitter.com/ashtom) is Principal Group Program Manager at Microsoft. He joined Microsoft through the acquisition of HockeyApp, which he co-founded and ran as the CEO. Prior to HockeyApp Thomas co-founded Codenauts and worked as a freelancer software developer at MTV Networks Germany.


**TRANSCRIPT**







**Paul Biggar:** Okay, so what is the worst part about being acquired?

**Keith Ballinger:** I would say the worst part about being acquired is there's always a tremendous amount of due diligence, and often times, there's an office move and new computers and new policies and new HR departments. And all of that feels like a headache versus just building really fun software.

**Thomas Dohmke:** I would say the worst part is the balance between the due diligence process, talking with lawyers and tax consultants, and then at the same time, with the team. They naturally don't know everything, so you have to kind of balance that out. You want to give them as much information as you can, at the same time not stress them out with the future that's unknown to them. That's stressed me out as a founder very much for a long time during the acquisition phase.

**Edith Harbaugh:** Now would be a great time for our guests to introduce themselves. We're podcasting for Microsoft Build, Microsoft's developer conference, and we have two people who've been acquired.

**Thomas: **Hey, I'm Thomas, Thomas Dohmke. I'm from Germany. I'm the co-founder of HockeyApp. I used to be the CEO of HockeyApp. As part of the acquisition, I moved from Stuttgart, Germany to Seattle, and I'm now the GPM at Microsoft for Mobile Center, and I work with Keith.

**Keith: **And Keith Ballinger. I was the VP of product at Xamarin, which was acquired last year. I luckily got to stay in San Francisco. Me and Thomas got together after the acquisition, and we built Mobile Center with a bunch of other cool people.

**Thomas: **I don't know why you say luckily. Seattle is so much nicer than San Francisco.

**Keith: **We just have to agree to disagree on the Seattle versus San Francisco thing.

**Thomas: **It's so awesome, they built it this year in Seattle because it's a 10-minute drive for me. It's just nice at a conference to go home with now too.

**Edith: **So you prefer Seattle to San Francisco.

**Thomas: **I guess it depends on your life situation. I have family, and so if you have wife and kids, I prefer Seattle or Bellevue or the east side really of the Seattle metropolitan area over San Francisco.

**Keith: **And I just love cities. I was raised in a small town, and so then once I was an adult, I always lived in cities. I've lived in, you know, downtown LA and downtown Boston. I lived in Singapore for a while, so. Downtown San Francisco, which is where I live now, is like perfect for me. I'm literally a block from the Twitter building, which is where our offices are as well.

**Paul: **Are you in that shiny NEMA building?

**Keith: **Right next to the NEMA building. I don't live in the NEMA building. I'm actually on the other side in like eighth and Mission.

**Edith: **So I'm very familiar with that building because I have my own startup, and we sat with Yammer for six months.

**Keith: **Oh nice! Did you use them to help you figure out what kind of product you were going to build?

**Edith: **Just method time, the accelerator I was in got a deal where we all got desk space at Yammer.

**Keith: **Oh nice.

**Edith: **And eventually this ended, but I took full advantage of it while I was there.

**Keith: **There's a startup in San Francisco called Lever that does HR recruiting. And they started by embedding themselves with the Twitter people, and just watching how Twitter did recruiting, and they did it for like six months. And that's how they ended up building Lever.

**Edith: **Oh cool, yeah I think there's a lot to be said of being with your actual customers.

**Keith: **Yeah absolutely. No one's ever explicitly told me this wouldn't be allowed, but


<blockquote>I would love if we had a policy actually where we could invite startups to co-exist with us. </blockquote>


**Paul: **Heroku did at this at the very start they had a space in their office where their customers who were generally very small early stage startups would come in and they could observe them in their natural habitats.

**Keith: **Yeah, that's fantastic, right? We've talked a lot about at least maybe bringing in mobile developers for you know longer than an hour. Like maybe "hey hang out with us for a half a day, or three days or a week, and we just kind of want to watch you," without that sounding too creepy. But if anybody's listening to this, shoot me an email and you know I'd love to have you come over and just watch you code for a while.

**Paul: **So it's interesting, I'm starting a new company at the moment and it's in the DevTools space. And one of the plans that we have is to sort of consider it to be as sort of a VC backed social club to a certain extent. So that we always have customers, or potential customers and sort of community around a lot in the early days as opposed to like not very much.


<blockquote>So instead of throwing it over a wall and announcing it, we want to say, "here's what I worked on today, what do you think of this?" "Well it's obviously stupid." And that's the kind of feedback that I want to hear today. Not three months time when we're fully in on it. </blockquote>


**Edith: **Yeah like when we were starting our product, our early customers were literally the desk over.

**Keith: **That's perfect.

**Edith: **Yeah, well it was perfect for us because we could go bully them, like hey why haven't you installed our SDK yet?

**Keith: **Well they get then really great tech support right? That's one of the things I like about Intercom, which we use on Mobile Center is we are constantly interacting with our customers at the moment of them hitting friction, and I think that lets you connect with them in a way as if they're at the desk with you. It's really you're at their desk. I just find that to be like such a high volume, or like what's the right, there's a lot of signal to that kind of interaction.

**Edith: **How do you sustain using Intercom at such a high level of developers as you have at Xamarin?

**Keith: **None of us sleep, which I think's the big deal.

**Thomas: **Sleep is overrated.

**Keith: **Yeah, so we just keep at it. So we don't use Intercom for the Xamarin platform product, and that's built into Visual Studio and Visual Studio for Mac. And there's no Intercom usage in that space, but for Mobile Center, since it's like a website, it's a SaaS service, we're able to pop the blue button there, and have those conversations.

**Paul: **Intercom must be something very special for Microsoft people because this is the second podcast we've had today where people have name dropped Intercom, and I don't think anyone has name dropped a single other SaaS product the whole day.

**Edith: **Well you name dropped LaunchDarkly.

**Paul: **LaunchDarkly of course, LaunchDarkly is a very important startup that we always talk about.

**Keith: **I think the reason Intercom gets name dropped is it's such a great way to talk to customers that I just love it. I don't have any problems with Intercom, it's not like I'm using Intercom and I really wish I had a better solution, and I'm just putting up with it, you know it's none of things.

**Paul: **That never happens, like every product that I use I hate.

**Edith: **Do you think that's the products, or you Paul?

**Paul: **I think it is the nature of software. Nothing is ever right, so if you've ever found a product that's fully right, then either you wrote it yourself for yourself, or it's kind of amazing, which I think Intercom must be in the latter camp.

**Edith: **I met some customers at a lunch Tuesday and I asked them for feedback and they're like no we just love it.

**Paul: **They're lying to you.

**Edith: **No I pushed them, I pushed them!

**Paul: **It's great, we love LaunchDarkly But I'm sure that your customers have something they hate and so they're lying to you.

**Thomas: **I think the thing with Intercom is that it's not getting in the way. And especially you know we mentioned Microsoft, mentioned it twice today, it's the classic Microsoft is an MSTN forum or TechNet or the real classic high scale customer support, we pay thousands of dollars per month. And the PM's and the developers have no direct contact with the customer, they're talking to the support engineer.

And then support engineer talks with the customer. Intercom doesn't get in the way, it's in the product, we get directly to talk to the customers so it moves us from this big company org chart into a startup culture, and that's why I think many Microsoft teams are looking for that solution and name dropping it because it really enables them to directly engage with and get the feedback that they need to improve the product.

**Edith: **How logistically if you're getting you know, people chatting with you all the time, how do you staff and manage that?

**Keith: **Yeah that's a good question and we struggle with that, because in fact the one downside we have with Intercom now is that occasionally customers will complain to us that no one's replied to their chat within the timeframe that they expected, and because it feels like real time chat you expect an answer really quickly.

**Edith: **Yeah.

**Keith: **You know, and intercom I think is addressing that, they're creating tooling around giving people an idea of when the reply will come and those kinds of things, but it is a real struggle. Now we have teams in South Korea, Redmond, San Francisco, Denmark, and then a few other developers in like India and other places.

**Thomas: **Germany.

**Keith: **So we have pretty good coverage around the globe, but as we scale up, you still kind of hit pockets of where there's just no one awake who can answer this person's question right now, and that is the downside, but it's just the upside is so worth it, you've got to go with it right?

**Paul: **Yeah. The problem of course is that when they've been waiting 10 minutes in Intercom the next step is to go to Twitter, and looking for support on Twitter is not nearly as pleasant sounding.

**Keith: **No


<blockquote>We incentivize people to be really mean. If you ask a polite question on Twitter to whatever brand or company you have, you might get a response. But if you say something about how you know terrible they are, and how you're going to uninstall their thing or ask for a refund, your tweet is the more likely you are to get a response quicker. </blockquote>


And so we've incentivized this behavior.

**Paul: **Even a pleasant question sounds unpleasant due to the forum that you ask it in. If someone is like standing up in your developer thing is like saying, your attention please, your attention please why can't we have this feature? It doesn't sound like a very pleasant feature request like it would be if they send you a private note, " oh I can't wait to get this."

**Keith: **Absolutely, and when it's private you can be more liberal in how you answer right?

**Paul: **Yeah.

**Keith: **Like there are times when you're not doing a feature for some reason that has nothing to do with, you know, satisfying users, there's like a internal company politics issue, or there's like a partnership that you want to announce that you haven't announced yet. There's all kinds of things like that. And if it's one on one, you can just say "listen I can't do this because of x y and z," but you're not going to say that on Twitter.

**Thomas: **I would argue though that public also enables other people to respond to those customers, right, like at HockeyApp we always did our own support, and we had forum not Intercom and so it had a private mode and a public mode, and so it scales fairly well as long as you have the public option because then people can help other people.

**Keith:**


<blockquote>We had two forums, we had the public forums, and we had like MVP insider forums. Anybody who's super active and was really into the product, we kind of bring into that insider forum.</blockquote>


There would be other experts there, there are all kind of like, you know they all want to have a great reputation with that community, and at the same time you could have more authentic conversations versus something that is very public.

**Thomas: **We have a public Slack for HockeyApp customers in our mobile site. And we have our private fanboys who defend us against criticism. Or just saying "hey you know have you seen that blog post, they announced it last week." And so it's kind of like a trade off between being open and honest about support, and having criticism from customers.

**Keith: **It's interesting that we're talking about this, because this is all about customer feedback right.

**Edith: **Yep.

**Keith: **And customer feedback, at least for me, is kind of like the final stage of continuous delivery, or of DevOps, it's like the whole point is to get more feedback more quickly.

**Edith: **Yeah.

**Keith: **And it's, to my knowledge I don't think I generally have seen people describing DevOps with intercom as the final step. But in many ways that's what you want. You want that really high fidelity communication because you're shipping all the time right.

**Edith: **Yeah.

**Keith: **It's fascinating to be that it's that is the part that we never talk about when we talk about continuous delivery.

**Thomas: **And it's not only the final stage right, it's also the initial driver for many companies.

**Keith: **Yes.

**Thomas: **Because you only start thinking about DevOps after you had a big outage, bad feedback, one-star ratings, right that's kind of like driving you into a DevOp process, and you're right it's closing the loop. Without feedback you cannot have continuous delivery.

**Keith: **Yeah well there's just no point.

**Edith:**


<blockquote>I have a diagram and its a continual circle and as a software company, you're always somewhere in that circle. You're always either getting feedback or shipping a feature. And you just want to make these circles as tight as possible.</blockquote>


**Keith: **Exactly. Yeah you want to go through that circle multiple times a day.

**Edith: **Yeah.

**Paul: **We were very very early intercom customers, like the private beta sort of thing. And we integrated a lot of customer communications that we didn't have because we needed that information filtered back into intercom. So like a ton of fields of our user model only existed to get data into intercom so that we could give people better feedback and better customization.

**Keith: **Yeah I think that's something we've thought a lot about is how can we do those same kind of things with intercom. But I think every developer must be thinking about this. We have, there's a future in HockeyApp that you know which is feedback. And a beta-user, it's for beta-users mostly right, and you want that feedback from your end user. You want to get it into your system, you want to see it, and you want to see it you know both in a qualitative way, you want to see what the words people wrote are, but you also want some kind of quantitative aspect to it right.

We do a lot of this at Microsoft with NPS scores, where we'll ask people after certain triggered events you know the whole zero to 10 would you recommend this. And I mean I found, we did that at Xamarin too before we were acquired, it was easily one of the best ways to quantitatively measure how our customers were responding to new releases.

**Edith: **That's interesting, we do our NPS surveys but we deliberately do it as an email because we don't want it to be triggered on a certain feature. I want it to be about the overall, holistic experience with out product.

**Keith: **At Xamarin we always did it as an email survey as well, and at Microsoft in general we tend to focus on the in-app experience instead. And I think there's pros and cons to both points.

**Edith: **I think any time you as a customer their opinion it's good I just want to hear more about the feedback you got when you were doing it in app.

**Thomas: **Who wants more emails though, right.

**Edith: **I do.

**Keith: **You can also do it unintrusively right. So we, in HockeyApp, when we asked for the NPS score, it's a little kind of toast at the bottom.

**Thomas: **Yeah


<blockquote>The NPS survey is a footer. The footer expands a little bit by 50 pixels or so. It says "hey do you want to vote?". If you don't want to vote you literally stay in your experience because it's just a footer. </blockquote>


**Keith: **I think the thing I've seen that's different between email surveys and in-app experiences, is email surveys will capture people who've churned out and then they'll tell you the really negative reason they've churned out.

**Edith: **Which is what you wanna know.

**Keith: **Yes you want to know those things right. The in-app one is how do I take, someone who's either feeling okay, all the way to fan and how do I amplify that. Which is two different things. And as a product owner you have to decide which one you want right. Do I want to go fix all the churn problems or do I want to take my fans and make them even bigger fans.

And you do have to kind of decide which of those two you're investing in. And how you get that NPS data, or even if you're doing both, which ones you're going to listen to are going to kind of dictate those investments right.

**Edith: **Well yeah I mean that's a classic product owner's dilemma of install base versus net new.

**Keith: **Yeah.

**Paul: **So the problem that I have with qualitative feedback like that. And this is I think a common pattern in new companies or new divisions where if you're good, you have some sort of natural talent at some particular aspect of the company, you'll be really late in developing that and sort of making a department around it, making it sort of systematic.

I think that's really true with let's say using intercom or getting qualitative feedback that you get so used to having these great customer interactions, right where you answer their questions and you're really happy that you're sort of slow to build out docs and overall sort of community stuff because you're really just enjoying this one on one interaction, and enjoying the feedback that you get from that.

That's kind of my one downside, I don't think it's a downside within the company per se, but it's just like a company has to realize as they grow that you want to be more systematic about things.

**Thomas: **Well the other danger there is that you go in the wrong direction, right. You get like five people feedback, and they all tell you something, and then later, like a year later you realize they gave you good feedback, but that's not where you want to grow the company. And you build a feature then for them that's not really helping you with your mission.

**Paul: **Right. Yeah you definitely need to be reaching at and talking to all the people who who have no sort of like, problems with your company. It's like what are you, what are you trying to achieve? Because you only hear from the people who are saying, "this is a problem right now."

**Edith: **This is why product management is hard.

**Keith: **Yes absolutely, this is the heart of the problem, right. I would say that one thing I do see a lot of in Intercom is just messages of delight, right. We do get a lot of high, "oh my god that worked" or you know things like that. So I don't know how to react to those though, other than to say thank you. Like I don't know how to translate that into a bug fix or a new feature or whatever, when someone just gives you positive feedback.

But I mean that's like a general problem I think with any human relationship right. If someone tells you you're awesome, it makes you feel good, but it's not like, it's not like you changed anything about the way you're behaving.

**Paul: **Yeah, well we always say thanks we'll relay it to the team and then post a screenshot in Slack of like, customer said this particular feature was great. The team that built that feature feel good about yourselves.

**Keith: **Yeah and that's a good point, it is very motivating at the very least right.

**Edith: **Yeah, now that we're into it I'd love to hear, I mean you both were part of very successful startups. How are some of the ways that you took in user feedback when you were early, and used them to improve your product?

**Keith: **Well I would say I've started a lot of unsuccessful startups. I joined Xamarin just to be clear. I consulted with them in their early days, because I was part of the original team that built .NET and C# at Microsoft. And then I officially joined as the VP of product you know, a couple of years into Xamarin's life cycle. So in terms of, I can tell you all the unsuccessful ways to start a startup, you need someone like Thomas or Nat at Miguel to tell you how to be a successful founder.

**Paul: **Well the unsuccessful is interesting. What's the biggest, not the biggest failure but the biggest negative pattern?

**Keith: **By far I think


<blockquote>The thing that is best at leading you to failure is assuming you're right, and not being skeptical of your own decisions, and never doing the kind of iterations and experiments, and customer interviews that lead you to that path. </blockquote>


**Paul: **Are you sure you're right about that?

**Keith: **I mean, I'm not sure I'm right about that that's the problem right? At this point, at this point I'm skeptical of everything I know.

**Edith: **You do basically like the X-Files.

**Keith: **Yes you have to be, you have to question everything. Absolutely.

**Edith: **Trust no one.

**Keith: **Absolutely believe that.

**Paul: **This is a huge challenge for me at the moment because I'm developing a new product, and you have these things that you believe about the world, but then you also want to question everything you believe about the world, and it ends up being like, you have to have some sort of conviction as a founder of the path you want to go down.

**Keith: **As a VC backed founder, I think our ecosystem is designed for that because what you have is the VC wants lots of people with conviction, and then they're making a spread of bets where if each bet they're making should be 100% convicted on their belief--

**Paul: **Probably not 100%.

**Keith: **Well you know to a very strong degree because some of those will work, some of them won't, but if you invest in a bunch of people who are very, you know, wiffly-waffly about their beliefs, you could easily see them all spin-out and not get anywhere. But as a founder you know that doesn't necessarily help you.

**Paul: **As a founder you need to validate your beliefs as cheaply as possible generally.

**Keith: **Yes.

**Paul: **But


<blockquote>You also need to have some beliefs where you say, "this has been invalidated by the market." But the thing that we're going to do differently is tell the market how wrong they are about this, we're going to show them how amazing that this particular thing that we're going to build is. </blockquote>


**Thomas: **When you said you know the biggest mistake is that you believe you were right, but then if you look at Xamarin, I'm sure Miguel and Nat thought that Mono was the right thing to do for native development, right? We certainly believe that HockeyApp is the right thing. We built it for ourselves, and we strongly believe that this is the right thing to do, and then you ask about customer feedback.

Well the customer feedback kind of helped us to validate whether your hypothesis, but even more so they became our biggest fan base and helped us to grow the product in a vital fashion, right. Like you said you know people saying Intercom you're awesome that doesn't really help us, I would say that helped us a lot, right because they say you're awesome and then they go to Cocoaheads, or the what was it back then, the Android community meetup in Frankfurt.

And they tell the guys next to the table, and you know what they work they are just the same kind of young developers, but they work at the German telecom or some bigger company, and they bring that, oh I heard they're awesome let's try them out with them back into the company.

**Paul: **So I think this is actually really key because the, at the start the whole point of being a startup is that you're doing something new, and so when you're doing it for the first time everyone is going to be like that's obviously a fucking stupid idea.

**Edith: **That's what Paul told me.

**Paul: **Exactly, and so you need to ignore a lot of those people who say it's stupid and listen for those couple of people who actually go "this is wow", and like what is it about these people that makes them wow. How can we double down on the thing that made them wow? How can we find more of the people like them who think about what is wow?

**Keith: **Yeah so I think you're on the right path. I think the revision to my statement that I would make is, it would be thinking you're right about the solution.

I think the thing that you do have to have conviction on is what the problem is. If you truly believe that it's really hard to get, you know, your app builds to beta testers, that's a problem. How you solve it, you have to be open to.

**Paul:**


<blockquote>I think the thing that you need conviction about is how the world is going to change. So when we were starting Circle CI, one of the convictions was everything is moving to the cloud. </blockquote>


And everyone did tell us at the start, everyone we tried to be customers it's like, we're not taking our source code and giving it to a third party service in the cloud.

**Thomas: **They still do right? We had that at our session today too.

**Paul: **Yeah, but they were wrong, and we had this conviction that this is something that people are going to do, and we had evidence. We looked at Heroku, we looked at GitHub, we saw this is the way that world is going. And so we had to continue in the face of all those people saying you're wrong, and it turns out that later those people relented when our name got big enough. Once we got big enough to overcome their security concerns it was fine.

**Keith: **But I do think there's like a danger in this thinking that at least people have to be aware of. Which is if I'm a, if I'm 25 years old, and I just spend a couple years at Facebook or Google or wherever and I'm going to go do a startup, you hear lots of success stories. You hear you talking about Circle CI, you hear Thomas, you hear Nat, you hear all these success stories, you don't hear from the 999 other people who were just as convicted, but they were wrong. It's a binary outcome.

**Edith: **You can be completely full of conviction, and then march off a cliff.

**Keith: **So you need the tools, you need the tools to get past that point.

**Paul: **Oh yeah absolutely, I think I think what I'm trying to say is that there's a certain amount of belief about the world that you need to stick with and for sure question it. But like try to understand why it is that you are convinced of this. Try to dissuade yourself from it for sure, even if the only purpose of that is to become more convinced yourself.

**Keith: **I believe that. I mean Thomas, did you build HockeyApp for yourself?

**Thomas: **Yes, we did.

**Keith: **That I think is the best thing you can do.

**Thomas: **And we were four founders, two were indie developers having their own apps, and then me and Stefan we were contract developers for media companies. So we had the two angles. The guys that had their own apps in the app store, and then the guys that were creating apps for agencies, and for big media companies. And we built it because we had to solve a problem for us.

**Keith: **That is the best non-mistake you can make.

**Paul: **Let me put a caveat of that, which I think that's only true in B2B. You get people building for themselves in to B2C, and just being so so wrong.

**Keith: **No I believe that.

**Edith: **Or even in B2B you can get stuck in the trap of like, you think every dev shop is like your own when really it's not.

**Keith: **Yeah that's true, I mean you may end up building something for a very small market. But I do think if you build something for yourself that actually solves real problem and you end up using it everyday, you will have some amount of market. Now if it turns out that you are a, you know, I don't know, a closure developer, and closure just never takes off, you may end up in a world where no one uses your stuff.

**Paul: **How dare you.

**Keith: **I love closure. Full disclosure, one of Paul's former employees actually taught me closure, and I love it to death. So I owe Paul, he's like my grandfather of closure in this.

**Edith: **We just traced the, we traced the lineage of closure.

**Keith: **Yeah exactly.

**Edith: **I didn't realize you knew that, I thought you were just picking a random language.

**Keith: **No I was speaking of something that's like, I love that I don't think anybody uses, you know, in large numbers, right. Like if you go build a closure based startup today for closure developers, you're probably not going to have a really big market.

**Paul: **Oh for closure developers sure, that's definitely a mistake, but ones where you want to hire closure developers it's amazing.

**Keith: **Closure is like the Python of 10 years ago.

**Paul: **Yeah, yeah, yeah.

**Thomas: **You said B2B I would scope it down to it's certainly true for developer tools.


<blockquote>You cannot be successful in the developer market if you're not a developer yourself, and if you're not using your developer product.</blockquote>


It's just like even at Microsoft that doesn't work.

**Paul: **You do see a lot of people who are trying to create these ways that they view that the world should be, and it's like something where there isn't like 15 attempts already it's like, "what if we did it like this," and it's like, "yeah no one is interested in your world view. Everyone is interested in solving the problems that they have."

**Keith: **That's actually an interesting point that you bring up because when I think about dev tools where somebody built it because they had a very strict point of view, I go back to Rich Hickey right, like there's not just closure but something like Datomic, which really represents how he feels about the whole world of immutability and complecting, and simplicity, and all those kinds of things.

And yes I mean you can argue Rich Hickey's not a billionaire he doesn't have you know one of the world's largest companies, but he is seeing success and he is seeing his ideas slowly permeate in the world.

**Paul: **Well he is kind of famous going into that. I think if you weren't Rich Hickey and you were trying to build Datmoic you might find yourself in a lot more trouble.

**Keith: **That's true, but he's famous because of closure and I think he's famous because of all these ideas he's created building up to Datomic.

**Paul: **So it's interesting, the Rich Hickey example is a really good one because it's not a world view that lots of people share. He's got a real cult around closure, and around himself.And you can build stuff from a cult, and it's much more difficult to build things if your sort of following is sort of low level, and no one really cares that much. You're much better with love it or hate it.

**Keith: **I mean counter example though, Miguel and Nat, you know, Mono was kind of a cult right? It was open source C#. If you went back in time and asked somebody from 2006 or so, " hey is this going to you know work out?" Everybody would have been super skeptical of you, right?

**Paul: **Yeah.

**Keith: **But they've transformed that to now, you know, Miguel's an incredibly influential person in the industry at least in the Microsoft world, but really in both the Microsoft world and the mobile development world. So you can go from you know, starting a cult to starting a larger movement.

**Paul: **Well it's interesting that they had this value, which was like C# developers need cool tools as well. Which, you know, if you asked the cool tools portion of the market they'd be like, "nah fuck C#."

**Keith: **Yeah but it turned out they were wrong.

**Paul: **Yeah, yeah, I mean that's the conviction that they stuck with.

**Keith: **Yes, and that's definitely conviction there.

**Thomas: **The irony is kind of like if Microsoft would have won the mobile game, then Mono wouldn't have been successful. Like if Windows phone would be the biggest player in the market today, and iOS and Android would be small. Then Mono would not be important. So it kind of like, they benefited from the failure of Microsoft.

**Keith**: There was a market condition that you know, they couldn't control that was perfect for them.

**Edith: **Yeah, like so I was at Tripit before, Tripit bet big on iOS, our rivals bet big on Blackberry, we became the number one travel app.

**Keith: **Yeah, exactly. I think you know, there are very few people who are Elon Musk and can literally invent the industry and move the market. And you know,


<blockquote>Unless you are somebody who literally thinks through force of will, I think you're going to sometimes just be very lucky that you introduced the right thing at the right time. </blockquote>


**Edith: **Well I think, so my advisor Sean Burns from Flurry he's a great inspiration because he was super early on mobile I mean he was doing mobile when nobody else was doing mobile.

**Keith: **Except Thomas.

**Edith: **Well I mean he was doing mobile in like 2003.

**Thomas: **No I was actually doing automotive systems in 2003.

**Edith: **His saying is like, "sometimes you got to be way out in the water so that when the wave comes, you're ready for it." Like you can't be sitting on shore like, "Okay this wave is only here."

**Thomas: **And then stick with it, right? I mean when we started HockeyApp in 2010, the only competitor that was out there was Test Flight. And along the way it was always Test Flight versus HockeyApp for long time. And then there were other startups in the space, that gained also reputation, but really in the original fight was like Test Flight versus HockeyApp.

And then they get acquired by Apple, we get acquired by Microsoft so it kind of turned out nice for both of us right? And I don't feel bad about them, and Test Flight is a nice tool, and we probably put it into mobile center pretty soon.

**Edith: **What gave you the conviction to keep going so early? Like so we talked about being out in the water metaphor, and you laughed.

**Thomas: **Well I mean so, I was in the automotive industry and so I was working for Daimler and then for Bosch. And I basically became an independent contractor when the iOS SDK came out. I had finished my PHD, and had time. So I basically left Bosch and became an independent contractor and then I loved doing that.

I love doing mobile development, I love talking with other developers. And then I think you know the passion for the scene, and then also for the customer communication kept us going, and I'm still doing like 20, 30 support threads every day on HockeyApp support.

**Edith: **That's so cool.

**Thomas: **And it's I love doing it. I mean we love doing it right? Like we wouldn't do mobile center if we wouldn't love it, and the same was true for HockeyApp, and as long as you love doing it. And you know, a decent amount of money comes in to keep the service running right, why stop doing it? I love my life as a startup founder.

**Keith: **Yeah I think there's something special about doing startup work for developers. When your product is for developers. Because it's your tribe, and it's just, there's a sense of satisfaction. Like you're talking about B2C earlier, like when I left Microsoft I did a startup that was, we were trying to build, essentially like a browser based OS in all in one hardware.

So think Chromebook before Chromebook, that failed. The next one after that was like a mobile spaced video messaging startup, again for consumers, that failed. But then when I joined standard treasury that was like four developers and it felt very different, and it reminded me of my time at Microsoft before because at Microsoft before I was in the developer division I was, you know, building .NET, building C# all those kinds of things.

And that sense of I'm building something for someone like me who is then going to go use it to build something else entirely. You know I'm building the hammer, I'm building the wrench, that sense of like moving the world of being that pivot point, it's an empowering one.

**Paul: **There's concrete feedback that you build it and someone else uses it, and that one person who gives you money, or who builds on top that is a concrete feedback point. Whereas when you're building in the B2C world, it's just so hard to get enough people onto the platform to get even one little piece of feedback.

**Keith: **Yeah I mean I remember when with the video messaging startup, when we hit like 100,000 monthly active users, I was like "wow okay it's time to go raise some money." And I remember going around to VC's and they were like, oh yeah you need at least 1,000,000 before you talk to us. And I was like oh you're kidding me.

**Thomas: **You know it's funny that you mentioned VC, so we had never any funding.

**Paul: **Oh wow.

**Thomas: **And so that makes it really easy to keep going right? Because as long as you love what you do, and you make enough money to pay salaries and servers. The VC's always, you know


<blockquote>When I talked to VC's they always said, "yeah you have a lifestyle business",and they meant it in a demeaning way. And we thought "yeah, it's a nice lifestylethat we have."</blockquote>


And there's companies that do those things for hundreds of years, right there's a company that's only doing gas station signs, and they've been always doing gas station signs, and that's kind of like their business. The world leader.

**Paul: **I have some bad news for them.

**Thomas: **You have some bad news for them?

**Paul: **Yeah like the market for gas station signs is not going to last terribly much longer.

**Thomas: **Well I mean the Tesla super charger also needs a sign right?

**Paul: **That's fair, that's fair.

**Thomas: **My point is you know, if you're not in the business of getting a quick exit, if you're really building something that has a strong foundation, and has a solid fan base you can go almost forever.

**Paul: **What made you get acquired or whatever when the time came?

**Thomas: **So the way it started is that literally PM in Microsoft was just looking at available companies in the crash reporting space. They were looking for crash reporting tools. But basically it was what we call at Microsoft an IC, like an individual contributor. Not a manager, not a high ranked person, something like that, and he was just looking at what companies are available.

And then they contacted us and we didn't even think about acquisition we just saw "oh it's Microsoft day, they want to get a demo and then use us." And we knew that for example Skype was using HockeyApp since 2011. So there was for a long time before we even started acquisition talks, and then it evolved from there and we had like conversations with Microsoft.

And should we do an SDK for them, or maybe they want a partnership or something like that. And so the discussion evolved and ultimately ended in an acquisition. But it wasn't like we were, we were not shopping around or anything like that.

**Keith: **The story's interesting because


<blockquote>One of the things I tell startup founders all the time, is to try to ignore big companies as long as you can. </blockquote>


Because what I found is, all the time we'll have startup founders come by and they want to talk to us. We're like "great come by" and they'll like demo their product to us. And every time I feel like they're kind of not spending their time wisely because the chances that we will go ahead and acquire them or do a partnership that will be actually useful for them are relatively small right.

And we're like, we're a shotgun, we're like spraying lots of ideas out there, and seeing which ones are going to be useful for our business goals, right. So you have to like really kind of know, when is it really worth talking to this giant company versus okay I just need to be heads down and acquire my next you know 10 customers. And that's like always a really tough one for people.

**Edith: **That seems like a really good loop because we started off the segment with what's the worst thing about being acquired. And now you just advised everybody just to focus on running a business.

**Keith: **Yes.

**Edith: **Well thanks so much, we really enjoyed you stopping by today.

**Keith: **Hey guys it was great.

**Thomas: **Thank you very much.








