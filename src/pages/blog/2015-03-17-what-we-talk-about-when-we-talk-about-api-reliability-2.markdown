---
author: johnkodumal
comments: false
date: 2015-03-17 20:36:07+00:00
layout: post
link: https://launchdarkly.com/blog/what-we-talk-about-when-we-talk-about-api-reliability-2/
slug: what-we-talk-about-when-we-talk-about-api-reliability-2
title: What we talk about when we talk about API reliability
wordpress_id: 61
categories:
- DevOps
- Feature Management
---

One of the first questions we often get from customers is about reliability-- how can you make a system that uses a remote API reliable? What happens to our site if your service goes down?

The usual approach to reliability is to pick an SLA, say 99.99% uptime, turn on a monitoring tool like Pingdom to measure uptime against that SLA, and then play a montage while your engineers do a lot of hard work to meet that SLA.

My issue with this is that uptime is a one-dimensional view of reliability. Counting nines is almost certainly a necessary condition, but it's often not sufficient. It ignores other important questions about reliability (_How much variability is there in response times? What happens to performance as the number of concurrent clients increases?_).

LaunchDarkly provides feature flags as a service, so our API delivers rules that determine which features our customers' end-users see. If our API is unreliable, these end-users could see changes in their UI, missing functionality, or worse. Of course, uptime is critical for our service, and we have to do all the normal "montage work"-- zero downtime deploys, extensive integration and load testing, and ensuring redundancy in all critical systems. But reliability for us also means handling things like sporadic packet loss, latency spikes, and other issues that are invisible to a tool like Pingdom, but potentially visible to end-users.

For us, thinking about reliability as a number line that goes from 0 to 100 wasn't sufficient. We started thinking about the problem from the ground up-- starting with what was even _possible_ in terms of designing for reliability.


## "It's happened again— you've wasted another perfectly good hour listening to CAP Talk."


If you're familiar with distributed systems, the CAP theorem is probably near and dear to your heart. In a nutshell, the CAP theorem states that a distributed system can have at most two of three properties:



	
  * Consistency: The system agrees on one up-to-date copy of data

	
  * Availability: The system returns a response, whether it succeeds or fails

	
  * Partition tolerance: The system continues to function in the presence of network failures


Most people think about CAP in relation to database design, but it's important to keep in mind that the theorem applies to _any_ shared-network shared-data distributed system. This means that any HTTP API and its clients are bound by the CAP theorem. And this is one point we often forget when we talk about API reliability.

In the case of an HTTP API running over the Internet, we have to accept two facts:



	
  * Occasional large spikes in latency are inevitable

	
  * Latency is often indistinguishable from network failure


Practically speaking, designing an API with CAP in mind means that we'll encounter a situation where something bad happens, and we have to choose between consistency and availability. In the case of a `GET` request, for example, this means:



	
  * Choosing consistency and returning an error

	
  * Choosing availability and returning stale content


The LaunchDarkly API returns “rulesets” defining how feature flags should be rolled out. For example, a ruleset might contain logic like “roll this feature out to 25% of all users, plus everyone in the beta testers group”. Serving stale data means delivering an older copy of those rules, which is preferable to returning an error or waiting an unbounded amount of time (the consistency route) and forcing customers to fall back on a “default” variant for the feature flag that they’ve hardcoded. With that choice in mind, we had a clearer mandate to work with:

	
  * Maximize availability by trading off consistency

	
  * Minimize the possibility of partitions




## The dream of the 90's is alive


The 90’s were a great time. Java came along and changed the web forever with applets. I rocked JNCO jeans and had blue hair. And CDNs hit the scene, dramatically decreasing the probability that clicking on a Slashdot link would lead to a server timeout.

90's reminiscence aside, CDNs were designed precisely to provide caching and redundancy. The challenge, though, is that CDNs are (traditionally) designed to serve static content. Proxying an API through a CDN leads to a host of problems. For one thing, CDNs typically aren't able to cache authenticated content, which is a must for our APIs. Another problem is that CDNs usually aren't well suited to managing rapidly changing content-- purge latencies on the order of 5-15 minutes are common. While we'd already gone down the path towards eventual consistency, 15 minutes is a little too eventual for us.

Luckily, we found a solution in Fastly. Fastly gives us the option to specify caching rules using VCL, which gives us the fine-grained control we need to safely cache authenticated content. All we need to do is specify `Vary: Authorization` headers, telling Fastly to provide separate content caches for distinct API keys. Fastly also offers purge latencies [on the order of milliseconds](http://www.fastly.com/blog/building-fast-and-reliable-purging-system/), as well as an API we could call programmatically to purge content whenever a customer updated the rules for their feature flag.

You might have noticed that using a CDN actually _increases_ the chance of a network partition occurring, because CDNs introduce multiple POPs as intermediaries that may fail. Here we leverage another consistency tradeoff that reduces the impact of partitions-- we try to avoid network calls altogether.


## The best remote call is the one you don't make


One advantage that we have with LaunchDarkly is that our API's "mission-critical" clients (the ones that serve feature flags) are under our control: we build and distribute SDKs for our supported platforms. This means that we can introduce another layer of caching in these clients, with a completely different set of cache directives from what we give Fastly, our intermediate cache.

First, we use a simple `max-age` directive to set a TTL for feature flag changes. This is another area where we trade off consistency for availability: our SDKs can avoid making network calls as long as the max-age of the locally cached content hasn't been exceeded. In production, we recommend setting the TTL to 5 minutes, which means that our SDKs only make one remote call every 5 minutes. No matter what the frequency of feature flag requests is, only one call every 5 minutes will have any significant overhead. We can even hide that overhead by using `stale-while-revalidate` to serve stale content while we fetch the new flag rules in the background. The main tradeoff here is that changes to feature flag rollout rules on the LaunchDarkly dashboard don't take effect for 5 minutes.

We also use `stale-if-error`, which tells our client caches to prefer stale content to error responses. `stale-if-error` gives our SDKs some resilience to things like Fastly POP outages.


## Conclusion


The takeaway here is that we shouldn't be satisfied with measuring reliability in terms of uptime alone. Definitely do continue using tools like Pingdom to monitor uptime-- that's table stakes. But other factors, like baseline error rates, median + 90th percentile response times, and failure mode under load need to be considered as well. In the case of HTTP APIs over the Internet, design tradeoffs between consistency and availability can be made to improve reliability according to these metrics, independent of uptime numbers.



* * *





###### _LaunchDarkly helps you build better software faster with feature flags as a service. Start your free trial [now](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._
