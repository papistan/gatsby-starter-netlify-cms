---
author: andreaech
comments: false
date: 2016-01-13 01:19:35+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-programming-languages/
slug: to-be-continuous-programming-languages
title: 'To Be Continuous: Programming Languages'
wordpress_id: 765
categories:
- To Be Continuous
tags:
- C++
- continuous delivery
- Erlang
- HipChat
- Hubspot
- Intercom
- Java
- Rails
- Rainforest QA
---

In this episode of To Be Continuous, Paul and Edith talk about programming languages and why they continue to evolve. This is episode #10 in the To Be Continuous podcast series all about continuous delivery and software development.

This episode of To Be Continuous, brought to you by Heavybit and hosted by Paul Biggar of CircleCI and Edith Harbaugh of LaunchDarkly. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.



Paul:      It’s official now, continuous delivery has a down side.

Edith:     I think we are in agreement as we always are.

Paul:      If you learn our language you are probably super into making reliable distributed systems, C++ is exactly the thing that you don’t want to be writing in distributed systems then. When you switch from an unsuitable language to a suitable language, you often end up with amazing advances in productivity and in reliability.

Edith:     The techniques that worked in that past are used up, you need to find new techniques and I think that’s the same with languages.

Paul:      Hi I am Paul Biggar founder of CircleCI.

Edith:     I’m Edith Harbaugh CEO and co-founder at LaunchDarkly.

Paul:      You are listening to; to be continuous, a podcast about continuous delivery in software development.

Edith:     You can get in touch with us anytime at our Twitter handle [@continuouscast](https://twitter.com/ContinuousCast).

Paul:      The show is brought to you by Heavybit, to learn more visit heavybit.com and while you are there check out their library, home to great educational talks from other developer company founders and industry leaders.

Edith:     Today was our episode ten and Paul and I took a pretty sweeping retrospective at where languages come from and why they continue to evolve. Paul, believe it or not I have a bet about our computer language.

Paul:      Okay this sounds interesting.

Edith:     I was catching up with a friend who started a company and he is a CEO and he told me that the company had decided to have their main application written in Erlang. I know the various popularity of all languages because I look at this myself what I see what things we’re going to build the STK for. Erlang is very load option, I’m not really making a judgment on whether it’s a good or a bad language, I’m just saying when we looked at what we were going to support Erlang was not at the top of the list.

Paul:      I think you’ve got something which is factually correct there.

Edith:     My bet with my friend who is a CEO is that he will regret having picked Erlang.

Paul:      Interesting okay.

Edith:     Not as I said any judgment about whether or not it’s a good language, but that it will be increasingly difficult to hire people who know Erlang.

Paul:      There is something I definitely have an opinion on, Circle, as you know, is built on Clojure, Clojure is a niche language at best. It was growing rapidly but it’s probably kind of flattening end at the moment, but niche languages are amazing in many different ways especially functional ones and there are so many reasons why they are amazing. The first and I imagine hiring is something that your friend was worried about or something like that.

Edith:     That’s what I worried about, we chose a niche language we are in Go but my co-founder John is like it’s a niche language now but it is only picking up.

Paul:      Right so that one is growing, but niche languages are actually fucking amazing for hiring, because when every startup in the world is written in Rails and you are trying to hire a Rails developer, you are competing against every single company that’s out there, and you have no differentiators.

Edith:     It’s hilarious because I remember in San Francisco in 2007 I went to a party and they were talking about how Rails was a differentiator, like I literally remember this I was like here is this …

Paul:      Yeah and it would have been in 2007.

Edith:     It was like because I was like how do you manage to hire engineers, they are like, “We are Rails everybody knows to work in Rails,” and then I remember eight years before that in 1999 Java was the hottest.

Paul:      ’89?

Edith:     I’m not that old Paul, come on.

Paul:      I thought you said ’89, ’99.

Edith:     ’99.

Paul:      Exactly.

Edith:     Ouch.

Paul:      Actually Paul Graham had an essay about this, I don’t remember the name of the essay, but he talked about how at some point Java had been an exciting differentiator and then you could find the great hackers by the fact that they knew Java.

Edith:     I remember going to Java one when it was the hotness and now it’s like the notness.

Paul:      Now it’s an old in carpet right, there were cycles Python used to be a thing that you only knew if you went to learn it to yourself. You couldn’t learn about it in college, there weren’t these boot camps, no one was doing it except because they were super into learning the latest things, and there is this correlation of great hackers being super into great things, which you may or may not or new things, you may or may not agree with that, but it’s an opinion that’s out there. If you are into a niche language like the people who learn Erlang are the people who, well okay there is all the telecoms people who learn through Erlang and I don’t know if that’s going to be helpful enough. If you learn Erlang you are probably super into making reliable distributed systems.

Edith:     Yeah but don’t languages kind of start to putter out, I mean if they don’t start to catch fire, if they are not getting new blood somebody who is really into the cool new thing like Erlang haven’t they already moved on to Scala.

Paul:      If they are already looking, if they are only into it as the cool new thing then yes, but if Erlang appealed to their certain sense of who they are or certain sense of how they think, certainly closure for me was the certainly the language that I hate the least and of all the languages I’ve tried Python adjusts in second. Certainly like in the future when I’m, well I probably won’t be looking for jobs but theoretically if I was looking for jobs Clojure would be a major differentiator for me.

Edith:     Because you’ve tried other languages and this is the one you like.

Paul:      I’ve tried so many other languages.

Edith:     So many.

Paul:      It’s and Clojure is amazing and I haven’t tried Erlang to be fair, but there is, my friend used to work at this video game startup, in fact I used to work at this video game startup it was called Demonware and it …

Edith:     Did you forget you worked there or just like?

Paul:      I wasn’t there for very long, so it’s now Activison Europe or Activision Rounder or something along those lines, it used to be called Demonware and they made this matchmaking software. When I say matchmaking is you are playing online gaming and you are trying to make a match there is all these bunch of people. They had written the software initially in C++ and …

Edith:     Okay I hear you are pretty familiar with this, that kind of software.

Paul:      Very familiar with C++, and C++ is exactly …

Edith:     I meant more with the matching.

Paul:      C++ is exactly the thing that you don’t want to be writing in distributed systems then and it was riddled with bugs, it was awful and then this guy Vlad and I don’t know how apocryphal this story is but this is how it was told to me and I know Vlad is very smart. Rod came along and he rewrote their match making software in about nine days I think in Erlang, and it solved all of the problems that they have ever had in C++. Because Erlang is a system that’s designed for building these things and when you switch from an unsuitable language to a suitable language or from a lower level language to a higher level language whatever it is, you get closer to the domain that you are trying to solve. You often end up with amazing advances in productivity and in reliability versus doing in kind of the old shitty way.

Edith:     That’s I think you said something very interesting which is basically that languages are evolving for custom purposes. Because what you said about Erlang and how it’s really perfect for this high scalability use case, I mean that might not be true at all if you are looking for like say a mobile app.

Paul:      Absolutely so Erlang is something which is designed for telecoms and telecoms is something with fundamentally, the packets are coming in and you are trying to do some transformation on them and get them to another place.

Edith:     Trying to decimize them.

Paul:      Something along those lines and the whole purpose of it is be super reliable, don’t this is telephone searches, don’t let some systematic failure take down the entire system. When you compare that to something like Rails, Rails is something which is built for making websites super quickly. If you are going to make a website super quickly like start now finish before lunch, Rails is your friend and Erlang is not going to be your friend. If you are looking to make telephone switches, Erlang is your friend and Rails is not going to be.

Edith:     Yeah I mean this, because it comes back to something we talked about before just the trade off between; time, quality and features.

Paul:      Right it’s all tied to it and those languages have certain properties that make it easier to build certain features in certain niches.

Edith:     Have you ever seen a case where somebody just had the wrong language for the wrong use case?

Paul:      All the time, it happens absolutely all the time and the reason; people rarely pick languages for the domain that they are running. People typically pick languages because it’s the language that they know or it’s the language that they can hire in. You have all these big enterprises who are writing everything in Java.

Edith:     Because that’s …

Paul:      That’s what you do, like there is an unwritten rule in fact it might even be written somewhere that if you are enterprise you have to write things in Java or C Sharp if you are a Microsoft shop.

Edith:     This is hilarious to me because I just remembered in 2000 I was working for a company and Java was very counter culture back then.

Paul:      Right, and if you look at the companies that were built around ’99 that were counter culture like Google for example has tons of software written in Java, and they were like one of the biggest counter culture companies that there is. Then they took a, they have this foray into Python which never really went anywhere now they are kind of super into Go, but they were building in this counter culture language that eventually became the enterprise language.

Edith:     It’s funny because, so I was at vignette which was built on Tcl which was actually very good for them.

Paul:      Holy shit yeah.

Edith:     Then they tried to move to Java because Java was the hotness and it turned out that Java was just absolutely just not the right thing for what they were doing.

Paul:      Interesting were they doing like a lot of string processing?

Edith:     They were content management and they were deploying between different systems, it was when the Java standard was really early.

Paul:      I see okay.

Edith:     It was basically a master of all trade around, all of our customers who build V6 was our Tcl version and then we tried to show this V7 which was Java with no migration path, they were like …

Paul:      Oh God.

Edith:     Yeah.

Paul:      Well I mean there’s the question of the big rewrite, the big rewrite never works. Spolsky has this big article about the Netscape rewrite that was supposedly a disaster.

Edith:     To tie us back into continuous delivery, that’s one argument for continuous delivery is there is never a big rewrite, there is just many.

Paul:      Many small rewrites, you take one system you move it often to another service, you write it in its own specific language or technology. Then you do the migration and then you delete all that code after the migration is done.

Edith:     It’s actually how, so my company LaunchDarkly is picking up customers.

Paul:      You really have a company called LaunchDarkly?

Edith:     Yeah.

Paul:      What does it do?

Edith:     I’m really happy you wore the t-shirt today by the way.

Paul:      I have several at home yeah.

Edith:     You can get a hoodie too if you want, so my company LaunchDarkly is Feature Flags is a service so basically the ability to roll features out to your own users, to permission them for different users and to experiment with them. What we’re seeing with some of our own customers is they built this custom for themselves, they just built it deep into their app and now when they are trying to migrate to new language they are sort of like wait a second.

Paul:      Interesting yeah.

Edith:     We are going to have to rewrite not only our app, but our framework too and we don’t really want to rewrite our Feature Flag framework.

Paul:      It’s funny we see this exact problem so we, at CircleCI I just switched to using LaunchDarkly and before that we had like …

Edith:     Thank you for wearing the t-shirt.

Paul:      Thank you for the t-shirt, so we had I think maybe five different Feature Flags implementations in our code base and different points; one was for users, one was for organizations, one was for different machines, one was for a different version of software. There was tons and tons of feature flags you could opt into experimental stuff, we could opt in it was, they were all over the place. We also see this when we’re selling CircleCI that we go into an organization and they’ve got a bunch of different CI systems, one team is on build bought from 2003 or something like that.

Edith:     Oh my God.

Paul:      Someone is using Jenkins, a bunch of teams have moved to Circle and they want to get everyone else over to Circle. Is it the same adaption cycle thread to enterprises that you have some teams that are leaders in, and that are explicitly asked to be the bleeding edge like the labs teams who are using GitHub and who are using Oracle and who are using CircleCI and that sort of thing. Then there is the rest of the teams who are ClearCase and C Sharp and that sort of thing and trying to learn from the LOBs people to be able to ship faster.

Edith:     That’s interesting because it’s very matter because one of the things that LaunchDarkly enables is LOBs features.

Paul:      Right where did we start?

Edith:     Erlang.

Paul:      Erlang okay, so this kind of this idea in talking about Erlang about the shifting role of languages in the space, so you were talking about people were using Tcl, people are using Python, people are using Java and Rails and Go and Clojure and all these things. What we see is almost like a continuous delivery in the programming language space.

Edith:     Well and then does it reach its limit where you have something that is too custom built because I have a couple of examples.

Paul:      Go for it.

Edith:     Well because you said a language for every use case, but I think if you get too niche you get to the point where you simply cant hire people or nobody is interested in your language.

Paul:      I agree and I disagree but give me your examples.

Edith:     I’m not going to name names, but companies that have no customers but have spent two to three years trying to come up with their own language because it’s just then a barrier to adoption. Because it’s like not only do you have to have this product that nobody wants, if you have to use it you have to learn the language.

Paul:      Right, now you could say that but it’s not how 37signals built Rails, I mean maybe they almost certainly didn’t spend two years not shipping a product, but they built Rails for their own thing and now it became this massive thing and they benefit from that.

Edith:     Well I think there is a difference between building it because you need it to build your own product, versus building it for other people to know how to use your product.

Paul:      To know how to use, so hang on this company other people, like their customers have to understand something about that language in order to be able to use it?

Edith:     Yeah.

Paul:      That was clearly an error.

Edith:     Not only did you have to buy their software, you had to train somebody on a new language to use the software.

Paul:      I see okay, I mean user adoption is a major problem for startups so if you add new obstacles; a new programming language, a new language of any kind in front of users before they can use your software I think there is going to be a problem.

Edith:     It was just like it’s one of those things that’s like never getting involved in the land walls it’s like never create friction like having to learn new language.

Paul:      I have seen lots of cases where domain specific languages have been very effective, so domain specific languages is a little language for a little domain. I’ve created a bunch of little languages myself.

Edith:     What do you mean?

Paul:      When I was doing my PhD we had to do code generation, so I was generating code and basically when I started about generating code it was in the, there were strings in the files and they were being cut net and there were variables in it and all that sort of thing and it just was like it was very, very unreadable. I was trying to copy large paragraphs of code into a place and I couldn’t tell, the different areas of escaping and all that sort of thing when you get when you are doing string processing in various languages. What I was trying to generate, I had a C++ compiler or a complier that was written in C++ which was compiling PHP into C. There was all these different …

Edith:     Yeah I was like but why.

Paul:      Because this is what we were doing, so every statement in PHP ended up being like six lines of C depending on certain various things. What I wrote was a little language where I could write that paragraph and basically do pattern matching on the basis of properties of PHP that may or may not have presence in the …

Edith:     It’s a compiler of compilers.

Paul:      It was yes, I mean that little language had a parser and it had like sort of a code generator and an interpreter sort of thing.

Edith:     This is very …

Paul:      Very matter.

Edith:     Yeah we throw on that word and we are like well.

Paul:      Yeah, but it was released so because it raised the level of obstruction for which I was writing software, got rid of a major source of bugs and it reduced my cycle time and the time to deliver new features on the basis of this incredibly.

Edith:     Well so what was the adoption?

Paul:      It was only for me, so it wasn’t being built for other people.

Edith:     You have a truly micro language?

Paul:      Yes, I mean essentially I wrote a library which obstructed a certain function and the obstruction was good and therefore I gained productivity.

Edith:     Does that qualify as a language though?

Paul:      I mean yes if you add a parser for it it’s a language.

Edith:     That’s like bigger as well; if you write a parser for it it’s a language.

Paul:      If you look at the design patterns book, the ganger for java design pattern thing, one of the design patterns was an interpreter, and this is essentially that. A little language, domain specific language and interpreter very similar kind of patterns, so I certainly wasn’t the first to come up with this.

Edith:     That’s funny I think it was [Jeff Atwood](https://twitter.com/codinghorror?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) though it could be someone else who said anything that can be written in JavaScript eventually will be.

Paul:      Right, I think that’s a different law. I think he is talking about things like in scripting where you can compile things down to JavaScript and basically everything will eventually on the web.

Edith:     I was in London I was visiting different people who were using Feature Flags and one of the companies I visited was Import.io and their entire business is they take webpage and they strip out to make it back into structured data. All web pages start …

Paul:      As structured data.

Edith:     Yeah, it’s like basically they are recompiling everything back down into a database which was pretty funny, it was like everything just reduces.

Paul:      We were talking about migration patterns or people doing migrations and I think this is, that’s almost part of the migration thing. You are waiting for someone to get an API and they don’t have an API yet, you have to use something like Imort.io or scraping of some kind. Then eventually they get an API and then you need to migrate over to it, but you could never have built your business waiting for that API because you needed to get to market faster or something along those lines.

Edith:     I mean you could say basically all trip it was that that there was no universal reservation APA.

Paul:      Of course not no, so you use the emails.

Edith:     Yeah.

Paul:      Yeah genius, it had a parser it was a language.

Edith:     It was regex.

Paul:      Sure, but I mean you could argue that there was a subset of English which is emails, which have flight confirmations in them for which you wrote a parser.

Edith:     Well not just flights, hotels, cars and then and I guess it is true, because then sometimes people would want to know how to structure an email to send it to us so that it will get parsed.

Paul:      Wow okay.

Edith:     Because like if you are an admin or something you are like if you are trying to add a …

Paul:      You just want to forward it.

Edith:     Because if you want, even I do this if you want to just to add an activity you know it was a hospital you go to the website and hand key everything see what you wanted to know …

Paul:      You want just forward to the yeah.

Edith:     It was I guess a language. Paul you talked about how Erlang was actually good for hiring because it attracted niche people, but there is also the point where a company will find that their language has started to go extinct. Like I’d put in this category Fortran, like the voyager is now struggling because the space mission was programmed in Fortran now people don’t really know Fortran so much.

Paul:      Right, I think everyone saw this in the 2000s with the dot com crisis and the COBOL, no one knew COBOL anymore so the gray beards were brought end over time and for massive salaries and that sort of thing to add two bites to something for year 2000 crisis that’s what I was talking about.

Edith:     Why do you think Y2K never really materialized?

Paul:      Because it was handled.

Edith:     Nobody remembers the crisis that was handled.

Paul:      I mean if you went through it or if you were just alive at the time you remember everyone talking about how these two extra zeros are going to make all the fucking difference. Anyone who had a problem with it just handled it, and also everyone shut everything off on at midnight.

Edith:     Yeah I went camping.

Paul:      Were you sure when you were coming back that there was a civilization to come back to?

Edith:     I went to Yosemite and it was like I like it there, I was like I’m going to hang here for a while.

Paul:      It’s good because when the more rotting hoards of post apocalyptic zombies were destroying San Francisco you would be at Yosemite already.

Edith:     Yeah some place to hangout.

Paul:      It was well thought out.

Edith:     I got a lot of food.

Paul:      Language is very obviously dieted, there is a life cycle of languages and being in San Francisco I think we see the very start of the life cycle, especially the shininess, the early adoption and even kind of the early mainstream languages if we are going to take a cross in the chasm terminology to. Then we get bored of the late mainstream and I’ve actually never looked at the latter part of that graph, so I don’t know what the bottom of the right most thing on the cosmicism graph is when everything is in decline. I don’t even know what you call that.

Edith:     I think it’s called retirement.

Paul:      Retirement there we go, so there are all these languages which are in retirement and there are all these languages which are in the late majority stage which I think is the unexciting phase if you are here. Those are obviously the Java and C Sharp and C++ and that sort of thing which are relegated either to career program or places where you never need to change your technology stack or legacy technology which is still relevant. I think Chrome is maybe a good example of something which is written in C++ and still very, very relevant.

Edith:     It’s interesting I think you are very accurate to describe it as that cycle it’s exactly right, and I think some languages just never cross the chasm. Why do you think some languages just never make it across?

Paul:      It’s an adoption thing, there was a very interesting talk by Simon Peyton Jones, he’s the head of Haskell and he talked about how almost all academic languages die and somehow Haskell managed to survive. I think he doesn’t quite know how and I think that’s the case with all kind of adoption, you don’t really know why this particular one you can have theories and retrospect, but there is no real good reason why one survives and something which is roughly equivalent doesn’t survive.

Edith:     There was a big heated topic now about the backslash around open source which is basically a lot of developers are tired of not getting paid.

Paul:      To work on open source.

Edith:     To work at open source and it’s the same cycle like I hang out with my really good friend on Friday, he’s super excited because he’s maintaining this framework and people are pinning him with question and he feels like he’s getting a lot out of it. On the other hand he is at his job and his job is paying him for his time, and then three years later I have seen people on the other side of that who are like I’m not getting paid for this, it took over my weekend to answer this person.

Paul:      Well then stop answering the person, I can’t say I’m, were they talking about open source because I think that’s a contentious topic there. Let’s talk about the games industry right, there is lots of people in the games industry who have worked on death matches, terrible working conditions, shitty salary and they get burnt at and then they complain about the situation. When they eventually if the industry there is thousands of not yet jaded people waiting to take their place.

Edith:     It’s like Hollywood.

Paul:      Right exactly like Hollywood and if you want to be an actor you have to work the shitty jobs and get your name out there and pass your résumé around. Once you make it great, and if you don’t make it or you make it into like a sort of, this isn’t a very good analogy for open source. I feel it’s getting further and further from me.

Edith:     I liked your story so let’s just go on with it.

Paul:      I have an open source project that I am de facto maintainer of because I couldn’t find anyone else to take over. This is my PHP compiler every now and then I get an email or a GitHub issue or something about it and basically project is dead I’m not doing anything. I went through a very stress, I mean it wasn’t particularly stressful, but there was a period where lots of people were asking for it at night, I had to decide was it alive or dead. I don’t have time to help people with it, I tried to answer emails, tried to get other people to contribute and it’s like at the end of it I let it die. It was like if your open source thing is good enough someone else will take, some else will fork it whatever. You hand over the rains or you just accept every poor request that comes, and if you are tired of it be tired of it and just don’t work in it anymore.

I think this breaks down when you are talking about larger projects, when you are talking about Linux or GCC or something like that where mostly contributors are paid. You are talking something like Rails or Amber or something like that where there is a lot early adoption and maybe not a lot of money in it. Well programming languages I think are good and NPM and Nodejitsu went through a big sort of like, “Oh we can’t afford to keep this infrastructure that everyone is relying on what are we going to do.”

Edith:     I think open source is worthy of its own episode, so just put a semi colon there and then say I think Zynga was really successful in gaming because they were the first gaming company to really adopt continuous delivery.

Paul:      Interesting.

Edith:     Because the old console games were like you put all your effort, when you talked about the death match it was because you were putting so much effort in it because you had to get it right.

Paul:      That’s really interesting, so you think that the entire creation of casual gaming and social gaming and that sort of thing was really predicated on the fact that they are able to release things quickly?

Edith:     Yeah, I mean it used to be, so I’m leaving aside the social aspect because you can have a social aspect and console game like as you just talked about.

Paul:      Absolute.

Edith:     You can have matching like there are good games Xbox with social.

Paul:      I’m not sure you can, because I think a major part of casual gamers was that they were able to iterate really quickly on the game mechanics.

Edith:     Yeah and that’s what I mean, I think we are in agreement as we always are but the reason why they were so successful is they could iterate.

Paul:      This is interesting, I think this is the first place where I have ever seen maybe unhappy about continuous delivery, because it created casual games and the pay to play and all the bullshit which makes gaming awful these days.

Edith:     Wait you are unhappy or you are happy?

Paul:      Unhappy.

Edith:     Unhappy.

Paul:      Unhappy I mean the casual games are like I sat down to play some casual games and somebody told me it was awesome and I downloaded on to my phone and I played it, and then I couldn’t get anywhere because I wasn’t willing to spend money into it.

Edith:     Oh my God the horror.

Paul:      I’d happily pay, well I would have happily paid $20 but I hate being asked for ten cents here and $2 there and like that model of gaming like fundamentally offends me as a consumer. I understand it’s what has to be done, but it’s what has to be done because of Zynga and because it exists it’s sort of a race to the bottom.

Edith:     Well it’s they have done, they have iterated their way into this, this is the best way to extract value is you would have to ask for somebody twenty bucks up front, but just instead get them soft and then be like quarter, quarter, quarter.

Paul:      Well it’s official now continuous delivery has a down side.

Edith:     It’s the parking meter versus the parking garage metaphor, like something that you keep feeding quarters into versus you just go and park there overnight.

Paul:      I see it.

Edith:     So it’s official continuous delivery makes Paul.

Paul:      Makes Paul unhappy for the first time.

Edith:     Unhappy for the first time, Paul so continuous delivery makes you unhappy you know this is …

Paul:      Only in this situation so far I don’t think I’ve seen it in another situation.

Edith:     Well this is our tenth episode so I have another situation for you.

Paul:      Excellent.

Edith:     So LinkedIn, so LinkedIn is getting a fair amount of flack right now because they are very aggressive about invites and re-invites and so on. There is just mean floating around like.

Paul:      The polar bear sticking his head into the bus do you want to connect on LinkedIn.

Edith:     Yeah really you know back to the future part three, the Western Union rolls up and says money make fly do you want to connect. The reason why they are doing all this stuff is because it works.

Paul:      Does it work? There is a fascinating talk by [Keith Rabois](https://twitter.com/rabois?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) or Rabra or I don’t know his name but it’s the uninsured way of pronouncing it, who is, he’s at Khosla but I think he is the CEO of Square or he was a CEO of Square I think he is a Khosla now and he was the CEO of Square.

Edith:     He was at PayPal before.

Paul:      He was at PayPal right, so he gave this talk in the Y Combinator startup skill talks.

Edith:     Did you see it in person?

Paul:      No it was the one where you had to be part of the class, like the Stanford class and he gave a talk. He talked about every KPI or every metric can’t have a co-metric and that was like one of his big three lessons, other lessons like have a dashboard. The idea was that every metric can be juiced …

Edith:     Of course.

Paul:      … and the way to avoid juicing leading to problems is to have a co-metric. It feels a little bit like there is a co-metric for LinkedIn’s engagement thing that they are not or they’ve got the wrong co-metric or no co-metric. It’s like people are getting very unhappy, people who don’t see a lot of value from LinkedIn are getting very little value from LinkedIn, they are still on LinkedIn. I mean I consider myself to be one of these people, like I’m on LinkedIn I never really use it, they have never really found a product market fit with me apart from having a profile on it.

Edith:     I love LinkedIn.

Paul:      What do you do on LinkedIn?

Edith:     Every time a new person signs up I go and look them up on LinkedIn so I can know their role and what they do. It’s like [we had Sam the other week](https://blog.launchdarkly.com/to-be-continuous-empathy-in-software-development/) from Rapportive.

Paul:      Right so that’s value for me but not so much value for them, so LinkedIn offers a lot of value to the people who are using the sales packages, the recruiting packages.

Edith:     Just anybody who wants to know more about their customers.

Paul:      Know more about their customers, their colleagues, the people they want to date all this sort of thing. For the people themselves, there is not necessarily a massive value and especially like if you are in a high demand area you are going to get tons of recruitment spam. I get tons of spam for people who want me to use their software or who want me to sell me their software and especially who want to sell me consulting services. The signal tonight is very serious is complete shit and at the same time I keep getting invites from people I don’t know or maybe I do know them, I was like did I meet them at a conference I don’t really know. I just don’t get a great lot of value out of LinkedIn, so it’s trying to juice up its metrics and try to make me better LinkedIn person or whatever that is.

With that I feel making LinkedIn a product that I actually want to use or that I want to use more. It’s funny because we talked about Rapportive, Rapportive If is like the greatest product I’ve ever used, or one of the greatest products I’ve ever used and it’s owned by LinkedIn and it’s amazing. LinkedIn the product is not a great product, I’m happy it’s in the world, but I don’t see myself wanting to engage with it more in the way that I do with Facebook or Twitter or Instagram or whatever.

Edith:     Well I mean I disagree I use LinkedIn daily I find it immensely valuable.

Paul:      You are in a sales role.

Edith:     Yeah.

Paul:      I know you are in recruiting role, but if you are not in one of these roles I don’t think you are going to find it useful even slightly. What’s that all old adage if you are not paying you are the product, it’s literally half of or I mean not even half 98% of LinkedIn is the product to the 2% who are selling or recruiting.

Edith:     Yeah I mean it was funny because a guy tried to ask me out over LinkedIn I never met him and it was like, “Dude, what are you doing this is LinkedIn not like not Match.”

Paul:      Maybe LinkedIn should add a dating package.

Edith:     I don’t know I was just really puzzled I was just like “what are you doing?” I really liked the idea of anti metric, what are some examples that he gave?

Paul:      I don’t remember it was a good talk though I’d recommend looking at it. I think the, like if you are sending out email invites or something like that probably your co-metric is dissatisfaction of some sort, so a number of people who unsubscribe is probably a good co-metric for number of people who reengage.

Edith:     I think there is a fine balance though that there is always going to be somebody who is unhappy. An example I heard was like so Gmail whenever they do a canary release either they are pushing out new code to some people; one of the things they monitor is the prevalence of Gmail sucks on Twitter.

Paul:      Right exactly.

Edith:     They always accept.

Paul:      Beautiful co-metric.

Edith:     They always accept that there will be some level of it.

Paul:      Right and I think it’s fine for there to be a level of like you are trying to hit certain things you are going to break a certain number of eggs. There is always lots of people who are angry about change, angry about …

Edith:     I read this great blog.

Paul:      … package.

Edith:     I read this great blog post by this guy and he talked about there is always people who don’t want progress, there is always somebody who would say the Sistine Chapel is good enough with that painting, I think you read that.

Paul:      I think I read that it was good.

Edith:     I enjoyed it, but what was your is was there specific inspiration to write that post or was it just?

Paul:      I mean that was really is the future post document like why everyone was hating on Docker, I think it’s sort of tangential to the current theme, but there is a little bit of a correlation there. People don’t like change, people like things to be the way that it is. You see people talking who send out angry skrids about LinkedIn should be doing extra fit, better example Facebook, Twitter.

Edith:     Twitter.

Paul:      Exactly Twitter should be doing whatever, Twitter shouldn’t have launched moments, they should launch moments, they shouldn’t have hearts, they should have hearts and that sort of thing.

Edith:     They should have mumbles.

Paul:      Fundamentally there is someone at the other end who appreciates your skrid and reads it and combines it with the five hundred other, ten thousand other elements of feedback that they’ve gotten and combines it with the metrics that they have and the co-metrics that they have to decide what they actually want to do.

Edith:     Yeah, I mean that’s the job of a project manager.

Paul:      Exactly.

Edith:     You can’t make everybody happy all the time.

Paul:      The people who are complaining about LinkedIn I think fundamentally they are right in the sense that every complaint is right, every complaint is accurate.

Edith:     I mean the thing that I didn’t like, so the thing that I don’t like is they’ve recently switched their messaging from something more like an email, to now this horrible like IM type style which what I’m doing a business communication I don’t like doing.

Paul:      Interesting.

Edith:     When I write somebody in a business I start with like dear or hi.

Paul:      There is a question should you be doing that, I’m not sure you should. One of the kind of fundamental parts of doing modern business is authenticity and if you are going to be talking to your customers, if it’s a very formal interaction versus a very informal where we’re friends, you are a part of the community, you are a part of the product. I’m very much a latter, a former, a fan of the latter.

Edith:     You are a former fan of …

Paul:      I’m a fan of talking to your customers with authenticity, which very often means dropping the hey john at the top and the best at the bottom and that sort of thing. More I am like unless.

Edith:     It’s funny because actually for biggest enterprise customers we give them a slack or a HipChat channel.

Paul:      Right exactly.

Edith:     Where like we just there like they are on and they ask us for stuff and we write in the back. It’s cool and fun and liberating.

Paul:      I had an interesting conversation with one of our very good customers; you are familiar with Rainforest QA.

Edith:     Yeah love them.

Paul:      They are our customer and I know them socially and that sort o thing. We sent out some email I don’t remember exactly what the email was and [Fred](https://twitter.com/fredsters_s?lang=en) who is the CEO said, yeah I’m telling the story. It was sent out over into commerce, so sent out to all of our customers goes back to like intercom inbox so where it’s monitored by product managers or support people.

Edith:     We use Intercom too by the way.

Paul:      Awesome, so Fred replies and I think it might have been an apology for something, maybe there was some downtime or something and he, his reply was no like a “Dear Paul” or “Best” at the end of it. He just basically, in fact he didn’t basically say I think he said the exact phrase “f*ck you”.

Edith:     That’s a very Anglo-Saxon for phrase.

Paul:      It is a very, Fred is English it’s a, the …

Edith:     I think that’s one of the oldest like Anglo-Saxon phrases.

Paul:      Right so I responded to Fred, so first my support people said, “I think we’ve got an R rated customer here, Paul you should talk to him,” and it was routed to me and I replied to Fred and I said “How about you go fuck yourself.”

Edith:     First of all do all "R" rated customers get routed to you or does Fred’s?

Paul:      I think it was routed to me because it was I think you could tell in the software that I knew him or that I had talked to him before or something like that. The point that I was making is not that I hail insults at customers, but that you are, the closer you are to friends with your customers the longer they are going to be your customers

Edith:     I don’t have any that I respond like that to.

Paul:      I have about one that I would respond that way to, but if I was to say, “Dear Fred I’m sorry that you feel this way perhaps we could have,” I don’t know whatever. “Perhaps we could arrange a call to discuss your,” well whatever.

Edith:     I think fair enough

Paul:      It’s an inauthentic conversation.

Edith:     I think Fred is a special use case that like.

Paul:      It’s an extreme example of making sure that you have authentic conversations with all of your customers.

Edith:     I think it is true to be authentic, like I remember so I was working at a internet of things company and this is before there was Intercom, so literally every time somebody registered their device I would just hand write their email because I was so excited and I just wanted to know more. Then I would get emails back like are you a bot and I’m like no.

Paul:      No, I did exactly the same thing before. Every, the first fifty or a hundred customers I wrote them an email. I mean the first twenty I wrote them an email before they became customers, but I said like why are you using, where did you find this, tell me what you think. Then when I eventually switched that to intercom when I was spending like 20% of my time writing those messages and we had enough customers to bid at. Then still tired to make it as authentic as possible, plus so as our developers so I put in the bottom this was, well this was automatically sent I’ll personally read and reply to all the replies.

Edith:     It’s funny because I think everybody is kind of this game now of personalization. I actually got a personalized pitch on LinkedIn from somebody who said they listen to the podcast. They didn’t just say they listen to the podcast, like they quoted from a couple of episodes and then they tried to pitch me for like the …

Paul:      I mean it’s the standard thing, you write a paragraph that shows your connection to the human being. “Hi how are you I see you just had a child that’s awesome, what lovely pictures you had,” and then you go to the pitch.

Edith:     Hopefully they’ve actually had a child.

Paul:      Right I don’t think you should apply that to everyone.

Edith:     I know I mean the worst is when you get something like hello “brackets” first name and inside it says first name not your first name.

Paul:      Right so it’s interesting you see, have you read the book Predictable Revenue?

Edith:     Yeah.

Paul:      Everyone has read “Predictable Revenue” now, it’s the modern sales techniques. So you start to see the emails that were in “Predictable Revenue” taking almost verbatim, and I get those emails all the time.

Edith:     It’s funny so I was talking to my friend she is awesome, she is in sales at Yammer/ Responsys/Mixpanel and there is just this constant evolution of sales pitches too. One of the most liberating things that HubSpot VPA marketing said is that what he said was not content marketing is God, which is what I expected him to say. The techniques that worked in the past are used up you need to find new techniques like and I think that’s the same with languages. You can more in the past to say oh my gosh why doesn’t, why has I remember when SEM was really good and now everybody does it. I remember when Content Marketing was really good and there are still niches and say with languages, where do you think languages are going?

Paul:      That’s quite the spinner from product here and sales things where are languages going, I think languages are fundamentally by reason the abstraction.

Edith:     Yeah we agreed.

Paul:      Yeah, there is a question of what is the next level of abstraction.

Edith:     Actually there is do you know Jesse Robbins?

Paul:      Yeah.

Edith:     He had an interesting interview in ReadWrite web about saying that he had to basically custom build everything for his new company because he couldn’t really use anything that was out in the market.

Paul:      Okay, like it’s a hardware device is that what you mean?

Edith:     Yeah so he had to build his own data center and all this stuff so it was the opposite of that.

Paul:      Build his own data center.

Edith:     He said it was the opposite of abstraction.

Paul:      Interesting there wasn’t enough latents or he had specific constraints around latency or something along those lines.

Edith:     Yeah.

Paul:      You often get this sort of thing where the fundamental differentiator of your company is that you are able to take some process and do that process much better, whereas everyone else is using sort of commodity components. In fact Google’s commodity component was the thing whereas everyone else was using specialized components. Google was able to succeed because they were, one of the many reasons that Google succeeded is that there is commodity components and everyone else are using. They discovered a new way of creating data centers or whatever it is that you are doing achieving business, being full stack, being less full stack, abstracting the right things, de-abstracting the right things is a major differentiator in most businesses. They find one process that’s better or different or gives them more success.

Edith:     Google is kind of legendary for building everything in house.

Paul:      Right when Google started all their servers used, everyone else was buying Oracle on IBM expensive multimillion dollar things and Google was putting like the Dell that you are using in your homeroom. They just figured that they had to make falter and software and they were ahead of the world because that’s what everyone is doing now.

Jeff:         Hi this is Fred from Rainforest QA ex-customer of Paol at CircleCI and still offended human, you have been listening the at best mediocre podcast To Be Continuous.

Edith:     To learn more about Heavybit, visit heavybit.com while you are there check out their library, home to great educational talks from other developer company founders and industry leaders.


