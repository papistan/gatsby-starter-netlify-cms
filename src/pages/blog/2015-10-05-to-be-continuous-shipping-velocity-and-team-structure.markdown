---
author: andreaech
comments: false
date: 2015-10-05 21:24:21+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-shipping-velocity-and-team-structure/
slug: to-be-continuous-shipping-velocity-and-team-structure
title: 'To Be Continuous: Shipping Velocity and Team Structure'
wordpress_id: 676
categories:
- To Be Continuous
tags:
- Agile
- JQuery
- microservices
- Pivotal
- product management
- TripIt
- waterfall release
---

In this episode, Edith and Paul talk about who owns code, how to scale your engineering team, and cowboy coding. This is podcast #4 in the To Be Continuous podcast series all about continuous delivery and software development.

This episode of To Be Continuous, brought to you by Heavybit and hosted by Paul Biggar of CircleCI and Edith Harbaugh of LaunchDarkly. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.





**Paul:** Okay, so one of the things we wanted to talk about this week was the idea of shipping velocity and how it’s affected by team structure, sort of miscellaneous factors that aren’t part of continuous delivery.

**Edith:** Yeah, I mean, can you explain a little bit more about what you mean by velocity first?

**Paul: **Sure, so velocity is a sort of nebulous term that they use a lot in product management and that sort of thing to indicate how quickly, or the sort of through-push with which engineers and product teams are able to put through code.

One thing that isn’t particularly clear, and there’s this amazing blog post by a guy called [Phil Calcado](http://philcalcado.com/) who worked at SoundCloud, and he talked about the idea that even though that they had a very high velocity, they weren’t able to ship features very, very quickly, so often it would take 60 days to ship a feature even though no one got blocked.


<blockquote>The idea of shipping quickly, is a combination of velocity and latency, and it depends on your kind of business goals, whether you need to ship correctly or you just need to keep the through-put up.</blockquote>


**Edith:** Well, do you think part of the issue with SoundCloud might have been that they were trying to do too large features? I mean, that’s somebody’s first reaction when they hear it takes 60 days.

**Paul:** So in the blog post what he said is first someone would spec out something, and then they’d put onto the next person’s queue, and that would be maybe a designer who’d drop wire frames, and then the wire frames would end up on an engineer’s queue to implement it, and in between someone doing work and someone else doing work, there would be, sometimes, you know, 10 or 11 days of just waiting for it to get to the front of that person’s backlog.

So it wasn’t so much, you know, are you biting off more than you can chew, it’s just the process wasn’t particularly set up to be able to ship things very quickly.

When he got in there, the first thing he did is he said, “Oh, you’re not doing continuous delivery,” or “You aren’t doing continuous deployment,” so he turned on continuous deployment and got that set up, and it was a 66-day process before he finished, and when he got continuous deployment set up it was a 65-day process.

**Edith:** So all that work to save a single day.

**Paul:** Right. Well, it was more about, the discussion was about how it wasn’t really about, continuous delivery. It wasn’t really about the time that people were spending on certain things, the vast majority of it was the time that was spent waiting on it.

**Edith:** Yeah, that takes me back a lot to the whole idea of just in time manufacturing and lean.


<blockquote>The whole idea of lean was to reduce waste, and one area of waste is time.</blockquote>


Like if you have people on a factory line who are waiting for the next part, or you know, stuff queuing up, then you’re being very wasteful.

**Paul:** I think this is how people, I think that that’s the thing that the backlog is intended to fix, that you’re never waiting for things because there’s always something in the backlog that needs to get done.

But what isn’t considered as part of that is something is sitting in the backlog, for five days, 10 days, two weeks or whatever waiting for someone to address it, then the speed with which you can get a feature out increases dramatically, or decreases dramatically, I guess.

**Edith:** Well, that’s the whole idea behind the Toyota factory line is that they, the just in time delivery meant that there was always a part right then, not before and not after.

**Paul:** Right, okay. But right when they’re ready. But you couldn’t say, “I need a car now.” I think it’s not really optimized around the idea of how quickly something goes from one end to the other.


<blockquote>It’s more optimized around how quick, or how much, how little waste that you can have in the system itself, which means, in this case, how much developer, engineer, or designer engineer and project manager time is being spent doing nothing.</blockquote>


And I think you can certainly reduce that time to very, very low without necessarily optimizing the speed that which it takes to assemble a car, which is something that you need, really, to get to market quickly, and that sort of thing.

**Edith:** Yeah, and it’s a trade off. You know, I went to a talk that the former CTO of Yammer gave, Adam Pisoni, and he talked about how on projects they always had an extra engineer. Like if they thought a project would take four engineers, they would actually put five on it.

**Paul: **Right, right.

**Edith:** For precisely that reason, that they never wanted anybody to be sitting around blocked. So they would rather take the cost of an extra engineer, just so there was always somebody to do the next task.

**Paul:** Right. And so there’s an interesting thing about how teams are structured in that. In the Yammer example, they have teams, and teams do a project, or do a particular feature, and I presume that they’re cross-functional, there’s a couple of designers, couple of engineers, whatever.


<blockquote>A different way to structure it is to have teams that are aligned on a particular, by what they do, and you have the engineers who are sitting at the front of the front-end queue, or who work on the front-end rather than work on a particular project which has components of front-end and back-end.</blockquote>


And you end up with a very different structure, or it’s obviously a very different structure, but you end up with a different ability to ship, depending on how you’re, depending on what you’re trying to do, and what’s the most important thing for your organization, also how your organization is staffed.

So the backlog works very well if you’re short-staffed in any particular area, and so you spend a lot of time prioritizing so that the people, maybe you’re short on design time, so that the design time is spent really, really well, but it doesn’t necessarily allow you to turn around a feature from start to finish and get it out to your customers incredibly quickly.

**Edith:** Yeah, and that’s a decision that different organizations make. Some organizations say, “We’d rather have 100% utilization, even if it means our features take longer.”

**Paul:** Right. My feeling is that most organizations don’t actually make that decision consciously.

**Edith: **It’s implicit.

**Paul:** Right. Oh. So, what do you mean by that?

**Edith:** Oh, well so I worked at a lot of big enterprises, and my saying was always,


<blockquote>The lack of a decision sometimes is a decision.</blockquote>


Like, we’re not going hire an extra designer to unblock a lot of people, so therefore our feature’s are always just gonna be gated by that.

**Paul:** So when you say it’s implicit, you mean that, I guess you kinda mean the same thing as I do, that people aren’t really thinking about the advantages or the disadvantages of the structure of particular teams.

**Edith:** Yeah, that people are just kinda, they say, “Oh, everybody looks busy,  and why does a feature take 65 days?”

**Paul:** So one of the structures that I really liked, there was a [talk at Heavybit](http://www.heavybit.com/library/video/2014-01-14-peter-van-hardenberg), and I think it’s on the Heavybit website by _Peter van Hardenberg_ from Heroku.

**Edith:** Oh, he’s so great.

**Paul**: So in the talk he talked about that at Heroku they have product teams that are around specific areas. And the product teams have two engineers and a PM, and maybe a designer and that’s kind of roughly it.


<blockquote>Teams have like two to five people, and they’re focused on a particular area, so they do the prioritization within their areas, they do the support and the ops within their specific features, and then they’re able to trade-off, or they’re very, very close to the problem.</blockquote>


They have then project managers who are working to protect them from other areas, or bleeding into other areas, but also working to solve their particular problems, rather than necessarily one backlog for the entire, maybe the entire platform or the entire web, or something along those lines.

**Edith:** So basically, little small start-ups within a bigger company.

**Paul: **Yes, and I think actually that’s how they structured it at the start. I remember them saying that there was a, they would actually have presentations to the board, and that each of the teams was structured, the project manager was like a CEO, and they actually like gave presentations to the board, and I think that didn’t necessarily last very long, but I think that was the initial idea behind it.

**Edith:** Yeah, we did something very similar at TripIt. We had a, you know, we would have a new project we wanted to do. We were trying to do TripIt offers, and we had a project team just for that, and that’s what they did.

And the idea was that they could focus. I’ve also heard of people who do stuff completely different. Like I talked to a guy who ran an agile shop and every project had to be a week long, and nobody had any ownership whatsoever.

So he set it at, and not even like ownership in the way we would think of it. He said our front-end people were back-end, people were mobile, also.

Like and every week you got a new project, you worked on it for the week, and then you switched.

Paul :     Right. It's kind of like Pivotal's pairing.

Edith:     Yeah.

Paul :     It's not the two of you pairing together on a particular thing. It's like, your pair changes every day, or twice a day. And you're constantly rotated through all the different things. It's not necessarily one thing that you work on for any length of time.

Edith:     And he said it stopped people from being possessive about their code.

Paul :     I think the key thing about this is that there's no right answer. And it depends a lot on the people, but once you get into a bad situation for your team, I think it's very, very difficult to get out of it. Because there isn't ... I think people don't spend a lot of time thinking about, "we structured it this way to solve these particular problems." And that makes it very difficult to reason about the problems that we have might be related to the way that the organization is structured.

Edith:     Are you talking about how people claim Agile will cure cancer?

Paul :     Something along those lines. But also how you see a lot of reorganizations, especially in big companies. And the reorganizations, I think, are recognition at a high level that something is wrong with ... the processor, the structure is a thing that's blocking good people from accomplishing good things.

Of course they don't necessarily work out either, because the whole thing is ... There's so many trade-offs, it's impossible to tell in advance how something is going to work.

Edith:     Yeah, I've worked at companies that have re-orged every three months. It's kind of like the seasons of the year. I had seven bosses in one year, once.

Paul :     Wow.

So I found it interesting when you were talking about the idea of ... you have a project team versus a ... let's call it an owner team or an area of responsibility kind of team, or something like that. I think it's really interesting that the difference that happens between ... when there's long term ownership and when there's not long term ownership.

Edith:     Yeah. And I'd say the difference is, when there's long term ownership that stuff starts to become very poorly documented.

Paul :     (hums) Interesting.

Edith:     You know, because ...

Paul :     Right, plus-factor goes down.

Edith:     Yeah, well, if one person owns it, they don't feel any need to document it.

Paul :     Internally. Right, because they understand it all in their head, and they're ... right?

Edith:     Yeah, so I heard a ... I was talking to a customer, and they said just doing a single build was a nightmare, because there's only one person who understood how to do the builds.

Paul :     How to do a build along ... I mean, surely they automated the build, and that solves that problem.

Edith:     It wasn't automated, and it became this cruft where, he said, every time they deployed there was always the hero who fixed everything.

Paul :     Got you.

Edith:     But the reason he was the hero was ...

Paul :     He caused the problems.

Edith:     Yeah.

Paul :     Right.

Edith:     He never documented anything.

Paul :     Yeah.

Edith:     So like, every time it's like, "Oh there's a script, and then you do this, and then it's all fine."

Paul :     Right, right, right.

Edith:     And it goes back to ... people claim that sometimes that continuous delivery takes more time.

Paul :     Okay, wait, what do you mean by that?

Edith:     Because you have to be disciplined enough to do continuous integration. You have to be disciplined enough to put all this framework into place.

Paul :     Right, okay, so instead of fixing something, you write a test first and then you fix it, or something like that.

Edith:     Yeah.

Paul :     Yeah.

Edith:     So it's like, you have to have the discipline to clean up your mess as you're cooking, basically.

Paul :     Right, okay. Yeah, obviously this affects my business directly, so I'm just going to put a defense in for this. And I think the defense is that, if you don't clean up as you go then you cannot write test. You cannot validate that your code actually works. And that will get your velocity up for the first month and then after that you'll be afraid to touch anything. You'll be afraid to move forward.

Edith:     Yeah, I completely agree, because LaunchDarkly's customers depend on there being continuous integration.

Paul :     Right, right, right.

Edith:     So I'm on board. And it's kind of the evolution of ... I'd say ... a cowboy culture, where it's like, "ship everything as quickly as possible. Just get it out, get it out." And then you realize that that's actually very slow.

Paul :     Right, right.

Edith:     And if you take the time to write test, to do good code, to do continuous delivery, then all of a sudden it's a very efficient way to do things.

Paul :     So I think we can all agree that continuous delivery is awesome, continuous integration is awesome, LaunchDarkly is awesome.

Edith:     CircleCI is pretty cool.

Paul :     Great, great. So I think, looking back at the teams, and how the team structure affects it. It's kind of weird that after all this time in software, and I would say there's been about, maybe fifty years of professional software development under the belt now, that there isn't an optimal way of doing it.

Edith:     It's really funny you say that. My mother, I realize now, has been in software for a long time. She was an IEEE fellow, and she actually has worked on many standards about software documentation.

Paul :     Okay.

Edith:     Which for a long time was held up as "if we just have better ways to document how software should be written ... "

Paul :     Yeah.

Edith:     "Everything would be golden"

Paul :     Oh, okay

Edith:     And I, as the rebel daughter have always said that that's (both laugh) that these docs are ridiculous.

Paul :     Right.

Edith:     There’s standards on how you should spec software, and I'd say, "That's not the way people actually build software."

Paul :     Right.

Edith:     And then I shake my fist and I'll listen to rock and roll in front of her.

Paul :     So it's been, I don't know, twenty-five, thirty years since people have recognized that waterfall was a bad model.

Edith:     I don't know if it's bad. It came out of ... Let's talk about ... Waterfall came about because it was better than cowboy.

Paul :     Okay. I would argue that it's not necessarily better than cowboy.

Edith:     Oh.

Paul :     And I would argue that waterfall isn't necessarily inherently bad either, it just depends on the situation that you're in, and the ...

Edith:     Paul and I were actually about to have a disagreement, and then you doubled back on yourself

Paul :     Okay, so in what situations does cowboy work, for example?

Edith:     I think if you're just one person, maybe.

Paul :     Right, right, exactly. So if you are the product visionary, and also the sole implementer, and also you are the customer, and also it's a relatively small-scoped project that you can do yourself.

Edith:     I'd say that one drawback, though, is if you want to have any sort of maintainability.

Paul :     Yes and no. So I was using this software too the other day. It's called JQ. Have you come across it?



Edith:     I haven't.

Paul :     So it's a command line tool for modifying jQuery.

Edith:     Oh.

Paul :     And it was written by one guy named Stephen Dolan. And it basically has a very simple interface that lets you pipe in some JSON, do operations on it, and pipe out some JSON at the end of it.

Edith:     JSON in, JSON out.

Paul :     Right. And it's just a tiny thing that does one thing. It's incredibly well implemented when you look at the code. And it's just a very ... it's a one-man sized project. And it's ... the design of it is just super clear, in the way that you often don't get in larger projects.

Edith:     Yeah.

Paul :     Because it's all one person's vision and one person's direction on it. And I think that if you have that, then cowboy is an excellent way to do it, especially if you have an incredibly good person who is that cowboy. I think that where cowboy starts to break down is where you have two or three different cowboys, especially if any of them are bad at communicating.

Edith:     Oh.

Paul :     And I'm sure we've all been part of software projects ... and you see this especially in open source, where bad communication is kind of the definition of it, that you end up with projects going in many different directions, and people pressured to take in things that don't necessarily follow the vision, because there isn't a vision, because there's three people going in different directions with it.

Edith:     Well there's three visions.

Paul :     There's three visions.

Edith:     The issue is that there's not one vision.

Paul :     Right. And there might be twenty visions.

Edith:     So your conclusion is, "Cowboy is good if you have the right cowboy."

Paul :     I think the right sized project is also good. And I think this is one of the reasons that microservice is so successful. That you can actually build a microservice with one cowboy, so long as you have a well defined scope and well defined interface to the outside world.

Edith:     I think you can do that as long as that person is always the person who is maintaining it.

Paul :     Well, you can't have a loss factor of one. That has to go away.

Edith:     Yeah.

Paul :     But you can have an implementation where one person does the initial implementation, sets down division, and there's a simple set of principles on which the software is built. And that can be maintainable like that.

Edith:     (hem and haw)

Paul :     You don't agree?

Edith:     I write down everything because I forget it. I'll look back at something I did a year ago and I'm like, "Why did I do that?"

Paul :     Right, right, right.

Edith:     That's why I take notes

Paul :     So you're saying that cowboys won't take notes.

Edith:     Well if you're just coding and you're not commenting correctly, if you're not writing up all the test right, you're just assuming that nothing will ever change. Then you go back a year later ...

Paul :     Yeah, that wasn't really what I meant. I guess it's implied by the name "cowboy" that it's someone flying by the seat of their pants. So that wasn't really what I was thinking. I was thinking someone a little more professional, perhaps a little more disciplined than that, but I take you're point, definitely.

Edith:     Yeah, I mean when I think about cowboy, I think of somebody who just codes, doesn't comment, doesn't test, just ships.

Paul :     Right, okay ...

Edith:     If you're saying, "Can a single person write good code?" Yeah, of course. That's not really a discussion.

Paul :     I think what I'm saying is that, you can succeed in a sort of a more fly by the seat nature versus a more structured waterfall-like or even agile scrum sort of thing, under the right situations.

Edith:     But you still have ... So I think we agree, we were just ...

Paul :     Right.

Edith:     Perhaps we were separated by a common language.

Paul :     So going up one level. What's ... After the sort of cowboy level, I said that waterfall can work.

Edith:     Yeah, so what are some places where you think it can work well.

Paul :     Well if you know exactly what it is you're going to build. And the reason that agile came out and ... When you look at the agile manifesto, one of the major things is, "Deliver to customers quickly and iterate on that." If iteration isn't a thing that you necessarily need, such as something that has a very well defined spec. And I can think of a couple of examples here. If you're building something for a mobile phone network, everything within the back end of a mobile phone network has excruciating specs and acceptance tests of what goes in and what goes out. And if you wanted to write a new one, well you've got all the acceptance tests before you go in. You don't necessarily need to ship that to a customer and say, "What do you think about it?" because the answer, "What do you think about it?" is "does it pass this automated test?"

Edith:     Yeah, does my phone turn on?

Paul :     Right, right. So I think that that's kind of one example. The place where it breaks down, and I think the place where agile really excels, is where there's a customer, and where, as you say, people are separated by a common language. Where specs are difficult to write. Where it's difficult to understand what people actually mean by them. And where you don't actually know if the thing you're building ... it might be what the person asked for, but it might not be what they wanted.

Edith:     Yeah, so I love agile. I've seen it misapplied so many times and I've seen agile used as an excuse to basically go back to cowboy. We don't know what we're building so we won't do all this ... like, you know?

Paul :     Right, okay.

Edith:     We're just going to write without any specs and then we'll iterate, iterate.

Paul :     So this definitely misuses of agile. I mean, the very common misuse of it is to just call it agile ...

Edith:     Yeah.

Paul :     But do a waterfall on it.

Edith:     Well I'd say a more common is to be a cowboy. And call it agile.

Paul :     Right, right, right, right, right.

Edith:     Like, "Hey, we don't know what we're doing, so we're just going to write a lot of stuff, ship it out, and then fix it." Right, well that's not actually agile.

Paul :     It's like, "We're agile but we actually aren't going to do any of the ... follow any of the manifesto, or kind of the best practices of how to do agile, but we're calling ourselves agile, so leave us alone."

Edith:     Yeah, so I was at this company ... And I say this, I'm thinking of a specific example where like, I was working with another group and I said, "Can I see your specs? Can I see your stories?" And they're like, "Oh, we don't need them. We're agile."

Paul :     Oh.

Edith:     And they're like, "Yeah, we just write code. We're that agile."

Paul :     So this ... I think you get this a lot with small teams, and small teams where they don't necessarily have a vision, but where there once was a vision and then the team grew. And the assumption was that what had worked for two or three people would scale to five or six people. I think you can do cowboy well if you have two to three people who really understand each other and really get each other. And when you scale that, it kind of goes awry

Edith:     Kind of like a startup.

Paul :     I mean, startups are exactly the place that this happens. People in particular who don't believe in product management. You see this a lot.

Edith:     Who can not believe in product management?

Paul :     That was once me, believe it or not.

Edith:     No, Paul! No!

Paul :     Yeah, I know. I was very much a believer in developers making the decisions themselves, and developers talking to customers and validating things early. And so, basically taking the role of product manager and spreading it across a development team. And the thing that you quickly learn with this is that developers, A: Don't particularly want to do this, and B: Aren't particularly skilled at it ... or I'm not going to say, "not particularly skilled at it," but don't necessarily have experience at it in the way that an experienced product manager does.

Edith:     Wow, this is fascinating. So you were once not a fan of product management. What ...

Paul :     No, I mean I didn't believe it. Well, so I say I didn't believe in it at all, but what I actually mean is that I did quite a bit of it myself, and I considered that to be a core part of what engineering was. And to most other people, engineering was a smaller set of things that mostly focused around code.

Edith:     Interesting. So was it because you considered yourself a good product manager ...

Paul :     No, I didn't actually know that I had any sort of product skills at all. It's just that I spent a lot of time listening to customers, and sort of condensing or coalescing their feedback into, "this is what the product should be."

Edith:     And so you considered ... So you're like, "Everybody should be doing this at a company?" Or ...

Paul :     The idea was, yeah, "Everyone should be doing this." And with a little more skill and particular practice in validation, which was a thing that I wasn't particularly good at, or didn't particularly have any formal skills at that, let's say, I felt that it scaled very well. Like, it would scale horizontally if everyone just applied themselves to these skills.

Edith:     So if every engineer goes and talks to every customer, everything will work out?

Paul :     Exactly. And obviously ... in the obvious places of scaling, this falls apart. So, it fell apart when people didn't have the same ... or didn't talk to the same customers. You got different feedback from different customers. Or applied their own feelings from using the product more than talking to customers. There's a desire, as an engineer, to see a problem and to fix it.

Edith:     Or duct tape it.

Paul :     Right. And this is how ... you just add another feature, you just add another flag. And without someone who ... to really kind of hold the whole vision in their head and set out values and an understanding of how the product needs to be built, or what the product is, I think, you end up just, "feature upon feature upon feature."

Edith:     It's funny, because I had that exact same evolution, and I think that's why I was saying that. Because you're so pro-product manager, which always surprises me from a developer.

Paul :     So, what happened was, we were experiencing a lot of these problems, and I spent some time with the VP of Product at Intercom, Paul Adams. And I think that he is ... I don't know if he's actually like one of the best product people in the world, he just seemed to me to be. He just completely blew my mind, and seemed really world class compared to many, many other product managers I've talked to since. And he talked about how they did things at Intercom.

So they have overall missions for how the product works. They have different names for this, so apologies if I'm butchering this. And they set out a set of principles for what Intercom is, and one of the examples is, "Intercom is multi-user" or "multi-player" or some word like that. And they said, "here's a couple of bullet points about what it means to be multi-player, and here's how it applies in the product." I think they had eight different ones of these. And I'm sure they evolved that over time, but the idea of, "here's a bunch of things that you can read, and you can understand, and you can discuss or debate amongst yourselves without necessarily reaching out to authority, or to someone's vision, or to someone's opinion, and you can understand we need to do this because it is a multi-player product and this doesn't work in a multi-player sense."

And that's an argument that can win debates, whereas the argument of, "Well, you know, I really feel this should be like this ... "

Edith:     Oh, yeah.

Paul :     "I really feel this should be like this." No one can get anywhere like this and it's just a recipe for frustration.

Edith:     Yeah, it's, "I feel this should bethis color." I mean, everybody has a feeling.

Paul :     Right, right, right "Should pop more."

Edith:     Well of course it should pop more. Every time.

Paul :     This is probably not a thing to get into in this thing, but the ... we can't get into it deeply enough here, but the thing that we came up with ourselves was sort of a conflict resolution framework, called Problem, Solution, Implementation. And the thing is that as engineers, we would always argue about the implementation.

Edith:     Oh yeah, and then you get so deep and you lose track of what you're even trying to solve.

Paul :     Right. And instead when we raised it up to, "Here are the problems we've been trying to solve," once you agree on the problems, or the goals, or whatever that you're trying to solve, it's very easy to say, "Here is a solution that I'm trying to get to." And then you can all agree on the solution, and then the implementation just kind of naturally falls out of the solution in most cases.

Edith:     Well, it's even more than that. I'm sure you have a persona on top of all of this.

Paul :     Yes, yes. Problems, goals, personas, user stories, it's all kind of principles, missions, it's all kind of built in.

Edith:     Well, because where I've seen the biggest disagreements is where there was not a unified view of who even the user was. So I was working on a project once and our architect thought that the user was an architect.

Paul :     Okay.

Edith:     Everybody else thought our user was a content editor.

Paul :     Okay.

Edith:     So he kept coming up with all this stuff that you could configure the heck out of with a lot of code. And we're like, "Well the content editor, like they just want to sit and type."

Paul :     Right, right.

Edith:     And then he's like, "But they want to configure everything!" I'm like, "They don't. They don't."

Paul :     So that takes us a long, long way from where we started, but the ... I think it's kind of fundamentally the same idea. That you need to understand the ... or that the structure and the way that one builds software, I think, is the biggest thing that affects the velocity and the latency with which you can ship.

Edith:     And I'll quote again the Yammer CTO. He said, "the org you design is the software that you'll build."

Paul :     Thanks for listening to this episode of To Be Continuous, brought to you by Heavybit and hosted by me, Paul Biggar of CircleCI and Edith Harbaugh of LaunchDarkly.

Edith:     To learn more about Heavybit, visit heavybit.com. While you're there, check out their library, home to great educational talks from other developer company founders and industry leaders.
