---
author: Kimh
comments: false
date: 2018-09-11 20:30:15+00:00
layout: post
link: https://launchdarkly.com/blog/the-billion-versions-of-facebook-youve-never-seen/
slug: the-billion-versions-of-facebook-youve-never-seen
title: The Billion Versions of Facebook You’ve Never Seen
wordpress_id: 193348
categories:
- DevOps
tags:
- A/B testing
- Facebook
- feature flagging
- feature management
- feature release
- gatekeeper
- test in production
---

At our July Test in Production Meetup we focused on testing systems and processes at scale. Girish Patangay, Manager and Engineer at Facebook, kicked off the evening with a talk about how Facebook manages different versions of its platform in the real world.


<blockquote>“This talk is about how not all Facebook looks the same. Even in this room, all you folks have different versions of our software, mainly because of Gatekeeper. So if you think about this, each person just has a slightly different version and the way we use Gatekeeper, even today, is almost everywhere through our entire stack.”</blockquote>


Watch his talk below to learn more about what happens after you roll out a feature—after you’ve released it, what you do when you want to tweak it, what you can see, and how you can make it better. If you're interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/).

[embed]https://www.youtube.com/embed/eXGgc79sGwY[/embed]

TRANSCRIPT

My name's Girish. I've done a few different things at Facebook, and kind of wanted to give you a brief intro of why should you listen to me. So, I started out as an engineer at Facebook. I was one of the first release engineers at Facebook. Took the site from about 100 million to close to, probably like 700, 800 million users before I moved off of that role. So I saw quite a bit of growth there. I wrote a lot of the tooling that Facebook still uses.

And then I went into developer infrastructure where I focused ... So the team managed a lot of the source control tools, a lot of the tools that the developers use, including tools like Gatekeeper and others that we do use regularly in our production environment, so I built the team around there, and then I also worked in Ads Reporting, as a consumer of all the tools I built and now I work in Building 8, which is not a building, it's an org inside Facebook that builds consumer hardware. Unfortunately I can't talk about what I work on currently, but I can talk about the past which I'm happy to share.

So this talk is a lot about how Facebook, not all Facebook looks the same, so even in this room, all you folks have different versions of our software, and mainly because of Gatekeeper, so if you think about this, each person just has a slightly different version and the way we use Gatekeeper, even today, is almost everywhere through our entire stack. Not just on our web stack. Not just on our front end mobile stacks, but even permeates down to our services stack.

And a lot of that is based on, kind of, early learnings where... our release engineering process really drove this mainly because our release engineering ... we never wanted to tie a code push to a future release, and that was just always in the core of the inception of all of these products, and so we started building all these tooling to make it really easy to launch features. And that kind of spiraled into, "Hey, we need to do more AB testing. We need to do more experimentation." Now we use Gatekeeper for a lot of things.

So Gatekeeper's pretty simple. Hopefully you guys, if you're familiar with LaunchDarkly, pretty similar to the same thing, and you know you just run a GK_check on a particular user. You don't even need a user, you can do it on pages. You can do it on other entities that we have, so as long as it's a unique id, it'll work. And what we use it for, a lot of testing and rollout. This is the primary way engineers get features out in the world. They start rolling it out to their team or their core team members and then after that, they go to all employees and then they kind out try out different pockets of users where we think we will get good traction on this feature and then slowly we'll start to roll it out to production. All of the user base.

We use it for policy and laws. For example, in Europe, the data protection laws are a lot higher than in other countries. We try to have a minimum bar across the board definitely, but in certain instances like for example, face recognition in Europe is different than the face recognition in the US or the rest of the world, so we use Gatekeeper for that.

We use it for load testing, especially the back end services. So for example, when we're rolling out a new version of News Feed or Search, it's really important to us to kind of shadow traffic, so we will fork traffic ... It definitely costs a lot of money, but will fork traffic coming from our web service to create two different sets of machines for the same data. We throw away the new one, but we try to analyze what the data set is. Is it different? Is it better? And we can do a lot of those types of tests with this feature and it's not just used as an if-then statement. It's also used as a "Go grab this, but hide this away from the user" statement.

And then experimentation. I looked around on the web on information about Gatekeeper, about Facebook and how we roll out features and a lot of it was around the rollout of features and what I thought would be interesting for you folks was how to do we do experimentation? 'Cause Facebook is a pretty unique opportunity where we are getting more than a billion users hitting the site every day or using our apps every day, so the experimentation at scale tends to be a little different than experimentation at a smaller level.

I kinda wanted to talk about what happens after you roll out a feature. Now your feature's there, but you wanna tweak it. You wanna see, can you make it better. So, for example, quick ... so our tool is called Quick Experiment and it's really used to launch experiments really quickly so developers don't have to do... write too much code or worry about how to analyze these experiments and it works across the board, across all our platforms. So you don't have to write experiments for each platform separately and at any given time, thousand is probably a low-balling figure, we have tens of thousands of experiments running on Facebook, so that's kind of why if you look at the combination of those, not any two people will probably have a different Facebook experience.

So for example, this is just the title of News Feed. You can see all the different variations we've tried and we use this to really inform us on how to get to ... what the feature was really designed to do. Either retention or user engagement or kind of just ... getting a person to go click on that bar. And in this case that actually is a search bar as well so when you click on it, it turns to a search bar. So these are all the different treatments we had for it.

So Quick Experiment works pretty simple to how Gatekeeper would work. So there's ... the big difference is Gatekeeper is binary and Quick Experiment is actually built on top of the Gatekeeper infrastructure and Quick Experiment returns key value pairs. So, it's really easy to kind of do a little bit more complicated experimentation. The other thing Quick Experiment gives you is automatic exposure and conversion tracking, which is really important because developers hate writing logs and hate collecting logs and figure out how to track them back to their experiments.

So of all of this stuff gets piped into our Quick Experiment framework and then it gets channeled into real-time graphs. We have a tool called Scuba that does real-time analytics. You can read about that and then we have another tool called ODS which is much more long-term analytics so it also gets stored into that so hive-type storage. So you could go back a year or two ago, but Scuba would be on the last 30 days, so you have kind of both of those and that really sets up the framework for our AB testing.

So to give you an example of how to start, what you would do is you actually start by limiting the audience. Obviously Facebook has a massive user population so we don't start off the experiment with everyone. We try to limit as much as possible so that the experiment can run in a much more controlled environment. And also, where the feature's really gonna be used so we don't launch features globally all the time. So you could have a feature that's only in the US or only in parts of the US that we could control using Gatekeeper. So the first step is you setup your Gatekeeper for the experiment.

And the second step is ... This is kind of the important one, is you come in and you can set up factors. Like all the different factors you can do, you can have uniformly distributed factors or you could have weighted factors and in this example here, there's three uniformly distributed colors and two text parameters that are weighted, so the bottom is kind of a distribution graph of how all these experiments are gonna run. And the Quick Experiment platform will go figure out, "I need to run these six different control groups and a control group as apart of this experiment and give the results." And then all of that kind of gets piped in and does the real-time analytics.

The other thing we do is ... just one experiment is not enough. So we have this concept of a universe, so we divide all of the user base you have selected. So it could be the US, or the world, and we divide them into about 10,000 different segments and then you get to come in and pick how many segments you wanna use for a current experiment. So in this example, for instance, the universe was divided into a lot of larger segments and there were other experiments running before the green experiment that I highlighted came in.

So all those whites were empty experiment segments that weren't used, and now someone wanted to run another experiment on top of it and they got those five other segments taken up and then they go run the experiment on that. And this really helps us contain experiments, so if you already burnt out a few users by showing them ... and you tainted them by showing them earlier iterations of your feature and then you come in and you modify it, you don't want to show it to the same set of users. You wanna go after different segments and this tool really makes it easy to kind of define this in a programmatic way.

Yeah, and this is another shot of Scuba that we use. It's really handy. Scuba lets you drill down over a lot of different attributes that we automatically log, browser type or mobile device type or the build version. All of these different areas where you can narrow down what the experiment graph is really telling you. And there's definitely a lot more to this than the screenshot, but I can't really ... without using it, it's hard to understand the power of Scuba, but it really helps us pinpoint what worked and what didn't.

So, yeah, and the other thing Quick Experiment lets you do is translate its strengths, so you don't have to ... as engineer, don't have to worry about translating strengths ... in the parameters you can put in are translated language and it will convert it, in this case, it did the translation and then it will show it on the product in the way that it was designed to. And all of this is kind of taken care of by the platform.

What are the hard parts? I think the hardest one is we give a lot of responsibility, a lot of flexibility to the engineers and the data scientists and that's where we definitely hit a few snags where they do tend to not realize the cost of each of these experiments, or end up abusing them unintentionally. We haven't had any malicious use, but definitely unintentional cost and we try to make the user interface and the tooling very simple to understand what you're doing, but it definitely has its drawbacks and then again, the infrastructure for storing all these logs, the real-time nature of the graphs, all of these cost the company, so the product teams versus the infra-teams, there's always kind of this trade off. Is this really worth doing versus let's just go roll with it.

The last one was mobile. We've had ... just the nature. I mean anyone who's double-up mobile is very familiar with this graph. This is a graph of all the android builds running out in the wild for Facebook over the last years and you really want that orange or that tan color to be filled all the way, but as you can see, the bottom segment is just really old builds, like years and years old that you can never get rid of and experimentation makes ... If you had a bad experiment or something that hasn't worked well, it's just gonna linger along for ... until the end of time, so mobile makes it really complicated. We are trying to move to more react-native to help kind of curb that sort of thing, but again, that's in the works. But that's ... to give you a flavor of how Facebook runs experimentation and hopefully I'll give you more information during the panel. Thanks guys.
