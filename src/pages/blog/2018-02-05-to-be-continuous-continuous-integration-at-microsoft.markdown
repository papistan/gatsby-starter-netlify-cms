---
author: andreaech
comments: false
date: 2018-02-05 17:33:51+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-continuous-integration-at-microsoft/
slug: to-be-continuous-continuous-integration-at-microsoft
title: 'To Be Continuous: Continuous Integration at Microsoft'
wordpress_id: 2271
categories:
- To Be Continuous
tags:
- continuous delivery
- DevOps
- testing
- tooling
---

In this episode of To Be Continuous, Edith and Paul meet up with Microsoft program managers [Simina Pasat](http://www.twitter.com/SiminaPasat) and [Joshua Weber](http://www.twitter.com/JoshuaWeberMSFT) to discuss how continuous integration plays a role behind the scenes at Microsoft. Hear how they develop across platforms, use feature flags, approach user feedback, and more.

<!-- more -->

This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.

<span data-mce-type="bookmark" style="display: inline-block; width: 0px; overflow: hidden; line-height: 0;" class="mce_SELRES_start">﻿</span>&lt;span data-mce-type="bookmark" style="display: inline-block; width: 0px; overflow: hidden; line-height: 0;" class="mce_SELRES_start"&gt;﻿&lt;/span&gt;&amp;lt;span data-mce-type="bookmark" style="display: inline-block; width: 0px; overflow: hidden; line-height: 0;" class="mce_SELRES_start"&amp;gt;﻿&amp;lt;/span&amp;gt;





**ABOUT THE GUESTS**


**[Simina Pasat](http://www.twitter.com/SiminaPasat)** is a program manager for Microsoft where she works on app developer tools for [Visual Studio App Center](https://www.visualstudio.com/vs/mobile-app-development/) for mobile.

**[Joshua Weber](http://www.twitter.com/JoshuaWeberMSFT)** is a Microsoft program manager on the Mobile Center team where he leads development on the [HockeyApp ](https://hockeyapp.net/)platform.

**TRANSCRIPT**

**Paul Biggar:** Okay, so, what is the thing that you like least about continuous delivery?

**Joshua Weber:** I could start off. Because it's actually, I feel passionate about what I like least about CI, which is, I hate setup.

Every single time I've ever done a CI system, it takes me a day. It's always a day. It always feel like it should take an hour or half an hour, because it's always like, "Oh yeah, I know what I'm doing." I wanted to just build and do the stuff, but it's just it always takes way longer than I want.

**Paul:** This is literally why I started CircleCI.

**Joshua:** I would say that it's by far, every time, my least favorite thing. It's always getting in the way of coding. It's always starting a project and it's always, I don't get to start because, instead, I am installing agents, or trying to figure out a connection or an authentication problem, or something like that. It's very passionate for me, that it's the setup costs.

**Paul:** The first time that I started marketing CircleCI,


<blockquote>the email that I sent out to our initial list was, "Set up your CI in 20 seconds," and that was massively effective.</blockquote>


**Edith Harbaugh:** Was it true, though?

**Paul:** In about 40% of cases.

**Simina Pasat:** How about the rest, of 60?

**Paul:** It took less than an hour. It was straightforward to get it set up. There's no agents to install. We have the infrastructure as well. It was nice and straightforward.

**Edith:** How about you, what's the thing you like least?

**Simina:** The least I like when there is a new version of Xcode or a new SDK, and then it starts. You have to update the Mac hardware, you have to update the agent, then things start failing. Then if you have one app on one SDK version, and another app on another version, things might start failing even worse. So it's becoming a huge mess.

**Paul:** I feel a lot of this pain. I feel like, as fellow CI providers, this is one of the nightmares.Your build machine or your build image has to update because the technology updates all the time. But then you fuck over the existing customers who were perfectly happy with how things were working.

**Simina:** Yeah, and people expect in the next 24 hours, it's there.

**Paul:** As soon as you make it. We had a process where building our Mac image in took three days and there was no way we were going to get anything done in the next 24 hours.

**Edith:** Paul, now's a great time for the guests to introduce themselves.

**Paul:** Let's do it.

**Simina:** Hey, I'm Simina, Simina Pasat. I'm a program manager in [Visual Studio Mobile Center](https://www.visualstudio.com/vs/mobile-app-development/) here at Microsoft.

**Joshua:** Hi, I'm Joshua Weber. I'm a program manager here at Microsoft, I'm working right now on the Mobile Center team, but I also own [HockeyApp](https://hockeyapp.net/) product, as we're basically running them in parallel.

**Edith:** We're recording this from Microsoft Build, Microsoft's big developer conference in Seattle, Washington. We're on the conference floor and there's just a lot of excitement here.

**Joshua:** The conference has been really exciting so far.

**Paul:** As people who are not traditionally in the Microsoft world, it's funny to see how different everything is in Microsoft land. But also sounds like quite a lot of it is the same. But from a mobile perspective, what is different in Microsoft world, than for us Mac lovers?

**Joshua:** I think the interesting take from me is, and I've been around in Microsoft for five years so I guess I can say that I've been on the inside, seen the transition, and I would say we really do feel that any developer, wherever you are, it is really like the motto,


<blockquote>we've stopped making decisions and we've stopped having this conversation about "Windows or Microsoft first," and instead it's really pivoted to wherever developers are.</blockquote>


When it comes to the mobile world, we evaluate the mobile world, we see where the majority of the developers are and that's where we leave off. We always leave with the largest groups of developers. We're always trying to find the largest value proposition that we can provide to those developers.

I would say that hasn't always been quite the way that we've done decision-making, but it definitely has been for the last few years here at Microsoft. I would say that's the part that I think is starting to come out at things like the Build conference, where it's really starting to,you're starting to see that in the actions that we take.

**Paul:** The CI/CD that you guys advocate and that your customers use, is that roughly the same as the rest of the ecosystem?

**Simina:** I think we took a really, very non-Microsoft-y approach, when we started. Because we want to meet the developers where they are today, and we said mobile developers are today on GitHub and are mostly developing iOS in Swift or Objective-C.

First iteration of the product, while you're in preview, was connect with your GitHub repositories, build and distribute your iOS apps, your Objective-C, Swift apps and then we started looking at Android Java, at Xamarin and at other solutions as well.

**Paul:** Gotcha. And Xamarin is now part of that whole thing since the acquisition?

**Simina:** Yes.

**Joshua:** I think we merged with the Xamarin team. It's been really exciting to see, especially, I would say, how passionate the Xamarin community has been as they've kind of folded into the Microsoft stuff. And the Xamarin solution's fantastically incredible.

You can actually write native UI and then have it deployed. It actually brings all this consistency across all your platforms, it's really exciting to see the stuff. We've really had the excitement and maybe some new energy.


<blockquote>Xamarin was an external company and so I think they brought in a very different perspective to how we're doing the development. </blockquote>


So it's really fun to work with those guys and partner up with them.

**Edith:** Yeah, I remember last year I was at Build and they announced that Xamarin was now available to everybody, and people were literally cheering. There's so much excitement around that amongst the developer community.

**Paul:** Xamarin is a C# solution, right?

**Joshua:** That's correct.

**Paul:** It's interesting that you folks were doing non-Microsoft-y technologies and it was the external company that brought in the C#-ness to mobile. Then Hockey was an acquisition as well, right?

**Joshua:** Yeah, HockeyApp was an acquisition.

**Simina:** It was in December 2014, I think.

**Joshua:** I think maybe two and a half years ago.

**Paul:** Was that before your time or ahead of that?

**Joshua:** It was actually right at my time. When the HockeyApp team, I actually joined directly with the team, when it merged in. That was really exciting too, especially with the popularity and how common HockeyApp was.

I would say, especially for that iOS distribution market, they really focused in at the starting days. They were very much an early innovator, and that's base distribution. It was really interesting to see this long history of development and this long engagement with customers that they had built up over time.

**Simina:** And for HockeyApp, it's so exciting. Because most of their customers are people that we at Microsoft, until now, we didn't have contact with.

**Paul:** Because they're so small?

**Simina:** Because they're small, because they're just not traditional Microsoft developers, they don't use C#, there's many smaller companies. And it's just so exciting to work with them.

**Edith:** What do you think is the difference between the traditional Microsoft developer and a non-traditional Microsoft developer?

**Simina:** That's a good question.

**Joshua:** I think it has a lot to do with just the stack. That you end up, I mean, everyone talks about the platform stack that you pick. There's very, definitely a Microsoft stack with a lot of tooling and a lot of richness. But it's not the only option out there.

There's a lot of other stacks, especially with the change in mobile development, to these brand new platforms for Android and iOS, where they were brand new platforms, nobody really knew at the start what they were doing.

I talked to the founder of HockeyApp, Thomas, and things like that. He talks about being one of the first people to have the original iPhone, and actually, his co-founder, Andreas, was developing an iPhone app before they had even published the APIs. Being there right at the thing, nobody really understood the new stacks. And there's these entire ecosystems of tools and stuff that have built up into those communities.


<blockquote>For a while the communities were very separate and maybe independent, and I think what's been happening over time is that these communities have been merging back together. </blockquote>


It turns out that we all have the same problems to solve and that innovations and the one set of tooling in our areas, something like CI or CD or these DevOps movements, it's starting to bring these communities together. Where it's not so much, you make one platform choice and then that means that you have seven other tool choices that just become obvious because that's the platform you are. And I think they're starting to become flexibility now, where you can go out and pick the best tool for the job and the tools support multiple platforms. I think that's really great.

I think it's bringing a lot more diversity to these different platforms, where developers aren't just locked in because they've made a platform choice at the start, to all the rest of the tooling and now they can experiment and see some of the different perspectives that other people bring.

**Simina:** In fact,


<blockquote>Microsoft developer or non-Microsoft, in the end they have the same goal. They just want to make some really cool apps that people love. They want to have good reviews.They want to make money. In the end, everybody wants the same thing.</blockquote>


**Joshua:** They have very much the same problems we all hate.

**Simina:** The app expression for everybody.

**Paul:** From the perspective of CD in the mobile app space, I feel that there's a lot of weirdness specifically around the App Store. You mentioned reviews and the fact that there's the app review process, how does that effect continuous delivery for people in the mobile space?

**Simina:** It affects it quite a lot. That's why we think, because you have to wait forever to get your app reviewed, not forever, but quite long, it's really valuable to have a lot of iterations. And we guide our product a lot around the "build-measure-learn" methodology.

We really think that once people start building the app, they want to test it with early testers, with their internal teams, maybe with alpha testers. They want to get feedback, they want to measure how people are using it. And then at some point start doing deployments to App Store and then get reviews and so on.

Even once they deploy to the App Store and the app is out there, it doesn't mean that their build-measure-learn stops, right? They still are doing alpha testing. All the games are always having some betas out there. We guide our product a lot around just making these continuous iteration cycles really, really easy for mobile developers and just making them immediately, not have to wait a few hours or a few days, but just shipping the apps as soon as possible in the hands of their testers.

**Edith:** I was formally at TripIt, which was a number-one travel app. It was something we were very serious about is, that you're always iterating.


<blockquote>You try to get stuff in the hands of users, whoever they are, as soon as possiblebecause user feedback is everything.</blockquote>


**Simina:** I think, in the world of web apps, it's much easier to do it because you have so many tools. But for mobile, you actually have to take the app and put it on their device,which makes it a bit more challenging.

**Joshua:** I always found that was the biggest paradigm shift for me, was always when you move from web to mobile. In the web world you own everything: you own the server that the web server's running on, you own the back-end database systems. Ultimately, you could just reach out and SSH into them and actually tech them.

When you go into the mobile world, there's so much of that experience now that's just outside of your control, right?


<blockquote>The actual device running it is a device in somebody's pocket. You don't have any influence over that, any control. </blockquote>


You can't push stuff there or the App Stores, where your delivering mechanisms, it's not your own server you're deploying to, it's some external system, that's controlled by Apple or Microsoft or Google, and you lose a lot of that ability to control and influence in it.

I think, for mobile, the transition shift where you're going to have to start working with these external systems instead of your own systems, where you have so much more influence, results in a lot more thinking about what the experience is, trying to define those interfaces with those external systems to how to work best

**Paul:** I'm not really sure I see such a stark difference. The way that I see it is that both mobile and web have essentially two phases, I don't want to say two phases because that's another thing, but there are two steps in getting code in front of the customers.

The first is getting the bundle that includes that code into customers hands, and in that caseit's the App Store or it's deployment to the server. But the second phase is enabling the code, feature flags, obviously, what Edith's company does.

**Edith:** Thanks for wearing your shirt today.

**Paul:** No worries. For once, you are wearing a LaunchDarkly T-shirt. It's a thing we do. Never mind. If people are taking that strategy of, "the code doesn't change until you flip the flag," then the fact that there's an App Store review or just code review on your web process, on your web deployment process, doesn't really look all that different.

**Joshua:** Interesting.

**Edith:** That's what basically what my company, LaunchDarkly, allows you to do, is separate out deployment from visibility. You can push a build to the apps, to the App Store, and then selectively turn on features or turn them off if they're performing poorly.

**Joshua:** It's an interesting idea. You're saying that by integrating in the feature-flag-type capability, that a little bit return that control back to where you can change the deployment to a little bit on your terms, as opposed, just the actual deployment to the store. It returns that a little bit to, it turns the same, I pushed the package to the web and then enable it, and I push the package to device and then enable it.

**Simina:** I think for the React Native world, it's even a bit more easy. Because you have technologies which really do updates in the app, without having to modify the binary and your code push, or other similar technologies, you just go in the app and you get a new update and you had no idea that you had any update. You just have a new package.

**Paul:** I remember this. There was this giant fiasco a couple of year back, you might remember about the Amazon Kindle app, that deleted all of your books. Amazon launched it for iOS and then had to get special Apple permission to launch a new version of the same app, the next day and get a fast track through. If they had had the new stuff behind a feature flag, it would've affected a handful of people and then they'd turned it off and it would never have become a big thing.

**Simina:** That's an approach we take with the product that we are working on all the time.


<blockquote>We have everything, literally everything, behind feature flags. </blockquote>


**Edith:** Oh, cool.

**Paul:** Do you have features around helping customers do the same things?

**Simina:** No, right now we have feature flags to help ourselves to help customers.

**Edith:** I'd love to hear more about that. Do you have everything behind a feature flag? And what's Microsoft's process on that?

**Simina:** I think Microsoft's process is very different across different teams. In our team, the way we run the product is that we have a support chat window in the product itself. So people ask us for features and things they want to try.

Many times we just take one of the asks that appears every time and we implement it. Then we ask the users that have asked for it, "Hey, can you give it a try? Is it what you expect?"Then we have a few iterations on that feature flag capability. Then once it meets the bar, we just release it to everybody. If things go wrong, we have a way to make sure that we don't delete everybody's apps or such things.

**Paul:** What is the process when you decide that that's not going to become a feature?

**Simina:** Many times we just shelve it for a while. We just don't release it.

**Paul:** So you have 100s of half-implemented features behind a feature flag that touches one customer?

**Simina:** We didn't start the product so long ago. We didn't get time to get to 100s, but it's very good for iterations and for just finding out if what we are working on for a few weeks, it's something that we should invest more months into, or if we just should call it a nice experiment for now and re-discuss it at a later date.

**Paul:** It sounds like you don't go back and delete those features.

**Joshua:** We do at times.


<blockquote>We'll do a stage rollout sometimes where we'll push a feature just to a few customers, especially since we have that Intercom technique where they can actually talk to us.</blockquote>


It's very easy to collect people who are definitely interested.

**Paul:** Do you actually use [Intercom](https://www.intercom.com/)?

**Joshua:** We use it pretty heavily.

**Paul:** Yeah, Intercom is awesome.

**Joshua:** That way we can collect up a small set of customers that are actually interested in this feature, and then we can deploy it out to those folks early. It's like a little bit of a limited release that gives us a little bit of a time to evaluate the initial response from those customers.

At times they're just happy, and we roll it out fuller. At times they maybe feel like it's not the right solution, and so we'll just continue to iterate, usually, to get it. I would say it's been maybe rarer for us where we've decided to abandon a scenario. I think that we tend do be pretty tenacious.

Once we take on a scenario for a customer or feel that this is a real customer pain point, I think we tend to be pretty, "Let's keep at it. We'll keep iterating, we'll keep redefining the product." It feels hard for us to give up on a user scenario and just be like, "No, that's not something that we're going to solve."

**Paul:** It sounds like, in that case, the user scenarios that you start to implement must be pretty fully baked at that point.

**Joshua:** I would say so. I think we usually feel like we're pretty confident by the time we take on a user scenario, because it is pretty costly.

**Paul:** You mean by the time you start to actually implement it?

**Joshua:** Yeah, when we start actually implementing it and the resources, I think, like to feel like we're pretty confident on that.

**Paul:** Do you have some phases before that, where you're trying to invalidate your hypothesis before it becomes a user story?

**Joshua:** I would say that's always part of our process. I would say it's always somethingthat we're trying to get better at. Making project decisions is difficult and trying to evaluate where you spend your resources is always a hardship.

It's always something we strive to improve, but we do try to go through a phase in the startwhere we understand the right features to go after and the right investments to make. We do things like customer interviews and even paper prototyping customer development. We really try to do a lot of that customer engagement where we just talk to customers,understand their pain points.

**Paul:** What you're saying is that there's many places for a feature to die before you're actually implementing.

**Joshua:** Yes, for sure.

**Simina:** It dies so many times.

**Joshua:** For example, we just tried something new yesterday which is that we have a little mini dev day where we brought in a lot of the Build developers directly into the Microsoft campus yesterday and then we just asked them questions about upcoming features, upcoming pain points to try to identify.

That's a great way where we can try to filter out some of those scenarios or pain points that maybe aren't worth further investigating. Or try to get a little bit more confidence in our own decisions, that the ones that we are going to invest in are the right solutions for us.

E- Tell me about it, you laughed when you said you've killed many features. Do you want to?

**Simina:** With Mobile Center we started less than one year ago. We have HockeyApp and Xamarin test cloud before, so Mobile Center is the new generation. Obviously we have a lot of things to catch up with and we have also a lot of customers to talk to. I think we had some good learnings around things we thought would be useful.

For instance, personally, we wanted to offer some experience around unit test and we thought, "We can be really MVP and see what people are saying." And we found out that the MVP is not enough for people.

Then we decided, "Okay, right now we don't have resources to invest heavily in everything, what we should do. So for now, let's shelve it for a while and when we can invest in it fully,we should go with a full-blown solution." Because just an MVP is not enough or people.

**Joshua:** Too minimal.

**Edith:** That's always hard.

**Simina:** It's not viable enough.

**Edith:** That's the hardest thing as product managers. I love MVP's, but what are they just sometimes too M and not V.

**Simina:** Exactly.

**Paul:** Did you leave the un-viable thing, the feature in, and some customers are still using it?

**Simina:** We left it for some customers that really wanted it and they still provide feedback.They said, for them, "It's fine for now." But we made sure not to roll it out to further customers. You don't want to set the expectations and then to take it away.

**Paul:** One of the places we end up, when that happens, we have it rolled there to a bunch of customers and then more customers hear about it by word of mouth or people tweet about it. And then it's like, we're in this awkward situation of, "Should we then roll it out to another customer?" Especially if there's migration involved to the newer version that we want to do later, as it ends up being really fucking awkward.

**Simina:** I think now we have the benefit that we are in preview. We have still a lot of space to experiment and people are really excited that we experiment a lot, and they understand.They're always, "Give me access to this, I want to try it out. It's fine if you take it away, it's just, I want to see."

**Edith:** I did a webinar with [Ed Blankenship](https://twitter.com/edblankenship), who runs another group. And in it he said,"Hey, I actually have all these feature flags with new features, people were so excited! They were like, 'I want to turn all this stuff on.'"

**Paul:** I really like enabling, allowing users to turn it on themselves.

**Edith:** That's what Visual Studio has now.

**Paul:** Oh, gotcha, nice.

**Joshua:** We've done that same self-enablement process with HockeyApp. We started in HockeyApp, what we were calling a "preseason program," because it's HockeyApp, so everything is hockey. Preseason was the early-adopter program, and I found it was very successful because it allowed the customers to want to be with the latest, who maybe have a little bit more of a tolerance for some of the unease or the experimental-type features.

It gave them a way that they could self opt in to being on the latest, and then seeing all the stuff and I found that by allowing your users to self select themselves in that community, I think it actually worked out really well, that they can try out these features in advance.

**Edith:** I think, what I've found is, that makes them feel a lot more community.

**Joshua:** Yeah, for sure.

**Paul:** I'm curious, how big is the community? And when you have one of these features,how many people are we talking, who enable it?

**Joshua:** For the preseason for HockeyApp, I think it's a couple of thousand.

**Paul:** How many total HockeyApp users?

**Joshua:** I don't think we usually share the total numbers. We'd say it's much smaller, it's a minority of the population, it's not a major segment of the population.

**Edith:** Joshua, I love puns, so what are some other code names that you can share from HockeyApp?

**Joshua:** I think we have our internal environments. We also pick up the same thing, so we called them "training," you know, you're practicing. I think we had the preseason program.

**Simina:** We had "the rink," which is the external web app. It's rink.

**Joshua:** I think the command line tool that we were using is "puck."

**Simina:** We have the logo, which is three pucks on top of each other.

**Joshua:** They definitely tried to keep with that HockeyApp theme.

**Simina:** Do you have a goon somewhere?

**Joshua:** You know, we don't.

**Simina:** In the Mac app, there's a Zamboni. The logo for the Mac is a Zamboni for the ice.

**Edith:** That's pretty cute.

**Joshua:** I really liked your idea about bringing the feature-flag concept into that CI/CD. I think, at least for myself, I usually think of CI/CD, I got caught up in the build infrastructureand the actual deployment of the package.

But in reality, we should take a step back and really look at the whole value chain. Which is, you do a code commit as a developer to have a new feature, and then it needs to get intoyour customer's hands and you want that to really feed back into your cycle.

**Paul:** The separation of CI and feature flags is a little bit unnecessary in a certain extent,that your one is an attempt to getting the code into production and you've got this branch in your Git repo, which is essentially the feature flag. But it's an incredibly coarse feature flag.

If you have people who, I've definitely heard of people doing this, who do feature flags by Git branches, and it ends up that that isn't possible for them to have multiple axes in whichthe feature flags are happening. I think it's interesting, that the rapid delivery process, I think it's sort of based on or sort of emerged from this idea of continuous integration. The old meaning, before CI meant build servers, when CI meant, "We start a new branch and then we merge it as soon as humanly possible." We call that feature flags now, I guess.

**Edith:** I guess.

**Paul:** CI name means build servers.

**Edith:** Thanks for joining us today. Do you have any final thoughts you want to share?

**Joshua:** It's been fantastic talking to you guys.

**Simina:** It was really fun.

**Joshua:** I really like these different opinions from different communities bringing everything together.

**Paul:** That's wonderful having you here.

**Joshua:** The collaboration's always exciting.

**Edith:** I loved hearing about how Microsoft builds software, because


<blockquote>it's always fun to talk to the people who are building software for people who build software.</blockquote>


**Joshua:** It's very inception-like, where you're deploying your stuff with your own stuff or your own CI's system's building you stuff.

**Simina:** It's also fun for us because every team does it differently. If I talk with friends from other teams, completely different approach. Best practices are always there, but not everybody does the same thing. It's always nice to talk to, even with people inside Microsoft.

**Edith:** Yeah, I think there's this perception that there's a "Microsoft way," but what you're saying is there's more different teams that build in different ways.

**Simina:** It's a huge company, right? It's very difficult to converge all the people to the exact same thing.

**Edith:** That's a good note to end on, thank you again for coming by.

**Simina:** Thank you.

**Joshua:** Thank you.


