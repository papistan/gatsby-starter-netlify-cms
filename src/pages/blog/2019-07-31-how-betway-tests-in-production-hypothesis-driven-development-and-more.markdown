---
author: Kimh
comments: false
date: 2019-07-31 01:01:11+00:00
layout: post
link: https://launchdarkly.com/blog/how-betway-tests-in-production-hypothesis-driven-development-and-more/
slug: how-betway-tests-in-production-hypothesis-driven-development-and-more
title: How Betway Tests in Production - Hypothesis-Driven Development and More
wordpress_id: 194167
categories:
- DevOps
tags:
- Betway Group
- hypothesis driven development
- test in production
---

In June, our friends at Intercom opened their offices in London for our Test in Production Meetup. Michael Gillett started the evening with a talk on how his team at The Betway Group has embraced hypothesis-driven development, and how testing in production is a key part of these practices.


<blockquote>"We perhaps should approach this slightly more scientifically. Which is using a hypothesis driven development style, where we're actually, whether it's us or people who we're working with, kind of setting out these requirements, have a scientific approach to what it is they want out of the features that are being done, adding more value, improving performance, et cetera." - Michael Gillett, Lead Developer, The Betway Group</blockquote>


This talk was inspired by an article Michael wrote in 2018, _[Hypothesis Driven Development for Software Engineers](https://blog.launchdarkly.com/hypothesis-driven-development-for-software-engineers/)_. Watch to learn more about the processes his team has put into place since then. If you’re interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/events/254964628/).

[embed]https://youtu.be/h6op1gLeoic[/embed]

**TRANSCRIPT**

Michael: I think the goal that they were trying to do. The modern day equivalent of that is with SpaceX, who are doing similarly impressive feats of engineering, where they are managing to land two rockets that have just put Apollo into orbit. Again, they've had some spectacular failures as they test in production, but ultimately they are achieving what it is they're trying to do. They're coming up with hypotheses around how can they actually get a rocket to land back on earth or on a floating vessel. They're managing to do it because they're analyzing all the data that they would get, even when it fails.

When we then apply that to the world of programming and computer science and development. Perhaps not here, but a lot of people do associate programming and developing with more of the craft based approach, which is someone is given a specification of something that looks right. It feels right and we got to build it. It's a unique bespoke thing that we as developers are doing.

That in the industry, we perhaps should approach this slightly more scientifically. Which is using a hypothesis driven development style, where we're actually, whether it's us or people who we're working with, kind of setting out these requirements, have a scientific approach to what it is they want out of the features that are being done, adding more value, improving performance, et cetera. But we actually need to understand what it is we're going to measure and what it is the expected outcome is going to be.

I'm not sure this term makes that much sense. If we are talking about having a more scientific approach, I feel it should be hypothesis driven engineering, but the industry standard is development. Engineering implies a little more science than perhaps development does.

So, let's have a look at how we apply this of that way. So first up is the kind of business hypothesis. So this is perhaps validation of an idea. What this often looks like for us is an A/B test. So we would create a hypothesis that we can improve something, add more value to the site of what we are doing. We will split traffic between the variations that we have. We log absolutely everything we possibly can, all of the metrics, the exceptions, et cetera. We log all of that. We analyze that information and at the end of it we can then, in theory, validate that the hypothesis was correct or not.

So the one I'm going to talk about is the Betway home page, which we will see in a minute. This is a live A/B test. So this should be good. On the current homepage, I call it current, there are multiple ways that a user can get through to our registration form.

What we found was number three is the least clicked of all these channels, but is the one that results in the most successful registrations. So the hypothesis from understanding that was if we emphasize a single link on the homepage, there will be more registrations. So we set about, several months ago, actually building a brand new application to be our brand new homepage to evaluate whether this hypothesis is correct or not.

So right now there is a 50 50 split between these two home pages. If you wanted to, you could check it out on your phone and half the room in theory sees the left one and half the room in theory sees the right one. So how did we do this from an A/B test point of view? Well first of all, we set a redirect up on the existing homepage. So on [Betway.com](http://betway.com/) we set a redirect up. Initially it was only up for the Devs and QA who we're building that new homepage.

Once they were happy with it, we then turned it on for a few key members of the business who were going to check out whether it did everything that they wanted it to, whether it looked like they wanted it to. We then turned it on for 5% of our UK English language users. If that was all good, we then rolled it out to 25% and then 50%, and that's where we currently are with this.

The hypothesis was by having one single bigger join now button, that is going to generate more successful registrations for us. What we have seen is in doing so, we have had 25% better successful registration rate in the last six weeks of running this A/B test at 50 50. So the hypothesis has been proven for this business hypothesis.

Alongside that we have had some technical accomplishments as well. So with this project we had no rollbacks. We have had no critical alerts or outages and all of our exceptions are decreasing over time. This graph here shows how that's possible. May not be great on the screen, seems a bit dark. Each line is a date since we've rolled this new homepage out. Each section of the bar graph is a different browser and what we're seeing there is the number of exceptions per browser per day.

What that allows us to do is there are a couple of really tall spikes. That was Edge. We were able to turn the redirect off for the Edge browser using feature toggles. We could then fix the issue and then turn it back on for Edge, which is why we have no rollbacks with this because we were completely in control of which by-users we're getting this new homepage. So we can turn it on or off for any of the browsers that we wanted to.

So when I say 50 50 there are some slight caveats to that, where we are testing stuff and identifying things. But as you can see, the trend for the exception rate is decreasing. I think towards the end you actually see different blocks of colors appearing and that's as we rolled it out to more browsers, that we were happy for them to start getting this A/B test.

So now moving onto what I'm calling technical hypothesis, which is perhaps validation of an implementation. So this is perhaps technical debt. It is a performance improvement. It's a refactoring of something. So it's not necessarily going to add more business value, but technically we should be doing this. So one way that we can use feature toggling, and I'm basing this off like a hypothesis, is we reckon that this is now going to be better for our implementation, but we aren't sure of that, so let's validate that. So let's roll it out. We can roll out things based on any number of targets here. These have all been used for various things that we've tested. Normally these have been for technical improvements as opposed to a new business requested feature.

We also are doing some cool stuff with being able to test slightly differently than we've been able to before. So the load testing one here, one of our new microservices makes a number of calls to get content. They wanted to properly performance test this new microservice or whatever. We didn't want to do is hit any of the downstream content requests they were making. They didn't want to put that load on them.

So they actually encapsulated those calls in LaunchDarkly feature toggles. Then during the load test it was only ever hitting a mach end point and just returned the data back from the app itself rather than hitting the real content endpoint. So we were able to put a shit load of load on the microservice without impacting any of the other apps downstream, which was really cool.

I kind of showed this in that other graph, we can do testing on browsers and platforms and devices and networks, that's quite a large kind of plethora of combinations. Doing that before you go live it's actually extremely difficult. Once you're in production you can start seeing in that graph where there are exceptions. Then you can just turn things on or off accordingly and fixing has now put it back live without really impacting users and without having the hassle of doing rollbacks and that kind of thing.

So there are a few things that I just want to share from Betway’s experience of doing hypothesis driven development and testing and production. So what we have found is by using feature toggles, we can move to, for some teams a trunk based development start. So they have stuff on their local machine and everything else goes to the master branch and goes to live. There is no other environment for them.

They're doing that by all of the new Dev work that they're doing lives within a feature toggle. It gets turned on only for them. Once they're happy with it they might share it with the product team or whatever. Once they're happy with it, we can then start doing that kind of phase roll out to our users just to see whether the feature is working as we expect it to. This is saving a lot of time and hassle for some of our front end teams because they don't have to go down the route of having lots and lots of issues with environments we have traditionally had in the past. Another thing that we have found is that it's much better to track per device not on session. If a user comes to the site one day, sees feature A and then they come back another day and see feature B and come back another day and see feature A.

It feels a bit weird for them seeing that feature time and time again. So we track on devices. Once they're logged in, we will then track them by their username. Some of my users perhaps just look at our pages logged out to see what the latest thoughts or whatever.

We also have a shared cookie across a number of our applications. If we want to have features that are across different applications in front end services, then we can use that. One thing that is coming to light more, as we are doing more feature toggling with testing in production, is what I'm calling scheduling complacency. Which is where a number of teams are working on a full end to end project. We might go ahead and do the work... You can't actually read all that. It's okay. It says we and then at the end it says four.

If you can figure that out. So we find that because some parts of the business know that we can turn feature on or off very easily, they request us to do the work. We go ahead and do the work. We turn it on and then we discover sometime later, "Oh no. but the downstream system wasn't ready for that yet. Can you turn it off please?" We turn off and then weeks go by. We've done the work a long time ahead of everyone else. Which is a bit of a pain because we think, "Well, we could've worked on something else then." So that's a tip to just be aware of because once people know you turn things on or off, they'll make use of that.

This one's a slightly different use case for testing in production, which is possibly not really testing in production, but it's making use of the permanent toggle. All of the other toggles that I've spoken about are more features or rollouts rather than something that's going to live on forever. But what we can do is when we have minified and unminified versions of our JavaScript on site, we can actually turn a toggle on for specific users within our network that will return the unminified version of the JavaScript.

So if we're trying to debug an issue it's much easier to do it with the unminified rather than the minified. This kind of stuff makes that much easier for us. So it's still the production environment, still the production site, but you're getting the unminified version. And then there are a couple of things when it comes to actually using hypothesis, and working with them is... This might sound very obvious, but we have found a number of instances where people's expectations of what success looked like for an experiment was not the same.

So what we found is it's really good to set a goal with everyone who was involved in the project. So we all understand what that goal is and we can agree on what the metrics are for that goal. Also having an understanding of what success and failure would look like, because sometimes it might not be a failure for some people and other people it would be. So again, agreeing what that really looks like is really useful

On the same kind of theme, understanding what the sample is going to be for the experiment. Our assumptions are not always the same as what the businesses are going to assume when they request the feature. So asking these kinds of questions has certainly helped us in the past. What we have then done with those kinds of things in mind is, we've started to use what we're calling our hypothesis specification, which is a document that goes over all of those kinds of things, makes us think about them.

We used to use this a fair amount, but we don't use it so much now, because we're in that way of thinking. So we don't always have to use this. But it has helped us to make sure everyone's on the same page. We are making that available, if anyone is interested in that or making it as a basis for your own. Hopefully that link works. Fingers crossed.

In summary, we're trying to use hypothesis driven engineering wherever we can, because we're finding it's giving us much better valuable information about what our users are actually doing and technically what our apps are doing. It means we're not having to do so many things like rolling back and things that we just don't want to do. So the thing that I think is to take away is to try and have a slightly more hypothesis driven engineering approach to the way in which we're developing software. That's it. Thank you.

Are there any questions?

So the question was, did we automate the transitions when we rolled out the A/B tests for the home page? No, that was all manual. We were checking the data ourselves, analyzing what the logs were telling us. It was mostly based around the number of exceptions that we were seeing in the click through rate on the button. As long as that was in line with what we wanted and it was no worse than the existing home page, then we felt confident to keep going there.

The follow on was, was that part of the hypothesis spec? It can be included in there. Again, it's kind of that conversation to make sure everyone's aligned. If that's the way in which we wanted to go with it, then it would be something that we would include then.

So the question is, is this just for the team or is hypothesis driven engineering more for the entire company and if it's not yet for the company, why? It's very much within the department. Some of our closest stakeholders kind of are beginning to understand the way in which we work. The business expectation is pretty much that we'll always have feature toggles on anything new we do, but they don't necessarily think through what the success would look like. That's caught us out before. So we do try and work with them to make sure that happens. So there is an understanding, but they probably wouldn't look at it quite how we look at it. If that makes sense.

So the question is kind of how do we schedule incrementing the the rollout. That does come up at the hypothesis specification kind of conversations. But ultimately the stakeholders just want that feature in theory to be live to 50 50 as quickly as possible. So it's slightly more for us to just validate that things are looking okay. We can do it on our own timeline.

Any other questions? Cool, thank you.
