---
author: andreaech
comments: false
date: 2018-05-25 21:33:07+00:00
layout: post
link: https://launchdarkly.com/blog/toggle-talk-with-matt-knox-twitter-2009-2014-reddit-2017-now/
slug: toggle-talk-with-matt-knox-twitter-2009-2014-reddit-2017-now
title: Toggle Talk with Matt Knox, Twitter 2009-2014, Reddit 2017-Now
wordpress_id: 193072
categories:
- DevOps
- Feature Management
tags:
- AB tests
- Decider
- DevOps
- feature flag
- feature management
- feature release
- Gateway
- microservices
- Twitter
---

_[tweet_box design="default" float="none"]"My life appears to be the result of some cosmic feature flagging system driven by something like a Chaos Monkey system from Netflix."[/tweet_box]_

Matt Knox has had quite the eclectic career from growing up on a dairy farm, practicing musical theater, studying physics at NYU, running biology labs, and even having done his own startup. All of which led to him moving back to NYC where he learned Rails at scale and helped build Twitter's Decider tool. Earlier this year Matt shared some of his unique viewpoints and stories about feature flagging/toggling with me for the Toggle Talk series.


### **How long have you been feature flagging?**


“Feature flagging” was about the first thing I worked on when I started at Twitter in 2009.  I needed to build it to ship native retweet, for which I was the tech lead.

At the time, people were doing retweets on Twitter, but it was always “RT space @”, whoever's name, and then the text of the tweet. There were a lot of problems, for one, you could lie. I could retweet Barack Obama and make him say something awful that he would never say, like, "Emacs is far inferior to Vim," or something like that, that clearly Barack Obama would not get into.

We wanted to make native retweets to fix this and to do that, for reasons beyond the scope of this interview, we needed to roll it out extraordinarily gradually, to ten thousandths of the user base at a time. 

Two components existed at Twitter at the time that I built Decider, those being Releaser, which allowed you to do fractional releases of things, and Darkmode, which turns things “on” and “off”. 

The two systems couldn’t support this change. Releaser didn’t support the level of granularity, so I knew I was going to have to do some pretty invasive changes to the Releaser code base. I also knew I needed to be able to shut the feature off really quickly, so I ended up having to find those two things, extend them, and then add new things.

I decided to build Decider as a single library, based on the idea that Releaser and Darkmode—they're just telling you whether you should or should not follow a code path. That seemed like obvious duplication, and I saw lots of cases where one or the other was there but not both.

_[tweet_box design="default" float="none"]"Obviously we want something to help you fractionally release something, but then if things go terribly wrong, turn it off."[/tweet_box] _

So that was when I started doing “dynamic decision-making” with a new combined system called Decider. The core of the work was done in about a day. It's not a ton of code, assuming you don't have to worry about where you get the data from to do your decision-making. Then that system was more or less unchanged at Twitter for several years. I continued to maintain it a little bit and it got extended/re-implemented by me and Brian Wickman, who was at the time a new Twitter employee who had just come from Google. Wickman came up with a really nice way of rewriting it so that it was much easier to understand and to extend, and then it much more interesting.


### **What do you prefer to call it and why?**


Dynamic decision making is what I call it. If you want to do a multi-way decision, like A/B testing, should this feature be on or not, you can have a chain of decision-makers. Each decision-maker can be passed the relevant data to make a decision, and it will either return true or false for whether it has made a decision. If it's false then it hasn't made a decision and you should go onto the next. Decision-maker number one says, "I don't know, I can't make a decision, go to the next one." And then eventually somewhere along the chain, you come to a final decision. If you walk off the chain, there's a default answer.

I'd never heard the term feature flagging at all. So this was independently invented, I mean, I knew that there were A/B testing systems somewhere, but it didn't occur to me at the beginning that A/B testing was a special case of the more general dynamic decision-making.

Not too long after that I realized that this also made sense for A/B testing. Understood that way, this kind of dynamic decision-making is just incredibly valuable in so many different contexts. It's needed, certainly for obvious things like turning features off, and doing A/B testing, but also for things like migrating from a monolith to a more micro-service type environment, or the opposite.

_[tweet_box design="default" float="none"]“The important difference is that this is a non-Turing complete thing that allows you to choose from a maybe large but finite set of spaces, a finite space of code, and it allows you to do it without doing any deploys. That to me is what the dynamic decision-making is all about.”[/tweet_box]_


### **When do you think feature flagging is most useful?**


It really depends on what size you are. If you're really small, monolithic and you don't have a lot of traffic, you probably can't really do A/B tests. Really the only thing you'll want to use it for is dynamically switching something on/off. Maybe you want to use it because your startup is about to get an article in TechCrunch and you want to put up a banner that says, "Hey, TechCrunch users, thanks for coming and checking us out. Here, go look at this link." Maybe you don't want to do a deploy to make that happen because you're terrified the site will be down while TechCrunch-ers are coming or whatever. And that, actually, I would call feature flagging.

As you get bigger, A/B testing starts to make sense. Also if you have a microservice/service-oriented architecture of whatever your system is, virtually guaranteed you're going to want to be able to turn off calls to a given end point. For example, if you're implementing a Foursquare competitor, you're probably going to have something that says, "Given this person's location, let's tell them where we think they are." One thing that happens is that you deploy to a service, and then because there's a bug, it goes down. Then when it comes back up you want to make sure that it doesn't get overwhelmed by a “thundering herd” of clients trying to talk to it all at once. One way to do that is to say, "Let's turn off all the traffic to that service, turn the service back on, then slowly run traffic back up."

That allows you to deal with thundering herd problems. And then when you get really, really, really big, you tend to use it for everything.  For example Facebook uses Gatekeeper, their dynamic decision-maker to deploy changes thousands and thousands of times a day. They use it for everything, changing DNS records and network configuration and how to get to caches and stuff like that. So it really depends, there's one use case per size of the company. But there's not one use case overall.


### **Best use of a feature flag - a personal story?**


I have plenty. I worked on growth at Twitter so I worked on a bunch of experiments, which all used Decider.  Of course, we literally could not have shipped retweet without using Decider. If I'd tried to ship without it, the entire site would have been down for days. So that was about as big of a deal as anything I can possibly imagine. 

Separately, when I was an on-call engineer, whenever things broke we'd start shutting off the expensive code paths, and that helped a lot too. As far as user things, yeah, there was a bunch of this every time we did experiments. It's a tool that beyond a certain size you just cannot live without. At least I can't.


### **What do you think is the number one mistake that’s made around feature flagging?**


I think a lot of times companies independently reinvent them. At Twitter, for instance, we'd never heard the term feature flagging. I didn't know anything about Gatekeeper or any of the other systems from other places. It's a fairly simple idea, so it's not that surprising that lots of people can have it independently. But as your company grows, you're going to start hiring people from big companies, and they all will have known about the feature flagging thing from their company and found it very useful in those larger contexts.

_[tweet_box design="default" float="none"]“The number one mistake is probably not cleaning up after yourself when you do this. It's really, really easy to leave your code base littered with if-statements.”[/tweet_box]_

You know, like, "If feature available, do this thing." It’s easy for those to accumulate in your codebase.  And the risk of that code is compounded if you use unreliable storage for the configuration that tells you what's available and what's not. For instance, at launch Decider was only trying to store decisions on a very, very short basis. It should only store a decision for a day or two, or a week at most when we would be gradually rolling something out. Eventually it would be fully deployed and then we'd go through and take out the “if” statement.

But in practice, you often end up leaving the “if available” calls for a long time. And then you end up with a risky situation. That is if a Memcached instance—the one that stored whether a given feature was available—goes down, it can change the site pretty dramatically. In a case where there is an expensive version of a database query and a cheap version, and you’ve Decidered 100% of calls to use the cheap version, everything's fine, but then late at night some weekend that Memcached falls over, and now the site is pointed back at the expensive query, and all hell breaks loose.  Or worse, maybe because it’s late at night, traffic is low and it doesn't fall over immediately, it falls over the next morning for no visible reason that you can see at the time.

_[tweet_box design="default" float="none"]“Failing to clean up after yourself is really, really tough. And as I said, makes it a lot worse if you don't know, for instance if you don't have durable storage for what your decisions are, then lots of things can be really chaotic.”[/tweet_box]_

So, number one is not cleaning up after yourselves, that is exacerbated if you don't have durable storage. If you don't have durable storage, then the result of calling Decider.available() is going to be dependent on what has been going on with your storage.

Then there's a long-tail of lesser problems. If you’re really serious about testing, how do you  make Deciders run both “on” and “off” in your tests? That can be very quickly a combinatorial explosion in how much testing you have to do. That's a pretty big challenge.


### **How do you think feature flags play into the DevOps movement? Continuous Delivery?**


I think it's a big deal for both. People doing DevOps typically do a lot of sloshing traffic from one bucket to another, and things like that. Those are dynamic configurations, they're just being done in weird ways. I think Facebook typically does a really good job at this kind of infrastructure. By unifying all those kinds of things within one tool, Gatekeeper, they made one interface that people have to know really well instead of a million different interfaces. Maybe you're manually writing DNS records to make something go from one set of servers to another, but it would be better for you to have some tool that did made the change, logged everything, and helped you revert when necessary.

It's difficult to imagine doing modern DevOps without some kind of dynamic decision-making. With dynamic decision making you can have the effect of having thousands of deploys a day with just a single developer, if that developer is slowly nudging up the rate at which some given feature is available. I did exactly that-nudging retweet up a hundredth of a percent at a time, and I did that for hours and hours while checking that the site wasn’t down.

I think it's incredibly valuable at any company beyond a certain size, but particularly if that company wants to deploy network services very frequently—which is a good idea for lots of reasons—and then dynamic decision making is also incredibly important.


### **Are you seeing feature flagging evolving? If so how? And how do you expect it to change in the future?**


I believe that there'll be a really good multi-language version of this that is available both as a library and as a network service that will allow companies to self-host or call out. I think probably this year or next there'll be one or more big open source projects that do this. It’s hard to do with traditional open source though-I think it's going to come from inside a large company that open sources their own thing, as opposed to something that people just build on their own. You only need this if you're controlling at least a modest-sized property that has lots of complexity and you need dynamic decision-making.

Like you were saying, it can be that one place where everybody has a source of truth. It can also sort of be a force multiplier for non-technical employees. If you have some marketing people who have the power to turn “on” and “off” various features on non-technical parts of the site like onboarding prompts or links for a scheduled promotion, or if at the moment of your founder’s big reveal on some stage you want to turn some feature “on”. For all these things, it’s very important to be able to roll those out without requiring a deploy. It’s perhaps equally important that if it screws up you can turn it back “off”, again, without requiring a deploy. 

_[tweet_box design="default" float="none"]“It allows the developers to play Prometheus. They can give fire to the mortals. We’re certainly not gods, but I do think the giving non-developers the ability to make a thing behave differently is pretty powerful, and something I think everybody should get to do.”[/tweet_box]_


### **Anything else you’d like to mention?**


It’s important for companies to try. I think that a little planning can help a lot on this, and if you let a company get too big before introducing this dynamic decision making system you’re gonna end up with two or three of them, and they’ll be different, idiosyncratic, and won’t particularly play well together. Sometimes it’s okay if a revenue team wants to develop their own system for turning ads “on” and “off”. Maybe that’s okay because it’s not balled up in the main thing. If you can see three different teams needing this on different timelines, then it’s probably a good thing to make the first system to serve all three teams at least reasonably well. If not, you’ll end up with three different systems that’ll be kind of annoying. 

_[tweet_box design="default" float="none"]“If there’s three sources of truth, there’s no one source of truth.”[/tweet_box]_
