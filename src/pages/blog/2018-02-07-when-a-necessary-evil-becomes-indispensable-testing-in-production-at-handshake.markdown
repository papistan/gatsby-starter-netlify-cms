---
author: Kimh
comments: false
date: 2018-02-07 17:25:28+00:00
layout: post
link: https://launchdarkly.com/blog/when-a-necessary-evil-becomes-indispensable-testing-in-production-at-handshake/
slug: when-a-necessary-evil-becomes-indispensable-testing-in-production-at-handshake
title: 'When a Necessary Evil becomes Indispensable: Testing in Production at Handshake'
wordpress_id: 2200
categories:
- DevOps
- Feature Management
tags:
- DevOps
- ElasticSearch
- experimentation
- QA
- test in production
---

In January at our Test in Production MeetUp, we invited Maria Verba, QA Automation Engineer at Handshake, to talk about why and how her team tests in production. (If you're interested in joining us, [sign up here](https://www.meetup.com/Test-in-Production/).)

At [Handshake](https://app.joinhandshake.com/login), Maria is focused on making sure her organization ships a product that customers love to use, as well as supporting the engineers with anything test related. In her presentation, she discusses the requirements her team has put in place to test safely. She also covers some specific examples of when testing in production is better than in pre-production.

"Whenever I hear test and production, I definitely don't cringe anymore. But I know that there are right ways to do this, and wrongs ways to do it. Right ways will always include a healthy ecosystem. A healthy ecosystem implies you have good thorough tests. You have feature toggles. You have monitoring in place. We have to consider our trade-offs. Sometimes it does make more sense to create the mock production environment, sometimes it doesn't. There are definitely things that cannot be tested in pre-production environments." -Maria

Watch her talk below.

[embed]https://youtu.be/RzjLUXYWFMs[/embed]

TRANSCRIPT

Hello everybody! Again, good evening. Thank you for having me. My name is Maria Verba. I work at a company called Handshake here in San Francisco.

Today, I'm going to talk to you about how we do, and why we do testing and production. My own personal journey from thinking about it as necessary evil, things that you have to do but you don't want to do, to thinking about it more of indispensable, quite valuable tool.

To start off, let's talk a little bit about Handshake. Most of you have probably never heard of it. It's a small company, it's understandable. Handshake is a career platform for students that helps connect students with employers, and helps students find meaningful jobs, and jump-start their careers. At Handshake, we believe that talent is distributed equally, but opportunity is not, so we work very hard to bridge that gap, and to help students find their dream jobs, and make a career out of it.

My role at Handshake is quality assurance engineer. Besides making sure that we ship very good products that our customers love to use, I think that my responsibility as a QA engineer is also supporting engineers, engineering team with everything and anything test-related, test infrastructure, test framework, as well as keeping their productivity and happiness high.

With my background with being in QA for about six years, whenever I heard "Oh, let's just test this in production," this is pretty much the reaction I would get. No! No way! Let's not do that. Why don't we want to do this? First of all, I do not like customers to find any issues. I do not want to expose them to any potential even small bugs. Yeah, let's not test in production.

The second thing is I personally create a lot of gibberish records. I don't care when I test. Sometimes it makes sense, sometimes it doesn't make sense. I wouldn't want anybody to see those records. Besides, it has a potential to mess up reporting and analytics. It's also very, very easy to delete records, and modify records, so making this mistake is very costly. It's very expensive, and probably engineers will spend like a couple of hours trying to dig out a recent database backup, and try to restore it. So yeah, let's not do that in production. The last one is data security. We are actually exposing some records to other people that shouldn't see that.

Then I started realizing that maybe it's not actually that bad. Sometimes we have to make the sacrifice, and sometimes we have to test in production. I thought, "Yeah, maybe it's okay as long as we have automation testing." Before deploying, we have something that verify that our stuff works. We also want to make sure that we have a very good system, early detection system and monitoring and alerting system, which we're going to find mistakes that we make before our customers do. We absolutely have to put it behind the feature toggle. There is absolutely no way around it. Even if there is no issues with our new feature, we do not want to surprise our customers. We do not want to throw in a new feature in them, deal with it, whatever you want to do. We want to have that material ready for them. We want to expose them to it before they see it.

In the recent times, the way that we've done it, it historically happened that most of our features were read-only. We would not create any new records. We would not modify any records. We also made some trade-offs. We thought about it. We realized that yes, it is possible to create those separate production-like environments and test it there, but for us, it's not realistic to do that. We move very fast. We don't have that many engineers to spend time creating new environments. Basically, it's a very expensive process for us. We really don't want to do it. Besides that, we are very careful about our data records, and we take security very seriously. We do constantly data privacy training. We have multiple checks in place and code. This helps us safeguard against any issues.

In the past where we did test in production, this would be a couple of examples. When we needed real-life traffic - general performance testing, performance monitoring on a daily basis. We also needed our production data. Sometimes it's very hard to reproduce and replicate the same data that we have in production. Examples would be Elasticsearch5 upgrade and job recommendation service. Lastly, we do a lot of A/B testing and experimentation at Handshake. We validate our product ideas.

I'm going to talk a little bit more in detail about a couple of these examples here. Elasticsearch5 upgrade was a pretty good example, because first of all, why we needed to this? We rely heavily on search engine. Search-based features are pretty much our core. Whenever students log in, most of the time, what they want to do is find a job. Our search service cannot be down. However, we were using Elasticsearch2, which became deprecated. That put us in a position where we had to switch to Elasticsearch5 very quickly.

Let's talk about why we can't really test this in production. The update is too large. Basically, we cannot afford making any mistakes here. It touches everything. It has a potential to affect every single customer we have, every single user we have. It's very extremely important for us to keep the features functionally working.

How did we do this? First of all, it took us a while to figure out where did the Elasticsearch version 3 and 4 go. Then we created new classes. The classes for the new search syntax. We started the upgrade with changing the syntax for our... We put those classes corresponding to each index behind the feature toggle, and we thoroughly tested with unit and integration framework. We've rolled it out to production incrementally, index by index, and we tested that in production, because we have that amount of data in production that we needed. We were able to verify that we get correct results after the update.

The second case study is slightly different. Job recommendation service is ... at Handshake, we use machine learning. We apply machine learning to recommend jobs to students based on students' behavior, based on students' major skill, maybe a previous job history, job viewing history, location interest, etc. We take hold of that melting pot information, and we suggest a job based on that to a student. The question that we were trying to ask here is "Does this job make sense to this particular student?" A lot of times, you cannot go through all of those possible combinations and computations to answer that question.

To recreate that environment, it would take us, again, a lot of time and effort. We, again, rolled out incrementally. We heavily used our interns, because they're still in school. After verifying that the jobs make sense, we started rolling it out to other schools as well.

talking about these two examples, I can hear the question in the audience boiling. You could still do this. You could still create a mock environment, and do the same kind of testing not in production. You could have done it pre-production. And yes, that's true. I agree with that. We had to make those changes based on what our business needs are, based on our speed. We could not afford spending time and effort in setting up, maintaining, and securing those environments. But yeah, it is possible.

However, what if it changed the algorithm behind the job recommendation service? How do we make sure that those jobs are still relevant to the students? Do we ask the students after we change everything? I don't know.

Here is where our experimentation framework came in. We use experiments and A/B testing a lot at Handshake. We pretty much test every major product hypothesis that we have. For us, it's a two-step process. We have impressions and conversions. Impressions are a call-to-actions, or but on the prompt, something that the user sees. And then conversion is action based on seeing that prompt. An example would be showing a profile completion prompt to a student on a dashboard, and that would be an impression. Conversion would be if the student fills out their profile.

The way that we do it is we, first of all, determine which users, which students we want to target. We separate them into a different pool. Sometimes we want to say we want our experiment to work only for, or we want to target only seniors. Base on that, we remove other students from the test group. Then we split it into treatment and control groups. Then we track their conversions and impressions. We track them for both control and treatment group. This allows us to get very accurate results.

We are using LaunchDarkly to do this. We're using targeting rules. As you can see here in the, maybe it's hard to see, but basically, we're specifying the user type as students, thus we're removing every other student; maybe there is administrators or something like that. And then we say we want 5% of students to be on variation A of the feature, and 95% on variation B of the feature.

Unfortunately, we can't do all of it on LaunchDarkly. Some of our experiments or yeah, maybe like a good chunk of our experiments rely on some more dynamic information, some things that change over time. For example, a student has seen a job recently. We have to define recently. We have to define what exactly we want to track about that job. In order to solve this problem, we create records for LaunchDarkly, and this allows us to take additional conditions and configurations, and split our user groups into more detailed cohorts.

As a result, we get a very, very powerful experimentation for framework, and we can only do this in production. There is no way around it.

Going back to my personal QA perspective and key takeaways. Whenever I hear test and production, I definitely don't cringe anymore. But I know that there are right ways to do this, and wrongs ways to do it. Right ways will always include a healthy ecosystem. A healthy ecosystem implies you have good thorough tests. You have feature toggles. You have monitoring in place. We have to consider our trade-offs. Sometimes it does make more sense to create the mock production environment, sometimes it doesn't. There are definitely things that cannot be tested in pre-production environments.

That also is in line with my personal goals of, first of all, keeping our customers happy, and product stable. Our customers would love to use the product that is driven by the data, and not our own hypothesis. I also think that it keeps the engineers on the team productive and happy, because they don't have to spend time creating and maintaining all of these different environments.

What's next for us? It's Canary testing. We want to be able to divert some portion of our traffic into new features, for example, Rails 5 versus Rails 4. Right now, we are working on moving to Kubernetes to achieve that.

Thank you so much for your time. If you have any questions, find me, I'm going to be around, and reach out. Thank you.
