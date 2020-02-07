---
author: andreaech
comments: false
date: 2016-11-24 20:57:50+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-the-10x-developer/
slug: to-be-continuous-the-10x-developer
title: 'To Be Continuous: The 10x Developer'
wordpress_id: 1288
categories:
- To Be Continuous
tags:
- CentOS
- Dave McClure
- David Sacks
- Elon Musk
- Keith Rabois
- Linus Torvalds
- PayPal
- Yammer
- Zenefits
---

In this episode, Edith and Paul dive into what it means to be a 10x developer. Is the 10x developer a myth? Is being a “rock star” a good thing? What about ninjas or pirates? The pair discusses what motivates them to see something through from start to finish, both in business and in life._  _This is episode #27 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.




TRANSCRIPT__







**Paul Biggar:** Today’s topic: the 10x developer.

**Edith Harbaugh:** Let’s start off by talking about where the phrase “10x developer” came from.

**Paul:** If I had to guess, I’d say, about 50% of things on this show, it came from Spolsky.

**Edith:** I don’t think it came from him. But it was an idea that there were some developers who were 10x as more productive than others, and that, if you were a startup or any sort of high-velocity, high-acceleration-type company, you wanted to hire these 10x developers. And the classic one was the [Max Levchin](https://twitter.com/mlevchin?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) of PayPal.

**Paul:** Was he a 10x developer?

**Edith:** That was the rumor, that if you hire these brilliant developers, throw them in a room with some Red Bull, your future is bright. And you don’t want to mess around with all the 1x developers.

**Paul:** Right. There’s a lot of controversy. I see people complain on Twitter all the time, on Hacker News, about, “Are there really 10x developers?” Like, “The 10x developers of myth.” And I actually have no idea what they’re talking about.

I’ve been my own 10x developer at various times. There are months where I accomplish nothing, and there’s days where I accomplish months of work.

**Edith:** Yeah, and then I think you also fall down, the phrase is that, “If I want the rock star or the ninja?”

**Paul:** Yeah. There’s definite problems of rock star, ninja, and pirate. Pirate is one that’s coming up.

**Edith:** I’ve never heard pirate.

**Paul:** Pick any subject of Disney movies that have actually terrible people behind them, like pirates and ninjas.

**Edith:** Yeah, and I’ll tell you my revulsion to these terms. They’re exactly what you said, terrible. I don’t want to work with a rock star.


<blockquote>When I think about a rock star, I think about somebody who’s late, who shows up hungover, who maybe kicks around their workstation, who’s a jerk to everybody else.</blockquote>


That’s not who I want to work with.

**Paul:** Well, I think you’re actually maligning rock stars there.

**Edith:** Oh, really?

**Paul:** Yeah. I don’t know very many rock stars, or maybe any rock stars.

**Edith:** I met Hammer once.

**Paul:** Oh yeah. He’s at all the SV Angel events.

**Edith:** So I did meet him.

**Paul:** Yeah, I saw him at the other side of the room and I was like, I don’t have anything to say to MC Hammer.

**Edith:** I saw Hammer, and my friend went up to him and, and he said to Hammer, “You were big when I was in middle school.” Which was, like, the most shade you could’ve mentioned.

**Paul:** Yeah, what did Hammer say?

**Edith:** “I get that a lot.”

**Paul:** That must be a painful thing to hear all the time.

**Edith:** “You were big when I was in middle school?”

**Paul:** Yeah.

**Edith:** I don’t know, it can go the reverse. There are these cool pictures of Michael Phelps and Katie, who just got the gold medal at the Olympics. She’s nine and he’s signing an autograph for her when she was nine, because she’s 19 now and he’s 31.

**Paul:** Did Phelps also win Olympics?

**Edith:** Michael Phelps?

**Paul:** I mean this Olympics. I haven’t been paying attention.

**Edith:** Yeah, he got a couple more gold medals.

**Paul:** Oh, okay.

**Edith:** To tie this back, there are truly people who are 10x. Like Michael Phelps, clearly 10 or 100 times X.

**Paul:** I think the allegation or the problem that people have with the idea of 10x is that if a person doesn’t feel that they are 10x, and


<blockquote>obviously our industry is full of impostor syndrome. Very few people feel that they are 10x.</blockquote>


Then the implication is that they are 1x or they are the blub developers that you want to avoid.

**Edith:** I think even more than that, my revulsion comes from… I think the true value of any person on a team is to be part of a team. And then let me explain what I mean by that.

I think there are sports like swimming, like Michael Phelps, where you are a single performer. You train to go to the Olympics or the world championships, and you have your one or two minutes in the pool to shine.

I think real life, when you’re building software or building something, is the day-by-day-by-day grind of working together with a team and collaborating and moving the ball forward an infinitesimal inch every day.

I think that the skills you need for one versus the other are very different. I think the skills you need to collaborate and build something, to build consensus, to communicate, to build something bigger than yourself…

**Paul:** I would say yes and no. Undoubtedly, to build something bigger than yourself, it’s not a one-person job. But you can carve out one-person niches of it. In the PayPal example, there were other people at PayPal. And they’re very famous now because they’re all ludicrously rich.

**Edith:** Who else, just for the viewers at home?

**Paul:** Keith Rabois, who we mentioned last week. He was COO there. Peter Thiel.

**Edith:** Dave McClure, who’s an investor in both of us.

**Paul:** Oh yeah. Oh, Elon Musk.

**Edith:** Not to mention David Sacks.

**Paul:** Oh yeah, Yammer and now Zenefits.

**Edith:** Yep.

**Paul:** Some form of corporate takeover of Zenefits there, I think.

**Edith:** Well, it happens to everybody, doesn’t it?

**Paul:** Oh, it hurts. No, I don’t mean to imply that there’s any sort of corporate takeover. That is not how it happened.

**Edith:** So, I’ve been called a ninja product manager, in a complimentary way. And to be honest, I didn’t really like it.

**Paul:** People identify with terms, or they don’t.


<blockquote>If you call someone a term that they’re not necessarily going to identify with, it’s not going to feel that great.</blockquote>


Even though they probably meant some very nice things when they said that.

**Edith:** It was the founder of TripIt, and he meant it as the highest compliment. He’s like, “Edith was a ninja. She did so much.” I think of a ninja as someone who goes around and kills people. And I’m like, “That’s not me.”

**Paul:** Right.

**Edith:** I’m not an assassin.

**Paul:** I mean, likewise with, if you think about rock stars, they are the most disciplined people who got to the very, very top of their craft,who have done things that no one has ever done before with the guitars and synths and… I actually don’t know very much about music.

**Edith:** I guess that’s the way you think of them. Maybe it’s an America thing; you think of a rock star as kind of like a petulant child.

**Paul:** Sure. There are many petulant childs. But then there’s also, what’s the Coldplay guy? Chris Martin or something?

**Edith:** Chris Martin.

**Paul:** Yeah, who’s supposed to be just the nicest, most down-to-earth human being on Earth. I think people would question whether Coldplay really qualifies as rock stars, but… I think it’s fair.

**Edith:** He’s incredibly disciplined. He practiced lean before lean was a thing. I remember a story about him where at concerts he’d be in these big auditoriums, and they have the doors to the back. And when the door opens, that means that people are leaving to go get another drink or to the bathroom. So any song where he saw a lot of doors opening, he’s like, “That’s not a good song to be playing.”

**Paul:** Oh wow, okay.

**Edith:** Because that means that people are kind of, “No, this song isn’t holding my interest.”

**Paul:** He had analytics on his music.

**Edith:** Yeah.

**Paul:** Yeah, interesting.

**Edith:** Because if it’s a good song, you’re like, “Okay, I’ll wait another song for that drink.”

**Paul:** Yeah. And when people talk about developers as rock stars, they clearly mean the people who are able to do the things that no one else is able to do. I think that negative connotation is… I don’t know why it necessarily has a negative connotation.

**Edith:** I think it depends on who it is. They’ve done a lot of studies. There’s a company, Text.io, that just does analysis of job listings. I think rock star is a term that traditionally appeals more to men than to women.

**Paul:** Oh, interesting, okay. I would guess that there’s also a particular kind of person for whom that appeals, who is probably much more of the extroverted side of things.

**Edith:** Yes.

**Paul:** And developers traditionally don’t isolate themselves from the MBA-type people, the executives, whoever the out group is for the traditional view of the introverted engineer.

**Edith:** Yeah, so let’s go into this for a second. I think the true value of an engineer or of anybody at a company, to be honest, is not just to be a good individual contributor, but to be part of a bigger, broader vision and help move everything forward.

If you’re working on your own project but you can’t coordinate with anybody else in terms of, say, release notes, collateral, anything else that goes along with the release, that thing is not actually valuable.

**Paul:** I would say that, in many companies and many teams, there is a place for a 10x developer and maybe multiple 10x developers. I’ve certainly worked with 10x developers before, and in any team, you generally have to recognize people’s strengths and their weaknesses.

If you have someone who’s able to put out some form of extraordinary amount of code or quality of code or whatever it is, that no one else on the team is able to do, but other people have the strengths, maybe the 10x developer’s a starter and not a finisher. You know, something along those lines.


<blockquote>Other people complement that strength. Then it can be a great thing to have on a team.</blockquote>


**Edith:** Yeah, and I’ll say I truly believe my co-founder John is like a 100x developer. I’m in complete awe of him.

**Paul:** Oh, wow.

**Edith:** But I think he has other strengths, too, besides developing. He can manage and inspire and lead an engineering team. He can go give talks.

**Paul:** There’s a funny thing I find about PhDs. John did a PhD in Stanford in static analysis.

**Edith:** Berkeley, but yeah.

**Paul:** Berkeley, oops. Sorry, John. And I find that in my personal experience, PhDs tend to fall into categories of genius or idiots. Did we talk about this on the podcast?

**Edith:** We talked about it briefly, when Martin came in. But Martin talked so fast it was kind of like a sideshoot, then we went off.

**Paul:** See, you get Martins and Johns, and I know a dozen more people like this.

**Edith:** The Dr. Biggars.

**Paul:** Yeah. And then you get people who are just complete idiots, and you wonder how they even got through college, never mind into a PhD program. And those guys get PhDs as well.

**Edith:** They don’t finish with just the master’s?

**Paul:** No, if you just keep working at it you’ll generally get your PhD. It’s kind of shocking.

**Edith:** I have a friend who, was getting his PhD in philosophy, and I was, at the time, the hard-nosed engineer.

**Paul:** A Doctor of Philosophy of Philosophy?

**Edith:** He managed to fail out of his philosophy PhD. I was kind of like, “What? I’m getting an engineering degree, which is actual work. All you have to do is sit around and think.”

**Paul:** I think that PhDs are a pure work ethic thing.

**Edith:** Maybe that was the issue.

**Paul:** If you’re lazy or you just don’t have good personal productivity, then you’re not going to finish your PhD. Those are the people who drop out as master’s, the people who do other stuff or can’t really focus.

**Edith:** Yeah, he went on to have a successful career.

**Paul:** Oh, good for him.

**Edith:** Eventually.

**Paul:** So, the personal productivity, I think, has this large bearing into whether people are 1x or 10x developers.

**Edith:** Yeah, I think you have to be very disciplined. I was just in Australia for a conference,and I, by the way, love getting out of the office and talking to actual people.

Somebody had had an idea like LaunchDarkly, which I also like, but he hadn’t executed on it. I was kind of like, “Why?” And he was like, “Oh, I’m a good starter, but not a finisher.”

And I think about, I’ll talk about myself for a second, if I want to do something, I’m incredibly disciplined to do it. I mean, I ran 100 miles but I did not finish my first three times I tried.

**Paul:** Okay. Are you saying that you’re also a good starter and not a good finisher?

**Edith:** No, I’m saying every time I didn’t finish, I’m like, “What can I improve on?” So once I got sick, I got altitude sickness, I was like, “Okay, I really want to finish this. What can I learn and go on? I’m not going to give up.”

**Paul:** I’m the opposite. I am a very, very bad finisher. I’m very, very bad at being focused, and I’m great at starting things. I’ve started dozens of things. And the thing that made me finish Circle, or I mean, it’s never finished, but you know what I mean, get somewhere with Circle, was having, essentially, an accountability buddy.

Initially that was my co-founder, and then it became customers and investors and all that sort of thing. And then it got to a point where like, okay, there’s some form of accountability. But without that, if I sit and try to work on something myself without any co-founder, partner, accountability buddy, whatever, I get nowhere.

**Edith:** Well, I think that gets down to intrinsic versus some external motivation.

**Paul:** How so?

**Edith:** Like whether you’re doing something because of the internal motivation and the pleasure that it gives yourself, versus the fear of people mocking you or judging you by not finishing.

**Paul:** Yeah, so I definitely work on things that I have the intrinsic motivation. And then when I lose that, there needs to be a push.

**Edith:** Actually, you gave me a push once. I was running Western States 100 and it was really bad. I was throwing up around mile 40 and I thought about quitting.

**Paul:** So 60 miles to go.

**Edith:** Yeah. A lot of people were dropping at 40; it was a hot day. And then I was like, “I don’t want to write the email, that I dropped.”

**Paul:** Oh yeah, that’s a very useful one.

**Edith:** Yeah, because I thought about the email, and I was like, “I don’t want to send that email.”

**Paul:** A thing that I used to use for motivation was “My startup failed because ‘X.'”

**Edith:** Oh yeah, that’s a good one.

**Paul:** My start-up failed because I didn’t know how to write the email to the investor, or because I couldn’t get around to asking for the money, or because I wasn’t able to make the offer to the person in the time that they needed, or all that jazz.

**Edith:** Yeah, I think, to go back to running, I think it’s very valuable. I’m like, “Okay, I can run 100 miles. I can write this email.” It’s funny, my coach is Ann Trason, who set the world record, literally, for every distance between 50k and 100 miles. Fast lady.

**Paul:** Right, yeah, and no doubt disciplined, and all that jazz.

**Edith:** And she’s like, “Edith, how do you do this CEO thing? Isn’t it hard?” I’m like, “Ann, running 100 miles in 14 hours is hard. Writing a couple of emails? Not that hard.”

**Paul:** Right. It’s interesting. We were talking about the starters and the people who are unable to finish. But clearly, in a team where they’re combined with finishers or combined with people who can provide the right kind of extrinsic motivation or the right kind of push or the right kind of support or whatever that is, clearly can be much, much more productive than if they were just starters by themselves.

**Edith:** Absolutely. Not to sound grandiose, but that’s the basis of human civilization.

**Paul:** Right, yeah, absolutely.

**Edith:** Instead of one person going off and hunting game, if you get 20 people together, maybe you could herd your game and get more.

**Paul:** The thing that I like about this is that it’s filling in for other people’s weaknesses.

**Edith:** And recognizing that you might have weaknesses that other people can fill.

**Paul:** Exactly, yeah. There is sort of a special type of 10x developer. Let’s say the “folklore” 10x developer. And these people actually exist. Richard Stallman is one example of this. And the story is that he went away to write a compiler, and 30 days later he had a working compiler.

**Edith:** Like I said, put the developer in the room with some Red Bull…

**Paul:** Exactly. But the thing is that Stallman must’ve been incredibly disciplined to get this done. The story was he was working 16 hours a day and sleeping under his desk, and that sort of thing.

Frankly, if you put me in a room and I was working 16 hours a day, I’m not sure I’d come out with anything. Like, 30 days later, I’m not sure if you’d have a compiler, and I know how to write compilers.

**Edith:** Would you come out with a couple of bald patches?

**Paul:** I think I’d come out with a lot of Hacker News read and inbox zero.

**Edith:** I do think you have to be disciplined. When I [bike cross-country](http://firstround.com/review/startups-software-development-and-the-art-of-bicycle-maintenance/), I set myself a goal of biking a certain amount of hours every day. So it’s like, “Okay, this is my job now.” So I’d bike four hours and five hours and six hours before I’d give myself a break.

**Paul:** But biking is thing that, you don’t really get distracted when you’re biking by a shiny thing.

**Edith:** Oh, you do all the time.

**Paul:** Oh, really?

**Edith:** You’re like, “Oh, there’s a historical marker. Oh, maybe I should stop and check my email. Oh, I’m a little hungry. Oh, that place looks good. Maybe I should go get a soda.”

**Paul:** No, okay, that’s interesting.

**Edith:** I mean, there’s every reason in the world to stop.

**Paul:** Right. “My legs are a little sore.” Any reason will do.

**Edith:** Yeah.

**Paul:** Okay. I mean, yeah, okay. Well then, it’s exactly the same when you’re developing.There’s a shiny little notification box. I think I mentioned in a previous podcast, I have to turn off all my notifications.

**Edith:** Yeah, I should really start doing that. I mean, I think HipChat and Slack…

**Paul:** Check it every hour if you need to, and get back to people. But the whole point of those things is that they’re asynchronous.

**Edith:** Yeah, it’s funny, I hate it when people do @alls or @here in Slack. I’ve been in some epic flame wars because I think Slack is still pretty new, and people are always like, “Well, my @all is important.”

**Paul:** “@all, there are donuts in the kitchen.” That actually is an important one.


<blockquote>At every company, regardless of the number of people, if there’s 10,000 people behind @all and you say there’s donuts in the kitchen, everyone’s like, ‘Okay, fair enough.’</blockquote>


**Edith:** I meant more that I’m on a lot, I’d say, loosely-affiliated lists, like, for my old accelerator. And it’ll be like, “@all, please go upvote this.” And it’s just like, no.

**Paul:** No, fuck off, yeah. The @all is for…

**Edith:** Acts of God.

**Paul:** Yeah. “@all, there is an earthquake. Read this quickly in the next 30 seconds before it hits.”

**Edith:** Yeah, and then the flame war is like, “It’s very important to me that you go upvote my product or do this,” and it’s like, no.

**Paul:** That should be @all’ed into something, into some set of people who really give a shit about you personally. If you have your own personal Slack and everyone on the Slack is into you, that’s the perfect place to @all the upvote.

**Edith:** Is there a Paul Slack somewhere?

**Paul:** No, there’s not.

**Edith:** I think the general standard is, “Does everybody get more value out of this than I get out of putting it?” Like, the donuts here? Yes, everybody gets more value than I get.

**Paul:** Unless they get to the kitchen and the donuts are gone. Then it’s this negative value where you’ve taken someone out of their coding bubble. Because obviously if you see the word “donuts,” you’re like, “Okay, the compiler’s not that important.”

**Edith:** It’s a Homer Simpson-esque response.

**Paul:** It’s built-in.

**Edith:** It’s Pavlovian.

**Paul:** Yeah, the caveman.

**Edith:** Simpsonian. Do they have The Simpsons in Ireland?

**Paul:** Yes. No, it’s a proper first-world country.

**Edith:** Let’s get back to productivity.

**Paul:** I could not sit in a room and produce a compiler. And I see these bootcamp grads.People complain about boot camp grads and that sort of thing, and maybe in another episode or another time I’ll say why I think that is and how I think it’s mistaken.

But in a boot camp, the thing that you’re doing is you’re literally, “Today, we are writing a Twitter. At the start of the day you will have nothing. Empty project or you can clone the last one, whatever the hell it takes.And at the end of the day, you’ll have a working Twitter.”

If you put me in a room and you ask me to make a working Twitter, I’d be investigating six different web servers and, “What’s the right language to write a Twitter in? What’s the right tool for this job?”

It’s like, okay, well, I guess you’re supposed to write it in Erlang. I don’t know Erlang yet, so let me go through a tutorial on Erlang and get good at Erlang. And then I don’t really like Erlang.

**Edith:** And then you come up with Rust.

**Paul:** Exactly, right. So you end up in this,I would personally end up in this, it’s essentially a yak shave, right?


<blockquote>A perfect yak shave, where at the end of it I’ve got some half-made sweaters and no actual product coming out of it.</blockquote>


**Edith:** And the yak is kind of still around.

**Paul:** I’m not sure where the yak goes in the analogy. Is it in the metaphor?

**Edith:** I was just teasing you.

**Paul:** So there was this, I think it was called “180 Websites in 180 Days” or something like that. It was a project by Jennifer Dewalt, and she didn’t know how to code. And she said, “I’m going to make 180 websites in 180 days.” And she included a blog post.

Every day she wrote a blog post on what she had produced that day. And you can see it on the internet if you Google for it. And on day one, it was fairly rudimentary. It’s like, “I’m getting forms to work.” I don’t know exactly. And by day 30, there’s real things going on. And by day 180, it’s, you know, proper stuff. But that’s discipline I don’t have.

**Edith:** Yeah, it’s discipline that every day you’re going to get a little bit better and a little bit better.

**Paul:** But just the discipline to keep doing it is insane. It’s like, how do you not take day 31 off? It’s like, “Well, I’m going to sit in my pajamas and watch The Wire from start to finish.”

**Edith:** Well, I’ll say two things. When I bike cross-country, I did take every seventh day off very deliberately, because you get burnt out.

**Paul:** Right, even God got burnt out.

**Edith:** Yeah. So I took the seventh day off and I wouldn’t bike. And that was good because I’d read a lot of journals of people who didn’t take days off and by the time they got 20 days in, they’d drop out.

**Paul:** Right. Maybe she took days off, but I don’t actually know.

**Edith:** Yeah, so you have to have a day off. But I remember, I got about halfway through, and I had been keeping a blog. This couple rode up on their bikes to hang out with me, which was pretty cool.

**Paul:** Okay.

**Edith:** And they said they liked biking, but they didn’t think they could bike cross-country because everybody they saw coming through looks so fit and so with it. And I said, “Everybody you see who comes this far…”

**Paul:** Right, has been biking for three months or something.

**Edith:** Has gone halfway across the United States. Because this was in Rugby, North Dakota. So, you did not see me two days in.

**Paul:** When you were dying and falling apart.

**Edith:** I was wearing canvas tennis shoes.

**Paul:** So perhaps what you’re saying is that there’s many, many people who started 180 websites in 180 days, got five days in; we’re only seeing the one who came out the other side.

**Edith:** No, I was saying it more positively.


<blockquote>You have to give yourself permission to be bad at the beginning of anything.</blockquote>


**Paul:** Yeah, fair enough.

**Edith:** You have to give yourself permission to be like, “Okay, I’m going to get better every day I do this.”

**Paul:** It’s very easy to say, like, “Imagine if I had been as good as Stallman,” or whatever. “I’m 34. What could I have accomplished if I had that sort of discipline or ability? Or if I’d started coding five years earlier?” Or that sort of thing. Yeah, you can’t do that. The past is gone. You can’t fix it, so just start today and look forward.

**Edith:** Yeah, I think about, “What if I’d started a company in my 20s?” But I’m like, you can’t. That door is not open anymore.

**Paul:** Yep.

**Edith:** I think people don’t give themselves enough credit for how much better they get as they get older.

**Paul:** Yep. My old one is, “What if I had pivoted my failed Y Combinator company into a developer tools company like Paul Graham told me to? What would’ve happened then?” And the answer actually is that was slightly too early for dev tools and slightly too early for it to be a really good-funding market. So it’d probably have died.

**Edith:** Yeah. But maybe,


<blockquote>I mean, you can’t A/B test life.</blockquote>


**Paul:** Can you feature flag life?

**Edith:** I haven’t found the right library.

**Paul:** I’ve tried various different personal productivity things. And there’s one that I was telling you about earlier called the [Pomodoro method](https://en.wikipedia.org/wiki/Pomodoro_Technique). And so the idea here is that you have a timer, and I think the word Pomodoro is picked for no particularly good reason. It’s a 25 minute timer, and then you take a five minute break.

**Edith:** Oh yeah, I do that myself. I’ll set my iPhone and I’ll do something. Because that way it gives you the discipline to get it done with the knowledge that there’s a break coming up.

**Paul:** In the Pomodoro method, I think the idea is that maybe you count the number of Pomodoro that you get in it, that you do in a day. So the idea is like, “Oh, today was a six-Pomodoro day. Today was an eight-Pomodoro day.” You’re able to measure how productive you are, and then you have a number to optimize.

**Edith:** I use it when there’s something unpleasant I don’t want to do. Because I’m like, “Okay, I’ll do this.” Usually it’s cleaning up my house. And sometimes what I find is, once I start doing it, I get in the moment and I do much longer than the actual time given.

**Paul:** Have you heard of structured procrastination?

**Edith:** Tell me more.

**Paul:** It was a blog post written by, maybe, a Berkeley professor, and its title is “Structured Procrastination.” And basically he arranges things so that he works on the second-most important thing.

So whatever’s the most important thing, there’s a deadline, this grading is due, whatever, he can never motivate himself to work on that. But he can motivate himself to work on anything else. And so he uses that to do the other stuff that he’s supposed to do.

**Edith:** Interesting. But what about the actual stuff?

**Paul:** Then you just need something of a higher priority, and then the second-place thing starts to look more compelling.

**Edith:** So, how do the grades ever get done, then?

**Paul:** I mean, I don’t know. Maybe his anniversary dinner comes up, and then he’s like, “Oh shit, I better get these grades done.”

**Edith:** “Sorry, honey.”

**Paul:** Right, exactly.

**Edith:** I find it sad that he’s not looking forward to his anniversary dinner.

**Paul:** I mean, I don’t want to put words in his mouth. I’ve no idea whether he’s even married.

**Edith:** I think it’s funny, because we’ve been doing this show for almost a year now…

**Paul:** God, yeah.

**Edith:** Time goes by. So we’ve talked a lot about productivity and personal productivity. I think the danger with the 10x theory is that you can have people who are 10x productive and then are actually very destructive.

**Paul:** Okay. Yeah, I know, I totally agree there.

**Edith:** What part do you agree with?

**Paul:** There’s assholes everywhere. I feel that the culture amongst engineers and tech is often built from the folklore of open source.


<blockquote>Way back in the history, you have people who are assholes, basically. And it correlates super strongly to the 10x developer.</blockquote>


Linus Torvalds is one example. I think Stallman is another example of people who lack certain social graces, and that becomes promoted as the way to be that person is to lack the social grace. It’s like if you wanted to be Jobs and you started wearing turtlenecks.

**Edith:** Yeah, it’s cargo cult coding.

**Paul:** Yeah, yeah. It’s cargo cult assholery that developers put on.

**Edith:** And it’s ultimately very destructive.

**Paul:** Oh, yeah.

**Edith:** Another company I worked with, there was somebody who was kind of the, “Oh, this person is a genius. He gets away with being a jerk because he’s a genius.” And it’s funny, because I’m still friends with some of those people at this company, and he left about 10 years ago. And they’ve said now, looking back after he left, everybody else got a lot more done.

**Paul:** Oh, wow, yeah.

**Edith:** At the time it was like, “Oh, this person is a linchpin and nothing will get done once he leaves.” And after he left, everybody just, the way they put it was he was a redwood tree stunting the growth of everybody.

**Paul:** Yeah. Everyone else is the shrubs in this metaphor?

**Edith:** Yeah, or it was just like, he would put people down, he would say, “That’s not good enough.”

**Paul:** I mentioned last week, the Rand Fishkin model of who to hire or whether to fire someone. If someone is culturally bad, you fire them even if they are a 10x developer.

**Edith:** Yeah. And then there’s something even more destructive. There’s the cowboy boss.

**Paul:** What’s a cowboy boss?

**Edith:** “Everybody who works for me is so stupid.”

**Paul:** Oh, yeah.

**Edith:** “Look at me saving the day.” And the reason why this works is because the cowboy boss’ managers are like, “Wow, we wouldn’t have anything if this guy…” And I say guy, it could be a woman, one that’s always saving the day. And it’s like, “Well, why are you always…?”

**Paul:** How did they end up in a situation where they have to save the day a lot?

**Edith:** Yeah, and “Why is your team so incompetent?”

**Paul:** Right. Because they’re responsible for hiring them, presumably, and for managing them and motivating them.

**Edith:** But his M.O. was, “God, everything is so messed up. Luckily I’m here to fix it all.”

**Paul:** Right. Oh, wow.

**Edith:** And really it was like, “Okay, everything is messed up because you’re not being a good leader.”

**Paul:** I’m getting flashbacks, too. The painful Nam-like flashbacks of the times where I had to swoop in to save something, and it was always because I wasn’t being a good leader: the thing that we absolutely must not ship. Or we can’t ship it in this state, or something like that. And that’s the sort of thing where if you swoop in at the last minute, that means that someone has put tens of hours into it.

**Edith:** Or hundreds.

**Paul:** Or hundreds, yeah. And then you’re coming in at the end and you’re saying, “Yeah, no, we’re not doing this.” Whereas if a much smaller amount of work had been done at the start, your product direction’s set, visions, alignments, all that management jazz that you don’t like to think is really important as an engineer.

But as I became a better manager and a better team player in the team, apart from actually writing code, it became obvious that you can’t just swoop in and do that. But I think that this is something that’s, again, encouraged by the open-source movement. Because the open-source movement has a heavy emphasis on code review, right?

**Edith:** Which is, it’s too late.

**Paul:** Exactly, it’s too late.

**Edith:** And let me be clear about what I mean by “too late.” It’s too late to say, “This doesn’t fit into the direction we want the product to go.”

**Paul:** Right, exactly. GitHub has built-in pull requests. There’s no built-in road map. There’s no built-in product direction. You never go to a Git repository where there’s a statement. I mean, you occasionally see roadmaps on bigger projects, but only on really well-run, bigger projects.

There’s no, “We want pull requests that do this.” Mostly, people have bugs in their issue tracker that people don’t really triage and say, “We’d actually accept a bug on this.” So the thing that’s encouraged is you arrive with code. And in fact, there’s a saying that people use, that’s like, “Code talks, ideas walk,” or something along those lines. I’m butchering that.

**Edith:** I think the ideal and what actually happens are very different. I think the idea is that, to go back to biology, that it’s basically something that’s evolving on its own, that you don’t need direction.

**Paul:** Yep.

**Edith:** And so people are like, “Why do we need a roadmap? The good code will just arrive.”

**Paul:** Well, it’s the bazaar. We’re not making a cathedral here.

**Edith:** And then what happens is the code arrives, and people are like…

**Paul:** I don’t really know whether this fits into the something, something.

**Edith:** What’s happening is that there’s an unstated vision.

**Paul:** There’s an unstated vision, yes.

**Edith:** So, there’s a vision and there’s a road map, it’s just not written down anywhere.

**Paul:** And when someone comes in with a new vision, a new direction…

**Edith:** And they’ve implemented it.

**Paul:** Yes, the code is done. I made a pull request against Atom the other day, the Atom editor. And it’s a new direction from where they were going with this particular component, but I should’ve known. On this components, there were 42 open pull requests.

**Edith:** Wow.

**Paul:** And mine got tagged about two days later as “needs review.” And we’re now five days, six days later, and no comments, no one’s looked at it. And it’s like, I should’ve known. I should’ve known, by the state of the rest of the pull requests, that this was going to go on deaf ears.

**Edith:** I think this comes back to, there’s always a process and a vision and a roadmap, it’s whether or not it’s explicitly stated or written down somewhere.

**Paul:** Right.

**Edith:** Obviously the maintainers of the project have some vision that is not prioritized in that area.

**Paul:** Yeah. Presumably, that area is done in some way.

**Edith:** I think it’s very frustrating for everybody.

**Paul:**


<blockquote>There’s nothing that turns people away more than: they arrive, they contribute some code, and then nothing happens.</blockquote>


I’ve been the maintainer of several abandoned projects, right? And someone comes in three years after I wrote any code on it and has a contribution of some kind. And I don’t remember that code.

**Edith:** You’re like, “My name is on this project?”

**Paul:** Yeah, “I guess I wrote this? I must have? I’ve written a lot of things.” And it’s worse when it’s something arcane like the build system. And it’s like, I want to make this build. I’ve got a couple pull requests like, “Make a build on CentOS,” or something like that. I don’t have CentOS, I don’t know anything about CentOS, and I don’t know if the code that they’re providing me is going to achieve anything.

Is it going to achieve anything good? Maybe there’s bad things here, I don’t really know. What do you do with that? And the vast majority of projects that they ignore, I saw a couple of projects where they default-accept it. “You make a pull request, we’ll accept it.”

Okay, so we’ve gotten quite a bit off topic. Should we just trail off awkwardly here?

**Edith:** That would be your usual M.O. because you’re not a finisher.

**Paul:** I think that’s why.

**Edith:** Yeah, let’s pick this on the next episode.

**Paul:** All right.


