---
author: andreaech
comments: false
date: 2016-02-20 00:01:05+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-software-development-at-vmware-and-facebook/
slug: to-be-continuous-software-development-at-vmware-and-facebook
title: 'To Be Continuous: Software Development at VMware and Facebook'
wordpress_id: 779
categories:
- To Be Continuous
tags:
- continuous delivery
- Dote
- Facebook
- Harvey Mudd
- Jocelyn Goldfein
- softweare development
- VMWare
---

In this episode, Edith goes it alone with ex-Facebook & VMware, current angel investor [Jocelyn Goldfein](https://twitter.com/jgoldfein). Jocelyn and Edith have a great conversation about Continuous Delivery through the lens of Jocelyn’s experiences at both Facebook and VMware. This is episode #13 in the To Be Continuous podcast series all about continuous delivery and software development.<!-- more -->

This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.



TRANSCRIPT

Edith:     Paul couldn't make it today but we have a very special guest Jocelyn Goldfein, who talked to me about Continuous Delivery and her experiences at Facebook and VMware.

What do you like best about continuous delivery?

Jocelyn :    I think it would have to be sort of the immediate gratification of immediate feedback. I think the worst thing in the world is when you go away and you have this labor of love, and you work on it for months, and months, and months, and then you finally submit yourself to other people's eyes and you realize you got it all wrong.

Edith:     I know you have a tonne of experience and now would be a great time for you to introduce yourself and tell us a little bit about you?

Jocelyn :   I'm Jocelyn Goldfein and as of today I'm an angel investor but I spent most of my career as a software engineer and a leader of software engineering teams. I did my own start-up and then I was fortunate enough to join VMware when it was pretty early, a couple hundred people and I was one of the first engineering managers at VMware. Grew with company through the early 2000s as we doubled every year for five years in a row. I stayed with VMware through 2010 and then made the big jump from enterprise to consumer and joined Facebook, and I was at Facebook from 2010 to 2014. As an engineering director I ran products like News Feed and photos that probably a lot of you listeners have experienced.

Edith:     I think your story is so fascinating, besides all that Jocelyn is also a trustee of Harvey Mudd College my home team thank you.

Jocelyn :      Go Mudd.

Edith:     What do you think is the difference between consumer and enterprise companies and how does continuous delivery play into both of them?

Jocelyn :    They're really different. VMware and Facebook aside from both being extremely successful in their respective domains could not be more different than two software companies can be. I think a huge part of that is because of the kind of business that they're in. When you're making enterprise software it's all about delivering a specific kind value up to maybe not one single customer. You want to serve many customers with the same product but you're really grounded in a use case and it's almost an intimate relationship with your customers.

In consumer by and large the price points are so low that you need vast numbers of users and so it's not the same kind of intimate relationship but on the other hand you're affecting people's daily lives. You're using your own product. You just sort of think really differently when you're trying to solve problems in mass than maybe when it's sort of hand crafted per person.

Edith:     I came from a consumer company before this I was at TripIt where we had 10 million users. One of the nice things about doing more of a B2B developer tool company now is that I do have that intimacy. I was little bit late for the podcast today because I was actually visiting a customer which was a luxury you don't really have when you have millions.

Jocelyn :    No, you don't get that millions.

Edith:     What are some engineering differences or do you think they're basically the same sort of engineering style or are there any differences?

Jocelyn :       Well, the engineering style at VMware and Facebook were very different. Some of that is enterprise versus consumer. Some of that is also that VMware was essentially building operating systems and Facebook although it has an immensely complex infrastructure is still a web app and a mobile app. Certainly, one thing that really mattered to VMware was predictability. We wanted releases to ship on time and when we expected them to ship and with everything that we had promised customers in the release. We were probably willing to sacrifice some amount of efficiency or overhead just in the name of achieving that predictability because it really mattered to our customer, and we want to keep those promises.

In Facebook, Facebook doesn't make any promises to it's users about features arriving on any certain schedules, things ship when they're ready. If anything users of Facebook probably wish that it would not change, that it would stay the same, and that's one thing Facebook can't commit. Facebook there's almost zero emphasis on deadlines because there's a realize vehicle everyday, actually there's usually two realize vehicles a day for website. Even the mobile app ship twice a month which is pretty fast for a mobile app but pretty slow for Facebook, and so it's much more of a, you don't think of it as a single product that's going to launch and be handed over to some customer to deploy. You're just sort of constantly iterating and adding features, and adding features as you go.

Edith:     That must be really hard then, how do you enforce discipline in getting a release out if you have this infinite amount of money and infinite amount of time?

Jocelyn :      We never actually felt like we had infinite money and infinite time, to be clear. I would say it was really ingrained in the culture and DNA of Facebook to move fast, and this was one of the reasons why, I arrived at Facebook in 2010 when it was already half a billion users. I remember sitting in new employee orientation and Chris Cox the head of product got up in front of us all and said, the core value of the company is to move fast. I said just to be devil's advocate here, obviously that serves you well but why do you need to move fast? The Facebook flywheel is spun up. There is no competitor who's going to overtake you if you slow down a bit. Why is speed so essential? The answer is because you don't have deadlines, the sort of urge to go fast without a deadline to give you discipline.

The need for speed does give you discipline because what happens is if you're fast then you make small changes and you iterate quickly, and you get feedback. That feedback gives you the discipline to make good decisions to decide what to do and what not to do, and that makes for better products. Just the constant drip of information, you constantly know if the changes you're making are headed in the right direction.

Edith:     The hard truth about any A/B test is that there's always a B.

Jocelyn :    Yeah, if you actually want to do right by users you actually need to try both things and do the one that's better. You can't do right by users by making something up, your heart may be in the right place, you can be wrong. As someone who's executed thousands of A/B tests the thing you quickly learn when you start working that way is your intuition is wrong more than it's right.

Edith:     Why do you think that is?

Jocelyn :     I don't know. I think humans have a tendency to over ... Humans are buggy in a lot of ways. First of all, we think that we're the user, so we think if something's true for me it's true for other people but maybe we're actually in the minority. We also are just not very self-perceptive, most people think they would like their News Feed in chronological order. They believe they spend more time. They believe it gives them more comfort. They believe they see more stories that way. Well, the actual data is you don't. I mean it's not just that like a tiny percentage of users do and maybe you're one of them and everybody else mm-hmm (negative) The lion's share of your likes, and your clicks, and your comments go to the first 10 articles in your feed. In fact the lion's share of those as a parallel go to the first article.

If those top 10 slots and especially the number one slot are burned on interesting stories which in chronological order is basically a random priority order, you've just destroyed a tonne of value for the network. For you because you're seeing less good stories but also for all your friends who're posting stories and those stories aren't getting seen by you and not getting interacted with by you. We think that, we read everything or we give equal attention to everything but we're not, we're buggy, we're biased to look at the top thing. We ran these tests over, and over, and over again because user feedback was so clear and user behavior was so clearly the opposite.

Edith:     I've been there with running the same test, at TripIT we always ... People always have this idea that people want to watch a video when they come to your homepage.

Jocelyn :      Oh God! I never want to see a video.

Edith:     What would happen is we would make this snappy videos and people would want to retest it. I ran the retest every time so like nobody believes me when I say “our conversion would be worse with video.” It doesn't matter what the video is. It's just this truth of like -

Jocelyn :     It's funny because there are moments when video is great, it's amazingly powerful. The AutoPlay video feature on Facebook, on Tweeter, on Tumbler like inline video playing is huge, but it has to be the right product. Sort of if I'm trying to accomplish a task which is to book a flight and you're video is delaying and interfering with my task, I can imagine that fails. The thing is like you'll never reason this out from first principles. You can't sort of reason whether the addictiveness of video sort of weighs more heavily then they're like it's interfering my task. That's why we've got to test it. You can't trust your opinion, it's just opinion. If you want to do justice to your users, to your product you should only deliver something when it's proven to be right.

Edith:     That's interesting, I know you're an angel investor and you advice consumer and enterprise. Enterprise companies as a rule I'd say do have enough volume to really do A/B tests, what's your advice there?

Jocelyn :     I think that's really true, but what they do have is they may like small data on one dimension, which is they don't have a large number of users, they have a small number of users. On another dimension they can go incredibly deep with them. You've just come back from a customer visit, a consumer company can't go on site, well you could run a user test with a one-way mirror, but your enterprise customers you can just go interview all of them. You may not get volume of data but you will get sort of depth an insight of data.

You can't A/B test your way to good design, you have to start with a hypothesis. You have to start with a belief and try it, but feedback it doesn't have to be ... It's an enormous luxury to have a huge volume of data. Facebook could run an A/B test and in two hours have enough data points to just have like a really clear answer and that's such a great luxury. Feedback is immensely valuable even if you don't have a bright line yes or no answer. Going and showing a new feature. Going and showing mocks. Going and just shadowing somebody using your product. Those are immensely telling and I think continuous delivery doesn't have to be A/B testing, it's just also the discipline of constantly shipping what you've got and absorbing feedback on it as it stands.

What that forces you to do is always design things that work end-to-end, and so you never go too far down the wrong path. You never implement the full surface area of one layer, and then the full surface area of the next layer, and the full surface area of the third layer before you ship it all. You do one API starts end-to-end and you get feedback on that and what you learn it forms the next API that you build. That to me is the most important thing about continuous delivery is sort of that discipline of building piecewise.

I think not only does that help you deliver higher quality software once you are VMware or Facebook that's going strong, but if you're an early stage start-up your job is not really to deliver products.

Jocelyn :     Wait a second, no, no, no. You think it, and you act like it is, and you believe it is, but an early stage start-up is not a machine for delivering product the way a large software company is. You're a machine for product discovery. You're a machine for discovering product market fit, and so it is not to take a product and perfect it, it is to take product concept and figure out if there's proof that this is a good product, and if not to try another one, and if not to try another one.

Continuously delivery is important at Facebook or at VMware to get high quality products for an early stage start-up. It's to figure out if you're even working on the right thing in the first place. At smaller scale that is the loop that informs whether you're building high quality software later on.

Edith:     This kind of fits back into lean principles then that continuous delivery is just the idea of more cycles and more iteration?

Jocelyn :   I think that's true but I think it's got to be a spiral not hamster wheel. You've got to learn something new and change something with each iteration not just go in circles.

Edith:     It's a little depressing for me right now because some of my friend's start-ups are going out of business and it makes me sad.

Jocelyn:    Yeah, that's really hard. I don't know how you could get 100% success rate. I don't know how you could get innovation without risk taking and guess what? The reason it's a risk it's because there's failure. If we knew in advance that it was going to be successful it would be an obvious thing to do and then everyone would do it, and then it wouldn't be innovation. I still believe it maybe is like the great cycle of life, it might be the end of the start-up but it's not the end of the entrepreneur. It's not the end of the founder, and sort of even that is a feedback loop but it's maybe the ultimate piece of feedback that hopefully you could take and apply into the next iteration.

Edith:     We have a mutual friend, [Sean Byrnes](https://twitter.com/sbyrnes?lang=en), he's an adviser. He started a new start-up and I was like why did you do that? He's like, I like doing start-ups.

Jocelyn :    Yes, totally. There's also absolutely the serial entrepreneur I mean is not like his last start-up failed it's going really strong. There's a stage of existence that I thrive in and I seek it over and over.

Edith:     Do you think there's any stage of start-up that's too small to adopt continuous delivery or a right point to do it?

Jocelyn :    Sometimes you're so small you just don't have any customers. You don't have anybody to show it to maybe your roommate or your friends, but I think you're not too small. I think even when you're a single person alone and a laptop it is the right thing to do to sort of wire things up to work end-to-end. To try to get one piece working at a time full-stack and then broaden your footprint from there, because even if the only feedback loop is yourself and your compiler you will still architect better, you will still learn. It's still a feedback loop like did this work? Did I get the functionality I expected? How does it feel to me? Is that continuous delivery within the meaning of the act? I don't know. I think it's in the spirit.

I think we've all gone on that yak shaving expedition where we have some amazing concept in mind and we wrote a tonne of code and then we got to the next layer, and it didn't work out the way we expected and we threw a lot away.

Edith:     Yak shaving, I've heard that one before.

Jocelyn :  I don't actually know the story behind it but it's just sort of like whenever you're working on solving a problem it's sort of like, but I could build a generic problem solver to solve my problem and it's sort of like the increasing spiral of obstruction we can get into. Sort of like let me build a tool to solve the problem, to solve the problem, to solve the problem that I'm trying to solve. Sometimes you do get a ton of leverage from solving something at a lower layer of obstruction or a higher layer of obstruction but sometimes you just end up shaving the yak in order to make the sweater.

Edith:     It's a great image. Do you think there's any enterprise organization too big to continuous delivery?

Jocelyn :   No. The largest company I've worked for VMware was a little over 10,000 people when I left but in my past life I worked for an enterprise company that sold software to really enormous enterprises Compact, General Motors. There's no size, and I think we all know this as computer scientists the larger a problem is the more you have to decompose it. The more you have to divide and conquer, and so you've got to break things up and continuous delivery gives you the discipline and the methodology to break things up.

Edith:     I agree but I'm pretty biased.

Jocelyn :   Sure. The people who I think who would say continuously delivery cannot work for me I don't think it's so much a function of size like VMware would tell you we can't ship our software every week. We certainly can't ship it twice a day because our customers can't deploy it that fast. It's an operating system, it runs in there data centers, it's on prem and if I give them a CD it takes them two months to test it before they gradually role it out. I certainly can't give them a new CD everyday because my customer's adoption cycle alone is along longer than that.

Edith:     That would be like the AOL of CDs.

Jocelyn :    I do actually somewhere in shoebox still have some little gold colored CDs that were the gold master version of various VMware releases I worked on. I think even in a situation like that where your customers cannot adopt very quickly it's still valuable to do continuous delivery first, internally. Second, an immense sort of unsung hero of ... VMware is known for the quality of it's software. When you think about deploying data center operating systems the only thing that ... In VMware early days, right now we all sort of take it for granted. It's actually so old it's become legacy technology, we're all moving on to containers, but you for granted that a VM works. You never question - in the cloud. Of course there's virtualization behind it. Who would deploy on bare metal hardware? My god!

Edith:     I remember when VMware was new.

Jocelyn :   Yes, it was science fiction. It was like I might ran a test in that VM but I could never entrust a production environment to some cookie virtual machine instead of a real machine. We had no business like we were out of business if we could not convince enterprises that this was rock solid, that it had no bugs. Quality, not just deadline predictability, release predictability but quality was incredibly important at VMware. One the ways we achieved that was an incredibly robust Beta program where we absolutely had users who were constantly trying and unreleased versions of the software and giving us feedback.

Actually, VMware has this sort of boutique products which are sort of hard to understand in the context of their revenue, it's like why do you have so many engineers working on something that is 1% of your revenue? Things like Workstation, or Fusion, or VMware Player. The answer is well, Workstation is a developer tool and yeah it doesn't make a ton of money but actually developers and QA engineers who are the users of this software are the ideal people to have in your Beta program. They will shake it down. They will find every bug. They will tear it up. They will spend their Christmas vacation trying it on every kind of hardware and every operating system, because they geek out on it. Lo and behold, you find all these bugs in your Workstation Beta program that hardened the platform before it goes into the data center production.

Even in a world where the data center cannot take a release everyday you can have a form of your stack that gets in front in a free or an open source manner, certainly in a Beta program. The Beta program was not something Facebook had in it's DNA because we always just ship things into production on web, and we would just control role out with feature gating, not Beta test, but actual in production live tests.

Well, when it comes to mobile that's more tricky, you don't get to ship everyday and you don't get instance - like two weeks is actually not continuously especially, as far as Facebook was concerned. Facebook actually runs a really robust Beta program for it's android and IOS mobile apps and those have been huge for Facebook.

I think one of the things that's really great about Beta too is like there's implicit consent, there's a contract between you and the user that you're trying something out on them. Not only do they agree to do that like in some ways you would think the set of users that you're giving this crappy, buggy, unfinished version of your product would have less satisfaction. Invariably people in your Beta program have higher satisfaction with you because when they see it in the unfinished state they feel like they get to participate. They feel like they have input and they're helping you build it and it's like that craving of ownership, of identity that people want.

Edith:     They feel like they're a co-producer of it.

Jocelyn :  That's right. When your software really creates value for people, when it really is meaningful in their lives, I think a lot of people want to feel that ownership. They want to feel that co-production credit, we'd all love to sort of see our name in the credits. I think that feeling inspires incredible trust and loyalty even though superficially it might seem like just the opposite, like you're taking advantage of them. I think is this sort of incredible win-win actually.

Edith:     Paul's not here today but Paul's company, CircleCI, one of the happiest thing I saw is one of their engineers used your product, and he made an Instagram of him using the product and then doing a little happy dance. I found out later the reason why he did it is he was trying to show his parents what it was like to release software.

Jocelyn :   That's cool.

Edith:     He's this kid from Ireland and he wanted to show his parents how it feels like when you realize something

Jocelyn :   Yeah, that sense of like victory. There was void, and then you typed, and then there was form. It's the act of creation.

Edith:     That's why I became an engineer is I love just feeling like I was creating something.

Jocelyn :  I think especially too you never just sort of type and have it work. There's always that period of debugging and why isn't it doing what I expected, and I have to track this down and solve it. It feels like sort of sometimes just like doing battle and will succeed or will I fail? That feeling of jeopardy that you get, and then we sort of come out the other side, you do feel victorious.

Edith:     When you were describing I was picturing the scenes, the original Star Wars where they're tinkering on the Millennium Falcon, they're like is it going to go? Is it going to go? Then just the right minute goes into hyperdrive.

Jocelyn :  Yes, exactly. I guess continuous delivery is like hopefully the whole success or failure of your enterprise does not depend on getting the hyperdrive online when shot. Hopefully you've many small engines and you get lots of them working one by one.

Edith:     That's a good point about continuous delivery doesn't always mean just pushing everything to everybody, it might just mean having to process to get it to the right people at the right time.

Jocelyn :  Yeah, I think as long as you don't let your code base ever sit in a state where it doesn't work.

Edith:     This is fascinating, so we had a conversation at Separate a couple months ago about why there's still so much legacy code out there.

Jocelyn :   Code long time.

Edith:     There's still like a lot of Fortran floating around.

Jocelyn :   In Y2K they had to take up all this people who knew COBOL because when all that code was written in the 70s nobody ever dreamed it would still be running and 30 years later and need to be modified. They couldn't find people with the current skills to modify it.

Edith:     I think that's one of the drawbacks of not using continuous delivery is if you build it once and then walk away that your code kind of becomes an evolutionary ...

Jocelyn :   Yes. Well, the nature of code is that everything connects, and so it's not like building a chair or even a piece of art where you finish it and it's done, and it exists in the world. I guess art grade paintings do sort of decay over thousands of years with light in photography, and museum quality glass, and restoration. In general, you put something out there and it's static and it has a lifetime, and at the end of it's life it's thrown away. Software is almost more like living organism, it almost need to sort of constantly be fed. It constantly needs new nutrients. It constantly needs cleanup. It constantly needs to evolve. I think that's because it's in constant interaction with its environment not just with the ways that people use it but with the system or the stack that it sits on top of.

I think it's tremendously frustrating. I've certainly worked with customers to whom it is frustrating that they can't just sort of buy a piece of software and have it be done and never think about it again, the way they can with another piece of equipment. I think that's just the nature of the animal.

Edith:     I'll just be provocative - do you think software will ever be done?

Jocelyn :  No, that's an easy knee jerk reaction. Could it be so self-contained? Well, that's the appliance vision, is that we can put some software on a piece of hardware and just treat it as though it's hardware but it's a black box. It comes down to what I said before that sort of everything connects and as much as we want to do a great job of API design and not having side effects. Entry software like modular building blocks. I do think in the microservices age this is more true, we've delivered more on that vision than ever before.

I still think that you can never anticipate all the ways that your code will be used and called upon up and down the line. I think you could truly imagine a piece of software running on a cable modem that sort of at the end of it's life you throw the cable modem away, you don't update it. You just get a new cable modem with a new software. Outside of like firmware embedded appliances like that, that have really contained inputs and outputs, it's had to imagine software that doesn't need to constantly evolve. That doesn't get used in ways you could never anticipate when you wrote it the first time.

Edith:     The only one I can really come up with gas stations.

Jocelyn :  Even gas stations are going to really change. Gas stations 20 years from now are definitely not going to look like they're today, but to your point we probably write completely new software to deal with battery charging and not try to sort reuse what's running in the meter at the pump. Not to sort of have a hammer and look at every problem as a nail, but I think this kind of goes to the theme of continuous delivery again and sort of constant feedback which is I would say the early days of software were sort of dominated by this idea of we have to anticipate everything that's ever going to be needed of our code. This is what led to sort of the 700 page volumes of specs and specifications of like under every possible condition. What do you want it to do.

I really think that we've learned in the decade since is that you cannot anticipate, and so rather than trying to get better and better at ... I mean there should be some anticipation but you shouldn't just sort of throw darts. There's really diminishing marginal returns and you should try to anticipate as well as you can but try and find out. Works far better than sort of sitting in an ivory tower trying to think of everything.

Edith:     Well, Jocelyn, I love geeking out about continuous delivery as you could tell, do you see any drawbacks to continuous delivery or have you seen it misapplied?

Jocelyn :   Well, churn - the allure of let me just build it once as opposed to let me build it over, and over, and over again is like is there a lot of overhead and constantly - because there's an overhead to shipping. Releasing in and of itself has a cost, and so if I release everyday that's in theory paying a higher price than releasing once a month. I think like the cost of the mistakes you accumulate over the course of the month without a feedback are much greater than the cost of releasing. Let me say like if you try to do continuous delivery and you have a release process that's designed for predictability, or quality, or something else other than release frequency then the cost of release can be very, very high indeed. If it takes you more than a day to ship then shipping everyday is just not possible or is pointless.

I would say that in order to be successful at continuous delivery you have to make the cost of shipping cheap, and that's hard. You have to trade off other things to make that possible. I'm trying hard to think of an example where that's the wrong trade off. I guess just a world where, I don't know, rocket launched systems, you don't need to ship very often. You're trying to change something, you're trying to change as little as possible and there's something else that's more important, but I just think that even if you're trying to change it as little as possible you also can't tolerate any risk in the rocket launch and so more test feedback, more Beta feedback. Even though you don't actually launch the rocket very many times you definitely want feedback all the time to make that high quality. Is there a world where you don't want things to change very often but quality is not the prime mover? I'm having trouble coming up with an example of the cuff.

I think keeping the cost of shipping down is definitely the sort of the key to being successful with continuous delivery. I think that sort of, I don't want to say it's easily overlooked but it's easy to say make shipping cheap and it's hard to do, especially if you came from a world where you didn't start out with continuous delivery in mind. You started out with infrequent releases and you sort of evolved into this very expensive, very heavy weight release process maybe of three weeks of acceptance testing. Whatever it may be figuring out how to dial back from that into something that can be more lightweight, that's just hard.

Edith:     That's hard, do you think it's because of people don't have the tools or it's a mental process shift?

Jocelyn :  Well, it's a risk. If you have a three week acceptance test process like your first thought is well how do I cram all of that testing into three hours, and maybe that's possible with automation maybe it's not. Then you actually just have to decide I'm going to live without that or I'm going to live with finding some class of bugs after I "release" rather than before. Hopefully not after you ship to customers but after some kind of internal release. I think that's scary, I think that kind of risk can be scary especially if you have a lot to lose. If you've had a lot of success, if you have a lot of customers relying on you. You need a powerful motivation to change from a status quo that's pretty good.

Edith:     That's so correct again.

Jocelyn :  I'm talking platitudes now.

Edith:     No, honestly, I'm just speechless. Well, Jocelyn, I really enjoyed you coming by today. Do you have any final thoughts you'd like to share?

Jocelyn :   I guess the one is as much as I'm a booster for continuous delivery I don't think there's any such thing as a release process that's one size fits all, that like everybody should do things exactly the same way. If had sort of one drum to beat it would be ... there's no one true way. There's no ideology that applies equally to set every software.

VMware and Facebook were just such different companies, they made software such different ways but they operated in such different environments with such different goals, and so I think that the best thing anybody can do when making software is just sort of sit down and figure out what really matters to you. Are you trying to discover whether you have a viable product? Are you trying to keep customers happy? Are you trying to acquire new customers? Are you trying to get people more engaged with your product? Are you trying to get a lot of bang from a very lean engineering team? Is it life and death quality?

Start from what you value and what your constraints are, and sort of back into the right process from that because it will be different. It will depend on what you're optimizing for.

Edith:     That's a really good way to frame it. Is it time satisfaction? Predictability?

Jocelyn :  We've all encountered and I have been that sort of crusty engineering manager who says schedule features or quality, pick two out of three.

Edith:     Yeah, that's me.

Jocelyn :  It's because those things are in trade off with one another like it's a fundamental time space trade off. It's like gosh! Why can't you people grasp that. You can't have everything all that time.

Edith:     Why can't everybody be an engineer like me?

Jocelyn :   These aspiration of other people not understanding the constraints you live with. In truth, I think it's actually many more than a three-dimensional trade off. I think there's also the number of engineers that you have. I think there's also a performance. When you talk about schedule there's like is the schedule predictable? Then there's also is the schedule frequent? I think those are two different things. How productive is the engineering team is yet another dimension. I think those trade-offs exist, I think you can move the trade-off curves with better tools, and so I think what's wrong with being that crusty engineer is when you accept the trade offs then you don't always see that there's a way to move the trade off curve. I think we should all be open minded about finding those.

I do think that sort of modern continuous integration tools are an immense leap forward on what we had to do five years ten years ago, and really have shifted some of those trade-off curves. I think sometimes it feels like magic and sometimes feels like a free lunch which is what turns us all into evangelists. At the end of the day those trade-offs still exist even if we can shift the curve, and so you just have to start from a place of knowing what you really care about. Knowing what you value.

Edith:     I'd love to hear about just one or two example about how the curve has shifted for you?

Jocelyn : The two really profound changes in the trade off curve have occurred in my professional lifetime. One, was the move from desktop software to web which was transformative. Deploying your code on your own servers that you control versus sending it on a CD to somebody to install it for themselves was absolutely game changing in terms of the cost of the release. Again, not because you had a three week acceptance test process but just because customers were not going to take a new CD from you everyday.

The ability to change our code as often as we wanted, the ability to know in real time what people were doing with our code that was transformational. There were years and years of desktop software people saying, well, the web is fine for sites where you look things up or for search, but it will replace rich interactive, engaging software feature like I have on desktop. Google Maps shipped with the first version of AJAX and all of a sudden it was like wow! This is kind of game over for desktop. Nobody setting out to built software today would dream of building a native client app before they build the web version. You might eventually, if you're lucky you eventually getting around to a Mac client or a Windows client but you certainly start on web.

The second big sea change has taken us backwards which is mobile and we have this whole new generation of software engineers who have grown up with this kind of attitude of well of course native mobile apps are the right thing and web is old and legacy, and because the web cannot deliver these really rich engaging, interactive experiences on your phone that you want, and so far they're right. The native app does beat the web in terms of that richness of user experience, and it's the wrong thing to do to try to coerce your users to use mobile web instead of a native app just because you can ship code faster, because you can have better continuous delivery, because you can change things on the fly.

For now you've got to meet people where they're at, give them the experiences they want and ship native mobile apps, but I do believe that long-term the advantages of deploying code on servers you control. Mobile apps are not as bad as desktops because at least the majority of the brands sit in the cloud, and it's really just the front end that's stuck on the users device, and you also have a better install path with App Stores than we did on Windows.

It's still a significant step backwards to be clear, to have to send your code out into the world to run on somebody else's device versus running on a device you have access to. I think the curve of history will bend back the other way, that we will eventually see mobile web become successful enough, rich enough, interactive enough. That the companies developing for the web will just be able to move faster and deliver more value to users, but it's a bet and it's not the same world as it was the 90s not least because Apple and Google have a different kind of power over their platform. We'll see, it will be fascinating to watch this play out.

Edith:     I completely agree with you, I'll even add that I think consumers don't actually want an app for everything.

Jocelyn :   Well, that's definitely true.

Edith:     I think there was a wave when it was just like everybody Levi's jeans has to have an app. Why?

Jocelyn :  Because you used to buy jeans on levi's.com from your desktop and you don't buy jeans from levi's.com on you phone, and everybody said the solution insufficient engagement, insufficient conversation on mobile web is a mobile app, but the trouble is I'm not willing to have an app for every brand that I purchase.

Edith:     Yeah, you don't want to have a Levi's app and a Nike app you want to go to a site.

Jocelyn :   You want the shopping mall with apps, you want to be able to buy all the brands in one place. This is maybe a good moment to plug one of my portfolio companies which trying to solve this problem, they're called [Dote](https://www.doteshopping.com/) - Dote Shopping is trying to be that sort single mobile app that gives you a rich native shopping experience but combines all the brands that you love. Shout out for Dote.

Edith:     We're almost out of time, but are there any other angel investments that you feel you like to mention?

Jocelyn :   This is like naming your children because there's more than a dozen of them and so I can't name just a few, let's top at one because that problem happen to come up as an example.

Edith:     Thank you very much for coming by. I really enjoyed talking to you, it was great to catch up with on Continuous Delivery and the future and past of apps.

Jocelyn :   Awesome, thanks for having me.

Paul:      Thanks for listening to this episode of To Be Continuous brought to you by Heavybit and hosted by me Paul Biggar of CircleCI and Edith Harbaugh of LaunchDarkly.

Edith:     To learn more about Heavybit visit heavybit.com while you're there check out their library, home to great educational talks from other developer company founders and industry leaders.


