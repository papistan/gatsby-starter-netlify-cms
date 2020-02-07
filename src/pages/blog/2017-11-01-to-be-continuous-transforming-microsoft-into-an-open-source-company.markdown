---
author: andreaech
comments: false
date: 2017-11-01 20:02:10+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-transforming-microsoft-into-an-open-source-company/
slug: to-be-continuous-transforming-microsoft-into-an-open-source-company
title: 'To Be Continuous: Transforming Microsoft Into An Open Source Company'
wordpress_id: 2151
categories:
- To Be Continuous
tags:
- Ed Blankenship
- Martin Woodward
- Microsoft
- open source
- To Be Continuous
---

In the latest episode of To Be Continuous, Edith and Paul are joined by Martin Woodward from Microsoft and Ed Blankenship from Algorithmia. They discuss the cultural and technological shift that was necessary to transform Microsoft into an open source company. Martin talks about how as the owner of CodePlex, Microsoft’s open source community, he created Microsoft’s Github account. He also shares tricks he used to drive adoption inside Microsoft, such as allowing people to use their personal GitHub accounts, the subsequent challenges that this created and how he overcame them.

This is episode #39 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->

This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.

﻿





**ABOUT THE GUESTS**







[**Martin Woodward:**](https://twitter.com/martinwoodward?lang=en) is Principal Group Program Manager at Microsoft and Vice President of the .NET foundation. Martin works on Visual Studio Team Services. Prior to Microsoft, Martin was Senior Software Engineer at Teamprise.

[**Ed Blankenship:**](https://twitter.com/edblankenship?lang=en) is Head of Product at Algorithmia, an API for algorithms, functions, and models that run as scalable microservices. Prior to that, Ed worked as Product Manager at Microsoft for DevOps, Visual Studio Team Services/Team Foundation Server, Application Lifecycle Management (ALM), and Dev/Test Workloads on Azure on the C+E Developer Platform Product Marketing team.






**TRANSCRIPT**




**Paul Biggar: **So what do you like least about open source?







**Martin Woodward:**


<blockquote>As somebody who has to help teams become open from Microsoft and learn how to work in an open source community, sometimes people aren't always very friendly, and it takes a lot of mental energy to be nice and be professional and be polite and suck it up. </blockquote>


And there's a reason why we can't have nice things on the Internet and why you never read the YouTube comments, and sometimes you just have to go with it. And I actually do worry about the wellbeing of our employees sometimes making sure we're not putting them under too much pressure.

**Ed Blankenship**: Yeah, just a piggyback, I think that's probably the thing I would say, too, but thinking about the morale of engineers, especially at Microsoft, who have never really been out in the open and been transparent about the code that they write.

**Edith Harbaugh: **Yeah, I read this great tweet from Solomon Hykes, the co-founder of Docker, and he said he wanted to restart in open source without his own name. But now would be a great time. We're recording from the floor of Microsoft Build, Microsoft's biggest developer conference. I'd love for you two to introduce yourselves.

**Martin: **Sure, so my name is Martin Woodward. I work on the Visual Studio Team Services Team over there and work with a bunch of communities. Before that I was the executive director of the .NET Foundation. And then before that, I helped introduce Git into Microsoft. And then I was with a company that did Java tools and things like that, we got acquired, where I used to work with Ed as an MVP.

**Ed:** Yeah, we've been together 12 years. Since the beginning of TFS. So, we went through all those years. But I'm Ed Blankenship. I'm now the product manager for our devops family of products and services. So, that includes team services, and TFS, and application insights, and hockey apps, so yeah.

**Paul: **So, I'm interested in this thing that you said, because the idea that maybe people are a little unpleasant in the open source community and the Internet in general, that's an idea I've never actually come across before. First time hearing this.

**Edith: **Are you being sarcastic though?

**Paul: **Okay.

**Martin: **The favorite part of my job as executive director is I got to work with the coolest people. There's so many people out there who are just awesome, like Shif-gee Bren-don-foss, he works at GitHub, and Brad Wilson, and Oren Novotny, and just these awesome, awesome people in the community. They're just amazing fountains of energy and creativity. And I've been in startups before.

Had a real job before I came to Microsoft. You always build this list of the people you want to go steal when you do your next startup. These are people I'm going to get to work for me sometime if I can. And I get to work with all those people. And we don't pay them. We don't pay each other. I was just there helping them be better at doing it. So, that side is awesome, and you've got to hang onto that side.

And you get people turning up with amazing gifts of code and amazing like detailed bugs and things like that, and it's all awesome. And then you get the other people who like to troll. You get the other people who like to be snarky on comments. And they just kind of forget that there's people behind those things. And if we could keep the conversation focused. Like it's okay to disagree, but let's disagree about technical stuff.

**Paul: **It's funny, because I see that


<blockquote>There are two camps of people. One camp says "let's be nice to each other on the Internet. We're a big community. We're people. Let's all be nice. And there's the other camp, which has some very famous people in it, Linus Torvalds, Eric Raymond who are like, "Who gives a shit about people's feelings? Code is the only thing that counts." </blockquote>


**Edith: **The feelings count. And just to check, you're not being sarcastic right now.

**Paul: **Not being sarcastic. I like people. It's kind of hard to explain to someone why they should care about the feelings of other people.

**Ed: **And I also wonder sometimes if it's because we're Microsoft employees.

**Martin: **Yeah, we've got a lot of history. And because you represent an entity that's kind of...

**Ed: **Historically evil.

**Martin: **Yeah, but you are the face of it, you know what I mean? And so people think, "Well, you work there you suck it up." And we do have to, but it does take a toll on us so we have to help them. But you were saying about Linus. I mean he can be sweary at times. One of my first visit a famous commit over a pull request on Libgit2, which is a project I'm committed to, and I had to help get Libgit2 to be able to shipped in a Microsoft product.

And this was actually the first time we'd ever shipped a GPL v2 type license product inside any Microsoft product. And so there was a few nervous things about it. And there were certain things I had to do, and I'm always trying to balance requirements from the lawyers and different people and actually what I'm going to get left at call for.

**Paul: **And it's full GPL. It's not LGPL.

**Martin: **Well no, well it's actually more liberal than GPL, because Libgit2 is GPL v2 with a linking exception, which was licensed means you're allowed to link to it, whereas LGPL we certain, anyway. I'll swerve away for that topic.

**Ed: **I think it was just so funny like how much we were trying to go under the table like as much as possible, like not be seen at Microsoft.

**Martin: **Well yeah, and still try to do it. We were very open with the actual community themselves. But we hadn't announced that we were going to ship Git in a Microsoft product. But, we were contributing to the projects we needed to contribute in. So, with Libgit2, because we were going to actually ship the source code with the binary, because that's part of the license, we wanted to make sure we did that, we have a rule inside Microsoft of making sure we don't ship swear words in products.

**Edith: **Oh. That's not true of Paul's podcast.

**Paul: **Yeah, it's completely legit, so swear as much as you like on this podcast.

**Ed: **Okay, perfect, it's fine.

**Martin: **So definitely one of my early pull requests into Libgit2, whereas to remove Linus's sweariness from the comments. Now, so like and this is an interesting skill you've got to teach developers inside the team is how to get a pull request merged. Because it's no good just coming along and going, "I work for Microsoft. And we don't have to swear by the way. I'd like to remove some swear words from this," and they're just going to laugh you out.

I was like, "How am I going to get this pull request to get accepted?" And the obvious way to do it is to turn it into a joke. So, I sent the submission in and it was basically removing expletives and all that sort of stuff from the code and tidying up the code because it had to pass our internal quality checks.

That was the pull request that it came in. But actually I'm thinking, "How do I make this into a joke? "How do I make this into a joke?" So, I checked, I made the branch name was fuckity fuck. And so the first comment was, "I love fuckity fuck." It's now been embedded into the Libgit2 history, which doesn't ship with the product, you see.

**Paul: **Genius!

**Martin: **So yeah, and we laugh at that. But still, it's like it's in Libgit2. You can find that anyone can find the pull request. It's great.

**Paul: **This could've backfired hardly. I'm imagining like they put it right into the change log and it's like, "The new fuckity fuck release."

**Martin: **Yeah, from Microsoft.

**Ed: **And I think that was a really interesting thing though. So, Martin said like, "Hey, we hadn't actually announced that we were going to have distributed version control if anything else get inside of our products." And for the whole year, right, before it was like open commits happening. And I've always wondered like what other big news is happening just in Git commit history like all across.

**Martin: **And with that particular one, we'd actually gone out and so back then. So, we basically I was on an airplane and I was traveling over to Seattle and I was reading The Innovator's Dilemma. And it's a book everyone has seen the title of and everyone thinks they know what it means from reading the title, and there's lots of people that haven't actually read it. And if you actually get to read it it's really, really good.

**Edith: **I love that book.

**Paul: **Extremely appropriate for modern Microsoft.

**Martin: **Every manager in Microsoft should be forced to read it every year. It's that important. Because it helps to identify disruptive technologies and also business tactics and how to organize a business to do it. We did it wrong, but it still worked, which I'm always amazed about. So I was reading this book and I was thinking, "It's so hard to identify a disruptive technology."

And I'd also been mulling in my head like distributed version control and centralized version control. And I was like, "Oh my god, distributed version control is a disruptive technology to us."

**Paul: **What year is this?

**Martin: **This is 2009 I would say. Yeah, 2009, November 2009 it was when I flew over. I see wow, it's a disruptive technology and it's like huh? Because it had a completely different cost model. Because all the processing is done on the client it's really cheap to host.

**Ed: **I see where we're going.

**Martin: **In terms of managing the cogs in a cloud service. And then where you see these centralized version control systems, which are really hard to scale, because like when you've got a load of Microsoft 65,000 developers hacking on that thing all day your services have to be really beefy. And so it's a really interesting problem space, and I was like, "Oh, disruptive technology. What do we do with it?"

So, you have to identify it. Then how are we going to adopt? Then we have to make the decision. It's again 2009, so the three options on the table were. We need distributed version control, so we at Microsoft three options now. One, buy or build is the first option. So with Microsoft the initial preference is to go build it yourself, because we're smarter than everybody else. That'll work out fine. The next option.

**Paul: **It worked out really well with the Team Foundation Server or whatever.

**Martin: **TFVC, Team Foundation Version Control, which is still in the product. What I still wanted to do was add a distributed version control, too. And I was talking to one of the engineers and he was like, "Yeah, what we'll do is we'll ship a version of SQLite onto everybody." I'm like, "Oh."

**Paul: **Oh no!

**Martin: **So there was that or we could've worked with the Mercurial community and added Mercurial into the product. Or we could look at Git. And then so we sat down and we had a look at that. And there was lots of different things that went into it. One was we were seeing that Git was being used more and more in actual continuous delivery cycles as the channel by which you transfer changes, which was a fascinating thing.

And once you dig into Git you realize the way it transfers the network protocol is the file protocol. It's basically the repository moving across disc. It's very, very minimalist. It's great classic. I love Linus. It's great classic Linus architecture, because it's simple and yet works.

**Paul: **Yeah. It's very immutable.

**Edith:** Have you seen that talk where he announced Git at Google? It is an amazing talk. You could look it up on YouTube, and it's basically him himself announcing Git and the Google engineers shouting him down. Them being like, "This will never work. "This is idiotic. "How do you sync changes?"

**Martin:**


<blockquote>There's so many things in Git that as a source control are wrong. It makes guesses about things. You don't make guesses with version control. It uses heuristics, but they're always right.</blockquote>


Even like using SHA for hashing and things like that. And it's like, "What if you have a hash glitch?" and it never happens. So you know.

**Edith: **It's a brilliant video, just because it's showing how nobody understood it at the time.

**Paul: **So interestingly, so I have a backstory of Git.

**Edith: **Is this a backstory for my backstory?

**Paul: **A backstory for your backstory. And I have no idea if this backstory is true or not, though I don't want to inquire because if you get too close to the truth you might not be able to tell the story again.

**Edith: **Is it like looking at the sun?

**Paul: **So, Git was apparently based on Monotone, and Monotone was this thing that was written by Graydon Hoare who's the guy who wrote Rust. And he had been writing it, and it was slow for reasons I don't remember.

And Linus had looked at it and was like, "Monotone is the thing I want to hack on," sent Graydon an email, and Graydon replied, "Would love to help, but I'm in Greece and have no Internet for several weeks." And he came back and then Git was written. And it's like Monotone is now dead and Git has taken over and there's no credit for Graydon as far as I can tell.

**Martin: **It comes down to him, as well, in terms of Linus like creating it over a weekend and all these sorts of things. The initial things began did begin very early, but then very quickly people came on and started contributing. Like people very, very quickly piled onto that central community in the buildup, but anyway.

It was an interesting question when we were doing it, which one do we pick? And Git was winning in those areas, but then everyone would say, "But Mercurial works better on Windows. Mercurial works better on Windows and Mercurial is more user friendly." And it is.

**Edith: **They're both true.

**Martin:** At the time anyway, especially on the works well in Windows. And then so I was like, "Huh, that's interesting." And then I went to a couple of different conferences, and I thought, "I'm going to go to every session I can go to about Git or Mercurial." And this was like an EclipseCon or something, because I was in the Eclipse community and this was at the EclipseCon. And there was sort of 90 bagillion Git sessions and four Mercurial sessions.

I'm like, "Huh?" And then the final one was


<blockquote>I just sat there and I was thinking, "So the reason we would pick Mercurial is because it works better than Git on Windows? I work for Microsoft. Surely we can fix that part. </blockquote>


And then let's just have Git. And they'll have every reason for backing Git was because it wasn't just better for the whole community, but it also makes sure it was pretty looking like Git was going to win, and then if Git was going to win but it didn't run well on Windows then the whole Windows developer community would get left behind in this little.

**Edith: **Galapagos Island.

**Martin: **Yeah, so again, it was to make sure that the Windows developers weren't left behind in their own little ghetto. Mercurial is awesome. Don't come after me. How would you know someone is a Mercurial user? Don't worry, they'll tell you.

**Paul: **I worked at Mozilla at the time that that decision was being made, like Mercurial Git. And the thing that I think that everyone missed, people made the decision on technical merits, right? And exactly like you're saying it works better on Windows, which is a consideration for us, and more user friendly. And the thing that I think that they missed then is that is not how developer communities work.


<blockquote>Developer communities make decisions on fashion, right? They're extremely fashion conscious. The thing that looks cool is the thing that's going to win.</blockquote>


And the technical merits matter basically fuck all.

**Martin: **It's also you get to like there's a curve isn't there, as well? You get past this curve where it just starts to snowball and then you've gone.

**Paul: **Yeah, yeah.

**Martin: **One of the clinchers for us, as well, was we were looking at Xcode. And Xcode used to have a pluggable SEM model, because SEM was always very, source control, sorry, was always very sticky, and then Xcode used to have a pluggable model for source control providers. And then with the new Xcode and I'm so, like I can use Xcode 3, Xcode4 but never quite remember now because it was that long ago, but with the new version of Xcode it was no longer pluggable.

And then we were like, "Huh. And the only options were Git and SVN. I'm like, "Huh. "So, we're going to have to build some kind of Git translation. If we built our own we'd have to build Git translation. Let's just build Git." So that's what we did. And then we had to work with the open source community. We had to, because if we're making that much of a strategic bet on an open source product,


<blockquote>It's no good just adopting Git. You have to contribute, because code talks.</blockquote>


Code does talk, it always does. It talks to you. Unless you come with solutions it's no good. So, we had to get there and provide stuff.

**Paul: **So you were telling us just for the show, you signed up for the GitHub account.

**Martin: **So, I created Microsoft's GitHub account.

**Paul: **Tell us about that.

**Edith: **I was going to say the backstories are way more interesting.

**Martin: **There's a few in here that are interesting. So, let's see. So, the highline news right now is is like six, seven thousand engineers from Microsoft working on GitHub day in, day out. That is their job. That's an amazing transition.

**Paul: **That's today?

**Martin: **That's today.

**Ed: **That's today.

**Martin: **So, back then, so I, so at this point it's zero. And now all the GitHub orgs that belong to Microsoft, I was the owner for CodePlex, which was Microsoft's open source community. And at the time kind of the rule was, it's a couple of rules, but one of the rules was, which we've slowly been walking back. That's one of the nice things in the company is we've got the process now a lot more streamlined.

But back then, yeah. So, one of the rules was like, "Open source goes to CodePlex. And then open source goes to CodePlex basically." And then there were teams that were like, "Well, I don't want to go to CodePlex because I need to talk to XYZ community. They don't use CodePlex and blah, blah, blah. I'll never get supported." And they were right. They need to go where the community is.

So people were not wanting to fight the battle about creating the Microsoft org, and so then they would create like team accounts. And another problem was they would also do, "Well, Microsoft has got a really bad reputation in the open source community. I don't want to affiliate myself with Microsoft because then they'll not take me serious." So, they'd create like a digital studio account. Well yeah, Azure, andwith .NET it was different. We deliberately created that, because that's a separate foundation.

**Edith: **So you had stealth. You had.

**Martin: **Well no, so I decided to fight the battle, because I don't know why.

**Ed: **Because you're Martin. And we had Bryan.

**Martin: **Yeah, it helps when you've got air cover, when you've got executive air cover. But yeah, so no, it was the right thing to do, because we're never going to convince the community that Microsoft is serious about open source if you kept hiding. And the only points of branding within a GitHub org are the URL and like the org logo. They're the only branding points.

And so we needed that to be Microsoft. We need to score brand credits everywhere. So when you go, you know, when you go look at PowerShell, when you go look at TypeScript, when you go look at .NET, well .NET is different.


<blockquote>So then when you look at these different open source projects that Microsoft contributes to, you want to know in your mind that they're coming from Microsoft, and that's the only way we're going to start to change perception. </blockquote>


And I think we're beginning to. I hope so anyway. So, we needed to do that. We needed to accrue to the brand. But, what I also needed to do was make sure then that CodePlex was change the rules so people didn't have to publish to CodePlex, and allow them to go to the Microsoft org. And then you've got to have an interesting question about how do you make it not the Wiki Wild West, you know, and how we actually do that in a controlled way. Like we've always got policies around it.

**Ed: **Yeah, I was going to say like that was the beginning of where we needed to really think about tooling within the company to help manage our GitHub tenant.

**Martin: **We have one of the biggest GitHub tenants in the world.

**Ed: **It is. But you want to make sure like we get security right. We ended up building the whole contributor licensing agreement like system.

**Martin: **And we have systems to help manage teams around AD groups and stuff, because it's just fine. But anyway, yeah, so I created the GitHub org, and it was cool. And then TypeScript. Yeah, it's just gone great. And then we did a lot of stuff to change the policies inside the company to make it easier for the people to contribute to open source, because again, there were hurdles they had to go through. And part of the team that did this. Well, one of the things we helped people realize was if we're going to take bets on open source technologies. Everybody wants to consume open source, because hey, that's free, whatever.


<blockquote>If you want to take bets on these open source technologies, you need to be able to fix those open source technologies.</blockquote>


If you're not contributing to those open source communities, if you're not fixing them and doing the effort to get a pull request merged, you're going to now be just forking. You're going to slowly diverge away from the open source project if you're not constantly getting your PRs merged. And that means you're going to miss out on the free new features that arrive, and then what was the point? You're now just giving yourself debt.

**Ed: **And the other thing I thought that was really interesting during this time is our attorney for developer division, Jason Barnwell.

**Martin: **Awesome guy.

**Ed: **Was like, he's like the coolest guy ever.

**Edith: **I have never heard before.

**Martin:** Our attorneys are special.

**Ed: **Yeah, they are very special.

**Martin: **They're awesome, because again, when you're a company that, you know, when you're a company like Microsoft you hire a lot of lawyers, you get to interview a lot of lawyers I guess. I took a picture of the meeting, because it was all very hush hush secret. I'm going to have the first meeting with the lawyers where I'm going to talk to them about the possibility of maybe introducing Git into Microsoft, the very, very, very first meeting. And it was just it was like I held it in a building that was away from where we normally are.

Another place is good. But when you book a meeting room in Microsoft you have to like add the meeting room into the meeting request. And so I added the meeting room into the meeting request and I was like, "Oops," because there on the wall in massive letters next to the meeting room is the schedule for the day along with, "Git and Microsoft, how do we do it?" right next to the thing. So, we got to book it private.

So, I booked a meeting with the lawyer, and the first thing he said when I was like I came into him, and I was like, "Hey, so we're thinking about introducing Git into TFS. This is why." I explained it all. He was like, "Oh, does that mean I can stop paying for my GitHub account?" So like my lawyer has a GitHub account?

**Edith: **That's what I meant by like shadow GitHub accounts.

**Ed: **So like Jason is an engineer at night. He does his legal stuff during the day.

**Martin:** But he's kind of cool because if we have like a license issue he'll send you a PR to fix your licensing issue. That's what you want from legal.

**Ed: **It is though. Like I had lunch with him recently. All the stuff that he's trying to do, like transform like our legal internally to Git. But anyway, so it was a good transition.

**Edith: **Maybe we'll have legal.

**Paul: **I get redline documents from my lawyers. I'd really like a pull request.You can see the history. Yeah, legal ops.

**Edith: **Bloomberg Beta, one of our investors, they actually have their manual in GitHub.

**Martin: **The way to understand lawyers is they're people who program in English. Because words have very specific meanings to them. But anyway, it was good fun, it was a good time. So then we helped transition the whole company into being open source and help our engineers. Like we had engineers who never ever used GitHub before. And the way of developing software at Microsoft, because we are such a lot of IP in house, was basically don't go out there. Look, we did everything inside. So, it was a very introverted opinion, and now it's transitioned amazingly to be much more external.

**Ed: **That also helped us about 2 1/2 years ago. We started thinking about how we built software, and we were learning about like all the different open source workflows and how they could actually help enterprise software development, as well.

**Martin: **Yeah, with InnerSource.

**Ed: **In InnerSource, right. And so like I think one of the best decisions that came out of even all of our transformation here was we used to have engineering systems all over the place internally, and then we also had an engineering system that we made available to our customers and our developers. And so 2 1/2 years ago we decided"Hey, why don't we have different engineering systems? Why can't we just build the best engineering system and have good portability across the company?" All of this was happening all at the same time, and then finally we made a decision at the senior leadership level.

**Martin: **Yeah. But the interesting thing about the reason why we had separate ones was because the Windows team have specific requirements and they want to do something to work on their system. So, we've got source control and issue tracking and building RM and all that stuff built into VSTS, which is Visual Studio Team Services, is what Windows now use. But when we had that system they were like, "Well, the reason I'm not is because". Classic corporate architecture, the further somebody is from you in the orgchart the more stupid they are.

**Paul: **That's just how it is.

**Martin: **Yeah. And so we're not going to use their thing, because their idiots, and we need to do our thing and we're super special. We have very different problems from everybody else.

**Paul: **And they're saying the exact same thing about you.

**Martin: **Yeah, yeah, exactly, everybody is. So, the trick that we had to do is we had to basically invest in a very, very deep extensability model into VSTS so that then the Windows team if they want VSTS to work a certain way, "Here you go. Here's the API." And it was very much of an open source workflow. You want you extend it. If you want to do it, you bring your people, add it. But what we did as well we opened up the source control.


<blockquote>In the old days, everybody's source control repositories were locked down.Nobody had access to everybody's else's source control. Now, I'm in engineering. I have access to the Windows source control code base, and I have access to Office, as well as my own.</blockquote>


And if I want to go send a pull request to Notepad to add Unix line ending support finally, which I've tried to do about five times. It's surprisingly a hard engineering problem, and I can explain why if you really want to know. But, if you want to add, hypothetically speaking, if you wanted to add Unix line ending support into Notepad, yeah, I could send that pull request. It wouldn't get approved, because it affects like 90 bagillion files, but you could. And that was the other thing is getting people used to a model of restricted write permissive read, again in a source. Because inside Microsoft when you had access to version control you had access. You didn't necessarily exercise it. And to get into that model has been a fascinating transition.

**Ed: **It's been a big transformation for us.

**Martin: **I knew we'd won though. I knew we were winning like the lion's share of developers.

**Paul: **You mean as Microsoft?

**Martin: **Inside Microsoft. So by we I mean us open source people infecting Microsoft with a disease. I knew we were winning when Microsoft. We're a very email centric company still. We use Teams and Yammer and things like that, as well, but we're very, very email centric still. When you have a baby you send out the usual, "We've had a baby," and a picture comes out, and then everybody sends out the obligatory, "Oh, lovely baby pics!" You know, it's what you do. It's email etiquette.

So, somebody sent out the obligatory, "We've had a baby," picture. "Everybody doing well?" And then the first reply came back from one of the devs saying, "Plus one, looks good to merge." We've won!

**Paul: **Nice, nice. So it's funny that all the large companies in tech have their own unique dev culture. And some of it leaks out and some of it looks like what the open source world and what all the small companies look like, and some of it doesn't. And now compared to Google, which just is its own unique thing, Apple who doesn't talk to anyone, Amazon which has 50 million unique things and who knows, and Facebook which is its own unique monoculture, as well, and doesn't really make dev tools so it doesn't matter, like Microsoft is the one that looks closest to what the open source people are doing, and who the fuck saw that coming?

**Edith: **Maybe Martin.

**Martin: **It was a big team effort.


<blockquote>So, one of the tricks we did there, was to make sure people used their personal GitHub accounts. So, we didn't require somebody to create a Microsoft specific GitHub account. </blockquote>


We instead realized that it's a social thing, so we managed to convince our lawyers that maybe what we should use is, we've already got guidelines for this produced, it's our blogging guidance. And that was kind of the guidance that we used as a template for the rules around open source, and it's to do it very much as an individual, as a person, who works for a company.

And so when you sign up, when you associate your Active Directory account, your CorpNet account, with your GitHub account it makes sure that you are associating Microsoft as your company, that you remember the Microsoft org so you get the little Microsoft badge, and so people don't feel tricked into accepting a pull request from Microsoft. They're not merging, but it still comes from you as a person.

**Edith: **Have you ever then had a person who's working on embarrassing side projects?

**Martin: **Well, so, yeah. We have had people, so this, again, this goes back to how we opened the show. We have to be responsible employers. You have to still protect your people. And there are people who are vulnerable and you have to be careful. And so you allow people to create pseudonyms, especially if they need to. We have had the odd people who we've had to give guidance to about appropriate profile pictures and things. But yeah, mostly it's, "Look, you're doing this wrong"

**Edith: **So there's HR for open source.

**Martin: **Yeah. You know, so it's interesting, but it's a good problem to have anyway, and it's fascinating. So, and one of the good things about that is because you're under your own name you build up your profile. And I see two reactions to this, which is hilarious. One is


<blockquote>Whenever a new team are thinking about going open source there's a huge fear from their engineering group. "Oh, let me just spend a year refactoring everything so the code looks nice before I make it public." </blockquote>


Why is that? They say, "Oh, well you know, it's going to be public. I don't know if I want people to see it." I'm like, "This code runs on a billion machines. You're telling me it's not good enough?" It's totally the human reaction to that. But it improves code quality, because everyone is like now they want to do a pull request they want it to be good, so yeah, it improves code quality, because you know everyone is going to look at it. And you can't slip in hacks for a deadline because people get shouty. You can't hide behind.

It's fascinating. And then the other thing is obviously people build up their GitHub commit graphs and things, it's history, and so you get that side, as well. And so you have to look after your staff, because now we're a lot more visible and they can see you fairly good. We have a chat ops bot called .NET Bot and a .NET team. And it's a chat bot we have that we get him to do stuff for us.

If we need to grep a bunch of files and make a bunch of changes across a lot of things, like do it manually or should we get .NET Bot to do it? If we're going to do some moving around the code, .NET Bot does it for us. And so you're in teams or you're in like GitHub and you're sending commands, or in the pull request you're sending commands to .NET Bot to do things for you.


<blockquote>So therefore .NET Bot has an amazing GitHub commit graph, because he's committing to one of the biggest open source projects on the Internet like every day completely. And so yeah, so he gets emails from recruiters like three a week.</blockquote>


The funniest thing is I'm actually almost convinced a robot is getting recruitment emails from another robot. The robots are giving robots jobs.

**Ed: **Oh my god.

**Martin: **It's the end of the world.

**Edith: **Well, I have a question. So we heard from another guest about how Windows itself started using Git.

**Martin:** So I was, yeah, that nearly killed me if I'm honest. Yeah.

**Edith: **Were you responsible for the Five Stages of Git posters?

**Martin: **I wasn't actually, that was genius.

**Ed: **That was genius.

**Martin: **No, so I was responsible in the people learning the five stages of Git potentially. Yeah.

**Edith: **The anger one.

**Martin: **No, we came in and sat down with the Windows team and we were like, "Hey, we need to rationalize your engineering systems. What's the deal?" And so Windows is a big code base. It's been built up over a lot of years. It's a big monolithic code base. It's all in one hunk of stuff.It was like so big, we had our own version control system that we'd written to handle the load of Windows, and it wasn't big enough to support them, so we had 26 instances of those. It was enormous. And then so we came in and it was like, "Well, Git is not going to work for that. Git works for really small. This is stupid. Git works for small modules.

You need to break up the code. But we don't want to break up the code. You're an idiot going to Git. Like why would you do that? And they were like, No, no, no, we really want to use Git. Git is really important. It'll help us recruit. It'll help us use standard tools. It's important. So I'm like, "Huh." And then so you come down the discussion and you think, "Well, let's break Windows open "to lots of little bits." Let's just componentize Windows.

**Paul: **I feel like this is how microservices happened. It was like when you thought about the world in SVN ways it was like monoliths make sense.

**Ed: **There you go.

**Paul: **But now, each team we want to have our own repo. So like the idea that Git also did the same thing to Windows?

**Martin: **Yes, well it didn't in the end.

**Ed: **It didn't, okay.

**Martin: **We'll come to that. It tried. Git does lead you to more component based architectures, which is actually better architecture, so it's interesting. That's probably why the teams have been successful. But yeah. So we moved Windows to the component based model. And it was insane, and it wasn't going to work, and it was horrible, and we tried.

**Ed: **It took us a year to figure that out, too.

**Martin: **Because we have the best engineers, we have lots of engineer, we can solve it.

**Ed: **They're like, "We're going to solve this."

**Martin: **Turned out we can't. So what we did instead was wrote, but what we can do is we got a lot of computer scientists. So, we ended up writing a file system, a virtual file system, GVFS, Git Virtual File System, which is open source. It's GitHub.com/microsoft/gvfs, and it's, yeah, a virtual file system driver that knows about Git repositories. And it has a deep understanding in how Git repositories work. And so when you clone the Git repo it only pulls down the portions of the Git repo you need to be able to do various operations, and in the background it hydrates. It has lots of pointers, and then it hydrates the real files and it can pull them down.

Rather than using the Git protocols to pull them down from one master server, it pulls down binaries from proxy servers from images that are nearer by and like virtualize a bunch of stuff. And yeah, and it's amazing to me that it works. I was like when the guys proposed this. A guy called Joe Duffy, who's a very clever guy from the Midori Team. He's this incredibly clever guy. I remember he first proposed it in this architecture meeting. I went, "Joe, you're insane. "That's never going to work."

**Ed: **It's never going to work.

**Martin: **Because there are times when being the open source guy I find sometimes our audacity is annoying me at times. I'm like, "Why would you do that? That's crazy, nobody would do that. That's insane." TypeScript, I thought TypeScript was going to fail. Andrew comes to me with TypeScript, "I'm going to open source this thing." I'm like, "You're going to do a thing on JavaScript. Dude, nobody is going to do that. Like what's wrong with JavaScript? It's fine." And then what do I know? Anyway. But I didn't think this was going to work either, and turns out I was wrong.

**Ed: **Two weeks ago, or two weekends ago.

**Martin: **Two weeks ago we moved Windows over, yeah.

**Ed: **All in one Git repo.

**Martin: **Yeah. And we're using GVFS. And that gives them the performance that they need. And they're still learning, you know. Everybody has that moment where you think you've lost your code in your Git repo. And there's operations, because it's such a different form of version control, there's some operations which work really well and are a lot faster than they were, but then there are other operations which are a lot slower than they were because it's got to analyze the whole tree to get the answer, so anyway.

**Ed: **You know, Sayid has been doing a bunch of different talks about like, "Hey, on this journey.."

**Martin: **Yeah, GitMerge has the big commit view. And so yeah, Sayid has got those views. Yeah, tonight's news story. And then it's all open source and we're trying to, we're actually working with different people to see if we can get GVFS actually bundled with different Git distributions, as well, so other people can take advantage of it.

**Ed: **The tower guys, the Atlassian team.

**Martin: **It's all good. Don't use it if you can possibly avoid it. Go component based. Go for small, discrete bits of code and your code will be better code, but we do have an option.

**Edith: **Yeah, well this was a fascinating journey here, everything from the first account to Windows moving to Git. Thank you so much for coming by today.

**Martin: **Thank you for having us.

**Ed: **Yeah, this was awesome.





