---
author: Kimh
comments: false
date: 2019-07-31 16:20:27+00:00
layout: post
link: https://launchdarkly.com/blog/api-change-management-feature-flags/
slug: api-change-management-feature-flags
title: API Change Management via Feature Flags
wordpress_id: 194173
categories:
- DevOps
tags:
- APIs
- experimentation
- github
- test in production
---

In June, we hosted our Test in Production Meetup at the Intercom offices in London. Claire Knight gave a talk on how her team at Github uses feature flags to experiment and test in production.


<blockquote>"Another thing that we do is to involve users in experiments.. But this is experiment around things like rate limiting. We're currently exploring changing some of the strategies we have there. We wanted to understand what that would do for specific users, specific pipe traffic users." - Claire Knight, Senior Engineer at GitHub</blockquote>


Watch Claire's talk to learn more about how her team sets up experiments, precautions taken and safeguards they have in place, and key learnings. If you’re interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/events/254964628/).

[embed]https://youtu.be/slBgqZj3STI[/embed]

**TRANSCRIPT**

Claire: Good evening everyone. Yup, we are a sticker company, we don't do software. Just version control and all that. I'm on the API team at GitHub. I slightly contest API endpoints are easy to hit sometimes. Hence this talk, or at least what they do when you hit them. Let's put it like that. I live in Berkshire, most of GitHub is still remote. We are 67% remote and in terms of engineering employees doing anything to the technology, we are probably close to 85% remote. So anybody asking about GitHub for another office, no we don't have one, we're not allowed to get one any time soon. Sorry, you will have to learn to like your own company or work in the coffee shops.

So, feature flagging. I'm pretty sure most of this audience has a bit of what this is. The other talker who came gave a bit of background knowledge. But it's enabling us to turn things on conditionally, not just 'is this user logged in' type of condition.

We have different options at GitHub. We use the Flipper-jack by John Lunamaker. Sorry, LaunchDarkly, nothing personal, this stuff has been in our code base for probably 10 years now, it's been a long while.

So we have specific options that we can turn on for and they are kind of variations in these. But these are the key ones. Individuals is a big one, so one of the examples I'm going to talk to you about in a little bit about the API. That has definitely been used. We also have groups, now these can be special groups, so if you were in the Actions-Beta, any of you. That is a group, to feature flight that on to you.

We have dark shipping to turn things on for an experiment. We also have the gradual roll-out, that Michael covered quite a lot in his talk. So 5%, 10%, in 5% increments.

We also have an enable/disable master override. The enabler's just when you go to 95% or you've got a group and you're simply giving it to everybody. That's when we use the enable for that. And for disabling, it's like uh-oh, everything is going red, everybody is getting paged. Let's turn this thing off.

One of the things that we do at GitHub a lot, is we eat our own dog food. We run our own company on GitHub. It's a thing that people are maybe not aware of, but Legal, HR, people like that. They have to use GitHub issues to do their job. Not the privacy aspect things of HR obviously, but things like documentation everything else we run through GitHub. Issues, merge requests and Markdown files, and the like. And likewise we will pretty much always staff ships on things, before we release it. It does get slightly confusing as a staff member, because can I talk about this feature yet, or not. But it is a great way for people to actively use things in the day-to-day job. And really test it out, rather than just 'I think it kind of does what users want it to do'.

So this is a process we follow. So we have a flight control code change. We have compliance code reviews at GitHub. We have code donors for various files. The code base is huge, we do have some services but the majority of code is still in the monolith. And even in those services we have code owners. So we have people that are... You have to have been there 90 days in one of these teams, they don't put new members on those. But you are taking responsibility to signing off on some kind of functionality. Not literally, if it fails, as bugs do. But still, you are primarily responsible. So, we will often suggest people, put someone behind the flag if we are not sure. Or if it could impact something. This is where it is great having these reviews spread across the company. Because as I said, I'm in the API team, I can talk to you a lot about our regimenting. What I can't tell you is the details is how certain feature set of issues works, for example. Or how project boards work.

So, we make a lot of use of flight control changes, even for small things. Just to be able to then test them on real one day data. We have some customers using our cloud version who have massive, massive numbers of users and repos and large repos within those. And they, mostly, we great relations with all of them. And we will talk to them about trying things out if we're worried about scale, for example.

So doing that testing in production, we would never opt in individuals or groups without prior consent and support of our support team. We call them Support LookOuts. They are brilliant go betweens for us on that. Because generally we are finding if we are helping people with solving a problem, they will say “Can we flag you into this?". To see how it's working for you, have we solved the problem you've got. And have we truly solved it. Probably what we think the solution is. Most people are willing to do that.

We will learn optionally enable for all users. And I say optionally because it could be that we don't want to. We've realized it's not the best solution. Its not linked to scale. Whatever the reason. And we will then have a P-out, either remove the flag or the code. We don't leave these flags in code forever, otherwise our Dashboard will become unmanageable. There's probably only about 5 or 6 groups in a minute. And so many in the scrolling pages of features. Its just not many given the number of developers we have working on our product.

So, kind of the key things I wanted to talk about are flagged API changes. Because we have done some of that in the last few months. So it's kind of fresh in my mind, and maybe useful to some of you.

So sometimes we have to make breaking changes to the API, with no notice. I would like to caveat that before anybody freaks out. We only ever do that in security situations and I could name you one of those in the year that I've been at GitHub's affecting API. So, we don't make those decisions lightly and our security team don't make those decisions lightly. So for those we would never flag them, if it is a security hold we are going close the whole regardless of the impact on you. Because we take that very very seriously.

What we will use flagged API changes for, however, are for changes and behavior. And by that I don't mean something that we need to put into a deprecation cycle in the new version of. But where there is an edge case, where there is a bit of processing that we haven't thought about or a flow-through permissions and abilities and everything else that we haven't thought about.

A recent example of this, is we have a concept of spamming users. We also have DMCA take down requests that we have to honor. Those are repositories that are taken down and they are considers differently from things not existing. And they are also considered differently from UI, from permissions either. We actually tell you that its been taken down in a repo case. And we had user who had a really odd use-case with one of these, where he was gettig the wrong error code and he didn't understand why.

So what we did is we made a change in the resolution that would change the status code, which is a breaking change in Rest API. However, we figured that this would not be affecting very many users if any of them, for the user. We also thought that we actually needed to try with his particular set of repositories, users, the permissions that have been granted, and everything else.

So we put that behind a feature flag and the developer that was working on my team and the person who made the book report, were the only two people that were flagged into that initially. So they did some testing, tried some things out, had conversation through the support channel. And that enabled us to verify that we have made the right fix for him and then satisfy ourselves that we had solved it in a more general case. So then we've got these two people opted in. What our system then allow us to do is say “Okay, we take them out of there or leave them in, depending on your choice”. I think where we took the our developer out of there. But we left the end-user in, so nothing would then change for him in the short term. We then started doing the gradual roll-out. But I won't go over that, because Michael did that earlier.

But then, we also do that and I think we jumped sort of 5, 10, then maybe 25 and then 50 and then a full roll-out for somebody who was asking about that. It's a judgment call, the developers or the managers of the developers, depending on the level of risk, who will make that call. We will be watching dashboards. We will be looking at logs. We will leave stuff running for a period of time. It's not that we flip it to 5% that we give it 10 minutes. It would be nice. We have a lot of traffic through our API, but we need to give it longer than that.

So that proved that feature flights are really valuable for us and then maybe three weeks later. So that is kind of your overall timeline there. We took a feature flag out of the code. But it gave us time to do everything that Michael talked about in terms of being able to roll-back if we have to. To be able to turn it off if we have to. To delay it until we have to do a deprecation change if there was an impact, because lots of people are encountering this and getting the wrong status code. Definitely real value in feature flags for us in that regard.

Another thing that we do is to involve users in experiments. This is not so much A/B testing, though that does happen at GitHub. But as an API team, we don't really have a UI as such. So that's not something we've we kind of concerned ourselves with. But this is experiment around things like rate limiting. We're currently exploring changing some of the strategies we have there. We wanted to understand what that would do for specific users, specific pipe traffic users. We get something like, I think last month, 608000 requests a minute for our API. So we have a lot of volume. But that doesn't necessarily help us see where the- Yes, we can see if somebody is rate limiting or not rate limiting. But if we change the algorithm we are not going to see the difference there.

So one thing is, not myself, I've been working on other things. But, couple members of the teams been working on very very recently is, they've implemented an alternative rate limiter algorithm alongside the existing rate limiting algorithm. And they've opted in certain of our large integrators, who we have good relationships with. So as I have mentioned.

And what we are doing is, we're logging out all of this data to say, they would have been rate limited by this. But they aren't by the existing system, or vice-versa. Or it's all fine. So the differences between the two. And this has been running now for maybe 6 weeks. So we're planning to keep it running for slightly longer, to make sure we can capture a good amount of data. To help inform these decisions.

But this will also mean that we are not gonna just say “Right, we've decided these numbers are going to be great for rate limiting and we're just going to do it”, nevermind the users. We've got two of our databases to do that with and also, I've used and consumed many APIs. I'd be annoyed if somebody did that to me. So we don't want to annoy people.

We do also use and do some performance things for real world scenarios. We have a thing in GitHub we call Science Experiment. Possibly where one of our stickers came from. Although we don't use test tubes in these experiments. Its frowned upon. Health and safety don't want that.

So what we would do is, we would say, if we changed the way we resolve this end point and we can enable that for a percentage of users, although that's done in code. Something different, to Flipper implementation, but the principle is the same. And again we can log things out to our statistics platform, our analytics platform. Push data to our data pipeline and dole a consumer. If we want to run a long term experiment. We have got masses of data that we do use to inform what we do.

And one thing I wanted to say overall of this, is that this is definitely about control access. We have and do abuse, I apologize, previews in our API. Previews should exist for a period of time and then graduate or become pedantic or removed. But that's a different conversation and a different argument.

But we would never do this for something we think should be under a preview flag but we will be able to opt in to using and play around and see what they think. This is specifically about something we need to be in control of. To potentially sort turn of immediately. We wouldn't again from a good API owner standpoint, we wouldn't turn off the preview flag without an application period either. Whereas with the feature flag, everything goes, we will turn it off if we have to, to protect ourselves.

So I would definitely ask you to view those things very differently.

So I just want to give you some closing thoughts here, and let you back to any food that's left. From there, wherever. But it is important to be able to experiment in production. I have had some pride losses that would disagree with me here. But it allows to make progress and it allows you to involve your customers. Now I am speaking from the APIs perspective and we have lot of users and we are in privileged position that we are big enough that we can ask them for feedback. However, we get an enormous amount of knowledge out of that and they intend, most of the time, like being involved and feeling heard. It also builds, kind of, rapport with your community as well. And I think for many of us that's an underrated part of our job. We are not just sit and write code in isolation. Its how its being used and what people want to do with it and how we can make their lives better.

So I've definitely would like to advocate for feature flagging being continuous with lots of testing. Yeah, 15 times a day for test now, continuous deployment to get help. Probably thousands of times a day, kind of a bit more of problem. But yeah, all of that is having not worked with a lot of those before. I'm a huge fan of all of it and I encourage you to explore it if you haven't done any of it, thank you.

Ah, the question was if we feature like something how, how does it ripple effect of that, I think, go across the other systems and into my systems and so forth. I would say it's very easy because of the monitoring that we've got set up. We have many dashboards for different areas and different things. We may use of incident commanders as well as on call shifts who will have maybe an awareness of what's going on. Everybody that is on call, again, you don't do that when you first join a company, you have to learn certain experience. Learns to look at what's recently been deployed and what feature flags are enabled, so I would say that's not something I'm particularly concerned about.

Also if, if it's something that you're changing that you think might impact the database rights, for example, you would talk to the database team beforehand. That kind of level of responsibility is expected of engineers. I get help quite rightly so. I would say on the whole we have the odd blip as everybody does where something is affecting an out of use system, but we are, we have pretty good boundaries and can see where things are starting to fall apart because of the variety of dashboards across different systems. So if it's like, "This is all green but that one's gone red then that's an indicator that certain things might be happening and we would know where to go look.
