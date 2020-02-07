---
author: andreaech
comments: false
date: 2016-02-27 00:19:10+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-staging-servers-and-continuous-delivery/
slug: to-be-continuous-staging-servers-and-continuous-delivery
title: 'To Be Continuous: Staging Servers and Continuous Delivery'
wordpress_id: 810
categories:
- To Be Continuous
tags:
- Docker
- feature flag
- load testing
- LXC
- Mozilla
- staging environment
- staging server
---

In this episode, [Edith](https://twitter.com/edith_h) and [Paul](https://twitter.com/paulbiggar) discuss a blog [post by Edith in ReadWrite](http://readwrite.com/2016/01/22/staging-servers). In the article, Edith asserts that you should kill your staging servers so that continuous delivery can live. This is episode #14 in the To Be Continuous podcast series all about continuous delivery and software development.<!-- more -->

This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.






**TRANSCRIPT **

**Paul:** So today we’re gonna talk about a [post that Edith wrote](http://readwrite.com/2016/01/22/staging-servers). The post is about the [death of staging servers](http://readwrite.com/2016/01/22/staging-servers). Can you give us a little bit of an introduction to what the post is, because I think we’re gonna talk about it quite a bit.

**Edith: **Sure Paul, happy to. By the way, did you read it yourself?

**Paul:** I confess, I may have skimmed it, a little more than read it.

**Edith: **Yeah, so I’ll give you the summary. And then we’ll talk about it. And then you should go read it, and then we’ll talk about it again.

So the article’s an outgrowth from what I was seeing with [LaunchDarkly](https://launchdarkly.com/?utm_source=launchdarkly_blog&utm_medium=organic), my company. So already one of the comments I saw on it is, and I like this comment because they talked about me in the third person. They said, “Harbaugh is biased.”

**Paul:** Right, I would say so.

**Edith:** But by the way, she does have a good point. So I’ll state upfront, yes, I’m very biased. My company makes a platform to manage feature flags. So my bias, though, is I’ve seen what our customers are doing.

And it’s the reason I wrote the article, is that this was a national extension to the way I saw our customers using feature flagging.

**Paul: **So were your customers using your product wrong, or was there a thing that was happening, that you’re talking about?

**Edith: **So feature flagging at it’s most basic is very simple. It’s just an if-then statement. You don’t need LaunchDarkly or any sort of system to manage that, you can just put a conditional in your code. What happens after that is you get more sophisticated. And you wanna have some sort of dashboard where you could see the different feature flags that are visible and uplevel them. Not even just to the business side, but even amongst the various developers.

You want to have a central place where you can manage. That was kind of our first version, is just you can manage feature flags.


<blockquote>The next thing that our customers were asking for in our road map was to support for environments. They wanted to be able to have feature flags on dev, QA, staging production, have visibility all in one place.</blockquote>


**Paul: **I’m a little confused when you say this, because surely an environment is just a flag?

**Edith:** Yes, go on.

**Paul:** It seems like you could say, have another flag that is a string, that is like staging or production or Dev or whatever. That you flag features on.

**Edith:** And that’s basically what LaunchDarkly is doing, so for us, we just have another flag.

So each environment gets an API key.

**Paul:** So again, forgive ignorance on this, why not use the existing flag?

What was missing from the existing feature flag infrastructure that meant environments had to be a separate top level, or first class feature?

**Edith:** So now we’re getting a little meta. The reason why people liked using LaunchDarkly is because they can get a consolidated view of all their feature flags.

So that they could not just have these floating around fig file for each machine, but have a roll up of what flags are turned on and off for different environments. And then on top of that the ability to manage the flags in different environments.

**Paul:** Got you, so they wanted a view that applied to just their environments?

**Edith:** Well, to see per environment what was turned on and off. So basically they were following a software life cycle, where you had dev people working on the developer boxes, pushing a QA, pushing a staging, and then pushing to productions.

**Paul: **When features moved from one to the other, was there a human promoting these, or was there an API call promoting these?

**Edith:** At this point it’s mainly human. I could see down the line that it would just be an API. And even beyond that … The next thing people ask for, once they got more people on board LaunchDarkly, we’re using more feature flags, is they wanted the ability to have lockdown of different flags in different environments.

**Paul: **Lockdown like people can’t change the flags?

**Edith:** So they wanted QA to have rights, and QA to change some flags, but not in production.

**Paul:** I see, okay yeah.

**Edith:** Then after that the natural step then is okay, if you have a feature flag in system where you can control any step, who sees permissions?

Who gets to see what? Why do you really have a separate QA staging and production box? Why not just collapse all this, and manage visibility with a feature flag itself?

**Paul: **Sure. That makes perfect sense.


<blockquote>All the feature flags provide the primitives on which you can build the things that they want.</blockquote>


**Edith:** The point I made in the article is that


<blockquote>people use the substraction of a QA and a staging environment to basically try to encapsulate a change. So that was the original intent, and at the time it was very good, because the alternative was just to push everything to production to have everything break.</blockquote>


But if you’re actually doing—

**Paul: **If you’re doing feature flags properly, then the concept of really having a staging server doesn’t make that much sense.

Because you’re not pushing a feature to the staging server, you’re pushing a feature to production and then slow rolling it to people and really having it in the staging server doesn’t make that much sense. Is that kind of the point?

**Edith:** Yeah, so that was the title of the article, [Kill the Staging Server](http://readwrite.com/2016/01/22/staging-servers).

**Paul: **This might be a good point to actually stop and read [the article](http://readwrite.com/2016/01/22/staging-servers).

**Edith:** Yeah, I’d appreciate that. Thanks, Paul.

**Paul: **We’re gonna take a, what’s gonna appear to be a 10-second break, but it’s actually going to be a five-minute break, while I read the article. I recommend you press pause and read the article yourselves right now.

**Edith:  **So welcome back, Paul has been furiously whiteboarding. I’d love to hear his thoughts now.

**Paul: **Yeah, so it’s a good article, I really liked it. The first thing that came to mind was the concept of names.

So the idea of having multiple environments is a weird one in particular. So imagine that you have … Service rented architecture, and it’s got like six machines or something like that, or it’s got 20 machines or whatever. The idea that you can’t spin up a new instance of it is kind of a little bit odd.

**Edith: **Yeah.

**Paul:** So what people have done historically, and this goes back to when things ran on machines, or particular ports, or whatever, was that everything had a name. It had DNS name or had a staging name.

And if you look in rails, configuration files, there’s a production name, there’s a staging name, there’s a dev name, there’s different environment variables for all of these. But it doesn’t actually make sense to have a name. Because a name implies there is one of them.

**Edith: **Well this goes back, are you going down the whole pets vs. cattle thing?

**Paul:** I’m going down the pets vs. cattle thing, yeah. If you’re naming your pets, then you can’t just suddenly get six of them, you can’t suddenly kill them. But what you really want is cattle.

So a staging server is not, I mean a staging server is a pet. And a very very important pet that everybody loves, and everyone plays with, and it gets a little bit confused as a result of it. And that analogy went—

**Edith: **I’m not sure if you’re agreeing with me, or disagreeing with me, so. We’ll continue, it’d be great if you disagreed, but I would also enjoy it if you agreed.

**Paul:** If that analogy holds, then what you’re suggesting is that we killed the cherished family pet.

**Edith: **Well, you know, sometimes … aw, I can’t even go there.

**Paul: **Well the analogy breaks down, but let’s say it’s for the best if that pet spends some time on the farm.

**Edith: **Went for a long walk.

**Paul:** Right. So obviously production is an actual thing that needs a name, it is a unique environment. But nothing else is really unique environment.

**Edith: **Yeah, and to fast forward, I think, I got a lot of feedback on the article, which I loved. That’s kind of why I wrote it, for feedback. I think there are cases where you do want to not go directly from a developer to production.

I think there are many cases where you want to have other places to test them.

**Paul: **I do agree with this, yes.

**Edith: **I think a lot of the cases though, of a forced march of we go from this step to this step to this step to production is actually very harmful, when if you just pushed off much quicker and perhaps skipped some of these steps, you’d get the feedback you want directly.

**Paul: **So what we did at CircleCI, and initially we had a staging environment. And we would occasionally use the staging environment if we want to test something that wasn’t that easy to write unitests for, or something along those lines. And usually for us that was stuff around LXC, or stuff around starting Amazon boxes.

Things that you didn’t really do that often, and that either had an expense, or had a weird architectural thing, where you couldn’t just do it in software, and practice it in software. So I think there is that need. Occasionally you’ll have things where it’s not tested well enough, so you need to put it up somewhere where a human validates to the best of their knowledge that it actually works.

And you can put that in your, I was gonna say you could run it on, but the whole point of the staging server in that situation is that it’s something which isn’t really that easy to put into VMs, or whatever. The other kind of use case that you see is where you don’t want to be running stuff on live production databases, and you can’t get a copy too quickly. So you see people like Haroku trying to build products that avoid the need for that.

So with Haroku … You can take a copy of a database, you can have a view or a read only view on a database, that’s a copy on the right in some way or whatever. So that you don’t need a separate staging environment, or separate copy or separate staging database or whatever.


<blockquote>But if everything is well-tested, if everything works in software, then there’s really no need for staging environments. So that says to me that staging environments is a sort of a yellow flag somewhere. It shouldn’t really exist, but sometimes you might need it.</blockquote>


**Edith: **I actually want to write a follow up article now, of the staging server is dead, long live the staging server. Because I do think that there are used cases where you don’t want to push to prod. I do however think people—

**Paul: **What are these cases where you don’t want to push to prod?

**Edith:** So what I heard from [Sean Burns](https://twitter.com/SeanMBurns?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor), our advisor, is if you’re testing a really deep infrastructure change, for example switching some batch processing.

**Paul:** Mm, no, I don’t believe that for a second.

**Edith: **Alright.

**Paul:** So if you’re testing a really deep infrastructural change, there’s two ways to do that. That deep infrastructural change. One of them is to say, “We’re gonna have these machines over here, we’re gonna have these machines over here.” And that’s the quarterly release cycle thing. We’re taking a big big risk, all hands on deck, whatever.


<blockquote>The way that you want to be releasing that sort of thing is that you wanna have it in the code base. You wanna have an if statement, a feature flag, that controls how much of the data goes one way or the other, and you duplicate the data, or you put 1 percent of it through.</blockquote>


**Edith: **I think the key there is to duplicate or have some fail safe. I mean the biggest risk you run with doing this is data loss, which is awful. If you’re cavalier about how you do this—

**Paul:** Well, I don’t think data loss is the worst thing, the worst thing is your whole damn service goes down.

**Edith: **Well, the worst thing is your whole service goes down, and you lose a case worth of somebody’s data.

I think people are actually more forgiving of a five-minute flip than you losing like a lot of their analytics. So his point was he had been at Flurry, was that we cannot afford to lose people’s data.

**Paul:** So it would be ludicrous then, in my mind, to create a whole brand new infrastructural thing where you’re gonna do some kind of overnight or immediate change, or wait for downtime change or something. If the data is all live, you can’t afford to have, we’re gonna switch over and see if it works. Regardless of how well it’s tested, like it’s ludicrous.

**Edith: **Yeah, so that was, now I’m coming back around to my article. I mean that was the point I was making.


<blockquote>People think that they are reducing risks by doing all this tested staging.</blockquote>


**Paul: **Yeah, in fact they’re increasing risk.

**Edith: **Yeah, you would think you’re—

**Paul:** Well, the whole point of continuous delivery is that by having a harsh cross over between one thing and another thing, you increase risk even though you think you’re decreasing risk.

**Edith: **Yeah, so Ket Beck wrote a really good article, about reversibility. So he’s at Facebook now, but he said everything at Facebook is reversible.

**Paul:** Interesting.

**Edith: **That this actually makes you much less risky, ’cause you’re like okay we make these risky changes—

**Paul:** But they’re reversible, so it’s, right.

**Edith: **Yeah, vs. the more cutover. As I called in the article waterfall deployments.

**Paul:** I mean I think that’s a really good way of thinking about it. It ties it to a name that everybody knows is bad.

**Edith: **Well it was a deliberate—

**Paul: **Yeah, good choice. So the agile deployments then, are the ones where it happens seamlessly, and you can go back and forth and change the requirements and whatever else.

**Edith: **So that was Sean’s example No. 1, was what if it’s a really risky back and change? He had some good examples from his own career.

**Paul: **Did he have any examples that I would agree with?

**Edith: **Well a priori without hearing them, I don’t know if you’re going to agree or disagree. Another thing people brought up, was it just seems very risky to people. It seems to increase risk because I think they’re used to thinking of staging server as a safe harbor.

**Paul:** I think there’s some semantics around the use of staging server. You very often want to have a complete copy of your environment that you can test against. So is that a staging server, or is that where you type docker up, you know new environment.

And then you run your testing on this whole brand new infrastructure that has never been touched by anything before?

**Edith: **Yeah, and the critique I made in the article, is I think people do that a lot. And they spend a lot of energy testing there, but these are artificial test pieces.

Paul :     I guess there's 2 things. One, yes if you spin up a separate environment you are getting an artificial test case but often that's an actually useful artificial test case. For example, you want to do a load test.

Edith:     So that was Sean's other example.

Paul :     Okay.

Edith:     Seann's other example ... By the way I think Seann is great. He's an advisor of our company and he's a brilliant guy.

Paul :     Okay. I certainly wasn't saying anything different to that.

Edith:     I disagree with him on some points. He said he would do load testing to the point of failure.

Paul :     Okay. The distinction that I was trying to draw there between the staging server and another environment that you can spin up. Why is staging special? Imagine that you're doing a load test and someone else is also doing a load test on the staging server at the same time and you get the wrong results or someone else is fiddling with the staging server or the staging environment or the staging data center or whatever the hell it is. Everyone should have unique environments for doing this sort of testing and you should have everything in a Docker Kubernetes. Something magic.

Edith:     It's the future dude.

Paul :     Exactly. Something that's the future and you type the one command that gives your own unique environment and you run your load test on it and then you kill it. And instead of costing $30,000, it cost $300.

Edith:     Yeah. That was actually the original idea for LaunchDarkly was a company called Continuous dot L-Y. Continuous.ly which was exactly that. We would have the ability to do push button spin ups sort of environments.

Paul :     Good thing you didn't do that.

Edith:     Why not?

Paul :     Because Docker would have killed you.

Edith:     We didn't do it because the tooling wasn't in place when we were thinking about this idea.

Paul :     Right.

Edith:     But conceptually, John and I both really knew that this was very useful.

Paul :     Right. Well, imagine if the tooling had been in place. If Docker had just started and then you started building this and you could have been a cheap Aqui-hire for Docker at some point down the line.

Edith:     Well Paul, you can't AB test life.

Paul :     Load testing ... What were Shawn's other examples these are?

Edith:     Load testing and infrastructure and others I've heard-

Paul :     The infrastructure thing, I just don't buy it all.

Edith:     The load testing, I agree you don't want a load test to failure in production. I'd say the greater risk I see and I've seen this from people who've come to LaunchDarkly because they load test in staging. They're very happy.

Paul :     Yeah.

Edith:     They push it to production without a future flag.

Paul :     Everything that we're talking about here is risk, right?

Edith:     Yep.

Paul :     And you can do something in staging to reduce risk, right? You get more information about how many hits per second this thing can really handle and you get more confidence and the risk goes down. If you test something in staging you still haven't reduced the risk to nothing. So you still need a feature flag when you roll it out to production.

Edith:     Well, I am very biased of this matter.

Paul :     I mean I'm very biased in this matter as well. In the sense that I don't want people to write shitty software or services that we rely on to go den because people think that a staging server is a good enough test to reduce the risk quin when you still have risk at the end of it.

Edith:     Yeah and that's the thing, I think I'm not advocating for willy nilly coating, just pushing everything immediately. I'm just saying that you can't really test something unless it's in production.

Paul :     Yeah? I'm trying to imagine a situation in which when you run something on a staging server, you have absolute confidence that it's going to work. And if you can't get absolute confidence then you still have to have feature flags or whatever. You still have to be able to slow roll it in production. Then, the advantage that you think that you're getting from the staging server is over feature flags and I guess the advantage is staging servers that you don't need feature flags and you don't need to test in production. You've lost that benefit then?

Edith:     Yeah and then you've added all these other costs.

Paul :     Right. The cost of staging servers insane. When we had staging servers, I think we've moved to “per developer“ environments that you can create or destroy. When we had staging environments, it was like, is anyone using this? Has anyone done a database dump into this staging environment recently? Then with the database dump, there's the horrible thing of trying to make sure that the data that's in it doesn't have any secrets in it. It's a complete nightmare.

Edith:     I know it's a nightmare. Like you're spending so much time to replicate production and then nobody-

Paul :     You're fake replicating production.

Edith:     You're fake replicating and nobody wants to do it because they know it's going to get blown away.

Paul :     Right. Yep.

Edith:     Everybody has been burned.

Paul :     Here's one place that I would say a staging server is useful, but again it's not a staging server. It's a staging environment or a staging set. When you're doing data migrations.

Edith:     Yep.

Paul :     When you're doing very big data migrations, that's something that, unless you have some sort of immutable data ... What's the name of it? Like Lambda architecture or whatever those things are, where you never actually over write data. In that case you want to make sure that the migration goes well. What are you going to do? You could theoretically say, Okay we're going to take a copy of the data into the staging server. We're going to run the thing," but really what we're talking about here is you want to take a copy of the data somewhere and run it on to it. And it doesn't matter that there's a staging server involved or that the staging server's involved or the staging environments are involved. What matters is that you have something and you could call it data migration 12 halls test.

Edith:     The rough draft. Yeah. I put it more that you want to ... Maybe I should use the word sandbox?

Paul :     Sure.

Edith:     Yeah.

Paul :     Sandbox is a better term than environment because environment implies a named thing, all right? If instead you say, "Oh, we're going to run this in a sandbox," it implies that you've got a new thing that no one else is interfering with or touching.

Edith:     Oh and also that it's temporary, that it's going to get stomped on because a sandbox is this env-

Paul :     Yep.

Edith:     It's going to get rained on. People are going to rake the sand out.

Paul :     So one thing when I was reading through your article-

Edith:     And thank you Paul.

Paul :     Another thing that came to me was different teams have different requirements.

Edith:     Absolutely.

Paul :     You were talking about the QA team and so on. When you have different environments, what you get is teams are protected from other teams. You have a staging environment and maybe that's for the developers. You have a QA environment, that's for the QA team. The QA team doesn't need to talk to the application developers or whatever. It doesn't need to talk to the opposite team but again, this is a thing where someone on QA could just have their own environment or just spin up this environment for 10 minutes and spin it down at the end. I don't see any advantage to having an actual staging environment.

Edith:     And then there's a further perversion which I saw, which is someone would want early access to a feature so I would do more. If you were doing any sort of sales and somebody wants to see an early feature then you give them access to QA and then all of a sudden everything goes sideways.

Paul :     Oh Jesus yeah. No, that seems like a complete nightmare.

Edith:     Well because there's somebody who really wants to see something early and you give them the access to a really sloppy environment. Then, there's all these other issues and all of a sudden you get emails like nobody touch the QA box because we're doing a demo.

Paul :     Right. We had a stage where our staging environment was Google-able.

Edith:     Oh.

Paul :     It was fine because it's the same code base. It's got the same security protections and that sort of thing. But our docks linked into the staging environment which were, how often did we update the staging environments? They were out of date and whatever. It was important obviously to get that out of Google.

Edith:     Yeah. It's just a nightmare. I talked about that article about when you try to have a separate beta server.

Paul :     Right. Yep, similar concept there except it's harder to tell Google not to go to the, actually…

Edith:     It's probably easier to just put it in a text. So Paul I'm really interested to hear about Circle CI and why you transitioned to not having a staging server.

Paul :     Well, so the major thing ... Actually there's a couple major things. The staging server was one server, right, because we didn't want to be running all these ... We used really expensive boxes so we didn't want to have 10 of them that were sitting idle doing nothing, right? We wanted one of them. When we had a staging environment, there was already one or two people using it and they'd coordinate and then we started having more people, whose turn was it to use the staging box and whose responsible for it? What software is on it? If we have a security vulnerability, are we going to remember the staging box?

Edith:     Yep.

Paul :     We should but who knows?

Edith:     Yeah there's just all those issues that just start adding up.

Paul :     Yeah. Instead, we started having per developer staging boxes. Then, we added tooling as well. We would have the per developer boxes would appear in our standard fleet management stuff so we'd be able to kill, if we had security issue or something like that, we'd just kill all the deaf boxes.

Edith:     Yeah, like cattle.

Paul :     Exactly, they were all cattle and if you wanted another deaf thing, there was a single command and it would come up. The reason that we have per dev environments or the reason that we had a staging environment was that we had some stuff that was really tough to test. In particular, we have a bunch of circle works by having a big, big amazon box and then splitting it up in 10 or 12 or 15 whatever it is containers, like elixy containers and then this fleet management stuff that runs across the set of boxes that does it. It was kind of tough to test that in production, right? If we wanted to test, does the new thing destroy our queuing mechanism or something like that? It was tough to test that thing that ran across multiple boxes in the fleet or whatever. The other thing that was tough is stuff to touch LXC. Our testing environment, obviously we tested circle on circle, but you couldn't run LXC test within the circle environment.

Edith:     Go ahead. Go on.

Paul :     You seem like you have a joke to make here.

Edith:     No. It was just ...

Paul :     No snark? It seems like you're really holding it in.

Edith:     I'll tell you later, Paul.

Paul :     Okay. We couldn't test LXC stuff and we couldn't test fleet level stuff. On the staging environment, we still couldn't test fleet level stuff because it was just one box. Then, we also, we could test LXC stuff and there wasn't a very good solution for testing LXC stuff. We didn't have like mock or stubs for LXC. We did but we didn't. We had a bunch of stuff. We had some typed closure things where we had more statically type things for those kind of name spaces. Then, we had the ability. If you're really going to mess with this, let's start a staging server. Let's run a bunch of things and make sure that it still works. So it gave us a little bit of confidence that the code did what it was supposed to do.

Edith:     What were some of your issues with the transition?

Paul :     There really weren't any issues with the transition because it's not like we got rid of a staging server when we were using it. We'd use the staging server sporadically and then we switched to per dev environments where we just started using dev environments and then staging went off and died.

Edith:     Oh. Did you have-

Paul :     Let's just taken that back and shop.

Edith:     Did you ever have a deliberate decision like we are going to stop using it or was it more like a dwindling?

Paul :     I mean it was one of those things where for a couple of weeks people are going, "Oh, this staging server's a nightmare. We really should have per dev things." Someone did a little bit of the work to get enough of it working for them and then sooner or later no one is using the staging server.

Edith:     Yeah so I was going to make a joke and say staging server is a technical debt but they're much more than technical debt. They're actual real money.

Paul :     They're real money debt. They're security debt. They're all sorts of debt.

Edith:     Can you talk about the security debt?

Paul :     Its just what I said a few minutes ago. If you have a vulnerability, which everyone has all the time and you take care of it and you forget to fix your staging server, it's another tie tractor.

Edith:     It's ironic that something, I keep saying this, that something that's supposed to reduce risk and say you save effort is probably this huge time sink.

Paul :     Yeah. Someone was telling me about the sales force data centers and machine models and that sort of thing. They have a new release every quarter. I think it's every quarter. For every quarter, what they do there's a new data center and they run the code in the new data center in parallel to the existing stuff. Then, they migrate one data center over from the old code to the new code at a time. This just seems like the craziest fucking shit I've ever heard. Who would think that this is a way to deliver software especially for the pioneer in SaaS. I think it's insanity.

Edith:     Well, it's waterfall deployment.

Paul :     It is waterfall deployment. It's pure waterfall and fair enough, they started in 2000, they're a big company now and they have all these enterprise customers who have all these enterprise requirements but I would not like to work there on that environment.

Edith:     Yeah. My real hope is ... I wrote the article to be provocative. I think there are many cases where people keep using this existing workflow but I hope it's the same sort of case as what you just said, that if you're using feature flags effectively. At some point you look at what's happening, you're like, "Hey, we could shrink this. We could do this quicker."

Paul :     If you have a staging environment, there's a reason why you have a staging environment, right? If there's no reason you have a staging environment and you can just use feature flags, you can kill it right now. There's some reason you are holding on to your staging environment. Maybe it's a part of your code base you can't test. Maybe it's something that you need to load bounce. Maybe it's something along those lines. I think the obvious thing for people who have a staging environment is make it so you could have any environment, right? Don't feel the need to claim the staging environment, just kill the concept, make it something that you can spin up immediately over there.

Edith:     Yeah. I go back to ... I loved it [when Kevin from Microsoft was our guest](https://blog.launchdarkly.com/to-be-continuous-continuous-delivery-and-mobile-development/) when he was talking about slimming down their release process. He basically did the con man style of why.

Paul :     Right.

Edith:     Why do we have a staging server? To reduce risk. Okay, is it actually reducing risk?

Paul :     Right.

Edith:     Why do we have a staging server? Is it to give certain customers early access?

Paul :     Right.

Edith:     Okay, could we do that in production?

Paul :     Right. Let's make a feature over there. That's exactly what I'm talk him in. Generally, there will be some risky aspect that has to be had in a staging server. There has to be had in a staging environment. Then, you get to things where they actually need a staging server, right? You've got one copy of that piece of hardware that you need or you've got a thing where you actually need one staging server. Maybe that's access controls that you can't deal with. I'm not saying those things will go away but they're probably not very good things to have organizationally.

Edith:     Yeah, I really like the word sandbox the more I think about it.

Paul :     Yep.

Edith:     I guess in this world, how closely do you think the data match between the sandbox and production? I guess it depends on what you're trying to test.

Paul :     Right. One of the things that we can do, that works really well, are our front end is a single page java script AP. You can have a single java script AP running in your dev machine that connects to the production APIs. You can just test in production. You can just test ... It's all the same security controls, right? You're jut heading the API. It's wonderful.

Edith:     Yeah.

Paul :     I think the answer to your question is, there's really not very much that you need a copy of the data that you need to format in a certain way. If you're doing a migration, yes, run the migration, have a practice run. Whatever it is you think can give you more confidence but generally, there's not many things where you need an actual copy sitting around on some server for someone to break into while you're not paying attention to it.

Edith:     Well, let's get into the nitty gritty then. At CircleCI, you have all your developers. Do they all merge directly in or what's your exact flow then?

Paul :     There's pull requests and then you merge directly in. There's a bunch of different services, we slow roll both code ... We can roll back both the code base that goes ash and we can also roll back. Well, we have feature flags for the rest of it. We generally put things at with feature flags on them if there's any sort of risk at all. If there's no risk, then they'll go straight in and obviously sometimes, we get at wrong.

Edith:     As usual Paul, we agree.

Paul :     Yeah. Well, I feel there's something about agreeing that shows like it's ... there's really a lot of best practices around doing continuous delivery and I don't think there's a whole lot of disagreement to be had about them.

Edith:     What other critic I heard was that I wanted to get rid of QA and I actually don't feel like I was advocating that at all.

Paul :     That you want to fire the QA developers?

Edith:     Yeah. There was like, "Oh, let's get rid of all QA developers." I'm like, "No, it seems that you actually have very good QA."

Paul :     QA seems like an orthogonal concern.

Edith:     Can you explain more?

Paul :     You might one these developers that believes in tester and development and the developers write all the tests and there's no QA at all, right? Or you might be one these people who believe that having a QA team provides a valuable thing and you can't test everything and QA goes and uses the things in production or distills or reproduces test cases from support or whatever QA does. That just sees entirely orthogonal from how you do your production environment. It's not orthogonal if you inject QA as a step before something goes out but hopefully you don't do that.

Edith:     Yeah, I actually agree. I think it more depends on how a given organization thinks about the world.

Paul :     Right.

Edith:     We've talked about this before but just how much risk you want to take before anybody else sees it.

Paul :     Right, the idea of having QA as a step that the software has to go through, I think it comes from a good place. It comes from a place that's like, "Oh yeah, we need all this testing to make sure that it validates." I think it's a crutch and I think it's not a particularly good crutch. You can't manually test all the things that might go wrong. I really like the way that Mozilla ditched QA. It had its staging channel, its canary channel or whatever that went at least a million people. There was a pre-released that went to 40 million people or something like that and then there was the rest of it that went to 400 million people. The developers would push straight to trunk after a peer review or code review and all that sort of thing. QA was there as ... They had all the environments and all the machines of all the different kinds that were supported so if you couldn't track something den, there was the availability to get that.

Fuzzers were being run from the QA team so they were fuzzing security stuff and they were fuzzing anything that could be fuzzed. In a web browser quite a lot of things can be fuzzed so they were finding crashing reports, they were trying to reproduce things ad test cases would come in and they would try to identify them and they would produce reports of what the real problems are that allowed management to put focus in the right areas. They would keep an eye on the long term stats like how often it crashed, how much memory usage is being done, what the performance was like. They provided really fantastic services to in conjunction with all the other teams that were working on it. It was never a blocking thing that every single chains that each of the, I don't know, 300 developers that are writing code, has to have their step go through some overworked QA team that's trying to manually click buttons as fast as they can.

Edith:     Yeah, I think that was what I was trying to convey is think a lot of continuous delivery so far has been ... Let's take our existing pipeline and make it easier and quicker to move between our existing steps.

Paul :     Okay.

Edith:     It hasn't been about how can we really remix or rethink about.

Paul :     So you are trying to get rid of the QA step?

Edith:     No, I'm just trying to say maybe it can go somewhere else in the process like Mozilla, like how do we remix this model?

Paul :     Right.

Edith:     Given that now that it's much cheaper ad easier to move between different states, what's the actual order we want our states to be in?

Paul :     We talked about this in a very early podcast that the two things that you need to make continuous delivery really work, you need to have testing, you need to have a high degree of confidence that your tests work and that you need monitoring.

Edith:     Yep.

Paul :     QA was a ... The manual people clicking things as a way of releasing software QA was really a crutch for both of those. It was a crutch for software that didn't have automated test so that you would catch the things that validate that still actually worked. It was a crutch for bad monitoring because you have to validate that it worked in advance because you didn't have any monitoring in production.

Edith:     Also, to go further back, it was because dev ops didn't really exist so there was just more of a wall of a developer.

Paul :     Right, it was literally thrown over the wall.

Edith:     Yeah.

Paul :     The QA team helped the development team. I don't know. The ops team was happier, the dev team was happier, everyone was happier to have this extra manual step even if meant that software didn't go out for an extra week or whatever.

Edith:     Yeah, I think this is an intersection of dev ops and having a more inclusive tent of ... Okay, we have these different groups. How can we make them work together in not the linear fashion that we have but in a way that makes sense quicker?

Paul :     One of the things about a QA team ...

Edith:     By the way, Fred just walked by and he sent you a lovely gesture.

Paul :     Lovely. The thing about a QA team, there's lots of ways that people imagine QA teams. I think a lot of them are pejorative, that the QA team is the low level, the guys who didn't get accepted on to the dev team and they're clicking buttons and maybe they're writing some occasional scripts and maybe someday they'll get to be a real developer or something along those lines.

Edith:     I disagree, I think QA is-

Paul :     I'm saying that this is one pejorative view of QA that lots of companies have, right? I know people who started on QA teams because they felt everyone has to roll through the dirt before they get option to get a real job. Whereas, I think that the ... if you have that model of QA, then you're missing the opportunity to have QA do real stuff.

Edith:     Yeah, truly.

Paul :     To have QA fuzz, to find bugs that exist there, to be able to identify broad classes of bugs that they can work with the dev team to eliminate to find things that affect people in production. They can have actual, useful jobs and not just be glorified button clickers hoping to one day become developers.

Edith:     Absolutely.

Paul :     The reason I'm making this point, is that I think that the people who ... There's a strong correlation between people saying, "Oh, you need the QA step in the way before it goes out," with people who view QA as glorified button pushers. The reason is, I think there's that political need to keep their jobs, to keep the value of the QA department and it comes from having that control on the code's journey out rather than actual utility.

Edith:     Yeah. It goes back to what I said of, "Why are we doing this?"

Paul :     Right, yeah. If you shift your understanding of what QA does, you automate the manual stuff. You have QA focus on real valuable tasks that improves the development process. Then, you know longer thinking of like, "We need to be in the way because this preserves our job, power or whatever it is. Instead, you're thinking, "We're obviously going to keep our jobs in our power because of the vast utility of the service that we're providing to the rest of the company."

Edith:     Yeah, that was the point I was trying to convey in the article is, I think QA is actually much more effective and can do a better job if they're not doing the drudgery of testing the same darn issue in a separate environment for times which is mind numbing, but can actually focus on finding real issues on production instead of just moving between boxes trying to reproduce phantom issues many many times. Did you ever have these issues with-

Paul :     I once did QA for a phone rollout back in the day. This was 2005 and iMod was being rolled out in Ireland. This was a terrible idea and everyone knew it but someone, somewhere had made it happen. I was part of a team that was literally clicking buttons. We had big lists of tests that needed to be run. Then, we would run them and then things would break and we would wait for them to fix and then we'd run them again.

Edith:     Yep.

Paul :     Not only it was drudgery but also it was completely ineffective actually. There was a bet going around the QA department as to whether when it launched, it would actually work. We really had no idea. We largely suspected that it wouldn't.

Edith:     Richard Feynman is one of my heroes. Have you ever read about his thing about cargo cult science?

Paul :     Yes.

Edith:     There's this blind belief that we're pushing stuff through QA so therefore-

Paul :     Right. Yeah, it's secure especially if you're copying it from like, "Oh, this is how Microsoft does it, " or this is the way it was 10 years ago and so this is the way it needs to be without a deep understanding of what the process actually is or why the process is there.

Edith:     Yeah, it's cargo cult. It's like, "Oh, we spend ... We push it through stages so it has to be safe."

Paul :     Right.

Edith:     I do have one contra, which I'd like your thoughts on. What do you think of the idea of soak time? I guess I have my contra to that one too.

Paul :     Soak time meaning you put out the code and you wait a while for something to happen?

Edith:     Usually, we would ... Soak time is we were just let something sit for 2 days or so on staging to see if any new issues can happen or we thought of anything but now, I think you can really effectively do that with feature flags-

Paul :     Yeah. You put an ad you turn on for a couple of projects and let it soak, absolutely.

Edith:     Yeah, just the idea-

Paul :     I don't see any reason that staging is the place for that.

Edith:     Yeah. At TripIt ... When we push out a new feature, we would wait 2 days or 3 days before we officially announce it.

Paul :     Okay.

Edith:     Basically, because we just wanted to ... It was live, people could use it but we didn't want to do a big PR push while we're waiting for a feedback.

Paul :     I think the idea of connecting the launch of the software with the launch of the PR campaign is a little bit silly.

Edith:     Oh, completely.

Paul :     I've seen lots of places where people are desperate, they're launching on Monday morning so they're desperately running the death march over the weekend trying to get the codec. If you're launching Monday morning, the code should go out weeks ago. It should've been turned on weeks ago just like let people play around, discover and then you did launch.

Edith:     Yeah.

Paul :     Maybe letting the beta group play with it. Maybe you're testing a dark and whoever discovers it can try it ad then PR doesn't need to happen on the day the code is pushed into production.

Edith:     Yeah, because that's a risky stay.

Paul :     Yeah.

Edith:     That's the absolute risky stay because you just push it live and that's when you suddenly find all the actual issues.

Paul :     Yeah, exactly.

Edith:     All this stuff that you thought you prevented in staging always happens in production.

Paul :     Thanks for listening to this episode of To Be Continuous brought to you by Heavybit and hosted by me, Paul Biggar of CircleCI and Edith Harbaugh of LaunchDarkly.

Edith:     To learn more about Heavybit, visit Heavybit.com. While you're there, check out there library, home to great educational talks from other developer company founders and industry leaders.




