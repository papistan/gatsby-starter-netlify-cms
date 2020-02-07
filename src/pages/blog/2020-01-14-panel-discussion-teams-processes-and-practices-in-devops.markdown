---
author: mattdel
comments: false
date: 2020-01-14 16:00:41+00:00
layout: post
link: https://launchdarkly.com/blog/panel-discussion-teams-processes-and-practices-in-devops/
slug: panel-discussion-teams-processes-and-practices-in-devops
title: 'Panel Discussion: Teams, Processes, and Practices in DevOps'
wordpress_id: 194761
categories:
- Continuous Delivery
- DevOps
- Feature Management
tags:
- engineering culture
- incidents
- SRE
- testing in production
---

At the November Test in Production Meetup in San Francisco, LaunchDarkly's Yoz Grahame (a Developer Advocate) moderated a panel discussion featuring [Larry Lancaster](https://launchdarkly.com/blog/machine-learning-for-log-monitoring/), Founder and CTO at Zebrium, and [Ramin Khatibi](https://launchdarkly.com/blog/planning-for-the-outages-youre-going-to-cause/), a Site Reliability Engineer (SRE) and infrastructure consultant. They shared their thoughts on the role of _process_ – or lack thereof – in software development, how to build effective engineering teams, the value of incident postmortems, and more.


_"...I've been in ones [postmortems] where...everybody trusts each other, and...I've been in ones where...people are just waiting to finger point, and then you're very defensive. For me, always having a good timeline from the beginning just simplifies everything because you start slotting stuff in the timeline, and now you've got something concrete. We can argue about who did what, but at least we've got the timeline." _




_– Ramin Khatibi, an SRE and infra consultant_


Watch the full panel discussion to learn how these two incident management experts think about testing in production. If you’re interested in joining us at a future Test in Production Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/).



Yoz Grahame: We have two experts in incident management and identification with us. We have Larry Lancaster who spoke earlier. He’s the founder of Zebrium, the AI-powered log monitoring and incident monitoring service. We have Ramin Khatibi, expert experienced SRE with some fantastic tips that we saw. One thing that was interesting to me was that Larry, you mentioned that you don't come from kind of the same kind of sys admin or ops background. You come from a data and AI background.

Larry Lancaster: Yeah. I guess.

Yoz:  So, in discussions earlier we were talking about some of the things that kind of we like about the process that we've seen, some of the things we didn't like. It was interesting to me the disappointment of seeing that it's still all about logs and indexes and things like that that you're trying to solve. What else did you see when coming to this domain that interested you or gave you more positive responses?

Larry: That's an interesting question. Well, so what really has struck me about sort of the modern reality of DevOps and SRE life has been, I've gotten to know more of, has been this sort of deep shared responsibility for something that you didn't make, that you can't necessarily fix. Of course, that's always been the case. There's always been sort of support or IT roles twenty, thirty years ago, there were those things. There's some of that, but I think now you have very sharp people being put into a context where, yeah sure if there's a bug maybe it's not your fault, but your job is to keep this whole application running for potentially millions of users; certainly hundreds is not uncommon. I don't know. I guess I'm driven by sort of a sense of empathy for that because it's like it shouldn't be that way without help. You know what I'm saying? You need help. Like you need tools that respect that responsibility, that respect your time. I guess is what I would say.

Yoz: Yeah. That's great. That's fascinating because it touches on so much of what you know and I've been in software engineering for a couple of decades now, a couple of days, decades, but sounds like couple of days. As the longer time you spend in it, the more you realize how much more it is about people than about technology.

Larry Lancaster:  Yeah.

Yoz: Ramin, when it comes to things like empathy and handling responsibility within teams, how have you seen that kind of manage well or badly?

Ramin Khatibi: So, I was a manager briefly in '99 and I had no empathy and I did it poorly. So that's why I'm actually in a senior like staff SRE at my last job rather than going into management. The last 10 years I've actually worked for a couple of managers that did it well. I do like that the industry seems to be getting better at management. I often thought as the industry grew so quickly, they would promote somebody and be like, you're a manager. That person would have had no skill. Their manager had no skill to manage. Their manager had no skills manager and generally the manager on your team was the most unqualified for the job. I think that started change. I think it still pops up in the industry more than I would like and you're a little bit stuck because you do have to have some deep technical knowledge I think to manage well. Particularly kind of your line manager as you go up the stack. Maybe yes, maybe no. Generally, I've done better with managers that have deep technical knowledge.

Ramin: Just because you can have that conversation you need to have, particularly if you disagree with other teams. What I was surprised was I had a manager a couple of years ago and not very empathetic, but he instituted all the processes and he's like, I'm going to have one on ones. I'm going to keep the doc. I'm going to like care about your career. He kind of like treated it like a check mark and I think personally he didn't feel it in his heart, but he faked it enough where it worked better than most people who consider themselves people managers. So, I thought that was interesting of doing the things was actually maybe more important than feeling them.

Yoz: That's a really good point of that, especially because it applies to so much especially in this industry in terms of with as I was talking earlier actually. We continually try and make it up as we go along as an industry and fail to learn from other disciplines, other industries and realizing what people have done this before. These are the standard processes maybe I should try following. Makes a great deal of sense. So, when you're evaluating processes to take on board as an SRE and you've got all these different ones, what are the particular traits that you either look for or learn to avoid?

Ramin: Sure. Actually, I think I'll talk a little bit about resilience engineering, which is somewhat kind of new in the field. John Aspa who I overlapped with a little bit when I was at Yahoo is kind of, that's his new kick. So, him, Eric Hufnagel, a bunch of kind of the people I mentioned are in that space. What they've done is they're like, you've got a bunch of process and when things go wrong, people have broken those processes. Then when things go right, people have broken those processes and they're really starting to look at like your people are the resilient part of your network. There's something called a work to rule strike, which I read about a couple of years ago and it's hilarious. I think Italian bus drivers used to do it and they would run exactly by the book and everything would take five times longer.

Ramin: They're like, no, no, we're doing exactly what you told us to do and it sucks. That was the point of like you pay us to be thinking people and you're trying to take that away.

Yoz: The job is often so much more than what it's really been described as.

Ramin: Yeah. So, I mean one of the first managers I worked at like around 2000 he said, “Figure out where you're going and create the least amount of process to get there.” Which I liked that, but sometimes it leaves a lot of room. So, I think I'll let you talk some. Don't want to run away with it.

Larry: No, I’m really enjoying this.

Yoz: Out of the particular processes, as you've been saying you're something of a newcomer, not an entire newcomer to this world. Are there processes that you've taken on in your work with Zebrium and when it comes to family company, especially running an online service of the SaaS that you found particularly useful?

Larry: Yeah. You know, I'm not a big process guy. It's interesting because I'm kind of a tech guy. I'm kind of like this until like three in the morning and I don't like going to meetings and I don't like scheduling them when they're hierarchical. I like the kind where there's a space or at least even if someone's remote, like just hop on a Zoom and talk, go through things. I like that kind of meeting. I like to make room for that processes. I guess in a small company you don't need a lot of process, you need really sharp people and you need to treat them with respect. Right? So, I guess I'm a bad expert on process.

Yoz: Well no that's actually, it's kind of one of the most founding principles of, one of the best ways I've seen Agile described. Kind of pillars of Agile is one of them is basically respect the people and respect the way that people want to work and don't want to work. Sometimes you have to guide them into new ways, but ultimately, it's kind of respecting that they have brains and they're going to want a good reason for working that way.

Ramin: I would argue you actually have a very highly developed process. It's distributed. It's sort of organic. The problem I've run into is you do that at a startup. Everything's running great and you get bought by a company and they're like, “What's your process?” You're like, “Well we just know.” They're like, “How could you? Like where is it?” You're like, “But we know.” And we couldn't articulate and so they gave us their process, and everything went to hell for like a good two months until we kind of pushed them out the door. We're going to go do what we know to do. We'll just write it down first. So, to me it feels like there's low process, but I would actually think about what you have if only so you can tell other people that you have a process.

Larry: Okay, I'll do that. Sounds good.

Yoz: Especially when it comes to onboarding people. So, what have you found particularly effective, Ramin, when onboarding new team members?

Ramin: So, the last time I was on was pretty stable and we maybe onboard one person a year and then we made a mistake and we onboarded five people in a year and this went poorly. So, what we didn't realize was it takes a lot of work. We had a lot of velocity and we didn't realize how much of a drag that was going to be on our velocity and we tried to pair people up with kind of your mentor and mentee, but I'd say we half assed it. We didn't really set a good process. I think making that big mistake was a big learning lesson for me because I figured like we've got a good team, like we've got a lot of trust within the team. People pick that up, but you really had to explicitly kind of explain to the team how you worked. Sometimes we had to actually agree how we really worked. I would say onboard more often if you can, but like don't do more than two people, particularly if you're kind of like the eight-person two-pizza kind of team.

Yoz: Right. Imagine the size of a pizza.

Ramin: Does that answer the question?

Yoz: It does especially because I think there's a really good answer that I don't hear enough to too many questions about how do you do this in a good way. The answer is don't do it very often. Right? Something in particular when it comes to teams, that there's a particular bad practice that I've seen in many organizations that are composed of small teams, which is that one small team is particularly successful at something and the organization goes, those people are brilliant. Let's break apart that team and move them all to other teams and so they can all. No, no. If it's a good team, you keep them together.

Ramin: Sometimes that works if only because those relationships go with that team. So that was one of the things I would say our team actually did well was you need resources from another team. Somebody senior on the team would walk you over and go, this is a friend of ours. Everybody do the handshake, be nice to them. We did that thing for you that one time. Like you're giving them a certain amount of social capital. I've seen other teams completely fail. Like people get launched in our help channel and they're like, “I need a thing!” You're like, “Who are you? Like that's complicated, why do I care? Like who are you again?” Like there was no kind of helping them digest the problem down to something that would be palatable to us and palatable to them.

Yoz: I suppose it's one of the things that is the difference when dealing with large organizations and going off on your own as a founder. So how large is Zebrium now?

Larry: 12 people.

Yoz: Are you co-located or you're all?

Larry: Yeah, we're down in Santa Clara. So, these are people I have run into over the course of meetups, online stuff, career, whatever. Since most of them were kind of in the peninsula or further South Fremont. I live in Alameda, but I was like, okay I want them to come. So, we'll make the office in Santa Clara.

Yoz: So, when bringing new people in have you found that, I suppose if a company's young enough then your processes are kind of up for grabs really all just looking for everybody to help evolve everything?

Larry: Yeah. I mean we do Agile since she brought it up, but I don't consider myself a scrum master or anything like that. In fact, I'm more of a titular. I kind of sit in the corner and grump when it needs to be done. Other than that, I try to be supportive.

Yoz: That is a pretty good description of the CEO role.

Larry: Oh great. I'm getting promoted. Excellent.

Yoz: It's interesting like mentioned Agile.

Larry: Yes.

Yoz: Now that you all kind of running a software as a service and online service, when it comes to things like outages, have you started evolving any kind of processes?

Larry: Yeah, for sure. So, we run our own stuff on our own stuff. First of all, everything runs in AWS and we bring all the logs into another instance from our production instance and then we monitor it there and we build features because that's the best way to learn.

Larry: You're going to see stuff you're using every day, especially when you've got a small stack and you're growing it fast; you're going to hit every edge case. So that's fantastic. Yeah, I highly recommend dogfooding to those who aren't doing it. It's been transformative.

Yoz: We actually at LaunchDarkly we started with the dog food instance.

Larry: Good.

Yoz: Then we renamed it to cat food instance because the dog food instance needed something else.

Larry: I see.

Yoz: Ever since then it's just been referring to cat food.

Larry: Nice.

Yoz: All the time.

Ramin: I got questions for you then.

Yoz: Get in. Excellent.

Ramin: No. So last time I talked to LaunchDarkly, you weren't giving end users a lot of feedback on how many flags were too many or like how complicated the data, has that changed at all or?

Yoz: We do. When was that?

Ramin: Maybe six months ago or at least whoever I was talking to was like, "Oh no, you can do whatever you want." I'm like, "Oh that sounds bad."

Yoz: Well it's interesting. So, I can't speak to what we were doing six months ago because I've only been there two months. So, in fact most of the other LaunchDarkly employees who are here have been doing amazing support on this event probably know considerably more about that than me. I will say that is something, we have now a customer success team that is focused on things like that, but also that we're building out more best practice guides. At the moment our documentation is kind of in the user manual style. We have a lot of blog posts that talk about best practices and it's something that we're seeing much more demand for, especially because there's not a lot out there about this kind of thing. What happens with feature flags is that once you start using them and you can realize how useful they are, you start using them all over the place and you end up with loads of them and that can be a problem. Right? Yeah.

Ramin: Then your immutable infrastructure starts to look pretty damn mutable. I did a bunch of stuff at different code paths.

Yoz: It can't be on fire. It's immutable. That's not allowed. Yeah. It's interesting because we have some of those problems where we're going, okay the main app now have several hundred flags and we should probably be cleaning some of those out. Part of it is about building the features to help identify the ones that and when we have some for that. Yes, there's continual work in providing best practices. As well we're kind of learning from the industry. There's a lot of this stuff that we're learning at the same time as everybody else. At the same time, I'll ask you the same right back at you. I mean with your experience with either feature flags or other things related to testing in production because this is a new field, this experience or insight is incredibly valuable.

Ramin: I think something similar for me was I was working on like a sysctl thing where within in Twitter we had a bunch of SKUs and machines and I wanted to be able to tune machines based on like different CPUs and a bunch of other stuff. So we built it and like you could have these fall throughs and knockouts and then it was sort of the person I developed with, we kind of looked at each other and was like, “Can anybody else make heads or tails of this or do we vastly need to simplify what's allowed?” It was good we had that conversation because I had done the last thing at the last startup where I was a department of one and I had built a system that only I had enough context to run. Right. To me that's what I see the feature flags is if you've got too many of them or really any sort of complicated like config system where you're merging a bunch of values and stuff like does anybody other than you know what's going on?

Yoz: Yeah, we are very good as an industry at making things that are too complex for us to manage and to describe to other people. Basically, lots of foot guns, very capable foot guns that we're happy to fire randomly. It's this kind of learning, especially about this. One of the things I was going to ask and chatted briefly about was about postmortems. Postmortems continually fascinate me because I used to work with a brilliant Agile practitioner who said that if you only learn one Agile ritual, it is the retro that is the most useful one because it's where you actually do the learning. It's where you do the improvement. I'm interested to know the practices that you found that make successful unsuccessful postmortems.

Ramin: It's funny because when a postmortem goes well almost nobody notices. We had an intern and we had a postmortem; it was a decision I'd made like eight months before and that turned out to be the wrong decision. We had a series of comedic errors and what happened was the app had stopped serving long enough for all the values to run, fall out of the cache and then what we realized was we needed to spin up a thousand instance of an app that normally has a hundred or like maybe a dozen and run it for 14 hours in order to rehydrate the cache. So like comedy of errors. We had a good timeline. Everybody knew the parts. We came up with the work and the manager kind of sat back and let the ICs do the thing.

Ramin: We did the thing and then I pulled the IC aside, or the intern and I said this was the best meeting you've ever been in and you have no idea. Part of it was like the people working on it had had about five years of context with each other and there was a lot of trust of like this is obviously how it got there. It was odd enough that there was no finger pointing because you're like, well yeah that is weird. Okay. Like we totally screwed that up and kind of broke it out for her of like how this all went and also had that discussion of like 20 years into my career when I screw up, I don't really pay too much of a price and I knew as a new engineer might feel that you can't be wrong or you're like I want to get promoted to the next level or whatever where I've sort of arrived in my career.

Ramin: How the team works. Like if the team is very uptight about being wrong, then you're going to be uptight. If the team is like, “Yeah it's wrong.” Actually, former coworker of mine was here tonight and he had this thing where he'd just say, “You're fired.” Which was sort of hilarious because like that's the worst thing that like really could happen. He was just like, "Oh, you screwed this up, you're fired." Then you look at it, you're like “Oh shit, I'd fire me too.” Or I'd be like, “no this isn't my fault. It's his.” Like we'd pass it around and eventually the person would be like, "Oh yeah that was me." That team could do it. I don't think the I'm fired works in general so don't go try that at work unless you know everybody for a while.

Ramin: It was funny, and it was this is the worst thing that could possibly happen, and it just was a way of passing like whose problem is it at the moment around and I thought that was fun. First postmortems though, it's really like I've been in ones where you have a very nice one because everybody trusts each other and there's this idea. I've been in ones where like people are just waiting to finger point and then you're very defensive. For me it's always having a good timeline from the beginning just simplifies everything because like you start slotting stuff in the timeline and now you've got something concrete. We can argue about who did what, but like at least we've got the timeline.

Yoz: Right, right. Then of course there's the timeline afterwards in terms of how do you, one of the problems that I've seen with postmortems is just finding the time to have them. In a situation where people, stuff is exploding especially if engineering at the same time, finding the time to slot in the postmortem and then the actual work, the remediation work to be done afterwards can be incredibly difficult. I mean is that something that either of you have experience with or in terms of…

Larry: What I've noticed about postmortems per se at larger companies that I've worked at was that there's two kinds. One is when the team that's present is capable of doing something that will prevent an occurrence of it in the future. The other is when they're not. So, then they have to do something brittle or a work around or they have to go complain or somebody else has to. So, a perfect example from my world would be, oh this actually this is a great. So, there was the Stripe outage, right?

Yoz: Sorry which?

Larry: Stripe.

Yoz: Oh, right.

Larry: A few months ago. Right. So, if you were looking at the logs, what you would have seen was the Postgres replication heartbeat was happening and then stopped happening. Then when a deployment happened, then all hell broke loose is how I understood when I read it through. Who knew to go instrument that message, that particular thing happening right or how to do it? Okay, fine. We get that. Let's say we had a postmortem, now we're not Stripe, not talking about that anymore, but let's say that was our problem. We could have a meeting, we can say, "Bob, go hookup something to look for that thing happening and then make sure that an alarm goes off it stops happening."

Larry: Right. Okay. While we're having that meeting, there's another service being created. There's another dependency being created and it's going to have exactly the same problem. So, have I really done a postmortem with a root cause corrective action? No, no it's going to happen again. So, it's a different class. It's the same class of thing, but there's no way that I sitting there with my knowledge could work around it.

Larry: So, at those points, people need to be willing to look for technologies or processes or budgets to go and fix or do something at a higher level. I think that's what makes a successful use of postmortems versus sort of a less successful, more typical one that I've seen.

Yoz: Yeah. What you were saying earlier, especially about responsibility that you're giving people who's responsibility, there's the continual complaint of being given responsibility without power. Especially in situations like you were saying earlier that with an SRE, like pull an SRE into the team and somehow assume they're going to magically fix all the problems and it's just their job to point out the problem.

Ramin: The other thing I've seen is I've often got into postmortems to help another team out because like we sat down and we did a thing and we knew we had a race condition and we reduced it down to a second, but we knew the binary was going to be missing and they were bad at making RPM. So, I'm like, just do it this way. It'll be close enough. We ran some tests that look good. So, then we get pulled into a post-mortem at SEV3 and we go and we find this team had had problems in this one second window and two other jobs failed to launch.

Ramin: We're like, okay. So, make it this straight, like we did this thing across all machines, several dozens of thousands and we had two problems. This is what we call a rousing success. You guys have some work to do. Like it wasn't about shifting work or shifting blame. It was the two really like that's why we're here? Like out of like literally a hundred million jobs. Go fix your stuff. We didn't say it that meanly, but it was like I think maybe you should just have some retry logic and that'd be cool. So, you as a senior engineer like that is a lot of your job is to go like, “Everybody take it down a notch. We've seen this before. Go fix your thing.”

Larry: Yeah.

Yoz: That's interesting. I mean it's great if you can make things relatively stamped, keep everybody calm, make it boring, you know it helps a lot. Is there anybody here who has? Do you have any questions, any comments about any of this because you know this is fairly small colloquium gathering of people. Any questions for the panel here? We have Cindy who has, where is Cindy?

Isaac: You were saying something about the-

Yoz: Sorry, Cindy.

Isaac: Italian bus drivers? Very useful I heard. Malicious compliance.

Ramin: Yes. Yes. I think I've heard that before.

Yoz: Love it, thank you Cameron. Malicious compliance. Sorry. Yes, I'm sorry, what was your name?

Isaac: Isaac.

Yoz: Isaac. Isaac was saying the term to describe the work to rule a habit. The Italian bus drivers was malicious compliance. So, doing exactly what they were told to do with malicious intent and it works surprisingly well because it's only once it's acknowledged how much more your job entails than what you're described as doing or what you're being paid for that people start to notice. Any other questions?

Audience question: How is the notion of quality affected by the frequent releases?

Ramin: So, speaking from the infrastructure side, which tends to be different, the joke we had on our team was you're your own grandpa which meant we had no product manager, no project manager, no QA. You generally spec the work, you did the work, you signed off on your friend's work and hope there wasn't an outage. Generally, been most of my career in infrastructures, you not have the same backup that you do on like front end or back end, like a main line sort of development applications. However, you end up doing a lot of the same work. You kind of figure it out.

Ramin: So that's more my experience is like you didn't have QA to begin with. So, you get better at writing tests. You get better at limiting blast radius. You're perhaps a little bit more conservative than you should be because you don't have other teams kind of teaching you how to operate in their world. I think it's gotten better the last couple of years, particularly with cloud vendors and stuff where you're not splitting your time between trying to manage the system and move the system forward. So, I write a lot more tests the last five years than I did anytime previous to that.

Yoz: So, automate the tests? So, doing a lot of there is QA, but it's automated.

Ramin: Yeah.

Yoz: Larry, what does Zebrium do for releases in QA?

Larry: Well, we test in production. What that means for us is that there's the dog food. Then we've got accounts that have their own clusters, but they're not always on using it. Depending, there's times of day they don't care. Then finally there's the multi-tenant instance, right? So that we kind of stage it out that way. Of course, there's internal testing, but it's short. It's like days or a week. So maybe we'll push some, every week we kind of churn out a new kind of set of cooperating binaries and then maybe for a few days if there's some tweaks, we'll be looking at it and then we'll push it to the first couple dog food and individual customer. Then finally we'll push them all the tenants. So that's like a rolling three-week window or something.

Yoz: That's a pretty common thing I think for this size of company. You're not doing daily releases yet.

Larry: Right.

Yoz: Especially the kind of gradual rollout, is it? It's not ring deployment is it? I can't remember. Do a rollout to some initial canary instances first. As Larry was saying, as you can tell by the name of the meetup, we're proponents of testing and production. There is something I think very important, especially in Ramin's presentation when he was saying that you've got to make sure you have signal to be able to tell whether something was a success or a failure. There are certain kinds of failure that you're going to immediately know about, and you can either roll back or flip a feature flag, or whatever it is to turn it off.

Yoz: There are some kinds of failure that you're not going to know about because they don't involve system failure. They involve users not being able to do something or possibly the failure. You got to be watching your user actions. You've got maybe they involve you've just destroyed your marketing funnel and you don't realize it. So, having numbers and signal through all this stuff so you can actually spot when something fails is vital. There's part of me that still really values exploratory QA before deployment. I think especially in new features, but especially since coming to LaunchDarkly, but also moving more in the Agile direction with my work. Seeing the ways in which testing in production does actually work and especially the way that it uncovers things that you will not be able to detect in staging. Right. It's only once you actually get real production traffic that you notice these things and so preparing for that is the best thing.

Ramin: Well the thing that would be aware of is we've certainly said this on our team of you release something into production, it doesn't go well, you release something in production doesn't go well, and then somebody on the team might come and have a talk with you and go, I'd like to see a failure of a higher quality next time. Just because like sometimes you're like throwing it over the fence and other times you're like, okay this was a unique thing that you triggered. Yay learning. If you're just making the same mistake over again, we need to have a talk. I think that's where you use the automated stuff?

Audience question: Are you running your automation pipeline in your build pipeline?

Ramin: Both. Yeah. I mean honestly like we do a ton. Like I manage Puppet a lot so that has a DSL. So, we like run all the tests on that, run all the tests on any Ruby that might be included, like try and compile a catalog, blah blah, blah.

Ramin: That's even on check in, then run CI, then somebody has to code review. Like honestly, it's as much as possible as automated. With that kind of stuff, it was actually we were getting to the point of spending on VMs, but it's really what do you feel comfortable? If you can fail back and forth quickly, great. You've got more options. A lot of times for me, config management being broken it was fine. Like we couldn't spin up new machines, but we'll fix it. Config management handing out the wrong values is terrible, because now you've just misconfigured your entire fleet. So, we optimized kind of for that last problem rather than solving for just broken. So, it really kind of depends on where your problems are in my opinion, at least where to do the initial investment.

Yoz: I think we'll wrap it up there. Marvelous. Can we please have a big hand for Larry Lancaster and Ramin Khatibi?
