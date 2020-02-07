---
author: andreaech
comments: false
date: 2015-11-05 23:32:18+00:00
layout: post
link: https://launchdarkly.com/blog/episode-6-use-cases-for-continuous-delivery/
slug: episode-6-use-cases-for-continuous-delivery
title: 'To Be Continuous: Use Cases for Continuous Delivery'
wordpress_id: 689
categories:
- To Be Continuous
tags:
- APIs
- continuous delivery
- developers
- Douglas Squirrel
- Facebook
- gatekeeper
- Google
- Jason Lumpkin
- LinkedIn
- microservices
- SaaSter
- SDKs
- stripe
---

In this episode, Edith and Paul discuss the spectrum of Continuous Delivery, and where Continuous Delivery will and won't work in software development.  This is podcast #6 in the To Be Continuous podcast series all about continuous delivery and software development.

This episode of To Be Continuous, brought to you by Heavybit and hosted by Paul Biggar of CircleCI and Edith Harbaugh of LaunchDarkly. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.







Paul:      Hi, I'm Paul Biggar, founder of CircleCI.

Edith:     I'm Edith Harbaugh, CEO and co-founder at LaunchDarkly.

Paul:      You are listening to To Be Continuous, a podcast about continuous delivery and software development.

Edith:     You can get in touch with us any time at our Twitter handle, [@continuouscast](https://www.google.com/webhp?sourceid=chrome-instant&ion=1&espv=2&ie=UTF-8#q=%40continuouscast).

Paul:      The show is brought to you by Heavybit. To learn more visit heavybit.com. While you are there check out their library, home to great educational talks from other developer company founders and industry leaders. In this episode, we discuss the spectrum of continuous delivery and where continuous delivery will and won't work.

Edith:     Paul, does one have to be all in to do continuous delivery?

Paul:      I think the obvious answer is no. In particular, you know that the answer must be no because nobody starts at all in or at least, if you are starting a new project you can be all in and many projects are not all in. Someone starts somewhere and they say, "Now we are going to do continuous delivery in some way." They have to go from zero to full continuous delivery along some way.

Edith:     I think people have this conception that continuous delivery just means pushing any time you want. A lot of very old school development shops did that. They would just hot patch in production constantly.

Paul:      Are we calling that continuous delivery? I feel that the idea of SSHing into the server is not continuous delivery somehow.

Edith:     People have this misconception because they are like, "Oh I did a continuous delivery before this was a thing, I just patched information."

Paul:      I am going to put a lot of money on the line here and say that if you define continuous delivery as I SSH into the production server, then you are not doing continuous delivery right. In fact you are doing it considerably wrong.

Edith:     What exactly are you doing wrong, then? What steps are you skipping?

Paul:      The whole point is that you have this automated process for releasing software, and SSHing into the production server is the very opposite of that. That's not to say you shouldn't do it in the occasional emergency. Occasionally if we have some sort of catastrophe we will SSH into the production server, replace some code, execute some code on the server to keep things as they are and prevent customers from noticing or from things from going down but that isn't the same as a continuous delivery pipeline or a release workflow or an automated release work flow which is essentially what continuous delivery is.

Edith:     Continuous delivery isn't just shipping stuff out to production. It's more having all the processes behind it.

Paul:      It's very much the process. When you think about can you be a little bit continuous delivery, I think what you are looking at saying is, is there a lightweight version where we get some benefits of the continuous delivery as we go between all and nothing?

Edith:     Do you have to be all in or can you be a little bit continuous?

Paul:      I think the very obvious instance of a little bit continuous is where you deliver the code. Where you have the automated release process builds some sort of artifact and then someone manually deploys that by a single click, or in fact where a build happens and test happens and the remaining automated release process is triggered by a human saying, "Now we are going to release." Then everything else is scripted so they just have one input which is now.

Edith:     That's really interesting. Do you think to truly be continuous it has to all be completely automated with everything always pushed?

Paul:      No, no I don't think so. I think it largely depends on the size of the team and that sort of thing but I have seen a couple of examples where our customers were asking for particular things and indicated that they had sort of semi-continuous workflows. One example of that is a team that only wants to deliver or only wants to do continuous delivery during work hours.

There was another team which only wanted to do continuous delivery at midnight because that was the only time that they didn't have enough customers on their site to be able to clear the caches. If they wanted to go to complete continuous delivery they would have to say we are going to clear a subset of the caches, or have some other caching policy that allows us to continue, or that allows us to deploy at any time but where they are is basically, we are semi-continuous.

Edith:     I had a really interesting chat with [Douglas Squirrel](http://douglassquirrel.com/) who actually listened to our podcast, and he does a lot of consulting for companies in England. He said he goes to a lot of companies that have all the tooling to be continuous but they don't actually use it.

Paul:      What does that mean exactly?

Edith:     They have set up continuous integration. They could in theory deploy whenever they wanted but they still, for whatever reason, still cling to their old schedules.

Paul:      I was looking at [this very interesting article](http://firstround.com/review/the-right-way-to-ship-software/) on the [First Round Capital blog](http://firstround.com/review/).

Edith:     Jocelyn's.

Paul:      Yes, that sounds right.

Edith:     Jocelyn Goldfein who was at Facebook, right?

Paul:      Yes, yes. That's right. What she talked about was this idea that delivery schedules are useful in certain contexts. In some cases velocity matters, and that's the Facebook case, and in some cases predictability matters a lot more. If you are delivering enterprise software for example, an enterprise is not going to allow you to continuously deliver your product into their firewall or into their enterprise. What they are going to want is they are going to want every quarter, a new thing.

Multiple times a year preferably, but each time you release to them creates a new workflow. They want to be able to audit it and see a change log and validate that things are, that they might have a change process internally. It's not necessarily going to be a good idea to continuously deliver there but a team that is building for that can do a continuous delivery process internally where they produce all of the artifacts and they do a complete release on every single push even if that is not released.

Edith:     There is a lot of reasons why an enterprise doesn't want to take new features constantly and a lot of it comes down to training. If there are big new features that need to be rolled out to people, then they have to take on the cost of training. It was actually interesting, I chatted with a guy from Square and he talked about how they really try to limit the amount of pushes they put out to the actual cashiers. Because of the training cost, a cashier at a coffee shop is doing a gazillion other things and they can't just suddenly pop up to new functionality and expect them to grok it or even take a tour.

Paul:      Got you. Right, right, right. That's an interesting idea.

Edith:     Although they have all the processes in place to do a lot of changes and to do continuous delivery, they actually really limit what they push out to the true end users.

Paul:      It's funny that the people who have far, far more users, someone like Facebook, can just do those changes because they don't necessarily value an individual user on a ... Not saying that they don't value their users but ...

Edith:     You're about to ... You're walking down a path.

Paul:      It is safe to piss off an individual user. Less so for someone like Square and as you go up the value chain, the more they are paying you or the more involvement they have to have in the product decisions, the less able you are to piss them off.

Edith:     Facebook is actually a fascinating example because at any time they are going to be pissing off somebody. It's kind of like Apple, you know they are always pissing off somebody it's just who.

Paul:      Did you hear about the day at Facebook where all the feature flags went on?

Edith:     It was LinkedIn.

Paul:      Was it was LinkedIn? Okay.

Edith:     Yeah. It’s probably happened to everyone that’s done feature flags, there is the day that that happens and it's ugly. Facebook is fascinating. Actually, I wrote a blog post about Facebook and how they use feature flags. They have a product called Gatekeeper that controls everything, everything. After they had a huge PR disaster, I think it was in 2011 with their news feed, they actually do really care if they piss off a lot of people and that's why they implemented Gatekeeper where they do a lot of 1% roll outs.

Paul:      I remember when I was setting up Circle I sat down and talked to my friend who worked at Facebook and he talked about their workflow and that sort of thing, and their release process was that code got released on Tuesdays. Everyone who was releasing code or who had code in that bit that was going out had to be available during the release process. The release process didn't turn on any features because that was all done by Gatekeeper, but the code itself had to go out and they had to validate that everything stayed the same and everyone had to be there. They had a fairly continuous delivery process but were still, manually there was a release going out.

Edith:     You want to have some sort of enforcement that people look at stuff and care.

Paul:      Care in what sense?

Edith:     The example I heard about also at Facebook is it's so large that there is just no way that all the groups can coordinate with each other. Literally what they do is, when they roll stuff out with Gatekeeper, they roll it out internally to Facebook only employees. That's how they find out if stuff breaks. It's not like at a smaller company like Circle or ...

Paul:      There is a difference between the code being rolled out and the feature being rolled out, and they don't do ... I don't know what the story is nowadays, but at the time they certainly didn't do continuous delivery on code, or continuous releases or whatever you might call it.

Edith:     I don't actually work at Facebook but what I did hear was that they just literally can't ... When you are a small company you could still coordinate in a HipChat or a Slack room like, "Hey, we're pushing this now, start looking for changes," but with Facebook the only way they know if something is broken is if somebody complains.

Paul:      There is an interesting discussion about microservices at AWS. I guess they didn't call them microservices at the time but being fully service oriented architectured. One of the things they talked about is how when you roll, or when you continuously deploy a service, you might break other services. The thing that actually breaks may not be in any way related to the people whose alarms start going off and in fact they may be multiple steps away from whose alarms are going off.

Edith:     Google has a similar system and I heard that they monitor 200-plus different metrics. One of the ones they monitor is just, do people say Gmail sucks more? Like on Twitter.

Paul:      Interesting. The thing that I am getting at in terms of how little or much can you continuously deliver is if you are a Google or you're Facebook and you have the monolithic code repos, the thing that you are releasing is, it's not the same release process as someone like Amazon who has what I would describe as pure continuous delivery. Every service does its own continuous delivery and your dependencies may be changing in any time and you don't actually know what is going on.

Versus Facebook that we are taking this multi-gigabyte binary and we are uploading it to a set of servers. Sure, we are slowly releasing and maybe we're doing that multiple times a week or multiple times a day, but it's not quite the same as Amazon releasing every 11 seconds. I think we can see even between these multiple large companies who have incredibly advanced release process that you could say that they are clearly at different spectrums along continuous delivery.

Edith:     What do you think is suitable for a medium company with 10 developers?

Paul:      There's a lot of different things going in ... Who is your customer base? What is the level of safety that you need? Let's suppose that it's a consumer web app. If it's a consumer web app, I would expect that that company should be continuously delivering all the time. Especially if it's slightly okay to break things or at least you break things, you can roll them back or whatever within a couple of minutes. A team of that size might not have the resources to make their continuous delivery process perfect, but it seems likely that they would have more success shipping with continuous delivery than shipping without it so lower risks, higher velocity, that sort of thing.

Edith:     It's funny how continuous delivery has permeated even the VC world. [Jason Lemkin](https://twitter.com/jasonlk?lang=en), you know the guy behind SaaSter, he tweeted yesterday that one of his due diligence questions was how often ...

Paul:      I saw this.

Edith:     How often can you roll back, comma and does it work? It's funny that I think of that as a very technical thing, can you roll back, but the VC is seen as a sign of technical sophistication.

Paul:      Can you roll back?

Edith:     All the time. Every day.

Paul:      Really? You break things so often that you must roll back.

Edith:     Paul, no. I mean, we feature flag everything.

Paul:      A feature flag is not a rollback.

Edith:     I think of it as a rollback. If you think of a rollback ...

Paul:      How often do you roll back the version of deployed code?

Edith:     Virtually never because we feature flag everything, so if something ...

Paul:      Could you roll it back? Does it work?

Edith:     That's funny. I think we're hedging now on what rollback means because I take it as can you take ... What LaunchDarkly really does is it separates deployment from visibility.

Paul:      There is a code deployment and there is a feature deploy which is done at a separate time.

Edith:     When I talk about rollback in my mind I'm just talking about, I'm rolling back the feature from any users or any systems. Because if we have a feature flag on something and we turn it off, it is in effect rolled back.

Paul:      I understand what you are saying. What I'm asking is, do your code rollbacks work?

Edith:     We never have to do it because we always just turn off a feature flag. Stuff breaks and when it does we will just flip the feature flag off.

Paul:      It's funny we've ended up with a ton of different types of feature flags. One of them that's very interesting is we started with this idea of pseudo hacks.

Edith:     Isn't a hack already a hack?

Paul:      Yes. We launched this within the first couple of months of Circle that when a customer would ask for a thing, customers didn't have pseudo at the start on Circle. They weren't able to install things, they weren't able to app to get install or do anything as root on a Circle box and we didn't want to give them access to root either. What we wanted to do, whenever a customer asked for a thing we would add a single line of bash that was executed when their container started up and would get their container into whatever state it needed to be.

It would, for example, install the new version of MySql or something like that and that in effect became a feature flag. A load of customers would start to ask for particular thing, we would add the line of bash to someone's container and then another customer would ask for it and then we'd have 10 or 20 customers who were using this in production. You can't see it on the podcast but I am doing air quotes when I say uses this in production, and that was kind of our feature flag.

Then that evolved into global hacks so that when we have a single container image that almost all of our customers use. When we launch a new version of that container, sometimes something will break and we do lots of testing in advance and we have an automated process that ensures that those things work but occasionally something will go wrong. Then we'd add a global hack that runs on all containers before the customer's code is run to get that back working.

We've evolved that. We have container feature flags, we have user feature flags, we have machine feature flags and the net effect is that we also almost never roll back. On certain things, on containers it's very easy to roll back. On our VM images and on our front end code base it's very, very easy to roll back. The back end code base is not as easy but it's getting much, much easier. There is a defined process there but we almost never have to do it because there is nearly always a way to hack it and to keep rolling forward.

Edith:     I did remember, so we can roll back. We try to protect everything with feature flags just because it is so much less stressful. Any time you have to do a rollback and redeploy code, it's very stressful because there is a lot of things that could go wrong and it's just stressful. We did have to do it the other day because we changed something around, an API schema. We hadn't feature flagged it because we thought it was so minor and this is always where you get tripped up, the thing you thought was so minor that you didn't feature flag that broke something very important.

Paul:      Stripe has a very interesting, I don't think you'd quite call it feature flags but it's their API versioning, so they never change their API. They just launch a new version of the API. New customers get it and old customers can opt into it. They end up in a situation where they never have to roll back their API, they define a transition from their old API to their new API, and there are definitely code changes that sit behind each API but there isn't a change to how a customer perceives it. Any change that the customer perceives is an actual error or is an actual bug that they need to fix.

Edith:     That's smart. That's what we do also. APIs are so painful because no matter how much you try to warn people there is always somebody out there who is using the version ...

Paul:      Who is using the thing that you haven't told them about but they inspected the data directly and thought that this was always going to be this way or something.

Edith:     Oh man, when I used to work at an enterprise software company and we completely deprecated and removed an API that somebody had found out when they upgraded and could no longer use it. They wrote it like, "Where is my meta transactions?" We're like, "Removed." We got this really anguished ... You could literally hear this guy sobbing. He's like, "I've written over 3000 modules using that metatransaction API. Now what?"

Paul:      What did you do?

Edith:     There was nothing to be done, the API was gone.

Paul:      You didn't bring it back for him? You didn't ship him the code for the API and, run this yourself?

Edith:     Mistakes were made and he was at a very large Telecom customer that was paying us a lot of money and he was extremely unhappy with us. He was extremely unhappy for good reason because he had spent years of his time.

Paul:      One of the things that we're doing at the moment is ... It's very important to be able to sunset features and to be able to know when exactly things are working or to be able to be in control of your own code base. One of the areas that is hardest is in API because people expect that the UI is going to change all the time, that the function of everything is going to change, that they may have to change their code base sometimes to fit in with that but APIs are a particularly hard thing to change.

Especially since you don't have any metrics on how people use them. I think that there needs to be a lot of effort if you want to have a continuous delivery to be able to change your API. A couple of things that we're doing to change the API is one at the moment is where, right now everything is in our V1 API namespace.

Edith:     Wow. Still?

Paul:      Still. We just add to it, we almost never change it. We did one change, maybe two changes, customers didn't notice so we were fortunate there. Ours is a product that where the API is not heavily used.

Edith:     Oh, really? Our product is all API.

Paul:      Is in API, yeah. Our products, very few customers use the API and the basic uses of the API is, build your own client, which almost nobody does, or build a dashboard and the APIs around the dashboard are relatively stable. What we are looking to do though is take a load of APIs which were in the v1 namespace, and move them into a private namespace, and this is things like billing. Our front end is entirely JavaScript. To communicate to the back end there is an API. Everything must be API and so there is a billing API.

Edith:     Is it public?

Paul:      De facto.

Edith:     That seems ...

Paul:      We didn't publish it, but you can see it in Chrome in the web inspector.

Edith:     Not to pick on you, though you picked on me earlier, that seems a little non-standard.

Paul:      I agree that it is non-standard but it ...

Edith:     To put that in the politest possible way, why?

Paul:      Because at the time we just took all of our stuff and put it in the v1 namespace. There was only one namespace so now ...

Edith:     It was like Highlander.

Paul:      Now we are looking at having multiple namespaces. The two that we are focusing on are the private, which is don't touch this and if you want it ask us, and the experimental which is we don't actually know how this is going to be used in public and we don't want to think about this too much. We just want to get this out the door.

Let you guys use it and give us enough feedback for us to put it in v1 at some point, or v2, whatever version it is at the point. I think that those are very useful API, the idea of namespacing and I think that the more advanced version of that is Stripe's thing where you validate or where you make a large number of APIs. You version them and you let people exist on all of them via canonicalization process.

Edith:     I agree. We take APIs very seriously because at its heart, what we are is an API. We are an API with some SDKs on top of it and then a nice dashboard. Our API is actually the most tested thing because our customers depend on that to run their business.

Paul:      That's all your business is, is a little API and a little dashboard.

Edith:     Then a lot of technology to make that all work.

Paul:      I keep going on about Stripe's API versioning.

Edith:     Is it because they're Irish?

Paul:      It's not and the people who gave a talk about this are not Irish. One of the Heavybit talks was by Amber at Stripe about their API versioning. The reason that I like this so much is, have you heard the word canonicalization? This is one of my favorite software engineering techniques which doesn't really get people talking about it, and the reason that I know about it is because it comes up a lot in compilers. The idea is that you don't have multiple ways of representing things.

You take the multiple ways of representing things and you modify them into the canonical way of representing things. That's how Stripe implements its API versions. Every version that the API has a canonicalization step which transforms it to the version that's expected the next step and at the core of it, they have a single canonical version of the API that every API talks to at the end of the day.

Edith:     To bring this back to continuous delivery, do you think then that they are practicing continuous delivery on their API or not?

Paul:      Oh yeah, yeah. No, I think that is exactly what they are doing because they are versioning it. They are allowed, create a new version of the API. They can make a backward incompatible change at any time and it will only affect new customers going forward.

Edith:     That's a good point.

Paul:      Then the only people who suffer are people like Barometrics where they need to talk to tons and tons of different customers, and actually that's not true because you can also specify the API version that you want in the API header so you're not actually stuck with the version that is specified in the dashboard.

Edith:     Cool. We talked about APIs, we talked about consumer companies. Do you think there is any company where it's not a good fit for continuous delivery?

Paul:      SpaceX. If you are making rockets, missiles ...

Edith:     Cars. Cars.

Paul:      Pacemakers, cars. Cars is an interesting one because you have something like the self-driving cars where they are almost assuredly doing continuous delivery. Where the ability to iterate is a key function of what will get self-driving cars to market but I wouldn't want Ford to be continuously delivering and doing an over the air update to something that is really important.

Edith:     Volkswagen was just hugely in the news because they basically hacked their software to evade the EPA.

Paul:      There's a question here as well of whether you trust software more than you trust humans.

Edith:     But humans write software.

Paul:      Right, right but whether you trust the humans on the ground versus the humans at Google who write software. I think it's fair to say that where you are writing low-level C or something like that, that affects the flight of the rocket, you want to be very, very careful about what you ship and how often you ship. If you are writing this high-level AI code that's written by the world's greatest engineers and replaces the world's dumbest people at the wheel of multiple thousand-pound weapons that can hit other people who are in their own weapons, I think there is definitely a case to be made where self-driving car code is not held to the same standards. Maybe not held to the same standards but is naturally of such a standard that you could expect that you would continuously deliver it.

Edith:     It's a sad story. I run a lot of Ultra marathons and a runner did a 100-mile race in Utah and then he was driving back by himself on the 80 and he just basically, to the best we could tell is he just fell asleep at the wheel and just literally on cruise control ran into the tractor trailer in front of him.

Paul:      Wow.

Edith:     Maybe if we had smarter cars, he could have taken a nap instead of trying to drive back instead of being awake all night.

Paul:      Wow, that's a tragedy.

Edith:     Then you hear cases like Volkswagen who had one of the biggest software cheats in the world.

Paul:      Fortunately they are going to be fined 18 billion for it and are unlikely to do it again.

Edith:     Unlikely?

Paul:      Unlikely. Yeah.

Edith:     You just have to think about the logic that led them to believe that they could get away with this. What exactly they did was, in California when your emissions are measured, they turn on some special software that decrease the pollutants enough that they could pass. Then in normal driving conditions, they turn it off so they could get higher mileage and go faster.

Paul:      I see. That's lovely.

Edith:     Somebody somewhere had to think that they could get away with it. It wasn't a bug.

Paul:      Continuous delivery clearly working there.

Edith:     What? How?

Paul:      It worked as intended. They weren't intended to get caught but clearly that's not the software's fault.

Edith:     Don't blame the software, blame the human that wrote it.

Paul:      Right, right, right.

Edith:     Or that person's manager, or their manager's manager.

Paul:      Or the Board. On the question of do different kinds of software lead to different kinds of delivery processes? Obviously. I often make comparisons of what level of testing do you want and the level of testing that you want for consumer software, or if you are an early stage start-up that has no customers, it's going to be different than most start-ups and it's going to be different than most enterprise companies and the tech stack that you use if you are going to be one of these web start-ups, you can use Ruby on Rails. If you are writing pacemakers, you want to be using software that has some kind of formal verification in it.

Edith:     Then you get into the whole area of government or financial which has its own set of rules.

Paul:      All their rules are around process which indicates that there is something to this process thing.

Edith:     I talked to a prospect the other day who made kids' apps and I had to turn them away, because there are so many rules around what data you can collect from children. That they can't use a key, they can't ask them for anything, and I said we don't want to touch this.

Paul:      That's interesting. I will have to not ask any of my customers whether they're building software for kids. Though we don't keep any customer data so we would probably be fine, but best not to know I think.

Edith:     It's better not to know.

Paul:      Yeah. Thanks for listening to this episode of To Be Continuous, brought to you by Heavybit and hosted by me, Paul Biggar of CircleCi, and Edith Harbaugh of LaunchDarkly.

Edith:     To learn more about Heavybit, visit heavybit.com. While you are there, check out their library, home to great educational talks from other developer company founders and industry leaders.




