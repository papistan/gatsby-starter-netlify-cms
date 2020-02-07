---
author: andreaech
comments: false
date: 2018-07-21 17:30:25+00:00
layout: post
link: https://launchdarkly.com/blog/request-disruption-at-linkedin/
slug: request-disruption-at-linkedin
title: Request Disruption at LinkedIn
wordpress_id: 193227
categories:
- DevOps
tags:
- chaos engineering
- LinkedIn
- resilience engineering
- SRE
- test in production
---

At our June Test in Production Meetup we focused on chaos engineering. Ted Strzalkowski, an SRE at LinkedIn, talked about how his team is focused on resilience engineering.


<blockquote>"Part of that was we owned a lot of front-ends, so a lot of my disrupted sleep was due to downstreams alerting on my stack that I couldn't do anything about. That made me interested in chaos engineering. I wanted to see what we actually needed to wake up for on the back-end and what we didn't."</blockquote>


Watch his talk (or read the transcript) below to learn how they are providing a comprehensive, automated, measurable resiliency feedback loop. If you're interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/).

[embed]https://www.youtube.com/watch?v=pYPCpFBtK2w[/embed]

TRANSCRIPT

I'm Ted Strzalkowski, I'm an SRE at LinkedIn. I joined LinkedIn about two years ago and when I joined I supported the publishing and article reader stack. Part of that was we owned a lot of front-ends, so a lot of my disrupted sleep was due to downstreams alerting on my stack that I couldn't do anything about. That made me interested in chaos engineering. I wanted to see what we actually needed to wake up for on the back-end and what we didn't.

I started to work on chaos engineering as part of what we called The Waterbear Team in LinkedIn. The Waterbear Team, much like Nora said at Netflix, it's more about resilience engineering, right? We're looking to build a culture of resilience. We're looking at eight engineers in testing and validation through tooling. With that, we're looking to make sure that we have transparent integration to make resiliency the easy option. This tool should be really easy to use, should be the default option and that will start to build a lot more resilience in the stack.

Our mission is to provide a comprehensive, automated, measurable resiliency feedback loop through education, validation, and frameworks. Right? That's what we're looking to do to build that culture.

We're going to do that in three different ways at Linkedin. We're looking to have an assertion layer, so we want people to say, "Oh yeah, my service can totally handle a failure of that downstream" when in fact when we run the validation, when we run an experiment, we find out that no, it may not be able to handle that and then they can actually come in and implement some corrective measures, make sure it does hold up to that.

So on request disruption, we need to kind of define a problem. And so what we found was that our downstream failures caused complete outages. We would have services that would call to a downstream and it wouldn't actually need some of the information it was getting from various downstreams and yet it would return a 500 to the front-end.

The front-end would take that and would show an oops page as we call them to our users. We have an idea at LinkedIn: members first. That's not very members first. The problem with identifying these problems that our dependency tree is complex. We have about 10,000 microservices in production and so finding out which services you call, which services they call, everything like that starts to get pretty complicated.

The other part was that with a 15 year old company, we don't know what the impact of all the downstream failures might be. Some of them may be pretty benign. Some of them may result in member impact. And then we found that once we started to interview all different teams within a company, that degradation strategies were completely different. They were either nonexistent or they were a variable.

We had some people implementing backup requests, right? Good low timeouts. We had other people figuring out default values so when they don't get a response from a mid tier, they can just come up with a default value and show that to the member. We wanted to standardize that.

So we created LinkedOut. LinkedOut is our failure injection framework. It provides us a few different ways to inject failure. First is through our A/B experiment pipeline. We call LIX the LinkedIn Experiment Framework, but that requires us to set up an experiment, run that experiment, measure it. Sometimes we just want to do ad hoc experiments and so we actually have a chrome extension, but we can also do it through Curl and we can set some cookies and have the targeting of those failures just to the member that's viewing the page. If you're a front end developer and you're wondering what if this downstream fails? You can actually inject that right from your browser extension and only impact yourself.

Supports multiple failure modes. The call tracing is automatic. So it happens on the back-end, it figures out all the call tracing, so it takes the complexity of that dependency tree and then, as I said through the chrome extension, supports ad hoc, and then we have automated testing so that once you figure out a failure plan, you can run that experiment over and over and maybe identify some regressions.

So the way we do request disruption at LinkedIn is through our [rest.li](http://rest.li/) framework and that's our open source REST framework. It gives us restful architectures, has its own dynamic discovery service discovery built in, it has the request response, and then it's a client that is actually in all of our products. So once we put the disruptor there, we didn't need to think about how somebody can opt-in as long as they had the latest version of this [rest.li](http://rest.li/) client, they had the disruptor.

This diagram shows a little bit about how the [rest.li](http://rest.li/) client works. So an application has the [rest.li](http://rest.li/) client imported and the [rest.li](http://rest.li/) client has what we call a filter chain. In that filter chain, you would have various experiments for your normal A/B testing that product as you doing and stuff like that. At the very bottom of the filter chain is where we put the disruptor, so you apply all the other experiments that you might apply and then at the very last thing, before the request leaves the client, we do any disruption. What that allows us to do, is to actually have a representative experience for whoever's going to be looking at the disruption.

That disruption can come in one of three different ways. So we can add latency, we can add a specific amount, today we don't support the ability to maybe make a total amount of latency, we just add onto whatever the downstream calls. When we add latency, we don't have any disruption on the server side for what we're calling. We limit that blast radius to the client for that single request.

Next thing we can do is we can have an exception and so we skip the downstream requests altogether. Again, we don't affect the downstream. We support latency in addition to the exception, so you can say wait 500 milliseconds and then throw an exception, and then the client actually just throws the normal [rest.li](http://rest.li/) response exception that it would get as if the downstream service had crashed on the request. Right? Pretty simple stuff there.

Then the timeout. We literally just dropped the request on the floor. We never see a response, that allows the rest of the client to handle a complete time out. Then again, notice the theme here is to limit our blast radius, we don't affect the downstream service. The last thing we want to do is have other people get paged because we're doing an experiment.

So that's great. LinkedIn has this A/B testing framework, we have all this stuff and I remember when I was at a smaller shop before and I went to a chaos engineering meet up, I thought to myself, "Well, it would be good when we grow up and we can actually implement that stuff." But once I started doing it, I realized that it actually doesn't require any kind of scale or major tooling.

We can actually do this and limit our blast radius, keep our customers in mind with Flask. So I don't know if you guys can see that okay. This is really simple Flask middleware that I just threw up on a slide. I wanted it to be the fewest lines of code so that it could fit on a slide. But basically, what we're doing is we're creating a Flask middleware here and the request object isn't exposed to the middleware, so we use work so I to actually get a request object so that we can take a look at the headers, right?

Then all we're doing here, in this case, we're just support the latency idea. Anything more than that wouldn't fit on a slide. And so we checked for that failure injection header and if that failure injection header exists, we grabbed that value and we sleep for that amount. Right? So you could easily write this kind of a thing and put it into your app.

Then we have to introduce, we have to wrap our Flask app with that middleware, so we get a quick little ... right there. So we're what, 20 lines of code in? then when we Curl it, we can actually see if we add that header, we Curl our API, we still get our response, but you can see that we added 250 milliseconds in our time there, right?

For LinkedIn specifically, what's coming next are a lot of things that Nora actually mentioned. We're playing a little catch up in the industry here. We're going to look at screenshots. So our automation platform actually runs selenium tests and navigates through the site. You feed it a URL, you tell it which failures to inject at which levels and it goes through and keeps reloading the site over and over and over. It'd be nice if that failed. Can we give a screenshot, right, back to the user who created that so that they can see what did that failure look like?

Right now we have a specific definition of what a failure is and it might not actually bubble up to the user. Then with that, once we have screenshots or anything like that, we want to be able to provide custom failure detection so the users should be able to define what failure means, right? It may return a 200 on the back-end and it may actually show us something and it might actually deliver a full page load to the user, but that might not be a useful page load to the user. So we wouldn't call that a failure normally in our framework as it is today, but it should. Right?

Then we're looking at reporting on most of our automation tools. We have weekly summaries that people opt-in to and stuff like that. They should be able to see that same reporting on their automated tests that run on a schedule for their chaos injection.

Today, we only support the [rest.li](http://rest.li/) client which covers about 90% of our environment. But there are things like Cassandra, there are things like Redis that we run internally that we can't disrupt today and we'd like to. So we're looking at couch-based client disruptor, that kind of a thing.

The other thing we're working on currently is the absolute latency. You saw that our filter actually is before the request leaves the client. So we don't know what the total time of the request was on the way back. We want to do absolute latency so you can say, "This request took 500 milliseconds, which means we need to put our disruptor on the response side as well." Right? So we're working on that too.

And then correlation. We're looking at which services, I think Nora called it a criticality score. Right? So which of these mid-tiers would actually have the most impact on the most upstreams and that's where we should target our efforts to start.

That's all I have. Thank you.
