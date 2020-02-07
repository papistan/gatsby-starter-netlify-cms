---
author: andreaech
comments: false
date: 2018-07-23 17:15:20+00:00
layout: post
link: https://launchdarkly.com/blog/great-gamedays-thinking-about-failure-holistically/
slug: great-gamedays-thinking-about-failure-holistically
title: 'Great GameDays: Thinking About Failure Holistically'
wordpress_id: 193230
categories:
- DevOps
tags:
- chaos engineering
- Gremlin
- resilience engineering
- test in production
---

In June, we focused on chaos engineering at our Test in Production Meetup. Patrick Higgins, UI Engineer at Gremlin, talked about how his organization runs GameDays. Gremlin is a chaos engineering startup, and they love thinking about failure.


<blockquote>"Essentially, our tagline, if you want our company's mission in a phrase, it would be, 'Resilience is a service.' Much like Ted and Nora, we're actually aiming for more than just Chaos engineering. We're actually looking for resiliency in general."</blockquote>


Watch Patrick's talk (or read the transcript) below to learn more about how Gremlin tests in production and how valuable 'Failure Fridays' have been. If you're interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/).

[embed]https://www.youtube.com/watch?v=pDiMUZAEI-M[/embed]

TRANSCRIPT

I want to talk less technically, more anecdotally, more organizationally about my experience. I'm a UI engineer. I work at a Chaos engineering start-up. What I want to talk about is how GameDays have been a really interesting experience for me. It's changed my perception of Chaos engineering and of more generally speaking, of failure. Essentially, what I'd like to convince you of is the fact that including people like me is really good for everyone in your organization when you are looking to think about failure and perhaps run GameDays in the future.

Who am I? Patrick Higgins. My handle's @higgyCodes and as has been mentioned, I'm a UI engineer from Gremlin. What is Gremlin? As we've previously said, we're a Chaos engineering startup. Essentially, our tagline, if you want our company's mission in a phrase, it would be, "Resilience is a service." Much like Ted and Nora, we're actually aiming for more than just Chaos engineering. We're actually looking for resiliency in general.

I'm originally from Sydney, Australia. I've lived in Utah for a little while and now live, actually just down the road, which is cool. Any World Cup fans here?

Audience: Yeah.

Pat Higgins: Cool. Any Mexico fans here? Congratulations. It's fantastic. Any Germany fans here?

All right, cool. Safe space. That's good. Regardless of what you thought about Slack this morning, I would have to say that Germany was actually the biggest failure of the day. It's a personal preference, but you may or may not agree.

What I really want to talk about is particularly my experience as a new employee at Gremlin. I came to Gremlin not knowing much about Chaos engineering, and I would posit to say that most UI engineers would not know much about Chaos engineering, and I would like to assert that we don't really think about failure that well either. When I joined the company, I wanted to ship a lot of features. I was actually the first UI engineer to join Gremlin, which was an amazing experience. I had a lot of features to ship. We had our first iteration of support for containers to do. I had to create a metrics dashboard for attacks. There's a lot of stuff to get out the door.

Then, a couple of months in, we started this process of what we call, "Dogfooding." I didn't know what this was at the time but essentially, it's the process of using your product on yourselves. Some people like to call it, "Tasting your own champagne." I think it's bizarre that the analogy that makes your products sound the worst, and the analogy that makes your products sound the best and there's absolutely no middle ground there, but I digress. In our case, it meant introducing failure into our own system. We call this process, "Failure Fridays."

What I started to realize really quickly was that Failure Fridays was essentially a Game Day, a Chaos engineering Game Day. What does that mean? It means dedicated time for teams to collaboratively focus on using Chaos engineering practices to reveal weaknesses in your services or systems.

When we were running these GameDays, we were setting hypothesis regarding potential outcomes that we'd see from the experiments we're running. We'd map out our system architecture, we'd pick very small localized points that we could fail, and we would iterate on the scope, and the effect of the attacks that we were running.

I'd like to say that my UI features, all these UI features that I'd been pushing out the door, that they all were incredibly resilient and user experience was exceptional, but it was not the case at all. I'd find that I'd get hung-up on loading states, there wouldn't be good enough error messaging. Essentially, what I'm trying to say is that use experience was quite poor.

This got me really thinking, I sat down, I was a little bit taken aback, I filed a lot of bug tickets and, essentially, over the next couple of weeks, I was able to gradually knockout all these problems that I'd seen from the user experience from the GameDays we'd been running. It got me thinking about remediation generally. What could I, as a UI engineer, do to essentially do a better job of creating a product that would be more resilient to conditions in which our systems run the duress. That was essentially the question that came to mind.

What I started to realize was that Failure Fridays had because a forcing function for me. I was beginning to uncover brittleness in the UI, and I was also beginning to understand our system at a deeper level. It was an incredibly educational experience.

Essentially, what I'd like to point out today is that everyone benefits from observing a failure. Even UI engineers, people from a UX background, product managers. If we all get involved, it encourages cross-organization collaboration, you find champions in the company that might come from areas that you didn't expect, and it encourages varied perspectives.

I want to talk about failure from a UI perspective now. I'm just using Twitter example purely because basically everyone knows Twitter and if you're anything like me, you're ... It's a pretty well-used interface at this point. What I'd like to point out is that say the tweets the following, and the followers service has essentially failed. From a UI perspective, we could end up with the profile card that you see at the bottom half of the slide there to that data could be omitted in its entirety. Through this omission, you might find that the user doesn't actually notice that anything's failed at all. In this particular context, that data is auxiliary data. It's data that is supplementary to the user's goal on this particular page, which is to look through their tweets.

What comes to mind is the fact that we have essentially, in the UI, we have different types of functionality and different types of data. It might be primary to the user's goal on that particular page, or it could be something that's supplementary and adds to that experience.

Not picking on Slack but actually, I want to still commend them on a really good user experience here. I'd also like to point out that in my Slack channels, it's a mix of Tim Tam's and soccer. That's basically all that goes on between me and our CFO, Daryl. But in this perspective, you can say some things that from a UX perspective, really helped.

First thought, if the ... This is the Electron app but if the Electron app is disconnected, the input down the bottom is disabled straight away, so I can't send off messages into the ether. Additionally, you can see on the green column section that you have on the left-hand side, just having the styling there that mimics the channels that you'd otherwise have means ... It doesn't feel broken. The page, the styling still feels like it's contextualized, so it's great that they really thought through that element of the site through the styling here, and you can see that Slack is telling me that they're going to try to reconnect in, at this point four seconds, or I have the option to retry now.

All in all, holistically, I'd like to say that Slack, in this particular, instance, I took the screenshot this morning. It's probably a pretty common experience across the board here but this UX experience was thought through and that might not seem like a lot, but I would like to pause it from a UI perspective. It's more rare than you'd actually expect.

What does this mean for UI in general? I would like to posit that UI engineering can benefit a lot from being included in these conversations about failure generally. End to end testing or marketing of services is not really enough. The reason I like to say that is because, at that point, you're really validating something. It's not about discovery. From my perspective, from my experience, the things that have been really exciting about GameDays generally is that element of discovery. I find things that I wouldn't otherwise find. You can find things in testing as well but for me, personally, having a primary motivation of discovery has been incredibly useful.

The open-source tooling around failure mitigation in UI is, I would like to say it's underdeveloped. I think there's a lot we can do to include better consideration of failure in UI development and tooling's regularly company specific. As you can see from today, the tools that LinkedIn have in terms of being able to inject failure from a chrome extension, that kind of tooling is something that, I hope one day we can see across the board. It's phenomenal.

Those opportunities, obviously, Chaos engineering is a real burgeoning field and the opportunities to think about how that interacts and intersects with UIs is something I'm really excited about.

Equally, from a product perspective, depending on which company you're at, I would say that mapping out of alternative states is something that doesn't really happen that much. That's not a conversation that's, in my experience, anecdotally, it hasn't been something that I'd seen a lot. It's really rare to get product specs that include a comprehensive idea about what user experience for failure scenarios should actually look like.

I'd like to leave you with just a couple of resources. Things that I found to be super cool, very useful. The first one is this particular GitHub repo is just stacked with incredible resources for Chaos engineering. Secondly, I'd like to point you to this list of resources that Gremlin's actually made available. It might help to codify how ... Or at least point people in the right direction for how they can actually do GameDays by themselves. Folks that go to Chaos Community Slack. It's a really active and I think it's a really excellent place for us to bounce ideas off each other. I personally learned a lot from engaging in this particular Slack. This is just a redirect link but it's not directly affiliated with Gremlin. That's super useful.

I want to say thanks. It's been really fun and I'm really excited to see where everyone goes with Chaos engineering as it picks up steam. Cheers.
