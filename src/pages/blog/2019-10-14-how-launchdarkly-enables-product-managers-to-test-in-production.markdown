---
author: mattdel
comments: false
date: 2019-10-14 14:55:37+00:00
layout: post
link: https://launchdarkly.com/blog/how-launchdarkly-enables-product-managers-to-test-in-production/
slug: how-launchdarkly-enables-product-managers-to-test-in-production
title: How LaunchDarkly Enables Product Managers to Test in Production
wordpress_id: 194354
categories:
- Feature Management
tags:
- experimentation
- product management
- progressive delivery
- test in production
---

Karishma Irani, Principal Product Manager at LaunchDarkly, gave an informative talk at our September Test in Production Meetup in San Francisco on how LaunchDarkly's feature management platform allows product managers (PMs) to experiment with and validate new features in a production environment.


<blockquote>"Experimentation is one of the pillars that feature flagging enables for you. If everything's feature flagged, you can actually test out different variations of a particular feature. Let's assume [we're testing] a button. I can ship five variations of a button ... I can do a percentage rollout, I can target specific users to see specific colors of that button, and ... I can run an experiment and see which color increases the number of clicks." – Karishma Irani, Principal Product Manager, LaunchDarkly</blockquote>


Watch to learn the lesser-known benefits of adopting a culture of feature flagging across your team and of giving PMs control over certain aspects of feature testing and releases. If you’re interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/).

[embed]https://youtu.be/0evo68QmcJ4[/embed]

TRANSCRIPT:

Heidi Waterhouse: All right, next up we have homegrown talent Karishma from LaunchDarkly. She would like you to know that she's not a developer and she's very ashamed. I don't know why she would be ashamed of that because it gives us a lot of perspective to see how the world works in a lot of different ways, but there you go. She's Principal Product Manager at LaunchDarkly, and she's going to talk to us about how LaunchDarkly enables product management to test in production. So, here you go Karishma.

Karishma: Thank you. Cool, so, hi. I'm Karishma Irani, Product Manager at LaunchDarkly and Heidi has requested I hold the mic the right way, so I am not conscious at all right now. For anyone who may not be familiar with what LaunchDarkly does, LaunchDarkly enables DevOps teams to deploy code at any time, even if a feature isn't ready to be released to users. The takeaway from that, or the TLDR version of that, is helping you and your team separate when you release and when you deploy. Engineer teams can deploy at any time and when the product teams or marketing teams, assuming they have control, feel comfortable releasing it to customers, they can go ahead and ship it.

So, why do product teams test? The first and most obvious reason is to validate the direction. So, are we actually building what customers asked for? I vaguely remember a customer mentioning this, but is it actually what's translated? Gone through the translation of the research process, designs, it's what engineering has built, what PM have specced out, et cetera.

The first and most obvious thing is to validate direction. The second, and this is my favorite, is the concept of a lazy Product Manager, that's me. I don't want to go into a room and figure out for a week what the next five best things we want to build, I want to ask our customers. So, I want to get on calls with customers, I want to see how they're using our products and what the next five best things to build would be. Whether that's iterating on existing features, or building new functionality.

The last one, the last benefit of testing is building this culture of incremental delivery. I feel like there are a few teams I've worked with in the past where folks are really scared to ship something to production and have customers see it. Their reasoning is, "I'm not sure if it's ready. We haven't tested every edge case." This is perfect. Launching things early and getting beta feedback helps you figure out exactly what doesn't work. Craig mentioned just because it works on your computer, doesn't mean it works in production and that's exactly the reason why we beta test.

Common questions that you get from a PM during a beta process as an engineer on the team. Has been deployed to production? What can our customers see right now? Could you please turn this feature on for these five accounts? What's the purpose of this feature, life, and the universe and everything? At least most of those questions are questions you should have gotten from your product managers.

By a show of hands, how many members here, how many folks here are part of a team that tests in production? Cool, that's a good, that's a good number. When you get those questions from your PM, I'm judging you if this isn't how you react. This is how you should be reacting as a developer on a team. That's why I got this Fitbit. It helps me track my steps as I run around.

So, what's different and why am I, what's different now and why am I so excited about the concept of testing in production? After having joined LaunchDarkly recently, and I love it here, I came to learn of this concept of triads. Triads is all about building as a team. It's where you bring a lead from engineering, design, and product management together and form a triad that makes all the decisions for a product or for a feature from concept to launch. And so, the team collectively owns the successes and failure of the project. What that results in sometimes is Vikram, and Vikram's here by the way, he's right there. Vikram's our awesome designer at LaunchDarkly, and here is where he schools me on how I should be functioning in a more triad focused model.

So, I've gone over what the frustrations from a product team are when they consider beta testing, how LaunchDarkly functions in triads, but how do we, how do we the product teams at LaunchDarkly test in production? The two main concepts that we adopt, and it's an inherent part of our culture, the first is feature flagging. Everything we build is feature flagged. This is because our subscription plan is really good for ourselves, but also because it allows PMs to have actual control over the product features. So, I can at any point in time turn a feature on or turn it off.

If I know something's wreaking havoc, I can just turn it off. If a customer has been requesting something, and this happens a lot of times. I'm on a call with a customer and they say, "I just wish I had X," and I'm like, "You can check it now." They don't even need to refresh the page, it just shows up and that's the cool part. Just the look on their faces, it's really cool.

The second benefit of feature flagging is allowing you to manage access across all of your environments. How do we use this at LaunchDarkly? We have this concept internally known as secret shopping, where we internally test all of our features before we ship it to production. We typically bring in someone outside of the immediate project team so they have an objective outlook. They're not familiar with the bugs issues, design decisions, et cetera. In order to allow for internal testing as well as external testing, I'm able to use LaunchDarkly to actually turn LaunchDarkly, to turn that feature on for all LaunchDarkly users in staging. Then when I feel like I'm comfortable, I'm confident, I can find a handful of users to turn it on for in production for beta testing.

And lastly, testing in production for real. I'm not talking about a design prototype, I'm not talking about an isolated test, I'm talking about testing in production with your production infrastructure, your production systems. With your production load and having a customer see what that feature feels and looks like in the larger context of their application. That's how feature flagging helps us test in production.

The second concept, and I'm kind of biased because I'm working on this currently, is the concept of experimenting everything. Experimentation is one of the pillars that feature flagging enables for you. If everything's feature flagged, you can actually test out different variations of a particular feature. Let's assume a button, I can ship five variations of a button to ... I can do a percentage rollout, I can target specific users to see specific colors of that button and I can see ... I can run an experiment and see which color increases the number of clicks.

So, I can run an experiment on literally anything if I've feature flagged it. That helps me validate the feature quickly, iterate quickly, and it allows me to do this at scale. So yes, getting customers on a call and asking them how they feel about a particular feature definitely helpful, but seeing how thousands of users engage with a new feature in production and then objectively evaluating the data for that, it's unmatched. Oh, and it may also prevent an existential crisis for your PM. Didn't quite work for me, but worth a shot.

I've shared a couple of what I think are good ideas, but I definitely want to ground all of this back into an actual concept. So, I'm going to use an example of a project that we recently discussed and talked about, which is pagination for all of our LaunchDarkly application pages. I know this isn't the toughest of projects, but I think it's going to make a clear point.

So, what are the steps that we go through when launching a project like pagination and how can LaunchDarkly enable PMs to test in production? It all starts with flagging during the planning phase. You absolutely need to sit down with the team, the triad in this case, and evaluate the metrics that will define the success for your project. I'm not talking about company-level KPIs or OKRs, I'm talking about precise, tangible, measurable things such as in this case, page load time. Does pagination actually improve my page load time? If not, I mean, it shouldn't degrade it, but is it actually increasing my page load time? Are users intuitively clicking on the Next button to see more entities on their page, et cetera?

Agree on what needs to be flagged. Devs may want to flag the backend logic so if something goes wrong and the page won't load for the customers, they can just turn, they can toggle the kill switch off and the backend logic stops functioning, and it goes back to the default behavior before we implemented pagination. PMs may want to dynamically configure page values. In this case, I may want to test out how loading 50 flags on a page versus 100 flags plays out. And, our awesome design team may want to AB test something. They want to maybe test if putting the page numbers at the bottom of the page, on the top left, top right, et cetera, what creates the most engagement and the most intuitive user behavior? Also, predicting all of this ahead of time can be hard, so just go ahead and flag it all.

With that, step one is all development is feature flags. Out here you can see an example of a feature flag that's being created for an image swap example. Step two, define your rollout strategy. This is super important and it's actually really exciting. It's an exciting part of the project, because it's where you sit down and you decide, cool, I want to ship this in three different phases. When the first phase is complete, I'm going to roll it out to maybe these three customers that have been asking for it, and I'll call it the alpha phase.

Then when I feel more confident that it actually works the way it's supposed to, I'll go ahead and enable it for 10 more customers, let's call that the beta phase. And then finally GA, which is general availability, or launch. So, how do we go ahead and turn this feature to 100%, knowing that we're actually turning on the variation that works best for us? And dev teams, please define your kill switch.

Here's an example where I'm actually using our Segments features. On the left-hand side, you can see Segments. What Segments allows me to do is just create a segment, in this case, pagination beta and with every flag the dev team builds associated with this pagination feature, they can go ahead and serve it true for the pagination beta segment. Then later as I add users, or accounts, or any arbitrary criteria to the segment, they'll automatically see the pagination.

Step three, deploy everything to production and go home. This is for the devs out there. This is where LaunchDarkly's differentiation or separation of deploy versus release really comes into play. Because, you can deploy everything to production, know that it's on your systems. Hopefully, you've run some tests and made sure, and then you can inform the PM that, "Hey, it's in production. You can go ahead and test it out with whichever customers you'd like to test it out with."

Step four is, begin testing this out with the rollout strategy that you agreed on. In this case, you can see I'm turning it on for a set of alpha users, which in this example I targeted anyone with an email ending in @humio.com, and I turned it on for Ellen, who's our awesome next speaker. I'm serving the true variation for them, so they should see pagination immediately and it's all for everyone else.

I can tell that all the devs in this room are really, really thrilled about giving this kind of control to their PMs and designers. So, let's talk about custom roles. LaunchDarkly's custom roles are honestly in my opinion, the best I've come across. I'm not being paid to specifically say that. I think what's really cool is a, feature flag has several components. It's whether the flag is being targeted on or off. Is it on or off, and what the specific rules are. In this case, you might want to provide the product manager with functionality to add more users, but not turn the flag off and that's exactly what the granularity of our custom roles allows you to do.

Step five, and I promise we're approaching the end, build a scalable feedback loop. LaunchDarkly is truly full stack. When most people think about feature flagging, they think about, like turning a UX element on and off, and that's definitely not the case. We have our own dev and ops teams that have feature flagged things like search algorithms, that have feature flagged things like particular ... Or, they're running experiments on things like page load time.

Examples of how you could build a scalable feedback loop within LaunchDarkly when you're launching a feature is creating an experiment. An experiment in LaunchDarkly simply associating a metric with a flag. Let's assume in this case the flag is what's displayed here, the five different variations. Vikram, our designer, is really curious where he should place the page numbers. Should they be bottom centered, bottom right, top center, top right, bottom left, et cetera.

The default as you can see, the baseline, in this case, is no pagination because we're building a new feature. You can actually turn this on and guess what? Similar to our feature flags, running an experiment does not require any kind of deploy from the dev team. PMs can just go in and turn it on for themselves. In this experiment, you can see that we have a clear winner and that page numbers on the top right.

So, now what do we do when we know we have a clear winner? I'm just going to go in and turn it on for that variation. Initially, each of the four variations we were testing out was allocated a 20%, or was turned on for 20% of our users each, 25%. I can't, math. But in this case, I know that the page numbers on the top right variation performed the best, so I'm just going to roll it out 100%. Again, you guessed it, no dev effort needed here. I as the PM can just go in and turn it on to 100% and it's turned on in production, and this is where I'm releasing it. The key takeaway should be deploy when you want, deploy when you want and release when you're ready. And of course, I'm sure everyone in this room understands the pain between those two steps, deploy and release.

Just to recap how LaunchDarkly enables product managers to test in production, it creates a single workflow with the dev team from concept to launch. We're all using a single tool to plan the different phases of the project, to release the different phases to customers, to control which customers actually get access to answer questions like, what can my customers see in production right now? Is that in staging? Is that in prod? I can go and figure all of that out by myself, and I'm not very smart guys.

Build for incremental and faster value delivery. You can actually ship features incrementally, and it encourages you to do so because you can get that quick test, quick feedback. You have the low toggle that allows you to turn it on and off so you don't have to plan for a large deploy or release. You can test out ideas and variations at scale for iteration. This was the previous example where we actually tested out for different placements for the page numbers and got feedback super quickly. And lastly, it allows you to control access and features for complete peace of mind. Something's gone wrong, I don't want to figure out what that is. Thanks for letting me know Datadog or New Relic, but it's three in the morning. Just go in and turn that feature off. Toggle it off, figure it out in the morning.

So, that's all. I hope everyone here who uses LaunchDarkly is excited to have their product managers muddy their hands and get using it also. And, I actually do work on the products so shoot me your questions, thoughts, feedback and I'll be happy to answer them. Thank you.

Heidi: All right, does anyone have any questions for Karishma? You're just all stunned by her eloquence. That's how it works out. So, we're going to ... Oh, you have a question? You're going to ask it, and then I'm going to run the mic back to her.

Audience: What other types of environments do you consider testing in to be essential?

Karishma: That's a great question. The question was, what kind of environments do you consider to be essential to test in? Honestly, my first intuitive answer is, it depends. If it's a feature like pagination, that lets say some of our large customers who I may not be allowed to name have been requesting because their pages load slowly or just timeout. In that case, we would have to test in production and replicating that in a staging or dev environment would be kind of hard for us to do.

Having said that, we definitely practice testing internally in our production app ourselves. So, we dog food our own application and it's a meta concept. Honestly, I'm still trying to wrap my head around it, but we definitely test in our own production environment on our app. Our devs are 100% of the time. They have LaunchDarkly up on the screen and we use it. We use it to ship LaunchDarkly. It creates a really cool cycle where we test in ... where the dev teams I imagine test in their own local environments, then we collectively internally test in staging, and then ship to production and get feedback from the handful of customers that we've targeted through.

Heidi: Any other questions? Cool.

Karishma: Thank you.

Heidi: Excellent.

Karishma: Oh, and we're hiring.

Heidi: Yes, that was the question I was going to ask you. We are hiring for so many roles. You wouldn't even believe.
