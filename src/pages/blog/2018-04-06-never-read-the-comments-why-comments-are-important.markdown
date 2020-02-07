---
author: Kimh
comments: false
date: 2018-04-06 22:35:28+00:00
layout: post
link: https://launchdarkly.com/blog/never-read-the-comments-why-comments-are-important/
slug: never-read-the-comments-why-comments-are-important
title: 'Never Read the Comments: Why Comments are Important'
wordpress_id: 2473
categories:
- DevOps
tags:
- audit log
- change log
- comments
- DevOps
- troubleshooting
---

In March we visited Atlassian's new Mountain View offices for our monthly Test in Production Meetup. One of our own software engineers, Traci Lopez, opened the session with a talk on how helpful comments can be for getting visibility into why an event happened the way it did, especially when troubleshooting.


<blockquote>

> 
> <blockquote>Maybe you have a clear understanding of where to go, but if someone's coming onto your team you get a lot more context of what the state of the world is and where you should go.</blockquote>
> 
> 
</blockquote>


Watch her talk below. If you're interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/).

[embed]https://youtu.be/Q_ox4oHIQyk[/embed]

TRANSCRIPT

I'm going to talk about comments and this new feature I worked on that we just rolled out and why we think it's so great.

So, a little bit about myself. Like she said, I'm a software engineer at LaunchDarkly and we're always looking for great people. If you know anyone that wants to work off development tools wants to work in Oakland, come talk to me.

Alright, so for those of you who don't know, this is flipping the table. So, what happened last week was I received a notification in our change log Slack channel that someone had turned on the firehose flag for one of our customers that has a bunch of those events that Erin's mentioning in the dev console. So, what this means is basically, we're taking all of these events to third party and that can cost us a lot of money and be a big problem. But, what was great was the person who did this wrote a comment. So, "Hey, I turned on this flag to send all this data because I'm trying to troubleshoot something." And this immediately gives us context into what's going on, so I know who turned on the flag, why they turned on the flag importantly, and we were able to immediately respond to him and be like, "Hey wait, don't do that. That's a lot of data." And he was able to immediately turn it off.

So, okay, I'm done troubleshooting. Great, so this happened within five seconds, you can kind of see the log up there. He could've provided a little more context here, like, "Hey, I collected over 30,000 events, got the data I needed." But that's kind of beside the point. What was great about this was it's immediately giving us some context into what's happening within our application, which is super useful for collaboration. So, I'm a big climber. There's gonna be some climbing pictures coming through. But I think it just lends more into working as a team. You have somebody CLE climbing and you're really trusting that person that's belaying you.

And this comes with visibility. So, why did he turn on that feature plan. Alright, he's trouble tubing something. So immediately, we know what's happening and we also use compliments. It's another way of keeping a good paper trail to understand why we've made all the different decisions to get to where we wanna go. And in this example, see all the different routes that could be taken and why we decided to take a certain route to get there?

So, another thing we have is the audit log, and within the audit log ... so all of these changes are also captured within our change log channel in Slack, but we also have this audit log to see everything that's been going on in application. So, for example this guy said "Flip it." Not that useful of a comment. It's like if I'm belaying somebody and they're saying, "Pull, pull, pull" or something, these aren't really useful commitments, either. We kind of have this understanding like, "Take" means, "Hey, pull up the slack." And "slack" means "Give me more slack so I can clip my boot" or something.

So what might be a better comment is initial launch. So, this is Alexis, he’s our Front End Team Lead. So he's turning on this new feature, rolling it out to everybody, and he's like "Hey, this is our initial launch." I'm like, "Great, you're probably the person in charge of this feature, I know that we're initially going south. If anything goes wrong or I have any comments, I know to talk to you most likely."

And that's not to say that he's not delegating this to other people, because there's a lot of people that worked on it, but with that responsibility of, "If something happens with that flag, I know who to talk to." And maybe if he wasn't the one even working on it, he'll know who to point me to, in the right direction. And that is extremely useful when you're working on a big team of people.

So, to get back to the new feature we rolled out, that I worked on, that we're so excited about, is comments are the context to understand what's been going on in your application. So, if I'm looking back for an extreme example is that firehose flag, I can understand "Why the heck did we turn on this flag?" "Oh, he was troubleshooting something and immediately afterwards, oh, this is done, resolved. I don't have to think about this anymore." I immediately know what was the problem and what was happening, and an easy example is "Hey, I'm rolling out this new feature. We're so excited about it." Great.

Comments can kind of be like a climbing ground, where you have an understanding. If you just show up to the climbing wall, like "Where should I go?" You see all these bolts and you can kinda get like a picture of where you're trying to go, versus if you're already on a team and you're with everybody climbing, maybe you have a clear understanding of where to go, but if someone's coming onto your team, you get a lot more context of what the state of the world is, and maybe where you should go.

So, another example I wanted to bring up, is we do AB testing, and often times if you have some hypothesis of how you think your test might go and that turns out to be really wrong, you're like, "Wait, what happened? What changed?" So, I can go back into my audit log and see if somebody played with targeting goals. Like, maybe we were changing our testing purposes because of something, and that can all be documented right there. So, if I think the testing isn't going how it should have gone, I can immediately see why that happened, who made those changes, so I can talk to them and be like, "Hey, I don't think we're supposed to do that." Or "Maybe that's what we were supposed to do," et cetera.

And this also depends on what environment you're in, so we use LaunchDarkly internally, and when I'm in my dev environment, I'm basically never putting comments in any flag updates in Twig, because I’m probably debugging locally, just turning things on and off, messing around, doesn't matter. And staging, still not really writing comments. We have a change log for staging, but still not as much, whereas in production, every change we make is pretty clearly documented why we're making changes. Besides that flippant comment, but we just rolled this out, so... we're still kind of developing our new best practices on how to use this new functionality.

And that's it. I guess we'll do comments later.
