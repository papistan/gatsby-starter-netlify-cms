---
author: andreaech
comments: false
date: 2018-04-10 23:51:43+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-open-source-for-enterprise/
slug: to-be-continuous-open-source-for-enterprise
title: 'To Be Continuous: Open Source for Enterprise'
wordpress_id: 193112
categories:
- To Be Continuous
tags:
- continuous delivery
- Enterprise
- GVV Capital
- HashiCorp
- open source
---

In episode 44 of To Be Continuous, Paul and Edith meet with Armon Dadgar, Co-Founder and CTO of HashiCorp, along with GGV Capital’s Glenn Solomon to dive into how CI/CD and open source can drive an enterprise-facing business strategy.

<!-- more -->

This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.

﻿﻿<span data-mce-type="bookmark" style="display: inline-block; width: 0px; overflow: hidden; line-height: 0;" class="mce_SELRES_start">﻿</span>&lt;span data-mce-type="bookmark" style="display: inline-block; width: 0px; overflow: hidden; line-height: 0;" class="mce_SELRES_start"&gt;﻿&lt;/span&gt;&amp;lt;span data-mce-type="bookmark" style="display: inline-block; width: 0px; overflow: hidden; line-height: 0;" class="mce_SELRES_start"&amp;gt;﻿&amp;lt;/span&amp;gt;





ABOUT THE GUESTS







[Armon Dadgar](https://twitter.com/armon) is CTO of [HashiCorp](https://www.hashicorp.com/) where he has contributed to projects including Nomad, Vault, Terraform, Consul, and Serf.

[Glenn Solomon](https://twitter.com/glennsolomon) is a Managing Partner with [GVV Capital](https://www.ggvc.com/), an expansion-stage venture capital investment firm based in the US and China.






TRANSCRIPT
















**Edith Harbaugh:** Armon, what do you like about continuous delivery?

**Armon Dadgar:** I guess what I like most about continuous delivery is not doing all the things I'd have to do without it. You know, it's funny, I think one of the ways Mitchell, oftentimes if you ever read a biography of Mitchell, he'll always say "automation obsessed."

He almost takes it to a bit of an OCD level, if you know him personally. He'll be like, "Yeah, I need a device that will open and close the shades of my house depending on time of day because I don't like to twist the little knob." I'm like, are you seriously talking about automating the little knob twist?

I think in some senses that's sort of the attitude, right? But then taking that knob twist and applying it to infrastructure and everything we do there. I really hate that little knob twist of, right after I git push, I have to go click a few buttons to do these things. It might seem insane, but you're like, yeah, I have to do that knob twist like three times a day.

**Edith:** Glenn, what do you like the best about continuous delivery?

**Glenn Solomon:** Edith, it's a good question. I think as a VC what I like most about continuous delivery is it gives me a ton of opportunity to invest. I look at continuous delivery as a symptom of a bigger opportunity. Symptom's probably the wrong word, but it's an enabler.


<blockquote>The great news about being a VC in the current market environment is I think every company is becoming a software company, across industry. </blockquote>


You know, Domino's Pizza for example, more than 50% of their orders today are delivered online and it's a real boon to their business. Who would've thought a pizza business would actually be a software business, but it is.

When you're in software businesses, you are in a deathmatch with your competitors. One of the ways you compete is by delivering better software, hearing and listening to the customer, and delivering as rapidly as possible. Innovation and features that people need to use your product and get benefit out of it.

So it turns up the pressure, but it also creates real opportunity for entrepreneurs. Continuous delivery is really cool because it creates lots of opportunity for VCs.

**Edith:** Well, you both gave enough hints that people could probably guess who you are. But do you want to go ahead and introduce yourself?

**Armon:** Sure, my name's Armon Dadgar. I'm one of the founders of HashiCorp, along with Mitchell Hashimoto. My background coming into the company was really not very operational, which is kind of funny.

I'm guilty to admit that I actually didn't even know a config management tool when I started HashiCorp. I know it's sort of like a guilty secret. Mitchell tried forcing me to learn when we started the company.

He's like, "You have to know one of them at least." But it was really my interest, more in the distributed systems and the end-to-end automation that brought me into this world.

**Glenn:** I'm Glenn Solomon, I'm a managing partner with GGV Capital. We're a 17-year-old venture fund, we manage about $4 billion in capital across six funds. We're currently investing in our sixth fund now.

One unique thing about our business is that we invest in both China and the US, and started with the premise many years ago that the technology world was going to get flatter. And we've seen that happen. So many of our companies are really starting to cross the Pacific Ocean one way or the other in lots of different ways across different dimensions, which we can talk about.

I've been a VC for 20 years. One of my more recent, exciting, notable investments is in HashiCorp. I participated in the series A investment with Armon and Mitchell back in 2014 now. Seems like Armon was 16 at the time.

Liked it so much we led the series B, and just co-led the series C more recently. It's been quite a ride and a real learning experience to be on Armon's board and Mitchell's board and watch the incredible work that they've done growing HashiCorp.

**Paul Biggar:** Was this the first open source company you invested in?

**Glenn:** It was not the first open source company I'd invested in. I'm actually also on the board of a company I invested, back now almost five years ago, a company called AlienVault which is a security business that focuses on selling to mid-market with a threat management and threat detection solution.

They actually have an open source SIM, Security Information Management product, that helps drive lots of usage of their core product and ultimately leads to pipeline generation and self-selection of potential interested customers for their product. So it's been very viable to them.

That gave me a taste for both the good and the challenge with open source, and made me more comfortable when, back in the series A, there wasn't much of a business model yet created for HashiCorp.

**Armon:** Generous.

**Glenn:** Yeah, generous. There was a lot of work left to be done and there still is. But yeah, the progress has been great. I've had a little bit of experience now with open source.

**Paul:** The open source and the business models ran open source, and that sort of thing is one of the things that we want to talk about. I'm curious, Armon, what was that business model, what does HashiCorp do to actually make money?

**Armon:** That is a good question. And it wasn't really one that like came easily. I definitely would not say we knew going into this what the right answer was going to be. I mean, when we started the company, the first few years were really just almost exclusively focused on open source product development and evangelism, and of getting the tools out there. I think Glenn and the rest of the board was kind and patient enough to give us the time to do that.

I think it was really late 2015 for us that we hit this interesting point where we'd released our eighth open source project and that was kind of what we imagined as being the full portfolio. This kicked us into this next phase of the company. We're just like, "Okay, all the open source we wanted to build, we've built."

We know they have their independent roadmaps and things we need to do, but the company's next phase was to figure out, what does HashiCorp the company look like? And not HashiCorp the set of projects. That was a hard process, I think we spent probably six to eight months sort of going through what that was.

**Edith:** How long, Glenn?

**Glenn:** Eight months might be generous.

**Armon:** I think the first, the biggest question, the hardest question for us was really, are we an SMB business and we're building Heroku 2.0? Or are we sort of an enterprise business and we're building VMware 2.0?

I think for a long time our answer internally was like, why not both, right? What's the difference? One person's paying with credit card and one person's filling a P.O., but otherwise, what's the difference? Turns out there is a difference, a major difference.

I think eventually what we figured out is


<blockquote>we really cared more to focus on the enterprise side, if only because we felt like our open source product let us already kind of reach the broader market. </blockquote>


Where if we were an SMB, yeah we could be, we could help everyone in a much broader audience. But our open source is already letting us do that. And so the market that our open source wasn't able to address was the enterprise, just because they were a different beast.

They were not going to go download our open source tool and run the bank on it without even talking to us. Where the rest of the market would. So I think once we had to figure that one out, then it was like, okay, let's convince the board, let's get everyone on board that we are an enterprise company. Then second questions was, what's the product?

Because, like I said, at this point we had eight open source tools. I think this really then kicks off that notion of, what's the business model? When we looked around we were like, there's a number of ones that you see work in the market. We'll do the "as a service" hosted model.

So great, you just want Mongo as a Service. Push this button, we'll manage the database for you. A lot of our tools could fit into that mold. There was more of the support, training, professional services model, a lot of that around kind of OpenStack.

So there's that play, and then there was more traditional, there's the more exotic dual licensing and things like that, but we were worried that would kill our open source community. Because anytime you see some weird, exotic license, you're not touching that. Then I have to go talk to legal or whatever.

Then really the final option was open core. Or some level of commercial differentiation and having a different binary. I think we weighed the different options, and in terms of what we wanted to focus on, we wanted to really focus on being a lean, mean software company.

That route ended up being the most appealing to us. It was like, we can focus on the features people want and the capabilities, and not necessarily building out a massive services arm.

**Paul:** What is the product, then? What is the thing that is around that open core?

**Armon:** Once we started with that decision, it was a matter of experimenting with the different products and figuring out what's going to work. Today it's four different commercial products. We have the six open sources: [Vagrant](https://www.vagrantup.com/), Packer, Consul, Terraform, Vault, and Nomad.

Of those, there's four commercial ones which is Terraform Enterprise, Consul Enterprise, Nomad Enterprise, and Vault Enterprise. So each, all four of those ones have basically a commercial variant.

**Edith:** What was it like to be on the other side of this, on the board? Did it seem obvious that they should go a direction? What was your role in this?

**Glenn:** After the series A, I felt like the company, there was definitely about a year's time when we had board meetings where we all left scratching our heads, not sure. It was a difficult year for the company in a lot of ways.

I think in other ways, a lot of goodness was accruing and Armon has talked to me and showed me curves, adoption curves of open source. One of the interesting things I think that we saw was that these were not meteoric rises. They take a while to hockey stick, but eventually with really all of the projects you guys have released, they become very popular over time.

There was still an innate belief even during that tough year that hey, there is a commercial opportunity here, we just need to figure out A, who's the customer, and B, then how to package something that they'd want to buy and do so in a way that is repeatable.

So I never lost that faith, but my partners were asking along the way, "Hey, how's it going over at HashiCorp?" Frankly there wasn't a lot of the traditional metrics one could measure and feel comfortable with during that first year. As, Paul, you mentioned, like


<blockquote>this open source thing, it's hard to get right. It creates challenges, but if you can get it right, and I feel like HashiCorp has really figured out how to get it right, there's huge, huge potential. </blockquote>


What happened after that first year, as Armon mentioned, the guys made a very brave but important call to focus, which is really hard to do as a young company when you're not exactly sure. You got a bunch of different roads you can walk down and you feel like you should walk down them all. But inevitably if you do that, you don't put your best foot forward in any of them.

We made a very brave decision to say we're an enterprise company. I think it was then incumbent upon the board to talk about, if you're going to be an enterprise company, how do you want to staff, how do you want to build a team that knows how to go sell and support enterprise, one. And two, if you want to go to the enterprise, what does the enterprise specifically want to buy from you today, and how might that change over time?

A second and key important decision that was made, that Armon and Mitchell really led during that time after focusing on the enterprise, deciding to focus on the enterprise, was then deciding to take the product, there was at one time a view that maybe we could launch into the market a more of a monolithic solution across all of the open source.

**Armon:** The product that shall not be named.

**Glenn:** The product that shall not be named.

**Edith:** What was it called, Frankenlayer?

**Glenn:** The guys made it, we really looked at the pipeline and it wasn't a hard decision to realize, wow, there's a lot of commercial interest in Vault, for example. And that has been layered, there's commercial interests layered in with some of the other products as well. So the company's taken to market four products. Which isn't easy, but so far so good.

**Edith:** What was this monolithic product called?

**Armon:** I mean, I think that one, yeah, we tend to rewrite history now to remove it from the history. But at the time, I think before we made the call to say we're going to be an enterprise company, the earliest commercial packaging we really tried to go for was a product we called Atlas.

One of the founding principles of the company was, we want to build Lego pieces and take a Unix philosophy of, "build one tool, have it do one thing well," and let the end user pick and choose and compose what they want into their own platform. We were sort of anti-platform from the beginning. We threw an extreme amount of mental gymnastics, built a platform called Atlas.


<blockquote>It was a basically a shrink-wrapped, end-to-end version of our tools without calling it a platform. We were willing to call it anything but a platform.</blockquote>


It was an opinionated, end-to-end pipeline for CI/CD. If anyone's like, "Well, that sounds a lot like a platform..." "No, no, no, it's just an opinionated platform. Or it's an opinionated pipeline, but not a platform." We sort of deceived ourselves a little bit with that. But it was moderately successful more in the SMB audience.

Once we had that conversation to say, you know what, we're actually an enterprise company, then you look at this platform where you're like, okay, yes, companies that are maybe less than 50 people, less than 100 people can be customers of it and it is an opinionated platform. Does it make sense to continue investing in this thing in the context of being an enterprise company?

It's super early in that process, it was like, okay, this thing has to be put to bed. And so we started sort of tearing out the pieces of it, but those became separate products. So instead of the giant platform, we sawed off the Vault capability and that became Vault Enterprise. And sawed off the Consul capability and that became Consul Enterprise.

**Paul:** So was this a closed source product that you were building?

**Armon:** Yeah, closed source, hosted, sort of SaaS, yeah. And then that was the other aspect of when realized the enterprise didn't want it in SaaS. They were like, that's nice, but we only want some of the functionality but not the whole platform, and also it has to be on-premise. So that was the final, like, yeah, this thing's got to go.

**Paul:** Do you find when you're selling open source enterprise stacks the developers at the enterprise spend a lot of time contributing back?

**Armon:** That's interesting, that's a good question. I think it depends a lot on the organization and their culture. I'd say it's really hard to say the hockey stick is not necessarily the size of the company that would really indicate it. It's just like, what is their cultural practice and their familiarity with open source?

There's some Fortune 500s that will be like, "Here's our Zendesk ticket issue of the bug, and by the way, here's the pull request that fixes it." Right, that's their level of familiarity and willing to splunk in. And then there's other people who will like not even read the documentation let alone get into the source code of it.

**Edith:** Let me ask another way. Do you think open source helps or hurts you in enterprise sales?

**Armon:** Definitely hurts, and I'd say it's the ultimate Faustian deal, right? What open source gives you is it's really easy to build awareness, it's really easy to build community and mind share around it. Because it spreads virally, right? It's like, I have a great experience, I tell my friends about it, and it goes everywhere. So the marketing side becomes really easy.

The the hard part becomes your sales side. Which is, you're selling against yourself, basically. The enterprise is no different, right? They're like, "We're already using the open source, why should we move onto your commercial packaging now?"

But it's two-fold, as it's that dual-sided blade of,


<blockquote>on one hand, the enterprise is using the open source. So they're willing to even engage in the conversation, so that's a plus. But the downside is you have to jump over your own highest bar. </blockquote>


**Glenn:** I want to take the other side of that argument. I absolutely understand where Armon is coming from and there are challenges to go the enterprise-with-an-open-source-business, for sure. That said, I also see some key advantages, and this comes from the perspective of having many battle scars sitting on boards of companies that are closed-source, trying to go after enterprise business.

I think the benefit that Armon has articulated that HashiCorp has really been the beneficiary of is this rabid community. And in a world where continuous delivery is becoming more prominent and businesses are more agile, and every company, even pizza companies are software companies,


<blockquote>developers and DevOps have become way more important and influential in what technologies get adopted and integrated and ultimately paid for in organizations. </blockquote>


If you can build a community of users of an open source that is really dedicated to what you do and becomes part of their business process, then it becomes very difficult to go rip it out. You have sold through the back door.

**Edith:** But have you sold? I mean, I think that's Armon's point, I think you've sold a product but you haven't sold something that people are actually paying for.

**Glenn:** But you've now traversed incredibly far down the sales cycle having already won the hearts and minds of some of the most influential people in the organization. Now, they may not have the budget, and so then the trick becomes how do you traverse the next level and make sure that the owner of budget, or the business unit owner is willing to write, sign the PO, and ultimately write the check.

That's hard, but believe me, if you're coming cold to a business with a closed source model, and trying to rise above the noise of every other company that's selling something similar, that's also very hard. So that's why I may take the other side of that argument.

**Edith:** I don't think they're two sides, I think there is "sales is hard."

**Glenn:** So is marketing, marketing is hard, too. That's what I'm saying.

**Paul:** You were mentioning the two sides of the blade, there. And the other thing in open source I think is two sides to the blade is the product development process. So on the one hand you have a lot of, I don't like to call people resources, but let's go with that for a second.

You have a lot of resources or people coming in from the outside helping you build the thing. On the other hand, you have a lot of people, a lot of noise in your product development process or your roadmap or, I mean, if you're like most open source products you don't have a roadmap. You just have what PRs show up. So how do you balance those two against each other?

**Armon:** The open source product management might be one of the hardest aspects of it. If only because there's so many stakeholders. From the early, early days,because before we had any sort of commercial product, I think even at that point there was still this challenge which is, everyone has a slightly different use case for our tools.

And especially, we're building pretty general-purpose tools. If you think about something like Terraform, you can use it to provision anything. Then you get these different polls in the community which is like, okay, do we overly specialize this thing towards being an IaaS provisioning tool?

Do we overly pivot towards, there's one side of the community that's like, "Hey, private data centers are really important," has a different set of constraints. And so having navigated that in the early days helped us build some discipline around, okay, let's at least understand what's noise here and what's signal.


<blockquote>Is it one person asking it, and that person represents the voice of one? Or is that one person the canary in the coal mine and a thousand other people alsothink that way about the tool? </blockquote>


A lot of that just came out of spending more time with the community, more time at conferences, at user sites, in sort of the mailing list, and on IRC and things that to really understand, hey, what's your use case? Like what are you really trying to solve?

**Paul:** It feels from what you're saying, and I think this is true of almost every open source project that has a company behind it, is that it is very much like sort of, the company is primarily dictating the roadmap based on user feedback even though the community contributes.

**Armon:** I guess one way to phrase it is,


<blockquote>we see the community as being one of our first-class stakeholders. </blockquote>


In the very early days, I think we saw it as there's two important stakeholders. There is our vision for what the product is and saying, what do we want Terraform to look like in a year, in three years, in five years? That's the long-range guiding vision of it.

And then there's the community's input, which is the second pillar. Which is, okay, great, we're setting maybe the one-year, three-year, five-year vision, but that doesn't mean there's not detours along the way.

**Paul:** But the input that you're talking about is actually having conversations with them as opposed to people who show up with PRs.

**Armon:** Right, exactly. Because oftentimes you'll get into these, someone will file an issue. Sometimes you get the really simple issues like, oh, there's a bug. But sometimes, "Hey, I can't solve this problem," and that turns into a 200 comment long issue where you're not talking about a bug, you're really talking about, in some sense this is proxy conversation for, "What is the future of this product?"

"How does it go, is this a use case that's in scope or out of scope?" And those will be the ones where we'll say hey, let's turn this into a Google Doc, let's actually do a video call, and then bring the community in to talk about, hey, maybe asynchronous tickets is the wrong way to have this conversation.

**Paul:** And you do that in the open as well?

**Armon:** Yeah. Because a lot of times those are people coming from the community just filing a ticket saying, "Hey, I have this use case, I can't figure out how to solve it with this tool." And that sort of plants the seed of, okay, how do we take this?

**Paul:** Do you have a open product process, per se? In the same way that somebody can make a pull request. Can they make a pull request to your product process or to your roadmap?

**Armon:** Interesting. No, not really. And I'd say in general we tend to keep a loose idea of where we want to go past one release cycle. So it's really only the next release cycle that we have a very concrete idea of, here's what's going into it, and let's sort of lock it in and execute. Once we're in the cycle, it's pretty much a change mid-cycle.

**Paul:** I find this a really interesting aspect of open source development because a lot of the open source development you get is just code. The product is sort of off to its side and maybe exists in the head of the person who runs the project, or the maintainer.

Either projects don't do any product management and don't have any sense of the roadmap, and whatever PRs sort of appear. Or there's no real involvement of the community, they can just show up with code and that's it. Then they often get told when they show up with the code, it's like, oh yeah, that's actually not needed.

**Armon:** Right, yeah.

**Paul:** It's a tough balance.

**Armon:** It's hard, yeah. I think we try and hit a middle ground which is, by having that one-year, three-year, five-year vision of where we want to go, the community just stopped showing up with PRs, the project would still march forward.

There was a certain vision and agenda and roadmap that we're marching towards. Then the PRs will continue to show up, that's the reality of it. So when they show up, it's like, do these fit into the roadmap? Do these deviate from where we want to take this scope? If not, if we can accommodate it along the way. Let's have the conversation with the community about what that looks like.

**Edith:** What's the split between community versus company in terms of PRs and code, then?

- Yeah, that's a good question. I mean in some sense I think it changed as the products have matured, right? So I think when the products were much younger, it was clear to us that--

**Edith:** As we all were.

**Armon:** Yeah. The balance was much more towards company vision, which was, in the early days we'd go talk to someone about Terraform and they were like, "What are you even talking about? What is infrastructure as code?"

It was this different thing where we knew the community wasn't, a very, very small percent of the community was thoughtfully engaging and really understood what the vision of the tool was. It was hard for them to really contribute in a meaningful way.

We had to push the project forward, but now as it's matured, it sort of flipped a little bit. Which was like, okay, we're getting pretty close to achieving our vision for a lot of these products. But now the community's coming with all sorts of use cases that we never even thought about. Maybe it went from 70/30 where we were leading it, to now the other way around, where it's 70/30 the community's leading it.

**Paul:** Do you find that people are building larger things or smaller things? Are they fixing bugs or small use cases? Or are they like taking leadership?

**Armon:** One of the decisions we made architecturally with all the products was, have this notion of the core of the system versus a plugin surface around it.


<blockquote>A lot of these problems we solve, our philosophy behind it is solve a workflow, not solve a technology. </blockquote>


If we think about, maybe I'll switch from Terraform, I'll use Vault as an example. Vault's workflow problem it's trying to tackle is I have all sorts of sensitive information, whether it's database password, an AWS key, so on and so forth, and I have many different clients whether it's a Docker container, whether it's a VM.

You can almost think about Vault as sort of this hourglass shape, where Vault sits in the middle, and there's an infinite number of things on the north mound, right? Whether it's different database systems, different clouds, different things that you might want to secure the end points.

On the bottom of the hourglass you have the infinite number of clients, and platforms, and applications, and languages. And so very, very early we said okay, well great, the common workflow elements, let's make that in Vault core.

But then the edge of the system, whether it's sort of an endpoint plugin, you say, great, I want to support Cassandra. You can come to us and have a Cassandra plugin where you say, "Great, I want to add a Docker authentication module." Great, you can add that really easily and you don't have to come in and grok a 50,000 line core implementation of the system.

You can be like, "Oh great, the plugin is 200 lines. I can contribute that over a weekend," type of a thing. Almost all of our products have this modular core versus plugin. And I think most of our contributions tend to be on the plugins. Just because the core is, it's not a casual endeavor to like context load, oh, how does Vault core work?

**Edith:** That's clever, it's like Linux was kind of one of the first big open source projects, but now you just kind of assume that Linux works. You don't show up and think I'm going to rebuild that operating system.

**Armon:** Right, exactly. And I think Linux is a perfect example of that same sort of divide, which is, Linux had drivers.

**Edith:** Yeah, well, that's what I was going, yeah.

**Armon:** It's very rare that you're like, I'm going to change the CPU scheduler for Linux. Like, oh, it's a very small audience. But the people writing drivers, that was very common, right?

**Edith:** Yeah, well, that's very clever for you.

**Paul:** It's interesting, the advantage of that, being able to build plugins or something like that, isn't really inherent in open source. It's not a thing that closed source can't do. Closed source companies can build plugin-able things, and often they do via APIs. But then that comes without the ability to share in the way that you do get with open source.

**Armon:** Right, exactly. I think the other effect that you lose with, if it's not open source, is for example, many of our plugins might start in the community. Community member has a problem, they scratch their own itch, they build a plugin.

When enough of the community rallies around and is like, "Hey, I have this shared problem," that eventually gets upstreamed, and it becomes part of the mainline distribution. Then it gets maintained, as opposed to always being the edge plugin where very rarely I think commercial software does a plugin mainline into the actual release.

**Paul:** Probably IP issues.

**Armon:** Right, exactly. Whereas with open source it's just much more sort of free flow, it's sort of like, hey, yeah is this a use case for one person or is this a use case for a thousand people maybe have this problem? And so it naturally filters in from the community.

**Edith:** I want to touch back on something you were talking about, how at the beginning of Terraform it was really hard to get mind share. Beause if you're giving people this false perception where you're like, I open sourced, and suddenly I got all this viral traction. And I've heard you talk other times about how basically, how hard it was.

**Armon:** What's the old proverb? It's like it was an overnight success, it only took ten years. That's kind of how most of our open source tools feel like. By the time a lot of people come to our open source tool, it's because it's reached them through word of mouth or community, or they saw it at a conference. It's after the tool is already successful, so it just seems like the tool must've always been successful. Versus from our vantage point.


<blockquote>So many of our products, we had to make that call, do we continue to make this investment? </blockquote>


And I think Glenn can, there's board meetings where it's like, yeah, we've been putting in years into this thing, should we pull the plug? When is the right time to pull the plug? Terraform's another one of those examples where today, people don't think about it as having struggled. But actually for the first two years it had very little adoption.

Honestly, for the first year it was like, it was a small miracle if it didn't crash within ten seconds of running. And so as you can imagine, it's not a great getting-started experience, right? You're at a 90% crash rate.

It just takes a while for the tools to incubate, hit the right level of maturity. For you to really figure out, how do I explain this to someone in a way that resonates with them, that they're not just like, what, what is this? It seems esoteric.

Getting the product maturity there, getting the messaging there, and then building enough of sort of the community, the early adopter community, that it doesn't seem like this ultra-high risk toy project. It's actually hard. It takes at least, probably two years for most of our tools.

**Paul:** What are your tools written in?

**Armon:** Almost all Go.

**Edith:** Good answer.

**Armon:** Yeah, the oldest is Vagrant and that's Ruby. But everything since has been Go.

**Edith:** I'd love to hear two separate questions. What were these marketing techniques you used for open source? Because I think there's this myth of you just put it on Github and magic happens. And then second, how did you get your board to be patient with these marketing tactics? And how are you showing progress?

**Armon:** Those are both good questions. The marketing tactics, I think a lot of it we learned from before HashiCorp was a company. Actually, I credit this to Mitchell. Mitchell figured this out, is when he released Vagrant, he was scratching his own itch. He was like, "Every three weeks I'm re-imaging my laptop, I'm tired of this. There's got to be a way out."

And so he really built Vagrant for himself, and it started out friends, colleagues, other classmates, things like that. The first year, I think Vagrant had like 100 downloads the whole year.

**Edith:** Total?

**Armon:** Total, 100 downloads.

**Edith:** Not per day.

**Armon:** Yeah, exactly.

**Edith:** So 100, so like basically eight a month.

**Armon:** Right, exactly, yeah. It'd be like, yeah, you talk to a colleague and you'd get one more download. It was like you were counting them one at a time. Then it started being like you'd go into the local meetup groups and talking, because it was written in Ruby, talking at Seattle.rb, which was the Seattle Ruby meetup group. And then you'd start getting ten downloads a month, right? That's like huge increase.

**Edith:** It's like 20% more.

**Armon:** Exactly, 25% growth. The rule of small numbers was kind of fun at the beginning. Then you hit these different communities. And so what really tipped it for Vagrant was the config management community.

They really figured out that they had a feedback loop problem, which was like, "Yeah, every time I change my Chef script, I have to boot a new Amazon thing, upload all of it, run it, SSH then test it, it takes half an hour, and then tear it down. Versus Vagrant, took me from a 30-minute feedback loop to a three-minute feedback loop."


<blockquote>Once the config management community saw the value in this, it sort of blew up because it plugged into that marketing channel. </blockquote>


Where Chef and Puppet and folks in the community would sort of evangelize it themselves and be like, "Yeah, the right way to test it is to use Vagrant." Then Vagrant, at this time when I say "blow up," we're talking it got from 100 downloads to 10,000 downloads.

**Edith:** What, that's real.

**Armon:** That's big. But now we look at it and Vagrant does two million downloads a year. So it all becomes relative, right? It's one of these things where it's like as Glenn says, it takes a long time to get to that hockey stick.

There's these plateau shifts where it was like the plateau shift of config management. Then eventually some of the early, the LAMP stack, and some of the Rails community started picking it up and you see these plateau shift after plateau shifts, and then it starts taking on a life of its own.

**Edith:** I think really the hockey stick is horizontal rather than vertically placed.

A- Exactly, it's a very long ramp. And then hopefully one day it arcs. When we look at things like Terraform, it was the same thing. First year of Terraform was maybe a thousand downloads, right? People would download it, be like, "I tried running it, it crashed instantly." So guess what? They stopped using it.

**Edith:** So a lot of meetups. What were the other things you did to try to drive awareness?

**Armon:** Early days was lots of local meetups. And then that eventually started going to the conference circuit. The [Velocitys](https://conferences.oreilly.com/velocity), and the [QCons,](https://qconferences.com/) and the [DevOpsDays](https://www.devopsdays.org/), and sort of the bigger, you know, go from a ten, 20 person meetup to a hundred person conference. The hundred person conferences eventually end up at the sort of thousand person, Velocity-style conferences. And those were kind of the big drivers, honestly.

The other side of it was very consciously trying to start building a HashiCorp audience. So building a mailing list following, building a Twitter following very, very early. We convinced the board to let us spend a ton of money on a conference. Originally we were like, you know, maybe we'll get a hundred people to show up.

Will a hundred people care enough to fly to Portland and talk about our DevOps tools? We were blown away, it was way more. We ended up getting, I think 250, 300 people the first year, and it's just super exciting. You get this different energy because you have everyone in the room and


<blockquote>it goes from this virtual community of avatars and Slack handles to all of a sudden it's real. You're talking face-to-face to the person who filed that ticket.</blockquote>


I think those were really, really powerful for us, having those sort of events. Because I think it made it much more real for us, but it also made it much more real for the community.

**Edith:** Yeah.

**Armon:** It just accelerates the effect, that adoption around the tools.

**Edith:** Yeah, it's funny, Jason Lemkin has this saying, I don't know if it's his saying, but he says it all the time, "Get on a plane."

**Armon:** Yes, yeah, totally. Actually, that was the other thing. Early days, anytime we'd get an interesting email about, "Hey, will Consul work with 500 nodes?" We'd respond to the mailing list but then I'd send a private response to the person being like, hey, just curious, where do you work? I'm based in San Francisco, we'd love to come and talk to you.

So many of those turned into these conversations where you go in and it's like, oh yeah, it's Twitch. The reason we ended up talking to Twitch super early was they sent an email about some random issue they were having at scale. I'm like, really, how much scale are we talking about that you're running into this issue?

I was like, "I'm just in San Francisco," and they're like, "Yeah, we're down the street." Ended up meeting with them and they're like, "Okay, so here's the story. Can it do 12 data centers, 5,000 nodes?" This was like 10 times bigger than any use case we knew about before that. And we're like, "Maybe. But we're happy to stay at your officeswhen you push the 'go live' button and help you debug it if anything goes wrong." And that's what we did.


<blockquote>We're just like, yeah, we want to make sure they're successful. It's word of mouth, right? Then the Twitch folks talked about it, and that made a huge difference for Consul. </blockquote>


**Edith:** How did you convince your board to stay on this journey with you? Glenn, what was your take of it?

**Glenn:** Just listening to Armon reminded of two things I'd like to point out. One is, it was apparent even in the early days, post series A that there was a significant amount of overhead associated with this model.

Going back to, is open source a good thing or a bad thing? It's a thing. I think if done right, you have to budget in, there's a significant amount of overhead. Mitchell and Armon have spent collectively no short of thousands and thousands of hours in kind of guerrilla tactic, go get on a plane, go meet the user, and go talk at this conference and that conference and spend a lot of time responding to community conversation and really trying to be very accessible.

I think others who are listening who are thinking about, hey, is open source right for me,


<blockquote>you really need to think through that and be ready for that part of the journey. It's a significant investment, and it really doesn't abate. </blockquote>


I still think you guys spend a tremendous amount of your time on those open source related community activities, that's one.

The second thing I'd say is, we talked about the hockey stick. One thing I think that HashiCorp benefits from today that I think the company will continue to benefit from is as you show the community that you're committed to building great open source products and to supporting a community with a well articulated view of how you're to manage and focus on open source in addition to commercial business, I think you get benefit from that.

If you look at the hockey sticks of the more recent projects, they start slow. But I think that they tend to tip up quicker. Because I think the community at some point starts to, you become innocent until proven guilty as opposed to guilty until proven innocent, as a company. So I now think that the community is, has NPS with HashiCorp products, and so they're much more likely to look at the next product or project and say yeah, I want to give that a try.

**Armon:** I think that's definitely true.


<blockquote>The later products were much, much easier to bring to the market. Just because it's like people trusted us, knew about us, used it already, so it's just an easier conversation to have. </blockquote>


**Glenn:** But it is hard as a board, because there was no class in business school, at least that I took, that talked about, hey, here's how you assess progress in a company that's doing no revenue and is building open source products that don't ever really aspire to generate revenue. How do you gauge progress in that kind of world? And so I think it's not easy, it's not easy.

**Paul:** How did you do it, what were the metrics?

**Glenn:** Well, the things was, we'd already invested, so--

**Edith:** Stick stickers on laptops.

**Glenn:** I actually attended, and Edith knows that, and I've learned this from Mitchell and Armon that I'm a big proponent of doing events early. Trying to inspire and energize a community around your company, whether you're open source or closed source, early.

There's so much benefit that accrues when you do that. I've attended all, and may be the only person other than Mitchell and Armon and some of the very earliest employees that have actually been to all three global HashiCons so far, and that was part of it. It's just really actually myself going out and trying to talk to the community and assess, okay, is this really starting to take flight?

**Edith:** I think that that's so hard because at the beginning it's just slow. And I think there's the other side where if you're closed source you think, I get advice sometimes of like, "Why don't you open source your products and just watch it explode?" And I'm like, I don't think it's that easy.

**Armon:** Right. It is definitely not the "push some open source code to Github and voila." The community up here. Yeah, I think that's the myth of "build it and they will come." It's "build it and you're just coughed into the wind," basically.

**Edith:** I think it's interesting that you talked about how open source, you still need marketing, which you just talked about, you still need product which you talked about, and you still need sales.

**Armon:** Right. Even now as a commercial company, it's like, you don't get to escape that by virtue of being an open source company. You still need all of the group to be functional.

**Edith:** Glenn, I heard that you were starting your own Podcast.

**Glenn:** Oh, Edith, thank you for the plug. First of all, this has been really fun to talk about continuous development, and also open source and hear from Armon who has had such a great run and is building so much excitement at HashiCorp.

But my colleague, Crystal Huang, and I from GGV are going to start a podcast and we're working on episodes now, focused on talking to founders. And so each of you, Edith, Paul, Armon, you're not off the hook, I expect each of you to be guests on our podcast soon.

We're going to ask founders about challenges they've had. We're going to call it Founder Real Talk, and what we're really after is not the glossed over, shining success story that all of you have had and are continuing to have, but some of the tougher challenges you faced along the way. And then how you overcame those challenges, and that's what we really want to dig into. We think that would be really valuable for other founders to hear, so that's what we're going to do.

**Edith:** That sounds great, going to be honored to be part of it.

**Paul:** Yeah, sounds great.

**Glenn:** Great, thanks.

**Edith:** I want to geek out for a second with Armon about something you said at the beginning, which was about autonomous code, making stuff be able to be pushed as quickly as possible. What do you think is holding us back from that?

**Armon:** There's this interesting effect, and I only learned about the name of it a few, maybe six months ago, called the paradox of automation.

**Edith:** Oh, yeah.

**Armon:** It's this interesting idea which is you would think that the more we automate, the more we remove humans from the loop, the more resilient systems become. There's less human error to be made and everything's automated. So how can things go wrong?

But I think what the paradox teases that out is, well, what automation's really doing is giving us a longer and longer lever. Before it was like, okay, maybe I do this manual thing and click 500 times. Now I click one time and I hit all 500 of my machines.


<blockquote>What automation doesn't discern is whether or not the change we're making is good or bad. So before, I could manually screw up one machine at a time, now I can automatically screw up all 500 machines. </blockquote>


I think this paradox sits at the crux of it, which is, yes, the more we automate end-to-end, the more continuous delivery we have, we get this huge leverage. But how do we do it safely?

I think this is a big, big question we run into with our enterprise customers, too. Which is like, great, we'd love to give this power of infrastructure as code, and continuous delivery, and CI/CD to our end developers. But we can't let 15,000 developers jeopardize the bank, right?

You're like, yeah, that's a fair point, that's too much risk. That's an area where I think there's still more work to do, which is like how do we not throw out the baby with the bath water. Because I think that's the natural tendency of the enterprises is, great, we'll solve this problem by throwing a ticketing queue in there.

Instead of letting you pull the lever, you file a ticket against someone who verifies that you're pulling it in the right way, and then we'll pull it for you. You throw out all the agility and all the benefits that continuous delivery gave you, because now you have a ticketing queue and manual review for an infinite number of tickets. That I think is one of the big challenges, and something we started looking at last year.


<blockquote>Where our heads went to was, how do we get rid of the ticketing queue? How do we automate, but with guardrails, is the way we like to phrase it. </blockquote>


Where we went to, naturally, being developers is, well, what we need is meta-automation. Our view was, infrastructure as code was level one. It let us say, here's the definition of what I want my infrastructure to look like.

Level two becomes policy as code, right? Is it's this higher-level language that is reflecting on the infrastructure as code and saying, is this allowed or not? So now, instead of me making a change and filing a ticket, and then someone's reviewing it manually, I make my change, I try and hit apply, and the automated system's like, "Sorry, can't do that."

You just asked for 5,000 VMs, the maximum you're allowed to ask for is, whatever, 50, right? Or you're deploying to the wrong AWS region, you're not allowed to do it. And so still having that sort of huge leverage, so that if I did mess it up I am within the sandbox. Then I can automate and I can get the end-to-end benefits. But the moment I try and leave my sandbox, it's shut down in an automated way.

So that's some of our thinking. I don't know if that's necessarily the 100% answer. I think our view's now might be at least the 80% answer, we can get a lot of the benefits of it. But yeah, I think that's a tough one.

**Edith:** I think it's really cool. For one, I love HashiCorp, and I kind of assume, because unless you're deploying multiple times, unless you're managing a lot of machines, I don't think you need a company like LaunchDarkly.

**Armon:** Right.

**Edith:** What I think is that more if everything pushes and it is right at a certain level, then it should start feeding out to different users.

**Armon:** Right.

**Edith:** And depending on their reaction, keep moving out.

**Armon:** Totally, yeah. I think that's the blue/greening, and the feature flagging stuff you guys enable is a key part of it. Because I think if you don't have those kind of capabilities, then you live in this really high-risk world.

Which is like, if I make one mistake, game over. I'm killing production traffic. But if I actually have feature flagging and smart traffic routing and I can do blue/greens or canaries, then I live in a world that's much lower risk. It's not that I won't make a mistake. Everyone's going to make a mistake.

**Edith:** Everybody always makes mistakes.

**Armon:** Yeah, but now my mistake only hits 0.1% of my users, and not 100% of my users.

**Paul:** Well, there's an interesting distinction between the blue/green that you're talking about and the automated out to 500 machines, versus the feature flagging, which I think is the magnitude at which that risk happens.

It's like if you have one build that goes out to 500 machines, or even if it goes out to ten machines first, then 100 machines, and so on, it's that full build. And all the risk from that full build that's being experienced by users. Versus the feature flagging and that which I think is, personally, a much, much better approach.

**Armon:** Right, yeah.

**Paul:** Not better, but I think if you were to remove one from it, I'd pick feature flags.

**Edith:** Thank you, Paul.

**Paul:** Well, that's why I wore my LaunchDarkly t-shirt today.

**Edith:** Yeah, thank you.

**Glenn:** I only wish there was feature flagging for venture deals. Because if we could roll back after the first board meeting or at the end of the year, of a few of our deals, that would be something we'd like to do.

P- Sixty day money back guarantee.

**Glenn:** Can you work on that, Edith?

**Edith:** You don't have to name names, but what happened where you wanted to roll back?

**Glenn:** I just stepped into one, didn't I? I have several of those stories.

**Armon:** You don't have to name us by name. I can step out of the room.

**Paul:** There's the open source guys, and they didn't want to build. They just wanted to keep building products, no users.

**Glenn:** We love HashiCorp and we're super excited that we're involved.

**Edith:** And then they built one big project.

**Paul:** We had to build two more rounds before they even went to market.

**Glenn:** Kidding aside, the way I think of continuous delivery, it's in some ways, yes it's Xs and Os, but it's also a philosophy.


<blockquote>It extends beyond code to business model as well, and I think we benefit today from the fact that companies are more agile. </blockquote>


Just the way software's built allows them to be more agile, and so if things aren't going well, you can back track and roll back to a time when maybe the business model wasn't settled, or if you made a decision that you didn't like, or a feature that you shouldn't have released, you can roll back the business feature as well as the software feature.

But I've been doing this long enough that that wasn't always the case. And I'll tell you, it was much harder business when you were building software and you built, built, built, and QA'ed it, and then you rolled it out. Maybe six months later or a year later, and then you kind of finally got customer feedback.

That was a much tougher time. You had to make bigger bets, there was a lot more risk. Let's just say that I've had my fare share of companies as a result that I wish I'd had feature flagging for at that time.

**Edith:** It was so hard also, because you really, I do think there's a place for sales, but in that model you very much relied on sales, meaning telling customers you need to buy this.

**Glenn:** In today's world, and open source is definitely one way to do this,


<blockquote>you can educate your champion long before they become a customer.They're qualifying themselves as you're qualifying them at the same time. </blockquote>


Back then in the old world of software, you couldn't do that at all. There's lots of good stories of companies that ran right into brick walls after spending all kinds of money. Look at like Webvan, which wasn't a B2B company, it was a B2C company. But it was an idea before its time, and so there's a saying in venture capital that being too early is the same thing as being wrong.

They were too early and they built what might've been a solution that could've worked today, in fact it obviously does work today, to look at Instacart and look at what Amazon's doing with Whole Foods. But back then it was, they spent an awful lot of money, only to find out that it was the wrong time and probably not exactly the right route to market and a couple hundred million dollars flushed down the toilet.

**Edith:** Doesn't seem like the note I want to end the podcast on.

**Glenn:** Sorry.

**Edith:** Any final thoughts?

**Glenn:** You know, HashiCorp, yes there was a period of a year or so where the company was kind of searching for that model while they were building a very engaged community. But it didn't cost a lot. And that's the benefit of agility.


<blockquote>You can make decisions, you can quickly roll back if you haven't made the right one, you can test until you get it right, you don't have to spend a lot of money. That's good for our business. I think it's good for the technology business in general. </blockquote>


So I'm truly optimistic that the next couple years will lead to some great businesses, and I think each of your guys' businesses has great potential as a result.

**Edith:** Armon, final thoughts?

**Armon:** One thing I guess I don't want to leave people with the impression with is that there is a super predictable formula for open source. We've gone through, we did eight open source projects, and there's just so much variation even within those. Like same style, same approach, same team that's doing it. We're holding a lot of things constant about it, but the results just vary so wildly between them in terms of, is it the right time. Some of our tools, like Serf, were wrong timing.

To Glenn's point, too early is the same as being wrong. You know, how do you tease apart the flat line adoption curve of Serf that stayed a flat line from the flat line adoption curve of some of our other products that didn't stay a flat line? In the early days they look the same, they look like a flat line.


<blockquote>There isn't necessarily a perfect formula, we haven't necessarily got it to a science yet. So there's still an art to it, there's still something, some wizardry there. I don't know. Some luck, certainly a lot of luck. </blockquote>


**Edith:** Yeah, the beginning is so hard, what you said stuck with me about, what was it, 100 downloads in the first year?

**Armon:** Yeah, is that a successful product or a failure, right? Because it's really easy now, 10 years later, to say Vagrant was a success.

**Edith:** Yeah, I mean, that's so hard. I've been an engineer on a product, it's so hard at the beginning where you want to believe that you're getting some of signs, 100 is more than zero, but 100 is still pretty--

**Armon:** It rounds to zero.

**Glenn:** If you stay linear, it's going to be a long road.

**Edith:** Yes. Well, thank you so much for coming by. We really appreciate you joining us.

**Armon:** Yeah, thanks for having us.

**Glenn:** Thanks Edith, thanks Paul.














