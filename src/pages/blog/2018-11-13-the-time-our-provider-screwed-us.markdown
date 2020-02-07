---
author: Kimh
comments: false
date: 2018-11-13 23:16:09+00:00
layout: post
link: https://launchdarkly.com/blog/the-time-our-provider-screwed-us/
slug: the-time-our-provider-screwed-us
title: The Time Our Provider Screwed Us
wordpress_id: 193518
categories:
- DevOps
tags:
- CircleCI
- security
- test in production
- transparency
---

In October we cohosted a special Test in Production session with [Honeycomb.io](http://honeycomb.io/). Since our monthly session fell one night before Halloween, we decided to invite speakers to share their scariest stories of operational outages and other horrors. Though stories of epic failure can be hard to hear, they are invaluable learning experiences.

Paul Biggar, CTO and Co-founder of [Dark](http://darklang.com), former CEO and Co-founder of CircleCI, tells a horrific tale of how a massive security breach nearly ended their company. As a result of Adobe getting hacked, Mongo HQ was compromised, and as a customer, CircleCI was also affected. At one point the team decided they had to completely shut down their service, and no one had any idea how that would turn out.


<blockquote>“So it started with a missing IAM key. Now an IAM key is an AWS identity and access management key. And those aren't things you lose. You don't leave them in your door; they're not physical keys, and so that fact that one of our AWS keys is missing is perhaps a cause for alarm.” - [Paul Biggar](https://twitter.com/paulbiggar), CTO and Co-founder of Dark</blockquote>


Watch the video below to hear how Paul’s team handled this event. Learn how they got through the incident with sage advice around transparency from the “Master of Disaster”, Jesse Robbins. If you’re interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/).

[embed]https://www.youtube.com/watch?v=uDi3zqb3gAA[/embed]

TRANSCRIPT

Paul Biggar: So it started with a missing IAM key. Now an IAM key is an AWS identity and access management key. And those aren't things you lose. You don't leave them in your door; they're not physical keys, and so that fact that one of our AWS keys is missing is perhaps a cause for alarm.

Let me back up a little bit and tell you a little bit about context here. My name's Paul Biggar, I'm the CTO of a company called Dark. Dark, [darklang.com](http://darklang.com/), makes it easier to code. Our goal is making it a 100 times easier to code. We are a programming language, an editor, and an infrastructure that attempts to take all of the accidental complexity from coding. But the "we" in this story is CircleCI. I was the CEO and founder of CircleCI, and five years ago when this happened, I was in charge. I should point out that current CEO of CircleCI would like me to point that I do not work there, I do not speak for CircleCI, and I'm not a company representative. Bear that in mind.

Five years ago, I'm in this building. CircleCI is a Heavybit company. We were two floors up ... when we had the almost company-ending event, the scary event of our first major, and our biggest, security incident. And it all started with a missing IAM key. We looked for all the places the IAM key could have gone. There was no scripts running, there's ... No one got drunk and went to the dashboard and deleted it, so we treated this, as you might ... This is a fully-fledged security incident. This is a scary moment. So we took every single key that we had, every single vendor that we used, and we recycled them. Our standard security policy. And it takes about 24 hours to do that; there's a lot of keys. And we're looking for how could this have gone wrong?

Coincidentally, we got an email from our hosted database provider, Mongo HQ, saying, "Oh, we've had a security incident. But don't worry, you weren't affected." It's Tuesday at two p.m. We've been looking since Monday, and we think that maybe there's a bit of a coincidence here, that we got this email. And so we got on the phone with them, and this is five years ago, I don't remember all the details, so I'm filling in the narrative a bit. So let's say we got on the phone with them, and they told us that, "Oh, actually you were affected, and your database was accessed by the attackers two days ago."

It's been two days, and we saw some other blogs that came out, people reporting their security incidents; Buffer was affected, Intercom was affected, and we have a lot of important data in our database, as do you all. We had user accounts with things like build logs and notifications and things that aren't that important. CircleCI makes continuous integration, and continuous delivery. We run your builds, so we have all the things that we need to run your builds such as the important keys to run your deploys. We have Heroku, access keys and SSH keys for all of our customers. We had 1,000 customers at this point. We have access tokens, and SSH keys for GitHub, so access to all of your repositories. And things like AWS and Stripe, and other keys that you might just have as part of your build.

So the amount of data we have is terrifying, the amount of the access we have. And what's really one of the scariest things about this for me, is things that were leveraged to get here. So Mongo HQ got compromised, and so we got compromised. But Mongo HQ got compromised because Adobe got compromised. An executive from Mongo HQ was using the same password that was in the Adobe password breach. If there's one lesson from this, is to go home and make sure that you're not using the same password for any one of your work accounts as any other account at all, and make sure that everyone else in your company is also not doing that.

But Adobe got hacked, so Mongo HQ got hacked, so Circle got hacked, and then what's next? So we're terrified of this. We have very important customers; we're ... One example that's publicly known is that Stripe was our customer at the time. That's a lot of payment stuff that goes beyond that. So we made a pretty quick decision. That's five p.m. we got off the phone, and we just turned everything off. We turned off every one of our machines, we turned off our builds ... I don't even remember if we let the running builds finish, I think we just turned every machine off.

And that was possibly a company-ending move, possibly a career-ending move. I had no idea at the time how this was going to turn out. So we turned it off. Now, we know we need to tell customers, we know we need to bring it back up, we know we need to do a security review, make sure everything's okay. This isn't exactly our first rodeo, but it's one of our first rodeos, and this is a bigger rodeo than any of us had ever been in for. We didn't really know how to deal with it.

And in probably the largest bit of luck I'd ever had in my entire life, there was a guy in this building, in Heavybit at the time, he's one of the Heavybit partners, he's a guy called Jesse Robbins. And Jesse Robbins is the CEO of Orion. He was previously the CEO of Chef, and before that he had the title ... I'm not sure if it's an actual title or just a nickname, but it was Master of Disaster at a company you might have heard of called [Amazon.com](http://amazon.com/). And he had sat through and been in charge of and all that sort of thing, 35 separate security incidents. This was literally the most qualified human being on the planet to help us solve our problem.

So we got very lucky, and here's what Jesse told us to do. This is ... He literally went on the white board ... I'm not expecting you to read this; I'm going to tell you what it says ... And he told us what to do, so on the right, we see a circle. That is a clock face. And every 15 minutes, I'm to check in with the team and see what the team has discovered. And every 30 minutes, at zero past the hour and at 30 past the hour, we are to update customers. Great, I know what to do.

On the left, Jesse pointed out that we needed an incident commander. That's me, Paul. And this is very good, because I was a big proponent, I think lots of were around the 2013 mark, of flat organizational structures, and so I hadn't really got a handle of this whole being in charge thing. The fact that someone else came in and said, "No, no, no, you are in charge": extremely useful. And he also laid out the order of our priorities. Number one priority; safety of customers. Number two priority: communicate with customers. Number three priority: recovery of service.

I think a reasonable person could have put those in a different order, especially under the pressure and time constraints of the potential company-ending situation. So I was very happy to have those in order. If this is ever going to happen to you, I'd memorize them, maybe put it on an index card in your pocket, in case this ever happens.

The last thing he said is to make sure that we log everything, that we go slow, and that we code review and communicate. His point there is that if we're going to bring our site back up, if we're going to do all the things that we need to do in order to save our business and do the right thing for our customers and all that, we can't be making quick, bad decisions. You can't just upload whatever code is on your computer now, because I have to do this now, I have to fix it. So we set up a Slack channel ... This was pre-Slack; it was a HipChat channel, where all of our communications went. Every single communication that we had about this went in that chatroom. Which came in extremely useful the next day, when I had to write a blog post that detailed exactly what had happened and all the steps that we did to fix it and remediate this, and I had an exact time stamps of all the things that had happened.

So one of the things that we had to do, was we had of these customer keys. What are we going to do with all these AWS keys, the GitHub keys, the Heroku keys? What we did, was we contacted those companies, we contacted GitHub, and we said, "GitHub, we have a security incident, an active, ongoing security incident, and all of these keys are potentially compromised." And there's a fairly obvious thing that we wanted to do here, which is delete all the keys. But they're not our keys. They're our customers' keys, and we don't know if they're using them for other stuff. They shouldn't be using them for other stuff, but people are people. So they're probably using them for other stuff. We don't really have any moral authority to delete all the keys, but it's definitely the right thing for our customers that these keys be deleted.

Fortunately, GitHub and Heroku and AWS and so on took this off of our hands. We sent them the keys, and they deleted them. Takes an hour or two delete all those keys. We were a couple of hours in, and we had most of the security things dealt with, we'd cycled all of our own keys, we'd checked our own things for intrusion logs, and then of course it's time to start the system back up. All the meanwhile, basically what I'm doing the whole time is emailing customers who have emailed me and replying to customers and tweeting things, and generally giving people an update throughout the night.

But it's night at the moment, this happened literally five years ago tonight, and it's the middle of the night, and most of our customers don't really work in the middle of the night. Most of our customers were in San Francisco or in this time zone at least. We had some European customers who were starting to complain, but we're a couple of hours from the bulk of our people coming back up, and we have not turned on the system in two years. We had turned the whole system on two years ago, and then we turned it all off, and I don't know. We spun it up, and we spun it down, and we scaled it, but we had not restarted it ever. I don't know how they did that. Sorry. But it happened.

Came back up, and the next day we wrote [a very transparent blog post](https://circleci.com/blog/mongohq-security-incident-response/). The whole time, we were as transparent as possible. Our customers are developers. Developers like transparency. And we talked to a couple of PR people who dealt with incident response and that sort of thing, and they had advised us to be vague and to avoid legal liability, and all that sort of thing. We decided not to do that; we decided to lay out everything, exact time stamps for when something happened, just do our best, and be as transparent as humanly possible with our customers.

The outcome was we lost almost no customers. We lost two large customers, we lost $1,000 in MRR, which was less than one percent of what we were making ... On the other hand, Mongo HQ, which had not told us the right things, and not told their other customers the right things, lost I'm told ... I don't know this from an official source, but I heard they lost half their revenue. So the distinction between the ... doing transparency well, and doing transparency badly.

The other thing that happened is of course companies fundraise, and they raise money from people, and they have investors. And we were two months from fundraising, and this large stain on our blog, where we posted the incident, was a pretty scary thing. And even though we got through the incident without much loss, there still could have been two months from having to shut the company down because we were out of cash. But fortunately, the investors talked to all the customers ... not all of them, but they talked to customers. And they looked at our blog, and they looked at our fairly professional response to the whole thing, and they decided to give us a lot of money to keep the thing going.

So that's the scary story of Halloween five years ago, at the time we nearly lost our entire company. And it all started with a missing IAM key. Thank you.

Yes, our hosted database provider, which we did not have access to, told us that it was fixed. It's not the favorite way that we would certify to ourselves that we were no longer compromised, but we did not have much choice in the matter.

Yes, definitely. So one of them, and I talked about this in the write-up, and it came up at the time, and I had it in the speech but I somehow forgot to get through it, is that we were not storing all those keys encrypted at rest. So we should have had all of them ... It would have to be symmetrically encrypted, but if you accessed our database, you should not have been able to access those things, and that was a big mistake that we made at the time, and we were too old to be making that mistake. I think we were two years old at the time, and that was maybe a year and a half too long to really have that problem, and possibly even longer than that.

The first thing is we went through this, and we learned how it's supposed to be done, and that's extremely valuable. So the thing I'm going to do if this happens again, is I'm going to do the exact script that we did before. I think one thing as well, is that there's now more information about how this is done. There's a book, there's the SRE book, for example, that goes into detail about incident response and that kind of thing, so there's that sort of thing, but there's ... I think basically, the one takeaway that I have for this that's going to affect everything that I do in the future, is making sure that we have utmost transparency, and also to encrypt our keys at rest.

Thank you.
