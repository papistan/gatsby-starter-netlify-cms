---
author: mattdel
comments: false
date: 2019-11-15 16:00:47+00:00
layout: post
link: https://launchdarkly.com/blog/nightmares-in-employee-onboarding/
slug: nightmares-in-employee-onboarding
title: Nightmares in Employee Onboarding
wordpress_id: 194527
categories:
- DevOps
tags:
- engineers
- onboarding
- test in production
---

Kristen Gallagher, Founder of Edify, a data-driven, human-focused learning design firm, spoke at the October Test in Production Meetup in Seattle, co-hosted by LaunchDarkly and the Seattle DevOps Meetup. She shared about nightmares in employee onboarding for software engineers and strategies for avoiding them.


<blockquote>"So, the story of the too big, too fast team. On a dark and stormy night, a team was gifted with ten new hires, which is such a good gift right? ... But you did not get the gift of any changes in your release dates for three critical feature releases, right? ... You're going to get ten new bodies, they're going to help you with all of your work, it's going to be so good, right? No, what actually happens in this situation? ... Everything slows down." – Kristen Gallagher, Founder, [Edify](http://edifyedu.com/)</blockquote>


View the slide deck of Kristen's presentation and read the full transcript below to learn how to create a seamless engineer onboarding experience with a retention-driven development (RDD) approach. If you’re interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/).



FULL TRANSCRIPT

Kristen Gallagher: Turn it off for a second. All right. Can everybody hear me? Are you all dead? Anybody alive?

Dawn: Yeah.

Speaker 4: Yeah.

Speaker 5: Woo!

K. Gallagher: Okay, I know it's dark outside. Okay, hi, my name is Kristen Gallagher, I run a company called Edify and I build software engineering onboarding. I'm not a software engineer, but I like y'all a lot and I know how to work with you.

K. Gallagher: I want to talk to you a little bit about nightmares from employee onboarding today, and it's going to be slightly different... I need my clicker... It's going to be slightly different than the... I guess, is this a Bluetooth clicker? Or are we...

Host: I used my laptop and I kind of just [crosstalk 00:25:11].

K. Gallagher: All right. I’ll just stand here. It's not necessarily going to be nightmares about your onboarding, although raise your hand if you had a terrible onboarding process at one point in time. I'm sorry, it's not my fault. It's your company's fault. But this is a [crosstalk 00:25:29].

Speaker 4: My ex-company.

K. Gallagher: Your ex-company's fault, yes. Proving points for me already. But we're going to talk a little bit about effects of new hires coming into your team, and how that can be a nightmare. So, that's probably a little different perspective on onboarding than you might be used to.

K. Gallagher: The first story I want to tell you is the story of the too-big, too-fast team. Just from the title of this, do you feel like you might know what this means? A too big, too fast team. Anybody want to volunteer for me what that means to you?

Speaker 4: More than two pizzas?

K. Gallagher: More than two pizzas, yes. And you had... The team grew too fast. Yeah, so it's more than two pizzas, but it also got too big too quickly. Oh wow, Dawn is amazing. Thank you.

K. Gallagher: All right. So, story of the too-big too-fast team, so on a dark and stormy night a team was gifted with ten new hires, which is such a good gift right? You all look so excited about this. But you did not get the gift of any changes in your release dates for three critical feature releases, right? That sounds really fun right? You're going to get ten new bodies, they're going to help you with all of your work, it's going to be so good, right? No, what actually happens in this situation? Anybody experienced something like this before?

Speaker 4: Chaos.

Speaker 9: Everything slows down.

K. Gallagher: Everything slows down right?

Speaker 4: Yes.

K. Gallagher: This is the great irony of not really planning your resourcing properly, right? Is that the moment you know that you need to build more product, then you also know you get the head count. But you really needed the head count six months ago, so you could have onboarded the people so that now they're ready to actually help you build.

K. Gallagher: What's a side effect of this happening? When I add ten people to your team, but you don't get to change your release date, what happens to the team? I see heads shaking. What was it in the back there?

Male: The team splits.

K. Gallagher: The team can split for sure.

Speaker 8: Well not real splits but-

K. Gallagher: Mental friction.

Speaker 8: [inaudible 00:27:36].

K. Gallagher: Yes. So, one way that this can happen is that new people end up kind of siloing out by themselves because they're too slow to be with the rest of the team. Was there another suggestion?

Speaker 10: Sometimes the work slows down cause you have to onboard the new people and bring them up to speed.

K. Gallagher: Yeah, work slows down. So, you're going to push those dates anyway. Unfortunately, that's going to happen.

Speaker 8: Sometimes you lose good new people because they think that everyone doesn't know how to organize work.

K. Gallagher: Exactly, you can churn out good new people. You can also churn out, you can also churn out say, old people, people who were on the team before because it's very frustrating for them right? Have you ever had to help onboard a new hire, but it's not your job? It wasn't your job to help onboard a new hire?

Speaker 8: Yeah.

K. Gallagher: Yeah, you were not their manager, but then your manager was like, "Go talk to Jane, go talk to Joe." And you were like, "Oh God, I don't want to talk to you right now. I'm not trying to be mean, but that is not my job for you," right? Unfortunately, this is how we onboard people right now, so that's scary story number one.

K. Gallagher: Scary story number two is the story of the time-eating new hired zombie. I tried to be really creative for you. So, in the middle of your sprint, you get two new hires, like a little better than a ten, right? But something is wrong with them. But they're regular new hires, okay? So, they're normal people, but you're just like this is weird, something is wrong in this situation. And you figure it out later when you find your architect under printed Confluence documents. What has actually happened is that your new hire spends so much time with your subject matter experts and printing out and trying to understand what the documentation actually says, which by the way your documentation is probably poorly written and definitely not organized. Don't pretend like it is. I know it's not.

Speaker 8: And out of date.

K. Gallagher: And what?

Speaker 8: And out of date.

K. Gallagher: And very out of date, right? But we're just going to scoot that over there, we don't have to look at that. And so, this horror story is your new hires coming and spending way too much time soaking up time of senior people in your team. That's not necessarily that the new hires are trying to steal this time from people, it's not necessarily that the existing team members don't want to give the time or don't want to help the new hires, but that's not necessarily their job, right?

K. Gallagher: And number two, it's actually probably the most expensive way to onboard a new person because you pay those senior people more money, and you need them to be working on other things other than the new hire onboarding. And so, you end up wasting everybody's time, and it's unfortunate because your new hire is still supposed to get productive pretty quickly, and the only way they know how to do that is to just ask questions. So, it's sort of this, unfortunately, Catch-22 problem that we have.

K. Gallagher: On top of that, you've probably been asked really stupid questions from new hires before. They don't know they're asking really stupid questions of you. So, that's scary story number two.

K. Gallagher: But how do we solve for these kinds of things? I have some ideas for you. We're all familiar with Test-Driven Development, right? We want to try Retention-Driven Onboarding. I have a worksheet for you. You don't need to pull it up right now, but if you want to make a little cheat sheet to make your own onboarding program you can have this. I will pause while you take photos or write it down. We can also probably put it on the Meetup or something.

Dawn: I can put it on the Meetup.

K. Gallagher: Yeah. It's tinyurl.com/yxnmvagv. All right, we good? Okay. All right. Oh, that's so tiny, I'm sorry.

K. Gallagher: So, we are familiar with general Test-Driven Development, but what I'm proposing with Retention-Driven Development, which would be the onboarding model that I want you to think about adopting, is that you have this cycle of collecting documents for an MVP type of onboarding, you update that MVP with new links, you clean up a few docs so you don't boil the ocean, you don't try to clean up everything, and then you actually go and tell your new hires to find the errors. And you use your new hire as your person who's testing and finding bugs and creating issues. And then you use your new hire to teach themselves how to ask better questions and get better docs written. And you just keep that cycle going. Every time you bring on a new person, you do a little bit more, you fix a little bit more.

K. Gallagher: Okay. So, generally this philosophy is a minimum viable program. You're not trying to produce a really beautifully done onboarding program because things are going to change quickly, right? So, let's just acknowledge that that's a constraint, and we don't need to change that. It's iterative so every time a new hire joins, they are searching out these sort of documentation bugs if you will.

K. Gallagher: And the other key component of this is Employee-driven onboarding. Most of the time we think about Manager-driven onboarding meaning the manager sets up everything for the new hire. Well, how many of your new managers actually did a really good job with you? Be honest. Okay, that's good.

Male: [inaudible 00:33:07].

K. Gallagher: Right, okay. Was there one other hand? Manager did a decent job? Well, it's also not that your manager doesn't want to do a decent job right? Generally speaking, they're not malicious in this. But it's tough, especially in a lot of the kinds of companies that I work for, managers can have five to ten to thirteen direct reports sometimes, and if you're adding new people to those teams it's really tough to make a good onboarding plan for them. And so we're shifting responsibility from the manager on to the new hire, and getting the new hire to take ownership over the kinds of questions that they ask, and teaching them how to ask better questions, how to get better information out of the existing team without taking too much time.

K. Gallagher: Okay. How do we do this? Step one, do not be afraid of the dark. You have to figure out your Four. Your Four are four specific learning elements. So, start thinking about these four elements: you have professional expectations, process, product, and your technical stack or your tooling.

K. Gallagher: Now what do I mean by professional expectations? Think about the professional expectations in your team. What's expected of you? Do you have any norms around video conferences? Norms around what you do with your code, or how you check things out. Norms around how you communicate. Norms around how you raise issues. How you do standups. Do you do standups? What do you with cross-team functionality? All those things are professional expectations.

K. Gallagher: I tell people if you're having a hard time thinking about professional expectations, what would you fire someone for? These are your professional expectations. Okay. So, if you're really struggling on this one figure out what you really don't like when people do. And this is what I'd call tacit knowledge. It's stuff that lives in your head and it's not explicit. Explicit would be written down, it would be codified somewhere. Tacit knowledge is the stuff that we call, "gut checking,” it's the culture fit. "This person is not a culture fit because I just don't like how they handle things in a meeting." Well, if you made that assumption about how they handle things in a meeting tacit, maybe you wouldn't have a conflict about it. If you'd said that in the onboarding program or this experience, then we wouldn't have an issue at all. So, we're trying to illuminate all of these tacit professional expectations.

K. Gallagher: What about process? Yes, question.

Speaker 8: I had a really good debate once with an HR leader about they should have known better.

K. Gallagher: Oooh.

Speaker 8: That's a classic sort of mistake of new people like, "Oh, they should know. They should never do that."

K. Gallagher: Help me understand, so the HR person was-

Speaker 8: HR person was... I don't remember, somebody answered an email. It was very distant. I just wanted to debate more than the incident, but it was something like I don't know, "Didn't answer their email for two hours," and that work was very [inaudible 00:36:07] responding to your email every ten minutes.

K. Gallagher: Do you have a stated SLA about your email contents?

Speaker 8: No, it's not written down.

K. Gallagher: I didn't think so.

Speaker 8: It's just very built into the organization, but her statement was, "Well, they should have just known better" and I was saying, "Exactly, [crosstalk 00:36:20]."

K. Gallagher: Right. Well, how the heck are they supposed to know better.

K. Gallagher: I know 45-year old people and 65-year old people who don't know how to speak properly to another human being despite having worked for 40 years. We just don't make assumptions in my land.

K. Gallagher: Process, what do I mean by process?

Male: Do this, do that.

K. Gallagher: Do this, do that. It's how things happen. I call this, "How work gets done." So, how do you actually check out code, what are the expectations around your technical work? What about product? Should be pretty obvious.

Speaker 4: What done looks like.

K. Gallagher: What done looks like. That's definitely something that goes in here, for sure.

Male: What are you producing?

K. Gallagher: What are you producing? Who are you producing it for? What do they look like? What do they need?

Speaker 4: If your product's need five different things [crosstalk 00:37:14].

K. Gallagher: Please explain, yes. Explain versioning in here, explain all kinds of ways to get into the product, which sand boxes you can play on, which ones you can't, all of that. And then last but not least your technical staff and your tooling. This is explaining what you use for what reason, why you have chosen it. Has anybody ever had a new hire join and critique a decision that was made prior to their joining? Yes. Okay. But how much context was shared with that new hire about why that historical position was made?

Speaker 8: Subsequently, quite a bit.

K. Gallagher: When you have to sit the person down and you were like, "I'm sorry, you need to stop critiquing this." If you can, maybe chew on the idea of in your documentation the next time you write something make just a line about why that decision was made. And when you start to have your new hires, use some of this bug tracking processing for their documentation, ask them to get the why out of the person too, so that people aren't joining and saying, "Well this is stupid, I would have done it completely differently." Well, I'm sure you would have except for here were the constraints that we have, and this is the rationale for the decision that we made.

K. Gallagher: Any questions about these four? Yeah.

Speaker 11: Well, just a comment. You say that stack or tooling, there also has to be clarity what was the person's skill level, were they interviewed to know Java so we can take that, or what classes do they need to take because that wasn't part of what we filtered on.

K. Gallagher: That's a really good point. We're making pretty base assumptions here about everybody is coming in with the same skill level. That's not true. You need to be aware of the kind of challenges, not necessarily challenges but definitely skill level or fluency that a new hire has coming in. And when you start building up this kind of structure, or if you use that worksheet I gave you, it makes it easier to figure out what kind of tooling they need to be exposed to because you have something for them to kind of rely on. And when they have questions, they can say, "Oh, this is past my skill level." So, you would have illuminated these issues and these potential conflicts a lot sooner.

K. Gallagher: Any other questions about the four learning elements? Is there any-

Speaker 11: I would also say it's not... First, you have to figure out what skills do they come in with, and then provide them the resources to learn them.

K. Gallagher: Yes, that's a whole another talk.

Speaker 11: I've been there where they didn't have it or [inaudible 00:39:52].

K. Gallagher: Yeah. Has anybody else been in that situation before where it was clear that you didn't know something. You needed to know it, but you didn't necessarily have the resources around you to figure that out. There wasn't necessarily a professional development budget or a learning and development program for you. I'm sorry on behalf of other learning and development professionals.

K. Gallagher: Any other questions about the four? Is there anything in your work environment and your workflow that you feel like doesn't fit into these four categories?

Male: I would just say that part of the tooling, give the person their laptop on the first day.

K. Gallagher: That's true. That could have been a horror story that I could have told you from the new hire perspective, but it's almost so usual, I hear that problem so much that I kind of... Because I do this for a living, I built onboarding programs, I think, "This isn't a problem anymore, right?" And that's completely false. It's really upsetting when people don't have desks or laptops, or the laptop wasn't provisioned properly, makes me very upset and sad. Which really just means that your team needs to work more closely with your IT and your procurement team depending on your company's structure.

K. Gallagher: Step number two, turn the monster into a hero. In this situation, our new hire is the monster unfortunately. You want to think of them as onboarding program managers. They're each going to be their own little onboarding program manager. Very few of us work at companies where there is an onboarding program manager. I can tell you even Microsoft, even Amazon having worked at Amazon, they have onboarding program managers, but it's not very good. So, let's just assume that the existing onboarding structure isn't very good, and it doesn't go into the technical level that we need it to go into, so we're going to treat our new hires as if they their own program manager.

K. Gallagher: Okay. How do you do that? We go back to this employee driven onboarding concept, and you're trying to solve for three main things, one is disenfranchisement, having an employee feel like their hands are tied, they don't know how to move forward. I don't know if any of you have ever felt that way before in a new job. It usually shows up as the feeling of, "Why the heck did I leave my last job? I'm such an idiot. I wish I didn't do this," all those sorts of things.

K. Gallagher: The second problem that were trying to deal with is overloaded managers. Dean spoke to this earlier when people just have too much to do, it's hard to manage all of it. And then the last one which we talked about earlier as well is stale documentation, things just get outdated pretty quickly. We are going to combat all of that with Employee-driven onboarding.

K. Gallagher: The thing we haven't talked about yet is what I call a touchpoint matrix. This is a spreadsheet that doesn't have to look pretty. It is basically your backend index of your onboarding program, and that worksheet that I gave you has a structure of that. It's basically a system of parent topics, child topics, and the documentation, and when they should be exposed, "they" being the new hire.

K. Gallagher: You stage out your touchpoint matrix because has anyone gotten an email from their manager with ten links or more that they were supposed to read? And there's zero context about how this is supposed to happen, or on what day, or does this one come before this one. And it just so happened that they copied them and pasted them into the same email. We don't do that. That's not good. Don't ever do it again.

K. Gallagher: Instead, what you're going to do is you're going to stage it out. So, week one, week two, month one, month two, those sorts of things, and really start to think about assessing your own assumptions about the knowledge. Try to put yourself back in the new hire's shoes and say, "Would they have the context to understand this documentation, to understand this concept right now, or do they need to read this first?" And if you're struggling to do that, take your most recent new hire, six months, maybe nine months even, and ask them, "What did you have to start with?" Actually, use that information from their own experience to start building your own touchpoint matrix.

K. Gallagher: Then you give this document to your new hires and you have them break it. Remember our cycle, tell them, "Find the stuff that's wrong, find the stuff that's missing. The broken documentation, the scale documentation. Find it," and then we're going to work with them on asking better questions of those subject matter expertise.

K. Gallagher: Okay. How do we do that? We cure the zombie docs. We need better questions. If we're going to tell a new hire, "I still want you to go fix some documentation, I want you to go talk to subject matter experts," those people on the team who's time they're going to take, the new here is going to take some of their time and probably irritate them, let's just make it as easy and painless as possible. Let's try to make it as least irritating to that existing team member, so we need to teach them how to ask better questions.

K. Gallagher: There are a couple different kinds of questions. Has anybody been familiar with Socratic questioning before?

Speaker 10: What do you mean by that?

K. Gallagher: Did you take any liberal arts classes in college? Yeah?

Speaker 10: I just asked what do you mean by that?

K. Gallagher: What do I mean by that? You're funny. Socratic questioning, I gave you a link in your worksheet to learn a little bit more. There's technically six kinds of Socratic questions. All the ones that I care about you knowing right now are ones that go for clarification, ones that probe assumptions, ones that look for evidence, and ones that look for implications of decisions.

K. Gallagher: You literally could just give this list to your new hire and say, "Construct questions about this topic that do those four things." You don't have to tell them what kind of question to ask. Just tell them, "This is what you're looking for. These are the four outcomes that you’re looking for." I'm not going to force you to go back to school and get a liberal arts degree as wonderful as they are.

K. Gallagher: Okay. So, empowering your new hires. You are sending them on info gathering missions, you're asking them to interview the subject matter expert, write something, diagram something, socialize it. You're asking them to basically create a bug, and sometimes I actually have people put something in Jira and have this be a test for them to work on, or whatever tracker you use. And then the bug gets closed when the doc gets reviewed. That can happen in a new hire's one-on-one with their manager, it could happen with the person who was the subject matter expert.

K. Gallagher: So, what I'm asking you to think about is instead of the person who wrote the original code, or who made that decision, write the documentation, because maybe you skipped that, maybe you didn't do it, maybe it was half done, that new hire finds that, they did the test, they interview you, they write it, and they give it back to you, and you QA it. Okay? So, that's taking a little bit of time away from you, and it's teaching the new hires, giving the new hires the context that they need as well. And then you update that touchpoint matrix in the links change.

K. Gallagher: Okay. Recapping, we are doing Retention-Driven Development, we're having our new hires focus on onboarding themselves, we are not boiling a ocean, we're doing MVP-style onboarding, we're helping our new hires think of themselves as their own program manager, and we're trying to re-factor our documentation slowly and with our new hires’ help. Okay?

K. Gallagher: There is no reason to be scared about your new hires now. If you've got questions, or you're dealing with a sticky situation and you don't really know how to handle it, shoot me an email or Twitter, and that's it. Thank you. Any questions?

K. Gallagher: Questions, concerns, horror stories you need to share in a therapeutic style? Safe space. Yeah?

Speaker 10: How have you found the difference between onboarding full-time employees versus onboarding short-term contractors?

K. Gallagher: The main question between onboarding a full-time employee and a contractor is what's the permission level. How much documentation and data needs to be shared with them and drawing a box around that. So, making sure that you have the right tooling to share confidential materials with that contractor. It really is the same process, so they just have the smaller scope generally speaking. So, you're trying to draw a box around the information that they need so it keeps separate from the rest of the staff.

K. Gallagher: Is that helpful?

Speaker 10: Yeah.

K. Gallagher: Other questions. Yes.

Male: If you have multiple people onboarding at the same time, how do you prevent them from both making bugs to say I want this place, and I also want this similar thing [inaudible 00:48:54] take place?

K. Gallagher: It's a good question. Bringing people together, I always, always, always tell people to do cohort onboarding. I have had long and arduous arguments with engineering managers who want to get somebody on their project right now and having them productive right now, and so they can't wait another week until there's two or three people getting onboarding at the same time. You should always try to onboard people in a cohort if you can. And then you should have them do a standup, be part of the team standup and say, what needs to be fixed, what's confusing right now, and have the existing team draw out those things that are basically the same that they should be working on. Is that helpful?

K. Gallagher: Other questions. Yeah.

Speaker 8: How long do you normally tell people to expect onboarding to take?

K. Gallagher: Onboarding takes a year, but target productivity shouldn't take three to six months usually. But your average I'm guessing is nine to 12. That's an industry standard. Yeah. Which we don't like doing it. Yeah.

Speaker 11: How much resistance do you get from people trying to invest in the long-term gain. My company, the mentoring or buddy, that is part of their job, and they put a lot of time into it, and it shows up in reviews, but I can see lots of places that and just like, "Well, that's a little side thing."

K. Gallagher: That's a good question. Resistance in onboarding. I'm going to try speak nicely about this. In cultures where soft skills are not rewarded, I get more pushback on having buddies, things like that. I'm hearing some chuckles as well, so maybe you've experienced this.

K. Gallagher: I find that generally speaking that if a team believes that your value is in your technical content and technical production basically, they're going to expect the new hires to get up to speed faster, and they are also going to be the teams that put them in the deep end sooner, and they are also going to be teams that have the highest attrition rates. So, you can burn through your hires quickly if you would like. That's fine, it's also very expensive for you.

K. Gallagher: I just did a calculation actually for a person who is hiring 600 engineers for their company next year, and they have a targeted productivity of about nine and a half months right now. And if they don't move their targeted productivity down to six months it will cost them $24 million in 12 months of just having them. So, you can argue about that if you want, but that is the math. If you want to go back to your customers and ask for that money, you can. I'm not going to.

Speaker 11: How do you measure that?

K. Gallagher: I measure it in three different ways. I have some calculations around attrition and [inaudible 00:52:00] costs in terms of productivity. Are you asking about [inaudible 00:52:03]?

Speaker 11: In terms of productivity yes.

K. Gallagher: It's going to depend on each different team, what productive means. Generally speaking, I'm finding with over the last five to six years what do I my teams by productive is a combination of type of commits, number of commits, and quality of commits as well, and how much they're able to work on their own, not using other team members time. It's not a hard and fast science unfortunately. Because I can't... I don't have any resource to code analysis on your code. And in fact, I don't necessarily care if you were on something really, really long. That doesn't mean anything to me. It's more about how you interact with the team and what quality you're producing in the team.

K. Gallagher: Question.

Speaker 4: Are there actual I guess... You spoke about hiring processes, and I think a lot of people are always trying to get a perfect candidate. Is there actually evidence that there is any predictive indicators of [crosstalk 00:53:10]?

K. Gallagher: I'm just [inaudible 00:53:16] to myself. Reframe the last part, is there evidence that what?

Speaker 4: I guess is there evidence that the sort of things that are being selected for a hiring process are predictive in terms of time and productivity? Is it pre-hire versus post-hire?

Rick: Our goal is how much it delays around the [inaudible 00:53:36] hiring process.

K. Gallagher: Right. I have seen teams take a really long time to search for that perfect candidate and they hire a senior engineer, somebody who's got great experience, great pedigree and they failed too. You know why they failed? They failed because of a shitty onboarding program and a crappy culture. This again is the same amount of failure as the new person, the junior engineer. And unfortunately, what ends up happening is... I call onboarding a skin off my nose problem because you don't feel it immediately because it delayed whatever the opposite ramification is, problem where if somebody leaves, six, seven, nine, ten, eighteen months they're leaving, and we say, "Well yeah, they didn't fit here. They didn't get the culture. They didn't want to do it our way." And then the reality is you probably didn't take time to explain all of the assumptions and all of the tacit knowledge, you didn't help them get plugged into the right environment, so they couldn't leverage all of their pedigree, they couldn't leverage all of their skill. So, you just spent $30,000 wasting your time hiring them and looking for them and interviewing the rest of the other candidates and then pissing off the rest of your team when-

Rick: To say nothing but the years’ salary.

K. Gallagher: Right, to say nothing of the salary. It's actually three and a half times the salary to replace somebody now, plus minus.

K. Gallagher: Yes.

Dawn: Do you find that companies that now have solid... Do you hire onboarding program, hire your junior staff?

K. Gallagher: They can, yes. Because you can afford the "pain" of a junior person, you can absorb it. I deal with my beloved engineering teams, and it's okay that you're not a good teacher. It's okay that you don't necessarily want to spend a bunch of time with this person talking with and doing all of these things. We've got this scaffolding in place, and it always to just kind of absorb and just keep the shock of the new person from diffusing the team. And if you have a tendency to hire junior people, those junior people can then onboard the new junior people because they've been in the same spot, so it makes it easier.

K. Gallagher: This dovetails nicely with some diversity and inclusion work too. I always get the complaint that, "Well, I'd be happy to hire more diverse people if it didn't diminish our quality." And I don't understand why that... It's like a 20-year old complaint at this point, which is just not true. But if that is your problem and or your team's issue and you feel like that's what's happening for you, build an onboarding program and you can solve it.

K. Gallagher: Other questions? Yeah.

Speaker 11: Well, this more of an interesting counter. I remember a guy some time back who was brought in, who... This is not best place to share that story, but everything he said was, "Well, at Microsoft," every two minutes. He'd say that. And he'd put himself in this niche where everyone just wrote him off. It was very interesting to watch because he just sort of refused to adapt. People were giving him, "Here's how we do things here." And he's, "Well, at Microsoft we dadada."

K. Gallagher: Gosh, some people need so much more therapy than they get.

Speaker 11: Yeah. [crosstalk 00:57:03].

K. Gallagher: Yeah. I'm just going to say I just, yeah. And unfortunately, that should have shown up in an interview. If you really interview the person well... Did you interview him?

Speaker 11: Sure, I'll tick yes.

K. Gallagher: Okay. You're like, "I don't know."

Speaker 11: I don't know remember [inaudible 00:57:16], but yeah.

K. Gallagher: Are we all familiar with behavioral interviewing?

Dawn: Yeah?

K. Gallagher: Familiar? Okay, good. If you're doing a good job with your behavioral interviews, you should encounter that kind of resistance in the interview because you might ask him about process or how they would approach something, or how they have approached something in the past…not in a rhetorical way. So, I think you should start seeing something like that. I've seen that kind of resistance too, and it's like, "Well, that's great. Then why would you work at Microsoft if you like it so much?" Do I see another hand? Yeah.

Speaker 4: I'm just wondering, does the industry recognize the strategic advantage of being able to pull from a larger candidate pool? Or you find that you're fighting an uphill battle here?

K. Gallagher: I don't think it's an uphill battle per se. Well, I would say it's uphill, but it's not like this. It's not a steep incline. I think the problem... I'm going to be a little more philosophical here. I actually think that the problem is the way we fund our companies, and generally speaking that incentive model for companies to perform well in the market, which also means that you have to shift more things out of your technical team, which means that just the velocity of your movement is so much higher than it should be to actually have a productive and effective and happy team.

K. Gallagher: And I think the byproduct of that is hire what you know, hire what you know, hire what you know. Which means looking at a specific set of schools, looking at degrees, looking at certain company category, all of things and saying, "Yeah, that fits mold, okay cool, they're probably good." And that just isn't necessarily true.

K. Gallagher: Yes?

Male: [inaudible 00:59:01] if there's a transition period between how many employees you have before you need an onboarding period. It sounds like work small you'd have new people, but you still need a certain [inaudible 00:59:11] to do the onboarding.

K. Gallagher: Yeah. I actually find that the smaller teams struggle more because they don't have people to diffuse the onboarding with. The question I think really becomes then when do you invest money and time in doing it. I would teams, "Don't hire me," for example or, "Don't hire another consult or somebody to build you something unless you're going to grow by 20, 30, 40%." Because it's just going to take too long for you to get the ROI on that. But you can do the equivalent of hiring a consultant by having teams actually divert work to their onboarding program. But you don't have to divert people's time if you do something more like this.

K. Gallagher: Is there a question? Yeah.

Speaker 11: Quick question. [inaudible 01:00:01] interviews, this is actually a really good question to ask that I tend to ask is what for certain level [inaudible 01:00:07]. But given that generally low standard for this, I was curious your perspective what would be on what you considered average or what kind of response would you think is pretty good for [inaudible 01:00:21].

K. Gallagher: I teach a class called Onboard Yourself to a code school in Portland so that those code school grads can try to plug in a little bit faster if we make the assumption that there's not going to be tactical onboarding, which is a generally fair assumption. So, the answers I think you're going to find if you're asked that question as an interviewee are like, "Um, yeah, we have onboarding, we have company onboarding."

K. Gallagher: Okay, so there's a module of onboarding that I know, which is a three-layer cake. You have company onboarding, you have departmental onboarding, and you have team onboarding. And you and I are going to get different slices of cake based on our team. And so, you're putting things for a backpack and say, "Well, what kind of onboarding do you have? Is it company level, like the business and history of the company, those sorts of things. That's great, doesn't help me in my job." And so, if you get a stumbling answer, which you're probably going to get, because they're not going to come out and say, "No, we don't onboard people," generally speaking.

Speaker 11: This is exactly like my last job. We think about it, and [crosstalk 01:01:28].

K. Gallagher: Yeah. We a plan, you and I, we're going to do one-on-ones, things like that. And I don't blame them, don't be mad at them for that necessarily. But the way that you turn it around I think makes the interviewer feel a little more comfortable about this too, because you never want to leave an interview having your interviewer feel you made them look stupid, pro tip.

K. Gallagher: So, the way you turn it around is say something like, "You know what I've found in my past is the most effective way for me to plug into a team faster is to have a structured onboarding plan. So, if you don't have that it's fine, but on our first day could we talk about that."

Speaker 11: Excellent, thanks.

K. Gallagher: Yeah.

K. Gallagher: Any further questions? No. Okay. It's been wonderful. Thank you.
