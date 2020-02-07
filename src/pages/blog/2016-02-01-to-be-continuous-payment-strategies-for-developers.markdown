---
author: andreaech
comments: false
date: 2016-02-01 01:41:25+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-payment-strategies-for-developers/
slug: to-be-continuous-payment-strategies-for-developers
title: 'To Be Continuous: Payment Strategies for Developers'
wordpress_id: 774
categories:
- To Be Continuous
tags:
- coding
- continuous delivery
- Dave McClure
- developer
- Heartbleed
- Linus Torvalds
- open source software
- opensource
---

In this episode Edith and Paul talk about the clash in OSS between developers looking to get paid and software companies looking for things for free. This is episode #12 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->This episode of To Be Continuous, brought to you by Heavybit and hosted by Paul Biggar of CircleCI and Edith Harbaugh of LaunchDarkly. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.


TRANSCRIPT

**Edith: **So Paul, what do you like about open source?

**Paul:** So I guess that depends on whether we’re talking about writing open source or using open sources as part of a company. Writing open source, I like just having all my code out there.

And I’ll do that as often as possible. Anytime I start a little bit of code, a little library, I’m looking to open-source it and have a readme and have it out there for other people to use. I had a very long discussion, which I eventually won, about the …

**Edith: **I like the way you think of all discussions as win or loss.

**Paul:** Well, yeah, yeah. It was more on the argumentative side of discussion. But with the other co-authors of the PHP compiler I wrote, which was originally GPL. And I argued very strongly that I actually don’t care if people give back, I just want people using my software. So to me, open source is a way of having people using my software.

**Edith: **That’s really interesting. So, I liked what you said at the beginning about, like, you liked open source ’cause it meant getting stuff out sooner. ‘Cause I’m a big fan of that.

Like, I always say you should just publish stuff. Like, my co-founder John said something really good at our team meeting last week. He’s like, if it’s 90 percent done and you don’t publish it, it’s actually 0 percent done.

**Paul:** It’s 0 percent done, yeah.

**Edith: **Yeah, and that’s a hard lesson, ’cause you always try for perfection lately.

**Paul:** Right, right, right. Well, I think there’s also some really hard downsides about that. So when you publish something before it’s ready, before you really —

**Edith: **Well, ready.

**Paul: **Well, there’s ready ready, but let’s say ready is, let’s say you publish it before you clarify what the software is to do, or the values or the mission of the software.

And then you get contributors who are saying, ‘Oh, this is great, but I really want it to do this other thing,’ and you’re like, ‘Well, that’s not exactly what I was going for here.’

**Edith: **Well, I’d say most open source projects are so lucky as to get contributors at all.

**Paul: **True, true, true. So I’ll give you an example. I wrote the V8 bindings for Closure. So a binding that allows you to write JavaScript and run it in Closure. And I did that for a purely selfish thing, for another, for a nascent pipeline that I was building called Stefan.

And then people came along and they wanted to do other things with it. They’re like, ‘Okay, let’s add a binding for this other thing.’ I was like—

**Edith: **Well, that’s kind of like a pivot.

**Paul: **It is, it is, but I really was not interested in it.

I’d rather someone took it over, took over the project and actually ran with it where they wanted to go, and I can stick on the old version, or I can see if the new version solves it for me, but I wasn’t interested in becoming a maintainer in this thing, I was interested in solving my itch.

And I just happened to open-source it, because I felt it might be useful for other people.

**Edith: **So Paul, I hate to say this, but I agree with you.

**Paul: **No, not again.

**Edith:** Not again.  No, I mean, I think what you said is exactly right, that you said, I did this for this reason, and I want somebody else to take it over now.


<blockquote>I think where open source runs into issues where people are like, it’s only this purpose and you can’t do anything with it besides my original thing.</blockquote>


**Paul: **So you think that’s a good thing, or you think that’s a problem? Or it causes problems in the community?

**Edith:** I think open source is so misused for so many different purposes that it’s hard to even say. Like, so, in Europe, people say open source is good because it means free software.

**Paul:** Libre or gratuit?

**Edith: **I’m sorry?

**Paul:** Free as in beer or free as in, what’s the other side of that?

**Edith: **There’s no such thing as a free lunch, is that what you’re talking about?

**Paul:** No no no, like people say open source software, it’s like free-as-in-beer software, as in software that has no cost vs. software that has no price tag vs. software that is, they use the French word libre for—

**Edith: **Oh yeah, that’s what I was talking about. So I remember I went to Europe in, I think it was like 2004 or 2005, and they just had this big push for open source, ’cause they thought it meant free.

**Paul: **Oh, this is like the German government and that sort of thing.

**Edith: ** So literally like, so I went to this customer and they’re like, ‘So it doesn’t cost you any more to give us an extra copy.’ So why shouldn’t just everything be free?

**Paul: **Oh, right, yeah, well.

**Edith: **And so I think open source has been misused by many businesses who think of it as just like, hey, we get all these developers working for free.

**Paul:** So I think that the main advantage to business of open source is not that it’s free, but it’s that it’s low-risk.

**Edith: **Low-risk?

**Paul:** Lower risk. So it removes—

**Edith: **Ah, I would argue—

**Paul: **Well, so, what I mean is that it removes a certain element of risk from it. So there’s, Joss Belsky wrote a blog post about how you shouldn’t use, I think it was a database that you didn’t have the source code to.

**Edith: **Well, so I’ll argue the reverse, and I think open source is sometimes more risky. ‘Cause I talk to people now who are like, nobody’s maintained this open source project that I depend on.

**Paul:** Right, right, right. But that vs. a closed-source version.

**Edith: **Well, so the opposite risk is that you end up that you are responsible for this open source project, and you’re like, well, actually, I just wanted to use this thing. I didn’t want to do the maintaining.

**Paul:** So absolutely, you don’t wanna end up the only person that, well, it’s actually fine to end up the only person which is using this thing.

**Edith: **Well, no, it’s not—

**Paul:** It’s not ideal.

**Edith: **It’s that many people are using it, but nobody is paying money, and then you’re stuck.

**Paul:** Because no one is maintaining it.

**Edith: **No one is maintaining it, and you depend on it.

**Paul:** Right, so, but imagine that no one maintained it and all that you could get was like a binary block. That’s the real problem. The company goes out of business. You have random database version seven, the binary, that only runs on 32-bit, that you’re maintaining, like, companies are literally maintaining COBOL—

Fortran things from 30 years ago. It sits in a machine, you can’t touch it, you can’t fix it, you can’t apply security updates to it.

**Edith: **Yeah, that’s fair. So [Tim Chou](https://twitter.com/timothychou?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor), who is, he’s an awesome guy, he was early Oracle, he said that people don’t buy, when they buy software, they’re not buying it what it is today.

**Paul: **Right.

**Edith: **‘Cause basically, anything that you’re buying today, you could just hire 20 engineers that could build it. What they’re buying—

**Paul: **Yeah, you could just copy it.

**Edith: **Yeah, what they’re buying is the promise of stability, that it will continue to be maintained. That there is a vision. And that’s actually, I went over to a big customer who won’t let us use their name yet, but they said they love LaunchDarkly because we thought every day about feature flags.

**Paul:** Right, right, exactly. This is why people buy SAS, because, because people think all day about CI, about QA as a service, about queues, or whatever it is from various Heavybit companies that I just shilled for, they’re, you can probably figure out yourself which ones they are by looking at the homepage.

**Edith: **Well, and Paul, by the way, thank you very much for wearing your LaunchDarkly t-shirt today. It looks very handsome.

**Paul: **The, I definitely agree that the benefit of the thing is that you use it every day. But you can do that with open source as well. You can have open source software that, so, for example, our front end is open-sourced.

**Edith: **Oh, I’m absolutely a fan of open source. Like, we use open source every day. Our client libraries are open source. I’m not saying that it’s, I don’t think it’s a religious thing vs. open source vs. not, I just think that many times people assume open source is something that it’s not.

**Paul: **Yeah, fair enough, fair enough.

**Edith: **I mean that if you have open source, that just means that developers spring out of the ground willing and happy to update your software every day.

**Paul:** A mixed blessing, definitely. If it even happens.

**Edith: **Like, I remember, so I remember when Sun, so I used to work on a, I used to be at Epicentric, and we had a portal server, and we were killing Sun. Absolutely killing Sun. And this was in 2003, so what they said is, ‘Oh, we’re gonna make our portal server open source.’

**Paul:** Right.

**Edith: **And so somehow this whole thing, we’re like, everything will be open source, and like, developers will spring out of the ground, and it’s like, well, no, developers, they don’t wake up every day like, ‘I’m gonna work on your thing.’

**Paul: **Right, right. They will if it’s sexy or exciting. There’s lots of developers who are showing up at Mozilla just to contribute. And in fact, they’ve fought through incredibly large hurdles to contribute to Mozilla’s software.

**Edith: **Well, that’s fascinating, ’cause I see so often the reverse, where people, so what do you think about Mozilla made people want to contribute?

**Paul:** I think the fact that it was an open-source-first company, and that it was a nonprofit, and it was all about the free and the open web and that sort of thing. Also, people had had very good experiences with Firefox for, like, a decade at this point by the time I was there. Well, maybe seven years, but, you know.

**Edith: **It’s fascinating, ’cause I went to dinner last night with the CEO of MySQL, and I don’t know if I should say this, but he said—

**Paul: **This is [Marten Mickos](https://twitter.com/martenmickos?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor)?

**Edith: **Yep. So he gave a talk—

**Paul: **He has a new startup?

**Edith:** Called HackerOne?

**Paul:** Oh, he joined HackerOne.

**Edith: **Yeah, he’s the new CEO. So the dinner was kind of like a debutante ball for him.

**Paul: **Nice, nice.

**Edith: **So what he said was that somebody had asked him flat out how much of MySQL was actually from contributors. He said 1 percent.

**Paul: **Seems about right.

**Edith: **He said the open source was more just a branding thing. Like it wasn’t actually like a productivity thing. It was more just a branding thing.

**Paul: **So you have this in Mozilla as well, that any time that there’s a really avid contributor, that Mozilla would hire them.

**Edith: **Yeah, that’s what he said.

**Paul: **Right, and if Mozilla didn’t hire them, very often they stopped being a contributor. Like, it was a real sort of a double-edged sword.

So someone who did it for six months, they were doing it for the love of the game. They weren’t doing it to be hired at, at least I think for the most part, they weren’t doing it to be hired at Mozilla. And then six months in, someone’s like, well, you know, you’re doing a really great job, wouldn’t you love to work on this full-time? They’re like, yeah, that’s so exciting. They’re flown out for an interview. And then it’s like, you know, actually, I don’t think so.

**Edith: **Wait, they didn’t wanna work for Mozilla, or Mozilla didn’t wanna hire them?

**Paul:** Mozilla didn’t wanna hire them. I mean, this isn’t a particular case. But you know, some subset of people, Mozilla didn’t wanna hire. And then what happens? Well, you kind of don’t wanna keep contributing to the company that just told you to f*ck off.

**Edith: **Yeah, I mean, it’s so true. I mean, I think there’s a very human thing about volunteering.

**Paul: **Right, right.

**Edith: **I volunteer, I was the moderator for a long time for the Lean Startup Circle, and somebody new came on, and they’re like, yeah, I’d love to raise some money so that we can get paid, and I’m like, they cannot afford to pay me.

Like, I don’t do this to get paid, ’cause—

**Paul: **Yeah, it’s like, it’s an altruism that people are trying to do.

**Edith: **Yeah, I was contributing like 10 to 15 hours a week, and at my going rate, it’s not, it’s like, I’m not doing this to get paid, I’m doing it ’cause I like giving back.

**Paul:** So there’s this thing that we were talking about earlier, about the current discussion around people getting paid in open source.

**Edith: **Yeah, and I think a lot of what has fueled open source is the whole 20 percent time. Like, that Google will give their engineers 20 percent for open source, and I know that other big companies, like Twitter and so on, do that too. So these people are, in essence, getting paid.

**Paul: **Right, right, there’s a, in most companies, in most startups at least, there’s an unspoken rule that you’re expected to contribute to the libraries that are in your application, and that sort of thing. If you’re spending time upstreaming paths that you’ve deployed, that’s work.

**Edith:** Yeah, so I think we’re agreeing, which, I thought we agreed that we were not gonna agree. It’s funny, ’cause I’m Twitter friends with a guy I’ve never met, who’s, he started Django, and right now what he tweets a lot about is—

**Paul:** This is [Jacob Kaplan-Moss](https://jacobian.org/)?

**Edith: **Yeah.

**Paul:** Okay.

**Edith: **That people are working their nights and weekends, and contributing to open source, and then just, people are kind of, for lack of a better word, jerks. People are like—

**Paul:** People are jerks.

**Edith: **Yeah, like—

**Paul:** Even when you’re paid, people are jerks.

**Edith: **But it’s more aggravating.

**Paul: **Right, right, because you’re doing it for free, or whatever.

**Edith: **Yeah, and so people will, like, they’ll be like, ‘I have this pull request and it’s been open for two hours. Why haven’t you reviewed it?’

**Paul:** Right, right. I mean, we get the exact same thing. We get customers who email us, or more often it’s the people who get, who are using the free version, who send us a support request and then, 30 minutes later they’re on Twitter going, I can’t believe Circle hasn’t solved my problem yet. It’s been 30 minutes.

**Edith: **What do you think drives that?

**Paul:** There’s a pattern across the population in general, that people are jerks.

Paul :     Humankind is not really the greatest people in ...

Edith:     Paul, I think people are the kindest people on the planet.

Paul :     There are lots of people out there, and many, many of them are dicks. If you have a bell curve of the people, all of the people who are in the dick category are on the internet, and they are the ones who are going to Twitter to tell you what an awful person you are for not having responded to their thing in 2 hours, or in half an hour, whatever it is.

Edith:     On the other hand, I think most people are honestly very helpful.

Paul :     I don't mean to come across as a curmudgeon for all of mankind.

Edith:     Too late.

Paul :     It's most of a statistical argument. There are a lot of people out there who get off on the idea of Twitter outrage or whatever.

Edith:     That goes back to the founder of Linux, where he's like, "I'm a jerk because I have to be a jerk."

Paul :     Right. There is ... I think one of the major problems that afflicts our industry is people who believe that the open source development model is the right way for people to develop software.

Edith:     I think it's also something a little bit larger, which is that people see people who are jerks who are successful, and ...

Paul :     People look at a successful open source project and they think that this is a thing to be emulated. For example, Linus Torvalds is just an unmitigated asshole. I've never met the guy, so I'm basing this on the internet. I don't think he would disagree with me.

Edith:     It's funny, because my mom was recognized at the same banquet as him, because they both contribute a lot to IEEE. I was kind of like, "That's kind of a mixed blessing, Mom."

Paul :     Yeah. Other people look at him being an asshole and they say, "Well, you know, I want to be an asshole."

Edith:     I see this, you confuse correlation versus causation.

Paul :     Right.

Edith:     You're like, is he successful because he's an asshole, or is he an asshole because he's successful?

Paul :     There's also ... A lot of people who contribute to open source are younger, don't have life responsibilities just yet, so they have lots of time to give. I think that there's a tendency, and I recognize this in my younger self as well, to be an asshole on the internet when you just kind of haven't learned to treat people well. An affliction of people in their teens and early to mid-20s.

Edith:     Paul, you're always spectacularly polite.

Paul :     Right, but you're meeting Paul of 34, not Paul of 24.

Edith:     Well, I knew you when you were 33.

Paul :     The Paul of 24, I think, would have written long rants about how right he was and how that was really important, that I was right and that everyone recognize that I was right.

Edith:     Let's loop back to the beginning where you said you'd won an argument. I don't ever think you really win in the argument. All you really do is ...

Paul :     True, true. I actually agree with that. I'm kind of being a little bit facetious on this for the sake of dramatic storytelling.



Edith:     I think it is true. I look back at how I was when I was 22. I was a bomb thrower. I don't know if I would have liked myself.

Paul :     Right. This is the problem. I mean, this is one of the many problems. A lot of the people, they see a good example in Linus, who clearly never grew out of his 22 year old self. They are themselves, 22 and full of ... What's the word? Full of ...

Edith:     Vim and vigor?

Paul :     Yeah, there we go. Spit and vigor. One of those things. They have a chip on their shoulder. They look around at all the software and they're like, "This software is shit. I'm going to write my own software."

Edith:     Paul, I thought the Irish said it “shite”.

Paul :     Sometimes. Sometimes.

Edith:     I feel like ...

Paul :     The person that I'm imagining in this story isn't Irish, so I'm putting their words in the words that they would use. You make a pull request, and 2 hours later ...

Edith:     Nobody's responded.

Paul :     What are they doing?

Edith:     What are they doing? How dare they?

Paul :     It's 3am. Are they not up working on their software?

Edith:     Oh my god. This was me. I was moderating this email list, and it was a global list. We put this policy on that if you're a first time contributor, you had to be moderated. People would send me the angriest emails.

Paul :     About being moderated.

Edith:     They're like, "How come you haven't responded?" I'm like, "Dude, I'm in San Francisco. I was asleep."

Paul :     I just go straight to archive, or sometimes mark as found. I feel that ... People feel that you have a responsibility to them, because you're a person on the internet. I'm perfectly happy with the idea. Sometimes I'll email someone famous, or someone who gets a lot of email. I'm not expecting a reply.

Edith:     Oh, no.

Paul :     I mean, I hope that they will reply. I try to write things in the nicest possible way so that I will get a reply, but people are busy.

Edith:     I was so shocked. David McClure is one of our investors. He literally has this auto responder like, 'I'm under a large rock. I never read any emails.'

Paul :     Right. There we go, right? He's a guy who's doing shit. He doesn't have time to respond.

Edith:     I was shocked. I sent out our monthly investor update, and he responded. I was like, "Oh."

Paul :     I'm sure he filters it into the actual important shit versus the things people send me on the internet.

Edith:     No, he responded. Our engineer just had a baby. He wrote back and he's like, "Congrats on your baby and your month over month revenue growth." I was like, "Oh my God, Dave reads our emails."

Paul :     Nice. When I was getting Dave to invest, I literally had to text him. I texted him again, and then I called him.

Edith:     Then you showed up at his door with flowers?

Paul :     It was 6pm on a Sunday. It was a very unreasonable time to call someone, but I had a $50K space for him. I was determined that this was going to happen, and it did in the end.

Edith:     It was funny, because I just sent him the update as a courtesy, because I assume he's not going to read it, but he read it. He said 'congrats' to our engineer who had a baby, and he's like, "Great job. Love your month over month growth." I was like, “gasp.”

Paul :     People are busy on the internet, and people assume that they have a right to their time.

Edith:     That's so true. That's kind of my push back against stuff like HipChat and Slack. I think there's already starting to be a little bit of a backlash.

Paul :     I don't know what you're talking about.

Edith:     People are like, "It's great. I could chat anybody anytime on Slack or HipChat, and they'll respond." It's like, great, you're responding instantly and you're not doing something else.

Paul :     Right, right, right. Yeah. I think people should turn their notifications off. This idea of an instant reply is a terrible, terrible idea.

Edith:     Why do you think it's terrible?

Paul :     Coding is an activity that requires concentration. The ADD set of ways that you're supposed to be multitasking and that sort of thing, it just doesn't gel very well with writing software. If I'm trying to actually write software, I put my phone in airplane mode. I turn off notifications, and then I write some software.

Edith:     I think HipChat and Slack are kind of like ... It treats you like a genie in a bottle, like somebody asks you and all of a sudden you're supposed to poof out and answer a question. It's like, actually, I don't want to come out of the bottle right now. I have stuff I'm doing.

Paul :     Right. I will go back every couple of hours. I'll check my email. I'll check Slack. Take my phone out of airplane mode, and then I'll deal with the list of people I want to talk to. This gets a little bit tricky when there's something that you have to keep on top of, and you only want to be notified for this. There isn't really enough control around that sort of thing. I think that's one of the problems of our age that will eventually get solved.

Edith:     I think it's just going to keep getting worse and worse.

Paul :     Exactly. It will keep getting worse and worse, and then eventually people will freak out and they'll fix it.

Edith:     I mean, I know Google Glass tanked and Apple Watch is in the ditch, but at some point we're all going to have implantables in our eyeballs that just flash text messages all day.

Paul :     Right, right, right. There's a talk at, I think, Dice in 2010. Someone gave a talk about how they're going to game-ify everything. It's like, if you want to watch this TV show, you should be drinking a can of Coke and show it to the camera or whatever and then you can watch the show. The suggestion was that this will actually be good for society.

Edith:     What?

Paul :     That you'll start to get things like, you know, your kid got a report card. You get some points, and then your points become redeemable.

Edith:     For Coke?

Paul :     No, for whatever. Then eventually you're ...

Edith:     Does everything just come back to Coke?

Paul :     Then your points become redeemable for a tax credit or something like that. Everything kind of ties together and there becomes points everywhere. It incentivizes good behavior. Probably bad behavior, too.

Edith:     The good behavior is that you take a picture wearing a ...

Paul :     Presumably good behavior is that you yell at someone in the internet for not responding to your pull request in 2 hours.

Edith:     I think, to circle back from our long detour, I think the open source is used for so many different things, including that there's this always on population of developers who are dying to work on your product.

Paul :     Right. You were talking before about the kind of backlash about people not getting paid.

Edith:     I think there's 2 separate backlashes. One is for businesses who thought that they would get software for free.

Paul :     Right. Fuck them. They should know better.

Edith:     The second is from developers, like why am I working for free? I think there's so much good in open source, but I think both populations are right when they're like, "Okay, I ..."

Paul :     I have, in my big long list of business plans, one of them is proper open source funding. The problem as I perceive it is that there isn't really a funding model for open source. There's a very obvious funding model for open source, which is to ask all the companies that rely on it for money. Have actual salespeople rock up to the door of Heroku and say, "Give us $100,000 a month." Recurring revenue, I think that's the key thing. People get little shitty donations here and there.

Edith:     The Wikipedia model.

Paul :     Right, right. I think it's like, get- I don't know, 1% of revenue from companies that do open source, or that use open source heavily. Apply it directly to the things that affect their business or are the riskiest. I think this open SSL thing is kind of a key example. If your company is on Python, then send it to Django or whatever.

Edith:     That's what they're trying to do.

Paul :     Say, "I want this money that I'm giving funded into this niche or this niche or this niche," or whatever the thing is that you use. Perhaps it could even automatically look at your Gemfile or requirements on text or whatever and know what you actually use and all that. That's kind of one side of it, that people should be asking the people with money for money and not just complain on the internet about it. The second thing that I'll say, and I'm going to launch straight into that rather than discuss the first ...

Edith:     Because I stewing over so many complaints.

Paul :     Right, exactly. The second thing is that if you're paid for it, it's a job, right?

Edith:     Yup, which is not a bad thing.

Paul :     It is and it isn't. If you already have a job and you hobbyist this stuff on your spare time, then you're not going to want the second job of actually ... You think people complain when you wait 2 hours for a pull request. What happens when they gave their $10 monthly donation, or their $100 monthly donation and they feel entitled to your time, because you're taking money at the other end of that.

Edith:     That goes back to when I was volunteer, and I'm like, "I don't want to get paid."

Paul :     Right, right. Exactly.

Edith:     If you pay me $10 an hour, that's ...

Paul :     Right, exactly. Even if you got a proper hourly rate- Let's say it's a good developer hourly rate.

Edith:     $100, $150.

Paul :     $100 to $150, right. Exactly. If you're getting paid $100 to $150, then you're suddenly actually culpable for doing a good job, and this is your nights and weekends. You can't just blow off the coding that you're planning to do to spend time with your family.

Edith:     Which is important. Family is far more important than code.

Paul :     Exactly. Coding is fun, and once you get paid, coding is a responsibility as well as fun. A job is never as fun as the thing that you're doing in your spare time. I think, I'm not saying that people shouldn't get paid for this. I'm not saying that developers shouldn't be able to quit their day job and focus on Django or whatever in their full time, but I'm saying that I don't think people are going to find it that much fun.

Edith:     Then it gets back to what does really open source mean. I think the word 'open source' has been overloaded.

Paul :     Go on.

Edith:     Open source has been overloaded to mean free software. Open source has been overloaded to mean I contribute when I want to. Open source has been overloaded to mean anybody can use it at any time.

Paul :     Right. It's actually none of these things, and also all of these things.

Edith:     That's what I mean. I use the word 'overloaded' very deliberately, because it's an old C++ word about you overuse a word.

Paul :     I completely agree. You're always going to have a clash where people with different values and different missions are interacting in the same space. If one person's, the value that they have in open source is that they get a free web server, and another person's thing is that they're looking to contribute in their spare time ...

Edith:     Or they're looking for a job.

Paul :     Or they're looking for a job. There's so many things that people look for in open source.

Edith:     Or here's this project that nobody is buying, so I'm just going to open source it, which is what Jut just did. They were like, "Nobody is buying our software, so we'll open source it."

Paul :     As in it will solve all our woes, or just we're giving up and shutting down and you may as well have it?

Edith:     Ambiguous.

Paul :     Okay. When people try to solve problems, they imagine that everyone knows what the problem is. In fact, generally, people don't share the same problem.

Edith:     This goes back to what you said at the beginning about how you'd updated- You said some, what was it, closure?

Paul :     Yeah, yeah, yeah.

Edith:     You tried to solve this particular problem, and everybody was like, "We want to use this for this other thing."

Paul :     Right. This larger thing, this is the next step in it, or whatever. I didn't feel confident in reviewing the code. I don't really know. Is this a priority? I'm kind of doing other stuff at the moment.

Edith:     As you should.

Paul :     Right. Although, it's still flagged in my inbox as a thing to do someday. I clearly have mixed feeling about this whole thing. I talked before about the problem-solution implementation framework that I use for getting people on the same page. The pull request that comes in is always the implementation, or the people who say open source should do this or should do this or should be this. It's always an implementation. I want money in open source. I think that there isn't necessarily a problem or a goal that everyone has agreed on, because there isn't a single set of values for what open source is or should be.

Edith:     I think that's the very definition of open source, though. I mean, open source is basically that anybody can contribute at any time. I think that's what's so fun and dangerous and risky. Any time you're depending on the work of everybody to get something done ...

Paul :     It's that open SSL issue, right, is a really good example of it.

Edith:     Do you want to talk more about that?

Paul :     There was a couple of giant vulnerabilities in open SSL. I think Heartbleed was the best publicized one.

Edith:     That was a very good branding, by the way.

Paul :     It was.

Edith:     If you just said 'open SSL 3.7 vulnerability,' nobody would have cared.

Paul :     Right, exactly.

Edith:     If you say 'Heartbleed,' everybody is like ...

Paul :     It was a big problem and it had slick marketing behind it. There was a logo. People were very angry about the fact that there was a logo before they knew about it.

Edith:     Why were they angry?

Paul :     These people are angry on the internet.

Edith:     Is that the way it is, Paul?

Paul :     I think that's how it works.

Edith:     Gosh.

Paul :     This is why you should never go on Twitter.

Edith:     You still haven't followed me.

Paul :     I thought I ... I will fix that. After Heartbleed, people realized that open SSL was basically not minted. There was one guy working on it in his spare time. He wasn't even paid for it.

Edith:     That's the thing. Everybody was like, "Why didn't this guy work harder and prevent it?" He wasn't paid. That wasn't his job.

Paul :     Right. There was an article about him in Wired. They asked him, "Why aren't you getting paid?" He was like, "Well, you know, I like the code and I don't really like the fundraising aspect of this," which goes back to what I was saying about there should be this nonprofit that raises tens, hundreds of millions of dollars.

Edith:     Developers. Developers for everyone.

Paul :     There's this problem for everyone that open SSL was just fucked. Everyone used open SSL.

Edith:     So are the tragedy of the commons.

Paul :     It is a tragedy of the commons., yeah. Very, very ... I mean all of open source is almost is tragedy of the commons.

Edith:     This poor guy who's getting paid no money and everybody is yelling at him. He's like, "I don't get paid. I'm just doing this because I liked working on software in my free time." The tragedy of commons, it's a classic econ example of if you have a piece of land and anybody can graze their cattle on it, nobody has an incentive to not put their cattle there. The converse is nobody has an incentive to maintain that ground, because they don't own it, because they return.

Paul :     Yes, agreed.

Edith:     There's this common piece of land. If you put effort into hey, let's put some fertilizer out. What happens is everybody comes and brings their cows there.

Paul :     I'm not sure that the tragedy of the commons is a great analogy for software, because ...

Edith:     No, I think for open source it is the perfect analogy.

Paul :     I think it stops it, because if you put fertilizer down, everybody gets advantage of that fertilizer. It's free for it to propagate.

Edith:     No, but you paid the money for the fertilizer and you put it down and then everybody's cows ...

Paul :     Right, but you get to use your fertilizer. Everyone gets to use your fertilizer. If someone else also puts money down, you'll get to use all of their fertilizer.

Edith:     No, no, no. Let me rephrase.

Paul :     I do understand the concept of the tragedy of the commons and how it applies.

Edith:     No, no, no. It's more like, so you want your cattle to come graze there. If you put seed down to get more grass to grow, which is basically what developers are doing, you don't get really any return back, because everybody just comes and takes your grass.

Paul :     But you do, because the grass is software. Software can be reproduced for nothing. If you pay for a contributor to work on a thing, everyone gets the benefit. That's why open source is beautiful.

Edith:     I was saying if you pay for the contributor and you don't get any money back, what's your advantage to keep paying?

Paul :     You're not getting money back, but you're solving your problems. You're reducing your risk. You're fixing the holes in SSL, whatever the thing is. I don't think it's a straight model of tragedy of the commons.

Edith:     I think it's a direct model. I think this is a good time to thank Paul for hanging out with me and talking about software.

Paul :     Arguing about what software is or should be.

Edith:     Paul, do you have any final thoughts?

Paul :     Just that we're really bad at ending all of these podcasts. Thanks for listening to this episode of To Be Continuous, brought to you by Heavybit and hosted by me, Paul Biggar of CircleCI and Edith Harbaugh of LaunchDarkly.

Edith:     To learn more about Heavybit, visit heavybit.com. While you're there, check out their library, home to great educational talks from other developer company founders and industry leaders.


