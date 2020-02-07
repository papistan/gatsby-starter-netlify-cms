---
author: Kimh
comments: false
date: 2018-09-19 21:54:16+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-resolving-accidental-complexity-with-dark/
slug: to-be-continuous-resolving-accidental-complexity-with-dark
title: 'To Be Continuous: Resolving Accidental Complexity with Dark'
wordpress_id: 193633
categories:
- To Be Continuous
tags:
- AngelList
- continuous delivery
- Software Complexity
---

In episode 48 of To Be Continuous, Edith asks Paul what it took to found his fourth startup, Dark.

This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.

https://soundcloud.com/heavybit/to-be-continuous-ep-48-resolving-accidental-complexity-with-dark?in=heavybit/sets/to-be-continuous













TRANSCRIPT







**Edith Harbaugh: **Hey, Paul.

**Paul Biggar: **Hello.

**Edith: **I heard you started Dark.

**Paul: **Yes, I started a new company, Dark. [Darklang.com](https://darklang.com/).

**Edith: **Tell me about it.

**Paul: **Dark is our attempt to take all of the accidental complexity out of building software. We started with the premise that building software is just way too hard, and we looked at all the various different points of that complexity.

The major four that we came up with was: infrastructure complexity, things like Kubernetes and Docker and AWS and that kind of thing; API complexity, deployment complexity; and then code complexity itself. That's everything from syntax errors to using git, to fixing your editor, or all that sort of thing. We speculated that we can remove all of those areas.

**Edith: **All of them?

**Paul: **All of them. All those areas of complexity.

**Edith: **I thought you were about to say, "And then we decided to focus on one."

**Paul: **There's certainly a question about the order of which we validate things and how we cut scope to get to market, but those are the four areas of complexity that we're looking at. The end results, or the initial end result, is a combined holistic editor programming language and platform as a service. Or hosting and infrastructure compiler, perhaps.

**Edith: **I have so many questions. How did you come up with an MVP given such a broad space?

**Paul: **The initial MVP I made about 18 months ago, and it took about two weeks. That was a thing where I had a bunch of ideas and what I needed to prove to myself was, "Is it possible to write software in this metaphor?"

So I built a blog with it. And it wasn't a very advanced blog, it was just like, "Is there a metaphor with which I can store data and do computation on it? In a way that's zero deployment and very fast to edit?"

And it was buggy, but it was fine and it proved that I could do it. It took me two weeks but really it was like 800 lines of Python and 800 lines of Elm. It was not very complicated.

**Edith: **Why did you switch from Clojure?

**Paul: **Why did I switch from Clojure?

**Edith: **And Elm, and Python?

**Paul: **We're still using Elm today. We switched from Python, and the original MVP was in Python, but I found I struggled to grow it. Very much for the same reasons as we switch from Python, which is that I believe in static types. We're building it in OCaml and I think that the result is not going to be that it's all done in OCaml.


<blockquote>When you're a very early stage in a startup and you don't know what you're building, you have to often completely change everything often. </blockquote>


The overhead of writing tests to prove that your code works is very high and having that layer of compiler checked or type system checked thing is incredibly valuable.

**Edith: **You felt it gave you guardrails?

**Paul: **Exactly, yeah. I felt a lot of security and we experienced the thing, and I've been coding for a while now. I know that if I fit within the guardrails, my program is probably going to work the first time in most cases.

**Edith: **The team started off with you and a prototype. How big is the team now?

**Paul: **We're four people now.

**Edith: **Wow.

**Paul: **Yeah, I know. Big changes. And we're interviewing heavily for five, six and seven. We're looking for a designer, front-end engineer and an infrastructure engineer. But yeah, we're four people now.

There's my co-founder Ellen, there's our engineer Ian, who has listened to every single podcast we have ever made. Which is a real struggle because he knows the ends of all my stories.

**Edith: **Does he ever tell you the story end?

**Paul: **Oh yeah, it's like, "Do you remember when you said this on this podcast?" I was like, "Nope. I don't remember that at all."

**Edith: **I started to try to tell a story to somebody at work, and they were like, "We heard this already."

**Paul: **That's every story I tell at work now. It's very irritating. And Stefi, who does operations.

**Edith: **It's funny, I met Ian. And I'm giving him a shout out because he's such a charming, nice guy.

**Paul: **He's lovely.

**Edith: **It's funny, because he's from Ireland too.

**Paul: **We went to the same university about 10 years apart.

**Edith: **Yeah, and it's funny, I also know that he said he felt he was a different generation than you.

**Paul: **That's probably true. The generation that I grew up in was the one in which Ireland had no money, and the Celtic Tiger came along. That's what we called the period of prosperity from between the early '90s and 2008, and you're coming 10 years later. You grew up through a lot of that prosperity instead of just seeing it as an adult.

**Edith: **That's funny because that's exactly the way he described it. I don't know if that's the way you described it to him, or that you both made the connection.

**Paul: **I had never heard him say that.

**Edith: **Yeah. He used the phrase "Celtic Tiger," that he was the generation that grew up with more prosperity. How do you feel like that's shaped your outlook in starting a company? To have grown up--?

**Paul: **That's very interesting. One of the things that matters to me, and I'm very much a millennial in this sense, is that I don't care much about money. I mean, I care about not having none.


<blockquote>Millennials are a generation that are defined by the need of experience overstatus or people who spend their money on experiences versus status. </blockquote>


**Edith: **I would say Ian is more millennial generation than you.

**Paul: **Yeah. I'm definitely within the cultural definition. I'm also within the technical definition, it's apparently kids who started in 1980 to 1995 or something along those lines.

**Edith: **Who were born then?

**Paul: **Who were born in those years. But certainly culturally, I'm a millennial. And I believe in it. This is why I'm doing another startup. I want to build a thing that I need to exist in the world.

**Edith: **Yeah. You just felt this need to create again.

**Paul: **After I left CircleCI I spent about 18 months doing nothing.

**Edith: **Well, you podcasted with me occasionally.

**Paul: **We podcasted. That was the only technical thing. Occasionally talking to the founders and trying to help them, but mostly I went to Costa Rica, I did a road trip, I moved to New York. I did the Recurse center, which is really great. And I thought about, "What am I doing next?"

Every idea that I had, everything that I wanted to build, I was lamenting the fact that would have to go and use all these subpar tools. And that I would have to go and learn Kubernetes or learn AWS. I felt I couldn't build a small company because the amount of infrastructure and overhead you need to have your code work is too high for one person.

**Edith: **There's echoes here of that post you wrote called, [This Is The Future](https://circleci.com/blog/its-the-future/).

**Paul: **Oh, yes. Very much so. I included that in all material that was discussing Dark in the early days. But there's way too much stuff, and there's way too much stuff you need to know, and infrastructure which was the subject of, "the future is crazy."

But the front end is crazy as well and there's just an explosion of tooling, and everything makes incremental improvements. All of that incremental improvement overall increases complexity rather than decreasing it.

[tweet_box design="default" float="none"]**Edith: **Remember when you could you just hack together an HTML page on a backend?[/tweet_box]

**Paul: **And that was it. People's expectations are much higher. There's a lot more people on the internet now. The speed at which you need to move is incredibly high, and that combined with the expectations of needing to work in a team to be able to do that. Those are a couple of the major factors of the complexity.

**Edith: **This is so fascinating. There's so many different directions. What's it like to work with somebody 10 years younger?

**Paul: **I don't know, I feel like I've been working with people much younger than me and also older than me, and also the same age as me. At Circle certainly a lot of us at the start were in the early family age I would say, late 20s early 30s.


<blockquote>We hired some incredibly smart 20-year-olds, some very experienced people in their 40s and 50s. There isn't a fundamental difference between people of those various ages. </blockquote>


We did once interview a 16 year old, and I think that was too far. But once you have valued team members, and you listen to what they have to say, you don't necessarily need to do what they say. But good ideas come from anywhere. And often I could not predict where the good points were going to come from.

**Edith: **Yeah. This is your second time founding a startup.

**Paul: **This is my fourth time.

**Edith: **Oh my gosh, I forget. Because we talked about these other ones. So this is you fourth time.

**Paul: **Fourth time, yeah.

**Edith: **How are you trying to be more intentional about culture and hiring?

**Paul: **One of the big things is that we're pushing a lot on being an inclusive company. That's very different from what we did before. I was on, Charity Majors and Rachel Chalmers, [they have a podcast](https://www.heavybit.com/library/podcasts/o11ycast/ep-3-distributed-systems-with-paul-biggar-of-dark/) on the Heavybit Network. I don't know if it's out or coming out.

**Edith: **You did that already?

**Paul: **I did an episode on that.

**Edith: **You're not recording with me, and you're recording with them?

**Paul: **I'm so sorry, Edith, I feel like I did some sort of infidelity going on here.

**Edith: **Well, you've been saying you're too busy to tape. In full disclosure, [I was on Glenn's podcast](https://founderrealtalk.ggvc.com/2018/08/10/episode-9-edith-harbaugh-ceo-co-founder-of-launchdarkly-on-building-an-enterprise-software-company/).

**Paul: **Oh nice. So, I talked on their podcast a lot about this. That was not a thing I saw the value of in 2011 and have since learned how wrong I was, I think it's important to really look at that in hiring. Which is something that we're doing at the moment, or have been doing since the company started.

One of the other major things is just that we wrote down a set of values from the very start when me and Ellen started working together. We worked out what our roles were, we worked out what our values were. And it's not that they were set in stone. We redid our values when we had employees.

But what was different about it is that we wanted to make sure that we were on the same page and that we were building the same company. Eisenhower or someone said, "Plans are worthless but planning is everything." With Circle we just got down to it.

We knew we had something to build and we never discussed or thought about values or process or any of that sort of thing. I'm finding that things are going a lot more, I wouldn't necessarily say smoothly, but everything feels smoother as a result of just having a plan and knowing what we're doing, even if we change that relatively frequently.

**Edith: **Something that was really interesting was you told me that you're already going to founders’ therapy.

**Paul: **Oh yeah, I'll be right on the air about that. I think everyone should go to therapy, but I think all co-founders should go to therapy. Therapy is the best. We started working with a company called Innerspace.

**Edith: **Oh, Joe Greenstein's.

**Paul: **We work with Semira. But Innerspace is great and they do things like T-groups. We haven't done the T-groups together.

**Edith: **I did my first T-group.

**Paul: **How was it?

**Edith: **You finish your story, and then I'll tell.

**Paul: **OK. I felt that from the very start, when I was talking to cofounders I was like, "I think co-founder therapy is really important, and that we haven't worked together and we're going to need to do this." And Ellen was on board. So we did it from the second we raised money. First thing we did was we went to therapy. And it's one of those things that you have to do from when you're not having problems, to make the marriage analogy.


<blockquote>If you go to therapy when you're having problems you're unlikely to save it, but if you start going when everything's good and you learn to communicate and you learn to raise issues through nonviolent language and that kind ofthing, then you can be much better partners than if you don't. </blockquote>


**Edith: **What's your cadence for the therapy?

**Paul: **It's about every two weeks.

**Edith: **And you feel like it's helped?

**Paul: **I love it. It's the same with regular therapy but I always feel great coming out of it and the problems have gotten taken care of. And it's almost like the feeling you get when you have tickets in your Trello and you move it into the done column.

**Edith: **Do you feel yourself looking forward to it, or is it more like at the dentist?

**Paul: **I feel myself looking forward to it a lot.

**Edith: **And I say that because my dentist is always super excited to see me. And I'm like, "Dude. I am not super excited to see you at all."

**Paul: **I love my dentist.

**Edith: **You love your dentist?

**Paul: **Yeah. I have a new dentist who turns it around in 20 minutes. I walk in the building, and I walk out of the building 20 minutes later.

**Edith: **And your therapy is like that too?

**Paul: **No, therapy takes a full hour. Therapy and co-founder therapy especially is very expensive. So you definitely want to be getting your money's worth.

**Edith: **Expensive? What's the ballpark?

**Paul: **I don't want to say exactly, but general management or executive coaching, it's the same price. That tends to be in the $500 narrow range. Do you have a coach?

**Edith: **I do not have a coach. I did do my first T-group. I got accepted to this program called Leaders in Tech, which is really interesting.

**Paul: **OK. What's that?

**Edith: **It's 24 people. It's a yearlong program where its peer group/coaching to be better people, better executives. So you have to have done at least a Series B or have a certain valuation. And they said a lot of people applied and they filtered the people they thought would get the most out of it.

**Paul: **Nice.

**Edith: **It's interesting. I've never done a tea group before.

**Paul: **I hear it bears all the emotions for everyone.

**Edith: **The thing is, I didn't know what a tea group was.

**Paul: **I don't either.

**Edith: **I just went to this thing expecting it was your typical CEO thing.

**Paul: **There's going to be talk, there's going to be some canapés.

**Edith: **Yeah. But instead, the tissues were there.

**Paul: **Oh my god.

**Edith: **Yeah. It was me, the hard-charging CEO, meets the group.

**Paul: **But you had fun?

**Edith: **The joke about me was they were like, "You came in charging ready to moderate the therapy group and therapy everybody to death. Once you calmed down, it was great."

**Paul: **Nice.

**Edith: **And I was like, "OK. You're done talking about your feelings. Who's going to talk about their feelings next?" Because I moderate a lot of dinners, and I was like, "OK. I don't need to moderate this."

**Paul: **We can talk.

**Edith: **We could. We could talk without me moderating. It was fun. So, it sounds like you're being more intentional.

**Paul: **A lot more intentional about how to work together with my co-founder, how the company is set up. We were also much more intentional about how we raised money. In Circle, we raised $50K, a year later we raised a $1.5 million, a year later we raised $6 million.

Each of those were very much on the angel and then the seed round, and then the Series A based on certain traction, and whatever. We sat down at the start with Dark and we made a plan. "What can we do? What is the right way to do this?" We came up with the raise $500K plan, the raise $2 million plan, the raise $3.5 million plan, the raise $5 million plan, the raise $10 million plan.

And then we looked at, "What can we achieve on the basis of where we are, what do we need to get to the next stage?" And we narrowed it down to two plans, the $500K plan and the $3.5 million plan. More than that was too much money and would have been too dilutive.

The $2 million plan which initially seemed the most natural, we worried when we drew out a timeline of where we would be or the team we could hire, where we would be. We worried that it left us in no man's land. It would give us 18 months. And obviously, if you have 18 months, you need to start fundraising six months beforehand.

So that means we have a year and that means we'd have to double down on the best idea within a year, and then try to raise off that. With the benefit of hindsight that would have been possible, but it looked like the riskiest plan.

So we looked at the $3.5 million and then we looked at the $500K. The risk with the three and a half million is that it's a lot of money, and to have a good dilution the implied valuation is quite high relative to how people were doing seeds.

People were looking at $12 million-post money in most things, and that's very diluted of to raise $3.5 million in that situation. So we thought it was the best plan and we tested the market out, and the market was receptive.

Not all of the market was receptive, we definitely talked to a lot of people who were not as receptive. We tried a couple of different plans before we hit our stride. In two months we talk to 160 investors.


<blockquote>That's the major difference between the first time and the second time. The first time you don't know what you're doing, you don't know who to talk to. </blockquote>


You don't know. Every lead seems like it's going to win. We could afford to be selective. There's a couple people that we talk to in particular, one thing I saw was VCs who wouldn't look Ellen in the eye.

They would ask a question, Ellen would be the right person to answer the question, she'd answer the question. And then they would ask the follow up question, still looking at me, asking me instead of Ellen. It was very frustrating, and doubly so for her. We had the ability to be a little more selective but at the same time it takes a lot of checks to get to $3.5 million.

**Edith: **In full disclosure, I am a very tiny investor in Dark.

**Paul: **You are our favorite investor in Dark.

**Edith: **I am your favorite that's doing a podcast with you right now.

**Paul: **One thing we did was we made room for small investors. The smallest check we took was $1,000. At CircleCI, the smallest we took was $10K, and that was a stretch. We mostly took $25K. But we made a lot of room for $1-5-10K investments in Dark because one, we had a method of handling the cap table.

Which is the AngelList syndicate, so we funneled all the angel investors through an AngelList syndicate, which made capital management significantly easier. Then we needed that social proof from people like yourself, and John invested.

**Edith: **John Kodumal, my co-founder.

**Paul: **Russ from Rainforest invested, Andrew from PagerDuty invested. Greg from OpenAI invested. There's a lot of people in the space. I feel bad now that I mentioned five when there's in fact 25 names that you would know. So we put them on a slide when we are fundraising. It's like, "These are the angels who are investing." And they're like, "I know like six of them." and it's like, "You should talk to them."

**Edith: **Yeah, it's funny. I'm definitely in the low side of those numbers you just named. But I did get pinged by people. They'd be like, "We saw your name on a slide. Is this true?" And I'd be like, "Yeah. Of course. I believe in Ellen and Paul."

**Paul: **Could you imagine if we put names on the slide that weren't true?

**Edith: **People do that sometimes. So LaunchDarkly, people put our logo on slides sometimes, and sometimes somebody will use ones we don't use anymore.

**Paul: **Yeah, that's a risk.

**Edith: **I'm like, "No, we don't use them anymore. Here's why. You should really take us off your slides."

**Paul: **Yeah. This is not a good idea. But that sort of social proof was absolutely necessary, and we eventually put together $3.5 million over, I guess, a month and a half I would say. Maybe you do a couple of experiments when you're fundraising. Now we're going to go, "Is it going to be Series A investors? Are they going to write these checks?" And we've tried a couple of different venues and then we hit our stride with Angels and funds writing $250K checks.

**Edith: **For those listening at home, do you think this is something that worked for you because you were a fourth time founder, Ellen had come out of some prestigious startups?

**Paul: **Yeah. Absolutely. We couldn't have done it without it. I see people do this, and I don't know how they do it. Certainly we don't like to tell a bigger story than we are. We like a good narrative, but we're not people to hype and to pitch and to pit investors off against each other to invest in the new hot round, or that sort of thing.

You definitely see that sort of thing go on a bit. We also weren't coming out of Y Combinator, which is a thing that often justifies those valuations. But it's not something that we could have put together without a little bit of prestige behind it.

**Edith: **I still mentor when I go to Collision and Web Summit. It was really cool this year, it was a bunch of South American startups.

**Paul: **Oh, lovely.

**Edith: **From Chile, Guatemala, Brazil. Which was so cool. Everything I told them was with this huge grain of salt. "I know the American market, I don't know if this will work in your market."

**Paul: **I tell them all, "Move to San Francisco."

**Edith: **I guess it did happen for you. You're were an Irish person and you moved here and you raised. Cool. So you raised the money, you set up your culture. You started doing something very interesting, which was you had, what would you call it? A developer in a residence? Or a hacker in residence?

**Paul: **We called it an EIR and it's unclear whether we meant engineer in residence or entrepreneur in residence, but it was intended to be a bit of both. Dark is a programming language, and it's an editor, and it's hosting.

We're doing all those things and as a result it's very broad. But you need market validation, and you need market validation as soon as possible. So instead of trying to launch it or something like that, because it is not polished. It is enough to prove out certain concepts and certain ideas that we had.

But we didn't know how to prioritize all the thousands of new polish things that we could put on it. So we had this idea. Why don't we get someone to build their actual startup in Dark, and because we wanted someone to really be doing this. We didn't we didn't want to find 50 people and try to have them stick with it.

What we ended up doing is saying, "We'll pay you." We're paying our EIR $3,000 a month. The CAC is super high, but who knows what the payback period will be. We just posted a post on Hacker News, we posted on Twitter. A couple of people retweeted because it looked really interesting, and in the end we had about 30 applicants.

Some of them were doing things that we weren't ready for. They needed more scale, more real time, more video. That kind of thing. But we finally came across this guy, and I don't want to say his name because I don't have permission.

But he's building a small startup bootstrapped, and has a bunch of customers, is building a new product in that and didn't want to really maintain it. And that's the promise of Dark, that the amount of work that you have to do to write and to maintain a backend application is low.

And he's helping us prioritize and tell us where the bugs are that really bother him, and he comes to our office everyday and he tells us what's wrong. We triage in the morning and we re-triage high level priorities every week. At the moment it's top slow, so we're scaling some things and optimizing some things that we hadn't optimized until this point.

**Edith: **Do you feel that you are in danger then of just becoming a consulting shop, if it's just one person?

**Paul: **I don't think so. At Dark we do retros every Friday. The company sits down together and talks about what isn't going too well, or what's going right as well. But one of the more recent ones is, "We feel like we've been a couple of weeks in the fixing bugs. What are we doing with the long term vision? How are we making sure that we follow the long term vision?"

And as a result we had a sit down, and we laid out what are all the things that are missing from long term vision that we aren't doing at the moment, prioritize them and try to set in motion and make sure that we get to market ASAP. But also, don't end up as a consulting shop for small people. Make sure that we would be the worst consulting shop, because we're paying them.

**Edith: **It sounds like things are going well. I have to ask, why the name Dark?

**Paul: **I wish I had a better story about this.

**Edith: **Does it involve a LaunchDarkly t-shirt?

**Paul: **It does. We talked about this, and I remember I said to you that it's called Dark, and you had this look on your face. And it hadn't occurred to me, "I don't know why you're looking at me like that." I honestly didn't.

I think that the name came from the fact that we were making editors and I always used the Dark theme in editors. But what I was looking to do at the time, I was putting together a proposal to send to a bunch of people and say, "Does this look interesting?"


<blockquote>I wanted something which sounded like if you saw the e-mail with the subject, that you would open it. </blockquote>


And it was called Project Dark. And that sounds like a doc that you want to read. I was spit balling for names until I came up and until I satisfied that criteria. And Dark was one of the first names I came up with.

**Edith: **Cool.

**Paul: **We liked it. And now we're DarkLang.com, and the company is Dark Inc.

**Edith: **Also, you're about a year into it now?

**Paul: **Ellen and I just celebrated our one year anniversary of being co-founders. Or was it of meeting? One of those two. But we started fundraising about a year ago.

**Edith: **It's funny, because it's LaunchDarkly's four year anniversary.

**Paul: **Oh wow. Congratulations.

**Edith: **And when we started doing the podcast, when I started doing the podcast with you we were four people.

**Paul: **You were four people. And you are 30 people now?

**Edith: **Fifty.

**Paul: **Fifty people. Holy shit, Edith. That's huge.

**Edith: **Yeah. We were four people sitting outside.

**Paul: **Yeah. And funnily enough now, that's like when we started my company was like 45. And now my company is four.

**Edith: **So maybe in a couple more years I'll be talking about--

**Paul: **You'll be starting your next one.

**Edith: **No, I like LaunchDarkly. Any surprises or takeaways you want to share?

**Paul: **Yes. There's one key surprise that was really interesting. Actually, I'll go with two. One is that we've learned that small UI improvements have really outsized impact when you're having a product that is the core of someone's workflow. You make a very small, seemingly insignificant change, and it has much bigger impact than the effort that goes into it.

So that's one. And the other one is validating. Often you want to validate with customers, and we do a lot of user testing and validating with customers.


<blockquote>When you're building a big thing you can't just give the whole thing to a customer. You have to rethink a lot about how you validate. </blockquote>


We've been doing weekly planning meetings, and in that we have a hypothesis spreadsheet. And it's like, "What are the hypotheses that we're validating this week, or invalidating this week?" And we hypothesize that this particular feature is going to solve a lot of problems, or just that we want to solve these problems and we're going to try a bunch of things to solve it and see which one sticks.

And it's a really interesting validation problem, and I think it's one where most people wouldn't choose to do because it's as a result of having a very large surface area to build. Which has its pros and cons, but it's what we're doing.

**Edith: **That's so cool, Paul.

**Paul: **Thanks, Edith.

**Edith: **I'm glad that you seem really excited about it.

**Paul: **I love it. I'm super excited. Thanks so much for investing in it.

**Edith: **You're literally bouncing with excitement.

**Paul: **I know, it's great. We're hiring, by the way. You should check out DarkLang.com/careers.

**Edith: **And then you get to work with Paul, and perhaps we'll hear new stories before they're on the podcast.














