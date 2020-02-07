---
author: andreaech
comments: false
date: 2018-10-05 18:22:23+00:00
layout: post
link: https://launchdarkly.com/blog/test-in-production-a-panel-discussion-on-chaos-engineering/
slug: test-in-production-a-panel-discussion-on-chaos-engineering
title: 'Test in Production: A Panel Discussion on Chaos Engineering'
wordpress_id: 193423
categories:
- DevOps
tags:
- chaos engineering
- Gremlin
- LinkedIn
- Netflix
- resilience engineering
- test in production
- TIP
---

_Originally published on [The New Stack](https://thenewstack.io/netflix-linkedin-and-gremlin-engineers-talk-chaos-engineering/) on Aug 28, 2018._

At LaunchDarkly, we host a monthly [Test in Production Meetup](https://www.meetup.com/Test-in-Production/events/251314415/) in the Bay Area where we ask teams to show how they test in production and share learnings and best practices around doing it safely. We recently sat down with engineers from Netflix, LinkedIn and Gremlin to talk about chaos engineering.  

Honeycomb CEO [Charity Majors](https://thenewstack.io/serverless-testing-in-production/) is one of the biggest proponents of testing in production. She describes it as: “When I say ‘test in production,’ I don’t mean not to do best practices first. What I mean is, there are unknown unknowns that should be tested by building our systems to be resilient."

Our June meetup was focused on chaos engineering. Guests kicked off the discussion with how their teams think about chaos engineering. [Nora Jones, senior software engineer at Netflix](https://launchdarkly.com/blog/testing-in-production-the-netflix-way/), talked about the chaos engineering tool Netflix developed for its own teams. [Ted Strzalkowski, senior site reliability engineer (SRE) at LinkedIn](https://launchdarkly.com/blog/request-disruption-at-linkedin/), discussed how his team is focused on providing a comprehensive, automated and measurable resiliency feedback loop. And [Pat Higgins, UI engineer at Gremlin](https://launchdarkly.com/blog/great-gamedays-thinking-about-failure-holistically/), gave a talk on resilience engineering and thinking about failure holistically. And then to wrap up the evening, Shantanu Joshi, senior software engineer at Twitch, led a panel discussion with our guests.

Here is Higgins’ summary of how chaos engineering  can serve as a very apt tool among security best practices: 


<blockquote>"Chaos Engineering is obviously quiet. It's still nascent. It's still quite a new concept for the mainstream. So for us there's also a pedagogical issue to consider. So in the way that we think about how you can run attacks on our platform, we also want that experience to be instructional. We want users to have the best experience. We also want those interactions to be simple, safe and secure, essentially. So we try to develop a user experience around those values as well." </blockquote>


Watch the video below to learn more about how these organizations enable their engineers to run chaos experiments and get valuable feedback they can actually use.

[embed]https://www.youtube.com/watch?v=YJVXtkE63c4&t;=5s[/embed]

TRANSCRIPT

Shantanu: While watching the talks [before the panel discussion], what struck me was the importance on order and the Chaos, having tools and monitoring and dashboards so that you can have a lot of safety. Thinking of that, I see two big chasms between where you start...essentially when you start Chaos Engineering at a company, you might work with  consultants more than with teams. And then Linkedin and Netflix use are very self-service. How do people bridge that chasm? And how do you get a buy-in for that long process?

This a question for the whole panel, I guess.

Nora: Yeah I can start. So it's a really interesting question. I find that, as someone who is on a centralized team regardless of it being a Chaos Engineering team or a site reliability engineering team or a DevOps team, you kind of have to put on a consulting hat sometimes and you have to put on your sit down and put on your headphones and code hat, sometimes. Yeah, we are making the tools very self-service now, but we also want to have insight into how people are using them and what's inspiring them to take action from these tools.

I have weeks where I am completely consulting with teams and then I also have weeks where I am completely coding. But I would argue that at any stage of the process that your company's at, that's very important for a centralized team to do is to be talking to your internal customers, your coworkers, and finding out what kind of things keeps them up at night. What're they afraid they're gonna get paged about. How are they using these tools. What's giving them more confidence going into critical periods like Black Friday or the holidays or what have you.

Ted: Along those same lines, we do a lot of that consulting time. I would say it's about 50 percent of our time currently.

We definitely see the internal customers as who we're building these tools for. And when we sit down with them, the first part isn't about how they're using our tools. We don't want to force that as a solution because it may not be the right solution. So what we start with is with just a customer insights interview. What are their problems? What are they looking to reduce in their problem atmosphere? And kind of figure that out. And we try to distill that down to user stories so that then we can take that and determine whether those are features. When we start to see common themes from one team to the next, those are the features we need to develop.

Then, once we get that information, without the bias of our products, then we introduce our products to them. If they haven't used them, we demo them on the spot. And then we ask them, "How do you see yourself using these? What problems that you just went over do you think these would solve?" And sometimes that makes them have an “aha” moment where they say, "Well actually, that'll solve this other problem that I forgot we had."

And then the same thing. Coming up with user stories again that kind of feed into, to validate the features you built so that we can then talk about how our customer engagement is internally.

Patrick: Obviously from our perspective ... bridging that gap is obviously a business interest. And I agree with everything that Nora and Ted said. Like Ted said, we do look at, essentially the interactions that our customers are having with our product. And that does inform some of our decisions from a product-perspective. Particularly when we ask them what kind of data they'd like to surface, as they're running attacks and essentially seeing the result of those attacks.

There's also another element to it, which is that Chaos Engineering is obviously quiet. It's still nascent. It's still quite a new concept for the mainstream. So for us there's also a pedagogical issue to consider. So in the way that we think about how you can run attacks on our platform, we also want that experience to be instructional. We want users to have the best experience. We also want those interactions to be simple, safe, and secure, essentially. So we try to develop a user experience around those values as well.

Shantanu: Thanks, guys. A couple of follow-up questions, I guess. Patrick, I found your talk interesting because I wouldn't have associated front end with Chaos Engineering, so that was really eye-opening.

I have a question on game-day for you.

Patrick: Yep.

Shantanu: Given ...I assume it's your whole company running Chaos experiments on the Friday. How do you prevent a thundering herd of Chaos experiments from taking over and bringing production down?

Patrick: So we don't necessarily have to run the experiments in production as well. Obviously testing and production ...essentially that's the final goal for Chaos Engineering.

When it comes to UI, failure doesn't necessarily have to occur at that level for me to see the things that I need to fix. Sometimes it does. And that's really dependent on... the thing about Chaos Engineering I think is that the real-world perspective, the real-world experience is an incredibly important part of it. I guess the answer is that I'm not breaking production on a Friday at three o'clock. These kind of experiments take place in a time and a place that is comfortable for the people doing the experiments and the people who essentially have to address them.

Essentially our goal in looking at proactive failure mitigation is to make sure that we're dealing with failure at times that are comfortable for us, rather than at 3:00 AM in the morning. So, I guess to sum it up, my answer is, "we don't do that."

Shantanu: Final question before I open it up. Ted, it looked like from the talk that currently failures are injected on the RPC client layer. Is injecting them on the server layer something that you're considering? And sort of mocking out the failure.

Ted: We get a lot of requests for that from our users. And we're a little skittish about implementing that today because implementing it at the request layer gives us an automatic blast radius limit. In the interest of safety, we haven't yet. We think it's something that we'll evolve to once we start to get a better picture of what's going on and where we can fix things and how we can fix them. And we start to address some of the more critical endpoints, then we'll be more comfortable. Because it turns out that customers that are coming to us asking for server-side disruption are the ones with the most critical services to our staff. And so, at this point the only reason we don't is purely based in fear.

Shantanu: Sounds good.

So we're going to open it up now.

Nora: I would probably set up Monocle from the beginning. We had about a year and a half, maybe two years, where we would sit in a room with people and spend three hours coming up with what makes a good experiment. And then we'd put it in a Spinnaker pipeline and it would run on deploys but we wouldn't look at that configuration again. And the users wouldn't look at that configuration again. And we have four people on our team so it was a lot of ... we didn't have a lot of bandwidth to do all of this consulting. So I think figuring out what makes a good experiment and what's actually good to prioritize and figure that out, would be good information to make from the beginning.

We started Chap because we had built this other service beforehand called Fit, which didn't limit the blast radius. And so if I was way going back, I would start by limiting the blast radius and keeping safety in mind from the very beginning. You know, it's actually really easy to build this tool and cause chaos. The hard part is to actually limit the blast radius and monitor what needs to be monitored in these situations.

I don't know if I would change things, but I would maybe change the focus a little bit.

Nora: When I use the word “vulnerability” I mean, "an issue hasn't become widespread yet." So it's something that we see as an issue, but it either only impacted a small number of customers or it did cause an issue but customers didn't notice. It gives engineers the time to actually sit at their desks and not be under the fire of a pager or people on Twitter going, "Netflix is down, my life is over." They do do that. We've talked about implementing a "go play outside" message ... when it does fail.

That's what I mean by vulnerability. And we're actually trying to figure out a way to easily service vulnerabilities to teams. You saw that Monocle screen I put up. I could pull up certain teams Monocles and see probably 50 vulnerabilities. But if you hand a team 50 vulnerabilities, they're probably not going to fix any of them. You know what I mean? So you have to figure out a way to prioritize those ... figure out a way to show them, "Hey, this is actually a very important thing that you want to fix because it's only a matter of time before it could actually become an outage and it could end up on Twitter."

Patrick: I think that's about getting them in the room for the game-days. And that's all that I'm advocating for. It's making this an entirely inclusive experience where you do get product managers in the room. You do get designers in the room. And obviously if people have a less technical background...they may not take everything in that's going on. But there's an opportunity there for a pedagogical side of performing these experiments. Not just to understand the way that the failure's functioning, but understanding the stack more generally.

Patrick: One of the interesting things, or the important things, about Chaos Engineering is that it's a practice. It's continual. Doing it once is not really an effective mechanism. So it needs to be something that is practiced on a regular basis. Perhaps like a gym membership or musical instrument. You can't just play a trumpet for 36 hours and be really good at it. It's really about...what I'm trying to encourage is this idea of thinking about failure from an organizational perspective and creating a culture around it. Doing these things on a regular basis and keeping that kind of collaboration going.

Ted: Some of the things we're doing..we call those the “critical path.” We're looking at default responses so that you can at least mock some data to show to the user it might not be the right data. Other things are to completely hide that data completely. Like Patrick was showing earlier with Twitter, the card, that's normally considered pretty critical information but it's just missing. And sometimes the user just even notices that.

Nora: Along those lines, it's to always make sure you have fallback paths in place.

At Netflix, when you log in to your Netflix you see, "Here are Nora's recommendations." And sometimes that row fails. And if that row fails we don't take all of Netflix down, we just show you things that most people like. So that's what happens there instead.

So I think if you're experimenting on those kinds of things, it's important to make sure you have some kind of fallback path in place. We have those services in the critical path too and we never run failure experiments on them because we know they're actually going to fail, and it's not going to be a good experience for the user. We do run latency experiments on them. So we'll add time in between those calls and see that it's still functioning properly and not actually opening that fallback path in that situation.

Nora: Yeah, that's why we're automating a lot of it. What we found was our users, our internal customers, didn't have enough experience in these areas to come up with a good experiment. They would actually pull us into the room a lot of the time, which we weren't expecting from the beginning. We thought, "They're this service-owner, they know what to test here," but it's not always the case. And it's actually a lot of information for the user to come up with, what makes that.

Our initial configuration page for creating a test case was very complex. It probably prevented some people from using it. So I think automating, filling out that information and automating running it and having that just move into an opt-out model has been good. That has really helped. I think most teams end up trusting the Chaos Engineering team or the tool as the expert, and they'll be called on as needed in that situation. It's definitely good to involve them, but what I've found is they want that realm to be simple so that they can trust it and not put a lot of thought into creating those experiments.

Patrick: On Nora's point, I think that is the thing that keeps us from, as you said, "making this configuration harder than the product itself is." Essentially, we're trying to incentivize these practices. If we make it too hard to do, people won't do it.

Ted: And that's why we developed the Chrome extension, to push that kind of discovery stage right onto the user's browser. They already know, right off the bat, that their blast radius is limited to their browser session, so they're not afraid to test anything. What we see in our user monitoring from the Chrome extension is that most people start by failing everything. And it's like, "Of course that's gonna blow up." And then they start “un-checking” things. But it's good to see that because it shows that they're engaging at that level and they don't have any fear. From the Chrome-extension, they come up with the actual sane failure plan and then we're adding the ability for them to export that to the automation framework.

So, same idea. A lot of the users come to us asking us, "How do we do this?" And now we can say, "Here's a tool for you to learn," because there's only three of us.

Ted: I'll answer the second part first. For new employees, we have a bootcamp where we onboard new engineers. We introduce them to the tooling right in that bootcamp. So on day three of their time at LinkedIn, they're already exposed to the tool sets. So they see that we have these available to them. It’s minimal blast radius and a go-play-with-them-tomorrow type of idea there. And once they get into the stack and they start actually writing code, and an outage happens, we sync up with them and we try to replay their outage once they say that they've fixed that from happening again. And that reintroduces them to the tool set, so that they can say, "Oh yeah, I really did fix that and now I can check for regression in the future."

Nora: I've experienced that a lot with the configuration things I've found. We've found that people's timeouts are too high or too low. And it's very easy to just go in a file and just change your timeout to 500 from 400 and then close the Jira ticket. But there's a reason why you did that.

What I ended up finding in a lot of situations is... we've taken a role as Chaos engineers to dig into the "why" a little bit at Netflix, as well. Like, "why is that even happening?" And one interesting thing I've found is that engineers didn't want to spend a lot of time setting up their new applications. So I would see people taking a configuration file from a service that looked similar to the one that they were building and copying and pasting the whole thing and putting it in their file. Because they just wanted to be done with that part. And that was really interesting learning. They can easily keep changing...or we could even submit a pool request from Chap to change their timeouts for them, but it's an interesting learning that was the case.

I think part of that is to dig into the "whys" with teams actually, actually interviewing them if you're seeing patterns across things. We've actually built into our tooling, "okay, here are the certain types of patterns that we're seeing." Now we can ask certain types of questions to teams afterwards to help them learn from incidents and to learn ourselves from incidents and why they're exactly occurring.

Patrick: Just from a...maybe just like a little bit more of a theoretical perspective. Because I can't actually speak to general circumstances as much as people who are dealing with users who are coming from one organization specifically, but Chaos Engineering essentially has a cyclical quality to it where we have an experiment and the point at which we find a failure...we undergo a course of remediation and validation. So from our perspective at Gremlin, trying to instill these norms of remediation and validation is a super important part of the process because we want businesses to essentially see that Chaos Engineering does have a business value for them as well.

Nora: I worked at a startup before Netflix. So Netflix has been doing Chaos Engineering since 2011 roughly. And I started it at a startup, which was chaotic every single day. I didn't end up setting up safety in a lot of my tools originally, and I ended up taking down our test environment for a whole week because of a vulnerability found. It shouldn't have taken down the test environment; it was a legitimate vulnerability found, but it was a very hard sell for me after that. That was sort of the first-use cases of that. So I was talking to product managers and I ended up getting a bunch of business people involved and I had to sit down with them and be like, "look, we should limit the fall-out of these experiments," but this process actually found a legitimate issue that luckily didn't happen in production.

It does take some evangelizing from the people that are implementing it, but I think it has a huge ROI if you're keeping safety in mind and if you're spreading, "here's what could happen if we weren't doing this, if we weren't being proactive about this."

I'll get companies that reach out to me sometimes and they're like, "We're a banking company, we could never possibly do something like this," but I would argue that they should probably do that more so than a company like Netflix. They should really know what happens. They should really know what happens when something fails. It's not a, "what happens if this fails," it's, "what happens when this fails?" And if you can't answer that question, that's very scary to me.

Ted: And for us at LinkedIn, the first step was showing that there was a problem to be solved. So what gets measured gets fixed. The first thing was to look at the on-call data and see that we were waking people up all throughout the night for things that didn't actually cause any member impact. So there we are saying, "members first," and we're waking people up for that.

So that was the first thing. And then we said Chaos Engineering is one of the tools that we can implement to solve these problems. The first question that came up is, "what if you break the site worse than we're already doing?" And that's where the safety comes in. Presenting all of our tools, the first question is, "where is the safety? Where is the safety in?" That's what I was saying before; it's all about limiting blast radius. And that kind of drives buy-in.

And then it's finding customers that actually want to change things. That's pretty easy too, once you have your on-call data — it's whoever is losing the most sleep. They'll be very on-board to help you out and implement Chaos Engineering.

Nora: It's not hard to...what I did was I ended up finding a team that was super interested in it. I had teams that were kind of apprehensive but I also had teams where like, "yeah, we wanna do this. This sounds like a great idea."

I started with them. I started with teams that had the greatest resilience story and I got success cases from there. And then it sort of evolved. Other teams wanted to get onboard after that.

Patrick: From our perspective, I think something that has been really beneficial is Chaos experiments is just starting small and showing that...I think for all of us, safety's a huge concern. In terms of the business cases, I think...from our perspective that really needs to happen in-house for our clients, but it's obviously something we'd like to initiate and we'd like to encourage businesses to look at the cost of downtime for them and the effects of downtime and...and what that means for customer trust for specific companies.

From our perspective, I think it's largely about raising those questions and asking questions.

Nora: I would also recommend starting in test. Don't start in production.

Shantanu: Please join me in thanking the speakers again.






