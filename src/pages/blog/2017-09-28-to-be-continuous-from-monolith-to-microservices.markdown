---
author: andreaech
comments: false
date: 2017-09-28 14:42:09+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-from-monolith-to-microservices/
slug: to-be-continuous-from-monolith-to-microservices
title: 'To Be Continuous: From Monolith to Microservices'
wordpress_id: 2057
categories:
- To Be Continuous
---

In the latest episode of To Be Continuous, Edith and Paul discuss the challenges and benefits of refactoring monolithic applications into microservices. They examine various approaches for creating microservice boundaries and dispel the myth that they should be defined as small as possible.

This is episode #38 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->

This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.







TRANSCRIPT







**Paul Biggar: **The idea of having something that you have a slow delivery cycle for some particular reason, or you have a normal delivery cycle but that still takes a day or whatever because there's code review and that sort of thing. And you want to have something really, really fast. You want to have multiple stages, multiple speeds of delivery based on different needs of different parts of the company, and that sort of thing.

**Edith Harbaugh:** I'm just so excited about this today, started talking about it. I mean this is really the promise of microservice. Like the old way was you had this monolith. The best thing I ever heard was a friend call it disgusting monolith, where everything was all tied together, and if you wanted to change one thing, you had to test everything all together.

**Paul: **Right, and we've all been there I'd say.

**Edith: **Yeah and it's very painful. It's very painful because then you get into this fix/release cycle. But decoupling things into different components that means that you can start iterating on some of them faster than others.

**Paul: **Right,


<blockquote>One of the questions that you get around microservices is, "How do you define microservices boundaries?" And a lot of people just go, "Oh you make them as small as possible" which I think is ridiculous. </blockquote>


But the ones that have always made sense to me is that you have service boundaries where there's different teams, or service boundaries when there's needs to deploy the service at different pace from the services around it.

**Edith: **Yeah, I mean I don't think you should decompose for the point of decomposing. Because that's when you end up with like 8,000 microservices, and you're like, "I don't know," this happens. I think you should decompose when, as you said, there's a functional reason why something has to move at a different speed.

**Paul: **Right, so the obvious one apart from those two is that it makes logical sense as a dependency for the API. This is a good API boundary for all the things that rely on it.

**Edith: **Yeah, because that releases you basically from release hell. Because you want to have a logical way that you can say, "Okay, this microservices interacts with this one at a certain time in a certain boundary." A really good example I heard is


<blockquote>There's this myth that you iterate very frequently on your UI, and I think this is true if you're in more consumer business where you can get a million peoplelooking at your app and rapidly iterate. </blockquote>


If you're at a company, if you're a B2B company, and you're rolling out your own customers, they don't actually want to have two people in the same customer have different user experiences. It's very confusing so you have to get a lot of support calls.

**Paul: **So I agree with you in the general case. But having used AB testing, it is an extremely useful tool to roll features out slowly and that's what I think even in B2B case.

**Edith: **I think it really depends on your B2B. Because I have heard some horror stories about people who try to do it at a B2B, and they get a lot of support calls. You know, "What's happening? The button I expected there to be is not there." Or "we just did a whole lot of training on this last week."

**Paul: **Yeah, and something has changed?

**Edith: **Yeah.

**Paul: **So I think one of the things that's really valuable about the modern dev tools go to market is that you have both on-prem and on-cloud customers.

**Edith: **Are we just doing buzzword bingo now?

**Paul: **Sure, sure, sure. So when you have customers who use both your cloud service and your downloadable software, the customers who use your downloadable software are the people who are naturally much more conservative. That's why they're using your downloadable software in the first place.


<blockquote>So you can do your AB testing in the cloud on the cloud customers who are much more early adopters and much more willing to put up with that sort of thing and happier to get the good UX that comes out of it. </blockquote>


**Edith: **Even then most people don't have sufficient volume to do effective AB testing.

**Paul: **I don't think that's true at all.

**Edith: **I think that's very true.

**Paul: **You don't have sufficient volume to do minor AB testing like to tell the difference between two different versions of blue, right? That's something you need Google Scale for. But if you're trying at a new positioning, you have AB testing. I think the major value when people complain about AB testing, the major value that they overlook is that it tells you that you didn't fuck something up.

**Edith: **Yeah,


<blockquote>I think AB testing is a misnomer. I think it's really risk tolerance. </blockquote>


**Paul: **Right, so if you're launching a new messaging or a new onboarding page or something like that that you think is going to deal with your position much better, or it mentions a new product which hadn't been mentioned before, you want a B version that was just the old version that tells you you didn't tank your conversions.

**Edith: **Yeah, and the dirty secret is that most changes have no effect at all.

**Paul: **Right, right. But you want to be sure of that. We launched a new, beautiful home screen once or homepage, and it dropped our conversions 20%.

**Edith: **Yeah, I remember. Paul always teases me cause I talk about TripIt. Like we tried a different footer, and it destroyed our conversion.

**Paul: **Oh! A footer.

**Edith: **A footer

**Paul: **Did it have a different call to action or move to call to action or something or provided more calls to action?

**Edith: **The footer had a lot of calls to action.

**Paul: **Yeah, that was exactly the thing with ours. We had, "You can sign up right now you can read the docs or you can do something else." And it ended up that a lot of people go read the docs, and then just forget about us.

**Edith: **Yeah, and this is the kind of classic product debate then. Do you want them to sign up if all they're going to do is read the docs? And you can argue about this for hours about qualifying leads, when to get people into the funnel.

**Paul: **I think if you have a drip marketing campaign, you generally want them to cross the line which gets them into drip marketing campaign.

**Edith: **Paul, you're a marketer!

**Paul:**


<blockquote>I was the CEO of a company. I've done fucking everything, for three months each. </blockquote>


**Edith: **What was the rotation? If you fucked everything three months each?

**Paul: **Yeah, everything that got done by me was done badly, but it was better than not being done at all.

**Edith: **So what was your rotation?

**Paul: **I did sales. I did marketing. I did PR. I did UX. I did support. I did everything.

**Edith: **What was it like when you were sales?

**Paul: **So fortunately Circle had so much interest and such strong product market fit that sales was literally having a call with the CFO saying the price is this. And he's like, "Can you lower the price?" "Uh, no. All right, well thanks." I had a couple of calls that were literally that. They brought some financy person or the manager and they were like, "We demand a discount." And it's like, "Yeah, this is a good price we feel."

**Edith: **So do they end up buying?

**Paul: **Yeah, yeah. I mean, some of them don't. I hated giving discounts. I felt like we had a really good price, and it was actually kind of cheap for the value that customers got out of it. And so when people came for discounts, I was just like, "No."

**Edith: **That's funny. You know there's the opposite which is you should price a little high expecting that you'll discount.

**Paul: **Yeah, I think for bottom-up tills, you can't really do that. Because people won't ask for it, they'll just leave.

**Edith: **Ah!

**Paul: **The old oracle way doesn't apply to our modern bottom-up. I guess, do you have a top-down?

**Edith: **We have both. I mean as soon as you get into procurement department, like their job is to get a discount.

**Paul: **Right, right

**Edith: **So if you don't give them a discount, they feel like they didn't do their job, and their like, "What happened here?"

**Paul: **Yeah, and that's why you end up, I guess in the microservice version of the sales process is you apply a different sales process to different people. And the bottom-up people get the price on the website, and the people who go through their procurement department get another thing. And the fact that you have to talk to their procurement department means that they're getting charged an outrageous price in the first place to deal with that.

**Edith: **I think the words continuous delivery terrifies a lot of people.

**Paul: **Mmhmm

**Edith: **It's funny because we do a podcast called..

**Paul: **To Be Continuous, yeah, I think that's what it's called.

**Edith: **I mean let me check the label. Yeah I think people think of continuous delivery is that you have to push out multiple times a day an hour. When really it just means that you need to be able to push out what you want.

**Paul: **Right, right I've rarely seen a continuous delivery company that does continuous delivery and uses that to mean we're only doing it when we can. I think they all push at every version. I find it extremely rare for people to push out, especially in small companies. Maybe there's a small company bias.

**Edith: **No, I'm talking more at larger orgs. They find continuous delivery terrifying. Because they're like, "Our processes are not set up to have a new version of the UI every day." Like, "We need to go train our support people. We need to go do this. We need to update this." So to go back to what you said, I think there's different functions within their systems that they would like to be updated at different speeds.

**Paul: **Yep, I agree with that. You can kind of think of the UI as one microservice. You can think of all the other things as different microservices. But the one that I've always found, people need to update quickly, but they don't necessarily want to update it repeatedly, is the marketing pages. So the entire front-end of your thing. You'll get to a point when you have marketers and the marketers ask for the front-end, which was beautifully built by developers.

**Edith: **With Han Loverdly and Jekyll

**Paul: **I think actually Jekyll is pretty good for them, but like will typically be built-in react, you know whatever the same as your website is it'll be nicely unified and has an excellent release process. And the marketers will be like, "Yeah, we don't want to talk to you to make a change here. We need you to put in the optimizely pixel and could you switch this over to WordPress."

**Edith: **Yeah, cause they want to be able to do it themselves, they don't want to have to go bug their developers.

**Paul: **Yep,


<blockquote>Then they end up with a terrible release process from a developers perspective in that there's no staging environment. There's no ability to preview your stuff. There's no code review. There's no nice automated releases that have pull request in them. There's just like someone playing around in Word Press.</blockquote>


**Edith: **I could feel the horror in your voice.

**Paul: **Well, I think it's easy to fuck things up that way. But it's better to only have to rely on your team to get something out. When you have to start to rely on other teams, that's when your deliver really gets slow.

**Edith: **Yeah, I thought of a classic thing where you want to have very quick releases and it's anything security related. This is actually one of my big things is that you want to be able to constantly patch security vulnerabilities. And the security vulnerabilities that exist today will be different tomorrow, the day after and the day after and the day after.

**Paul: **You generally want to have a way of dealing with security vulnerabilities immediately even though that is extremely scary and very, very dangerous.

**Edith: **But whatever you know today will be different later.

**Paul: **Yep, we had multiple approaches of dealing with different container images. Because a container image would take like 36 hours to roll and to deploy. So we needed to be able to run something on that image. It was partially for security. It was partially for user experience. It was partially because sometimes things broke in the ecosystem.

But we had the ability to go change, we called it the pseudo hack. So a command that would run a pseudo. And there was 30, 40 times where we need to make some change to the pseudo hack to support something weird that was going on.

**Edith: **Yeah I think a lesson is if you have to do a fix, how long does it take you to do it?

**Paul: **Right, there's the actual fix itself, and then there's the process of getting the fix into production.

**Edith: **Yeah, and if that process is more than a day, you're in serious trouble.

**Paul: **Yep. Well, I mean if it takes you a day, but you're able to get it patched really quick, I mean that's kind of the source of the word patch, right?


<blockquote> If you patch it immediately and then you go fix it, and it takes a day, that's no big deal. </blockquote>


**Edith: **Oh, yeah, but as long as you can patch.

**Paul: **Exactly yeah. So we ended up at various points with a very quick process to update our engine X, so that we could filter particular data or filter particular user types and that kind of thing, and a bunch of different levels to deal with particular security vulnerabilities that might theoretically come up. Not just security vulnerabilities, but also like DDOS.

**Edith: **Yeah, just everything that comes up.

**Paul: **Incidents of whatever kind.

**Edith: **Yeah incidents that are not your core functionality, but are crucial to be quickly addressed.

**Paul: **Right exactly.

**Edith: **So I think I could break down different speeds of which you want stuff to update. Stuff that leaves you vulnerable to the outside world, that's kind of like your protective cocoon, if there's a hole breech there, you need to repair it immediately. Or else you'll end up hacked.

**Paul: **The problem with those is that you also need to maintain those. So you need to have testing around those. You need to have people remember how to do them. If you go to use one of those things, and no ones touched it in six months and it went stale or it rotted in some way, then you're even more fucked now especially if you've provided yourself an accidental back door, or provided your attackers an accidental back door.

**Edith: **Yeah, and then there's stuff that you want to go at different speeds. Like if you're doing any sort of billing update, you actually want to be kind of cautious.

**Paul: **Yeah, I mean this is for feature flags I find particularly useful. You enable a billing chains like that for one person and then you watch what happens. You make sure that they're able to do the thing, and you go very, very cautiously.

**Edith: **Thanks for wearing LaunchDarkly shirt, Paul.

**Paul: **No worries! Feature flags are awesome.

**Edith: **It looks really good on you by the way. It matches your haircut.

**Paul: **Thanks.

**Edith: **I get really excited the more I talk to our LaunchDarkly customers right now because I've seen the way just the world has changed even in the couple years that we've been around.

**Paul: **What are people using LaunchDarkly for that blew your mind? Or how perhaps are they using it that blew your mind?

**Edith: **I'm pretty jaded so not much blows my mind. But it's more like they visited a big customer and they said how much less stress they were in and how much less risky their releases were now.

**Paul: **Right, we've been saying this for years that


<blockquote>Continuous delivery is less risky than monolithic delivery or stage delivery.</blockquote>


What did we use to call it when it wasn't continuous?

**Edith: **Waterfall?

**Paul: **Sure waterfall. I think people didn't really believe us.

**Edith: **I think there's still a lot of doubt. I think if you draw like a crossing the chasm type thing, I think we're still like squarely in the early adopters.

**Paul: **Yep, that's true.

**Edith: **But I think it's starting to move.

**Paul: **Yep.





