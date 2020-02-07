---
author: Guest
comments: false
date: 2018-03-16 18:02:33+00:00
layout: post
link: https://launchdarkly.com/blog/hypothesis-driven-development-for-software-engineers/
slug: hypothesis-driven-development-for-software-engineers
title: Hypothesis Driven Development for Software Engineers
wordpress_id: 2400
categories:
- DevOps
tags:
- DevOps
- engineer
- feature flagging
- hypothesis driven development
- QCon
- software development
---

_Guest post by Michael Gillett, Windows Insider MVP, Lead Developer at Win Technologies_

Last week I attended the [QCon London](https://qconlondon.com/) conference from Monday to Wednesday. It was a thoroughly interesting and informative three days. The sessions I heard ranged from microservice architectures to Chaos Engineering, and from how to retain the best people to new features of the Windows console. But there was one talk that really stood out to me—it took a hard look at whether we are Software Developers or Software Engineers.


<blockquote>

> 
> <blockquote>QCon London is a conference for senior software engineers and architects on the patterns, practices, and use cases leveraged by the world’s most innovative software shops.</blockquote>
> 
> 
</blockquote>


QCon London describes itself as a software conference, not necessarily a developer conference. It focuses more on the practices of creating software as opposed to showing off the latest and greatest frameworks and languages, and how to work with them. This came through in the talks I attended where most showed very little code and focused on how we work as teams, how we can interact with tools, and the idea that how we treat our code can have a huge impact on what we ultimately deliver.

With that in mind I went to a talk titled “Taking Back ‘Software Engineering’” by [Dave Farley](https://qconlondon.com/london2018/speakers/dave-farley). I wanted to understand the differences he sees between being a software developer and an engineer, and learn how those differences can help create better code. During his 50 minute presentation, Farley outlined three main phases of production we have gone through. The first was craft, where one person builds one thing. The next was mass production, which produced a lot of things but wastefully resulted in stockpiles of products that weren’t necessarily used. The final type of production was lean mass production and Just In Time (JIT) production. This is the most common form of production today and is possible because of tried and tested methodologies ensuring high quality and efficient production lines. JIT production requires a good application of the Scientific Method to be applied to enable incremental and iterative improvements that result in a high-quality product at the end.

Without this JIT production approach and the Scientific Method, Farley pointed out that NASA would never have taken humans to the moon and back. It is only through robust and repeatable experiments that NASA could understand the physics and engineering required to build a rocket that could enter Earth’s orbit, then the moon’s, land humans on the moon, and then bring them back to Earth. It’s worth noting that NASA achieved this feat within 10 years of when President John F. Kennedy declared the US would do it—at which point NASA had not yet even launched an orbital rocket successfully.

Farley surmised that engineering and the application of the Scientific Method has led to some of humanity’s greatest achievements, and yet when it comes to software there is a tendency to shy away from the title of “Engineering”. For many the title brings with it ideas of strict regulations and standards that hinder or slow creativity and progress rather than enable them. To demonstrate his point Farley asked the audience, “How many of you studied Computer Science at university?” Most of the room raised their hand. He followed up with, “How many of you were taught the Scientific Method when studying Computer Science?” There were now very few hands up.

Without a scientific approach to software development it’s perhaps an industry that follows a craft-like approach to production where because it works, it’s good enough. For example, if a software specification was given to several organisations to build, one could expect widely different levels of quality with the product. However, the same cannot be said of giving a specification for a building, car or rocket to be built—they could appear different but would be quality products based on rigorous tests and standards.

Farley went on to talk about how Test-Driven Development and Continuous Delivery are great at moving the software industry to be more scientific and rigorous in its testing standards. Though they are helping the industry to be better at engineering, there is perhaps another step needed—Hypothesis-Driven Development (HDD)—to truly move the industry to being one of engineers instead of developers.

Through HDD, theories would be created with expected outcomes before the software development aspect was even considered. This allows some robust testing to do be done further down the line, if the hypothesis stands up to the testing then it can be concluded that this appears to be correct. Further testing of the same hypothesis could be done too, allowing for repeatable tests that demonstrate the theory to be correct. The theories could be approached on a highly iterative basis, following a MVP like approach, if at any point the theory no longer holds up then the work on that feature could be stopped.

The theories wouldn’t need to come from developers and engineers themselves, although they could, but could come from other aspects of the business and stakeholders who request work to be done on the products being built. This would result in more accountability for what is being requested with a clear expectation around the success criteria.

Whilst I and my colleagues apply some of these aspects to the way we work, we don’t do everything and don’t approach working with software with such a scientific view. I can see clear benefits to using the Scientific Method when working with software. When I think about how we might better adopt this way of working I am drawn to LaunchDarkly.

We use LaunchDarkly at work for feature rollouts, changing user journeys and for A/B testing. The ease and speed of use make it a great tool for running experiments, both big and small. When I think about how we could be highly iterative with running experiments to test a hypothesis, LaunchDarkly would be an excellent way to control that test. A feature flag could be set up for a very small test with strict targeting rules, and if the results match or exceed the hypothesis then the targeting could be expanded. However, if the results are not matching what was expected, then the flag could be turned off. This approach allows for small changes to be made, with minimal amount of time and effort being spent, but for useful for results to be collected before any major investment was made into developing a feature.

I found Farley’s talk at QCon London to be an interesting and thought provoking look at how I could change the way I work with software. I’m now thinking about ways to be more scientific in how I approach my work, and I think LaunchDarkly will be a very useful tool when working with a Hypothesis Driven Development approach to software engineering.


*   *   *


_Michael Gillett is a Microsoft MVP and a Lead Developer at Win Technologies, a member of the Betway Group, in London. He has experience of a range of web technologies and can often be found on Twitter (@MichaelGillett) talking about the latest tech._
