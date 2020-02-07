---
author: andreaech
comments: false
date: 2016-12-22 21:27:24+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-goal-setting/
slug: to-be-continuous-goal-setting
title: 'To Be Continuous: Goal Setting'
wordpress_id: 1290
categories:
- To Be Continuous
tags:
- Brendan Eich
- Firefox
- Google Analytics
- Gregg Brockway
- Hadoop
- metrics
- Mixpanel
- Mozilla
- Nicholas Nethercote
- OKRs
- scrum
- Sean Ellis
- TripIt
- Valgrind
---

In this episode, Edith and Paul talk about OKRs and other goal-setting methods. Hear them discuss the good, the bad and the "gameability" of measuring success. The pair remind us that there are learnings in the journey, not just the destination, despite what the term “growth hacking” might have you believe. This is episode #28 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.




TRANSCRIPT__







**Edith:** This week’s topic is goal setting.

**Paul:** All right, so, last week and the week before, we talked a little bit about various things where we touched on goal setting. In the episode where we talked about how to scale from your small team to a larger team, I think that was episode 25 maybe, we very slightly touched on OKRs.

Goal setting, or some version of goal setting like OKRs, is probably the most important thing that your teams need to do that’s not exactly intuitive, especially if you’re an engineer. Last week we touched on personal productivity, and I think we mentioned The Pomodoro Method. But goal setting on a daily or weekly or monthly basis is also this super powerful technique.

**Edith:** Yeah, I’m actually a huge proponent of goals. I think the reason why I’m a huge proponent of goals is that


<blockquote>if you don’t set goals or objectives, people, including yourself, will do everything but the most important thing.</blockquote>


**Paul:** Right.

**Edith:** To me, I explicitly say, “These are the two or three things we need to get done.” And then people usually, and even I say, “Well, what about the 20 other things going on?” It’s like, “Well, if we don’t get these three things down, the other 20 don’t matter.” But of course, if we don’t do the other 20, the three things don’t matter, either.

**Paul:** If the servers don’t stay up, then the new feature’s kind of pointless.

**Edith:** Well, all right. So, you have to set some bedrock ones. What do you think are bedrock goals?

**Paul:** For a software product, you mean? Well, it has to stay up. I guess you have to answer customer support.

**Edith:** You don’t.

**Paul:** Okay, I guess you don’t.

**Edith:** I mean, I don’t say that flippantly. I mean, you can do stuff like stagger your response times.

**Paul:** Yeah, you could choose to de-prioritize answering people on Twitter.

**Edith:** Like what you just said, we have to answer customers’ questions. Okay, in what time frame and at what depth?

**Paul:** Right, yeah. And of course we can always say, have an auto reply saying, “It’s answered in the docs. If it’s not answered in the docs, raise an issue here and we’ll ship in the docs,” or something along those lines.

**Edith:** This sounds very harsh, and I’m not advocating you always do this.

**Paul:** No, I understand what you’re saying.

**Edith:** But it’s definitely a dial you could turn. Like, when I was at TripIt, at one point we got completely overwhelmed. It was before I joined. They got overwhelmed by tickets. And they just did not answer about, I think, some thousands of tickets.

**Paul:** They just declared inbox-zero on them.

**Edith:** I would be looking at tickets later and there would be a note in a back log. Just basically like, “Closed it,” with no response. And then they did a big project to get back to where they could respond within a decent amount of time.

**Paul:** Okay, and they just sent out a thing to everyone saying, “Sorry, we can’t. We’re underwater.” Or they sent nothing.

**Edith:** This was before I joined, so we did get back to the state where we did start responding again.

**Paul:** To the old ones?

**Edith:** No, to the new ones.

**Paul:** Yeah, to the new ones, yeah.

**Edith:** And people were really happy because they’re like, “Most consumer products don’t give support at all.”

**Paul:** Yeah, I mean, I kind of think that when something has an app, that there’s no support.


<blockquote>I can’t imagine emailing Snapchat and expecting a reply.</blockquote>


**Edith:** I think if you’re an enterprise product, you do have some expectation of support. However, I heard this awful story about some.

**Paul:** So, hang on a sec, there. On the topic of goal setting…

**Edith:** Yeah.

**Paul:** We’re getting off topic, and one of the things we have to do to make our goals is to restrict going off topic.

**Edith:** Thank you, Mr. Biggar.

**Paul:** Yeah.

**Edith:** Or should I say Dr. Biggar? So, and by the way, thanks for keeping us back on track. I think part of the goal is, as you said, shepherding.

**Paul:** Yeah, exactly. Right. You have to cut out the unproductive stuff and say, “This is interesting and this is fun, but let’s cut that out. Because the most important thing is the thing that we all agreed was the most important thing.”

**Edith:** Yeah, exactly. So, like customer support, you said, “Yes, important,” but at what degree are you giving customer support?

**Paul:** Right, exactly.

**Edith:** Are you spotting within an hour, within two days, within a week or never?

**Paul:** I think one of the things that goes into this, as well, is code reviews. People feel that code reviews are essential. All right, and then you end up with, often, a backlog of unreviewed code and unreviewed poll requests, that people are getting frustrated. Maybe it bit rots and, actually, code reviews are not essential.

**Edith:** Tell me more.

**Paul:** I mean, you could just ship them, technically.

**Edith:** Particularly if you had a feature flag.

**Paul:** Well, yeah, exactly. If you use feature flags effectively, then yeah, you could just ship them.

**Edith:** And thanks for wearing your LaunchDarkly shirt today.

**Paul:** Oh, thank you.

**Edith:** So, for code reviews you could say, “What is the purpose of this code review?”

**Paul:** Right, right. And the purpose of the code review is to make sure that the code works.

**Edith:** Though, how you figure out if code works is, you ship it.

**Paul:** Well. [Keith Rabois](https://twitter.com/rabois?lang=en), who I’ve mentioned several times, “Rib-wah”… it’s not the French way. So, it’s like Rabois, or yeah, “Rib-boys.” Anyway, he gave a talk in YC’s How To Start a Startup series, and one of the things he mentioned is having co-metrics:


<blockquote>Whatever goal you have, you want to have a co-metric.</blockquote>


We want to get way more people to the site, but the co-metric is, we want to keep our conversion rate at 10%.

**Edith:** Well yeah, because otherwise you over-optimize. I mean, that was the joke I was making about, “Well, we need to finish on time. Why don’t we just finish now, then?”

**Paul:** Yeah, exactly. So, you can pick a co-metric that, this number must go up, and this number must not go down or must stay the same or whatever, at the same time.

**Edith:** Well, because people optimize for a metric. I’ve heard of coders who are paid by line of code. And you know what happens then.

**Paul:** Right, exactly. Or coders who are paid by number of bugs they fix, yeah. Ludicrous ideas that people have done a lot.

**Edith:** Well, you want to measure what you can. But then what happens is, you’re basically taking the balloon and squeezing it.

**Paul:** Yup. Now, Spolsky really did have an article on how knowledge workers game shit, because they’re good at gaming shit. If you make a game, they will game it.

**Edith:** The gamification of gamification?

**Paul:** The gamification of work. So, if you gamify, I mean, goals are essentially gamified work. But if you gamify it, wrong then people will optimize for the goals that you set.


<blockquote>If you set the goals wrong, then you’re going to get what you’ll think you’ll get.</blockquote>


**Edith:** Well, and then, I mean, the terrible, kind of natural play-out of that, is something like the [Zenefits scandal](https://www.buzzfeed.com/williamalden/zenefits-under-scrutiny-for-flouting-insurance-laws?utm_term=.yp4edPXxGm#.ov0dYAp51G).

**Paul:** I’m going to disagree there.

**Edith:** Oh, this is great.

**Paul:** Yeah, I know, finally. I mean the Zenefits thing was perfect.

**Edith:** Well, they over-optimized for revenue and then under-optimized for compliance with government regulations.

**Paul:** And they’re worth a billion dollars now.

**Edith:** So you’re saying that Parker…

**Paul:** Parker got ousted. Presumably he still owns all the shares that he owns. So he’s a hundred millionaire, and now he doesn’t work anymore.

**Edith:** So you’re saying maybe this was his evil, evil plan all along?

**Paul:** No, I don’t think it was his evil plan. And I should say, I’ve met Parker.

**Edith:** I’ve never met him.

**Paul:** Years ago and never discussed this. But he seems like a nice guy. And a good Circle CI customer. But if I was in that position, where essentially he became the fall guy. “Yeah, sure, I’ll take the fall. I’ve got a couple hundred million dollars. I’ll go do something else.”

**Edith:** Well, I think that speaks more, I mean, for you. I know I’ve never met him, but I know that, from what I’ve read, he was not happy about basically being booted out of his old company.

**Paul:** I’m sure he’s not happy about it, but he probably, I mean, again, no idea. But I’m imagining that, you know, the situation in that board meeting where someone says he has… Oh, you’re right, you’re right. We’re totally off topic.

**Edith:** Yeah, I mean, this is an interesting topic in and of itself.

**Paul:** Yes.

**Edith:** It’s not a, I mean, to sum it up, if his goal is how can it, no.

**Paul:**


<blockquote>His goal is probably stay at the company, and he probably didn’t succeed at that. But he did produce something big.</blockquote>


So the goal got hit to a certain extent.

**Edith:** I think his goal was to be an Aaron Levie or a Mark Zuckerberg who was running a company, not the sidelined ex-founder.

**Paul:** Right, fair enough. So, yeah, you tend to produce the goals that you hit. And often related to that, I think where people talk about, “immoral Silicon Valley companies” and that sort of thing, what they’re often hitting is someone who has a goal that they want to optimize that they don’t necessarily use the same baseline ethics as other people.

So, let’s say, for example, the [dark UX patterns](https://darkpatterns.org/).

**Edith:** Oh yeah.

**Paul:** LinkedIn does a lot of dark UX these days, and it’s like, yeah, they’ve got numbers that they need to optimize and things they need to choose, and $25 billion exits that they need to get to and yeah, maybe they don’t do.


<blockquote>Maybe the incentive isn’t there, to stay within patterns that their users actually like.</blockquote>


**Edith:** Yeah, I can’t comment on LinkedIn. But I know that sometimes there’s pressure to…

**Paul:** I bet they’re a customer.

**Edith:** No. Though, I would like it if they were.

**Paul:** Sorry, carry on.

**Edith:** I think with every goal,


<blockquote>there’s the danger that meeting a primary goal might mean causing harm or causing negligence in a second.</blockquote>


Like, a classic one that happens in marketing is, we want more leads, you get a lot more leads, then your sales department says, “Well, these leads are all really shitty.”

**Paul:** Yup, they’re poorly qualified.

**Edith:** Yeah. So it’s like, on a consumer site, when we want to get a lot more signups, these signups aren’t as high-quality as the signups we used to get.

**Paul:** Right, yup.

**Edith:** Well, that’s just part of, they’re both kind of symptoms of the same thing, which is when you brought in your funnel, you’re broadening your funnel, you’re not getting the same high-quality traffic.

**Paul:** Right. So the goal setting thing that a lot of people these days like is OKRs. And OKRs stands for Objectives and Key Results. Objectives: you set three high-level company things, and then you set key results which indicate that you hit that objective.

So, those three key results reach objective, and you then pass them down by group. You have the company objectives, and then teams look at the company objectives, and they pick their team objectives and then individuals. Oh my God, you’re sighing.

**Edith:** I’ve just seen this implemented so poorly. I was at a company where, it was the end of the year and we had to write reviews. And they’re like, “Here’s the objectives that you should’ve been doing the whole year. Please go write your results against these in your year-end review.”

**Paul:** Okay, so what you’re saying is that when you take a system and you do a really shitty version of it, that it doesn’t end up being good.

**Edith:** I guess that’s a fair point. Because it was the year end.

**Paul:** Yeah, it would’ve been good to know these objectives in January, that would’ve helped me be aligned against them.

**Edith:** And the other one was, we’re at a big company and our division really had nothing to do with these bigger objectives.

**Paul:** Right.

**Edith:** Like, it was just like, this is totally…

**Paul:** Well, yeah. So, I mean, you need an intermediary layer saying the reason for this division and how this division relates to the larger company objectives is, I don’t know, producing valuable research that will lead to the future of the growth. And then you have your objectives against those.

**Edith:** Yeah, I think also, and you’re right, maybe it was just the poor implementation of a process.

**Paul:** I’ve noticed that


<blockquote>people struggle a lot to get OKRs right, especially the first time.</blockquote>


**Edith:** Yeah.

**Paul:** And this is a thing that they say about goal-setting in general and OKRs in specific, that the first, maybe, two quarters that you set OKRs, that you’ll get them wrong. And part of the upside of them is actually getting it wrong.

It teaches you about how hard it is to set goals and how you change directions and how much you can actually produce, versus how much you think you can produce. So I think getting it wrong, maybe not in the sort of Dilbert-esque way that your company got it wrong,


<blockquote>but I think getting it wrong is a learning experience.</blockquote>


**Edith:** I think that’s fair. I think my complaints might be, like, somebody complaining that “Agile is not good.”

**Paul:** Right, yeah.

**Edith:** It’s like, well, anything poorly applied is not good.

**Paul:** Yeah, so the specific way that that I failed the first time I tried to implement OKRs was the key result is very important, right? So the key result has to be a number, so you have to measure, and so people would have tasks and they would have key results, and the key results were actually kind of hard to measure, or didn’t directly measure the thing.

So, people would spend time working on actually getting the right results or, sorry, not the right results but work on the results framework. You know, actually measuring things. And spend so much time on measuring things that it ended up being very difficult to, actually, all the time was spent on measuring, not achieving the goal.

**Edith:** Yeah, so Sean Byrnes, co-founder of Flurry, advisor of LaunchDarkly, he paired Oxfordly for a dude who founded a metrics company. He says, “Don’t measure everything.”

**Paul:** Right, yes, definitely don’t measure everything.

**Edith:** And that’s very scary to people because people think we live in a Mixpanel, Google Analytics monitoring world where everything should be measured. He’s like, “No, if you measure everything, one, you’re going to have a lot of error. Two, you don’t trust your data, because now you’re just in a metrics paralysis.

**Paul:** Yeah, we instrumented every click, and we measured every click, and then it was like, “We don’t know what these clicks are. We don’t know if this is the right thing to be in the funnel.”

Often, it wasn’t the ‘click’ that was in the funnel. It should’ve been something else that was in the funnel. And we ended up, we wrote a blog post about this, how we tossed away our analytics and switched to new analytics. But basically,


<blockquote>we measured so much that we didn’t know what was signal and what was noise.</blockquote>


**Edith:** Yeah, I think there’s this dream that people have. This mass data lake that you throw in Hadoop and get these wonderful insights. But in reality, what happens is you have a lot of metrics which you’re not even really sure what they’re measuring. And it becomes it’s own task just to sort that out.

At TripIt, we had this metrics thing that had completely ballooned to the point where we were tracking, like, 200 daily metrics. And nobody cared about it, so something would be very broken and we wouldn’t notice it.

**Paul:** Yup.

**Edith:** What we did is we just recombined and said, “Okay, these are the five-to-10 things we need to look at every day.

**Paul:** Right, and so this is why people like OKRs. That there’s like three of them at a company level, and there’s like three of them at a team level and three of them at an individual level. And then you have specific KRs, like specific numbers that are going up.

At Circle, for example, we had ticket volume as an OKR. We need to get ticket volume down.

**Edith:** That’s game-able though.

**Paul:** Yes, you’re right. And it wasn’t the only metric. We also had time-to-first response, time-to-resolution. So we definitely picked things that, while they were game-able, if you end up with people on, I like the phrase, good faith, we were acting on them in good faith, aren’t going to game them.


<blockquote>Because every metric is game-able.</blockquote>


**Edith:** Every metric is game-able.

**Paul:** Yeah. And so if everyone’s on the same page and going in the good direction… All of our support people we hired because they love giving support, right?

**Edith:** Yeah, they’re great. You have an awesome team.

**Paul:** Well, thank you. We really do. And the support team was entirely hired by Jim, the new CEO, so all credit there.

**Edith:** No, Lev.

**Paul:** Lev was hired by Jim, I think.

**Edith:** But he’s great.

**Paul:** Yeah, Lev’s wonderful. So, the way that we get the ticket volume down is you put more new docs, alright, that’s the easiest way. And at the time, our docs were not that great.

We added a discuss site, I think that was the first major change, so that people could ask their questions there. And then when you have a question, it’s already been answered in public. And I think if I was to do, the reason that we ended up with so many people emailing us was, that in the early days, we wanted people to email us.

**Edith:** Oh, yeah.

**Paul:** So that we could maintain that customer thing. And four years in, that’s no longer the most valuable thing for the customer or for you.

**Edith:** Well, it’s like, at the beginning you do the things that don’t scale because you want to have a one-to-one relationship with your customers.

**Paul:** Yeah, but you need to make that scale. And often, the obvious way to make a scale is, “Let’s throw more support people at it. Let’s use a better ticketing system, where we can get to it faster. Let’s focus a bit more on it, or whatever.” Instead of taking a side step and saying, “Maybe the original goals that we had for this weren’t the most important ones.”

**Edith:** Yeah, and I think where it breaks down is where you try to use your old system with your new scale. And you don’t realize that this is not helping anybody.

**Paul:** Right.

**Edith:** Like, we’ll still give one-to-one support, except for we don’t have time. So instead, we’ll answer nobody.

**Paul:** Yeah, yup, like whatever company that was, was it TripIt?

**Edith:** Yeah, and then they realized. So that’s when they put in all these new processes, so that could answer everybody.

**Paul:** Yup, so that’s the sort of thing that you can do when you identify the goals.

**Edith:** Yeah.

**Paul:** So, we had a goal which was to reduce our server costs. And the guy we gave that goal to, who’s just this incredibly amazing engineer at Circle, his name’s Mahmood. And we talked about 10x engineers.

**Edith:** Recruiters everywhere are like…

**Paul:** No, no, no.

**Edith:** Are googling.

**Paul:** Anyway, don’t recruit our 10x engineers. So, this task fell into his department. And we had all these tasks. Previously we’d done, “We need to optimize in this way and we need to make it better in this way,” but when we said like, “Actually, we don’t care about the tasks, all we care about is the goal.” He’s like, “I’m going to do a two-day spike on this thing that might work to reduce the goal.

And so he did some modeling and made some experiments and determined that the spot market was a thing that would reduce our costs. By the end of the quarter, he’d halved the costs.

**Edith:** Wow.

**Paul:** Yeah. And we hit a goal of like 25%, so he doubled the goal.

**Edith:** I think this goes back to something we talked about before, which was problem/solution implementation. And I think goals go back to that.


<blockquote>I think where goals do poorly is where you give people the implementation.</blockquote>


Like, “Your goal is to implement this.”

**Paul:** Yes.

**Edith:** Versus your goal. Like, if you just said, “Hey, here’s all the projects to go implement to bring down our server costs,” he would’ve met those goals. But he wouldn’t have really solved the thing.

**Paul:** Yeah. One of the areas that this comes up a lot is growth. You have like, “We’re going to do this task that will help with growth.” And the successful growth hackers, what they did was they said, “The numbers are what matters, and we don’t actually know what’s going to succeed in the metric.”

And so we need a process by which we experiment quickly. And the way this was put to me is that, the success,


<blockquote>the OKR that you need for a growth team is number of experiments run.</blockquote>


**Edith:** Yeah, velocity. I mean, [Sean Ellis](https://twitter.com/SeanEllis), have you ever met him?

**Paul:** I haven’t met him, but I know him. I love him.

**Edith:** Cool guy, yeah. I mean, basically, it’s all about velocity.

**Paul:** Right. I think this came to me indirectly via Sean Ellis, because Bubba is good friend of his, and Bubba’s my VC.

**Edith:** I just love the name Bubba, by the way.

**Paul:** Well, he’s also a great guy. Yeah, anyway…

**Edith:** I think


<blockquote>the mistake people make with ‘growth hack’ is the latter word, where they think it’s like there’s one easy trick.</blockquote>


**Paul:** Right, yes. I mean, it’s a hack, right? There’s just one of them. “We make the button red instead of orange, and suddenly it works.”

**Edith:** And we’re like, “We changed this subject line to this one, and suddenly it spikes.” Really, what experimentation is, I did a lot, it’s just a grind. It’s just a grind. When you find the one thing that works, of course, you’re like, “Why didn’t I just do that one thing?”

**Paul:** Yeah.


<blockquote>The answer is that you needed to process, and the process was dictated by the goals.</blockquote>


**Edith:** Yeah, you need a process and you need to do all those things that don’t work to find the one thing that does work.

**Paul:** Right, exactly, yup.

**Edith:** And the thing that might work is very temporal. Like, Facebook ads, I think, are less and less useful. They were very useful five or six years ago. So, this is drifting away from our goals, so let’s get it back.

**Paul:** Well, I think in general, the concept of goal-setting is, I think it’s the thing that engineers don’t like. They don’t like setting goals. They like this organic, “Oh, we’ll figure out the problem, then we’ll solve them and figure out the next problem. Then we’ll solve it. We should all know what the thing is. We don’t need organization-level goals. Like, what is this bullshit?”

And leads to planning meetings and weekly scrums that turn into, like, two-hour backlogs, triaging, blah, blah.

**Edith:** Yeah, I have been in an organizational hell. I’ve been in one of those circles that you described, of Dante’s Hell.

**Paul:** Yeah. Actually, one of the best goal-setting things that I ever saw, it was this organic this in Mozilla. It was done largely by a guy called Nicholas Nethercote, who’s one of those PhD savants that I talked about last week. He’s one of the guys who wrote Valgrind. And he set up this process of reducing the memory footprint in Firefox. And that was the goal: Firefox uses way way too much memory.

Over the course of several years, every Tuesday there was a meeting. And on the Tuesday meetings, they triaged the memory bugs that they had, they prioritized them and then they found people to work on the highest-priority things. And that was what they did for two years. And the memory footprint of Firefox plummeted over that time as a result of this.

**Edith:** Yeah, so at the beginning…

**Paul:** And, sorry, just one more thing, they had…

**Edith:** “I’m gonna let you finish.”

**Paul:** They had a chart literally of the memory footprint of Firefox, it was called I think, “Are We Slim Yet?”And you can go to areweslimyet.com, because Mozilla’s all in the open, and it’s a graph. And you can see it dropping.

**Edith:** I also love that a URL can be interpreted as “Are we slimy yet?” No, I love that, but I think the important thing with goals is that people, at least for me, I’ve realized if you set a goal, that means that other things will not get done.

**Paul:** Yes.

**Edith:** And you have to be very explicit about that.

**Paul:** Right.

**Edith:** Like, the world is…

**Paul:** The question is, “What are we not going to do in our day, to achieve this thing, is important.” Because it’s too easy to say, “Oh, we also need to do this.”

**Edith:** Well, that’s from the very beginning. That’s why I was pressing you on, “We need to do this big project, but our customer support can’t slip at all.”

**Paul:** Yeah.

**Edith:** Okay, something is going to slip here, and


<blockquote>you have to be very explicit with yourself and your team whether these are personal or public goals, about what’s slipping.</blockquote>


Like, in my own life, I’m pretty disciplined. Sometimes I’m like, “Is it more important that I run or I hang out with friends?” I’ll be like, “It’s more important that I run this week.”

**Paul:** Do you tie that back to monthly goals that you set, or something along those lines?

**Edith:** Yeah.

**Paul:** All right, so you have monthly goals: “I need to run 10 times this month, or something.”

**Edith:** They’re usually tied to a big race.

**Paul:** Right, okay.

**Edith:** I really wanted to finish a couple bigger, 100-mile races, and I said in the lead up to that, that that was my priority. Above, you know, hanging out with people. Right now I’m like, “You know what? I missed hanging out with people. I’m not going to prioritize running right now.”

**Paul:** A while back, I started setting monthly goals and weekly goals, just, “What do I want to accomplish this week?” But the thing that really, that really, really works for me is daily goals, where at the start of day where I want to accomplish something, which is occasionally now, but that sometimes, has been every day.


<blockquote>I’ll sit down with a piece of paper and I’ll divide up the piece into hours of the day.</blockquote>


Like, nine o’clock, 10 o’clock, 11 o’clock. I’ll write all the things down that I want to accomplish, and then I’ll find places that they go on the thing. And if there’s no place for it to go, then something needs to get cut from the list.

It might be an important thing for the monthly goals, but there’s urgent things, there’s important things, and you need to prioritize them. I forget who invented this and got to me, like, sixth hand, but it’s a really awesome personal productivity thing that’s really worked for me.

**Edith:** Yeah, I did that. In college I was getting an engineering degree, which was kind of a full-time load. And then I decided I would get an Econ degree at the same time, which was also kind of a full-time load. So I was very disciplined down to half-hour blocks of, like, “I’m going to work on materials engineering right now.”

**Paul:** Right.

**Edith:** I’m going to do my labor economics papers.


<blockquote>I would be disciplined about, also, what I was not going to do that day.</blockquote>


I think where people get into trouble, is they think that everything will magically happen on its own.

**Paul:** Yeah, and if you just have a bucket of things, if you don’t schedule them, we’ll just get to that next. Time is fungible. We’ll finish one, we’ll do the next one. And we can kind of organically…

**Edith:** Or that everything needs to be perfect within its own bucket, rather than there’s some virtue of, like I said, the tradeoff between shipping early…

**Paul:** There’s that saying, “Plans are worthless but planning is everything.” I believe Eisenhower said that one.

**Edith:** Oh really?

**Paul:** Yeah. The other war-related planning one was Von Moltke said, “No plan survives first contact with the enemy.”

**Edith:** Well, the one I always remember is from [Gregg Brockway](https://twitter.com/gbrockway) at TripIt: “A good plan today is far better than a perfect plan next week.”

**Paul:** Right.

**Edith:** He very much had a philosophy of “We need to move.”

**Paul:** Right, [Brendan Eich](https://twitter.com/BrendanEich) at Mozilla used to say, “Perfect is the enemy of good.” I think that’s a very common thing that people say, but, you know.

**Edith:** Yeah, I think you need to have a philosophy, this is what I loved about TripIt. And I thought it was very awesome to get to work with great mentors like that, is that they very much encourage that.

I think where companies get into trouble is, where they say, “Let’s ship early, ship often,” and then there’s this acrimony and backbiting about, “Oh, we shipped something that broke, why?”

**Paul:** Yeah, and where the “ship early, ship often” doesn’t have a direction of like, “Why didn’t ship ‘x’?” Well, because we were just shipping early and often. We didn’t prioritize shipping ‘x.'”

**Edith:** Yeah, or whereas at TripIt, they’re like, “Hey, we shipped, wasn’t quite right, got these bugs. Okay, fix, move on.” Instead of, where I’ve seen it break down at other companies, “We need to fix our processes so everything is perfect and the right thing when it ships, and we need to ship more often.” It’s like, you can’t do all this.

**Paul:** Right. Somehow we managed to actually tie this back to continuous delivery.

**Edith:** Well, you know what? I think we’ve met our goal of the podcast. Any final thoughts, Paul?

**Paul:** No, let’s just let it trail off awkwardly.


