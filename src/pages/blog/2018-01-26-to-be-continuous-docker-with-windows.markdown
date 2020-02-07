---
author: andreaech
comments: false
date: 2018-01-26 16:56:41+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-docker-with-windows/
slug: to-be-continuous-docker-with-windows
title: 'To Be Continuous: Docker with Windows'
wordpress_id: 2266
categories:
- To Be Continuous
tags:
- cloud
- containers
- Docker
- microservices
- serverless
- Taylor Brown
- Windows
---






In Ep. #41 of To Be Continuous, Edith and Paul meet up with Taylor Brown, Program Management Lead in the Windows and Devices Group at Microsoft. The discussion of the day: showing the benefits of virtualization and using Docker with Windows.




<!-- more -->

This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.

﻿﻿<span data-mce-type="bookmark" style="display: inline-block; width: 0px; overflow: hidden; line-height: 0;" class="mce_SELRES_start">﻿</span>&lt;span data-mce-type="bookmark" style="display: inline-block; width: 0px; overflow: hidden; line-height: 0;" class="mce_SELRES_start"&gt;﻿&lt;/span&gt;





**ABOUT THE GUESTS**


[**Taylor Brown**](https://twitter.com/taylorb_msft) is Principal Lead Program Manager at Microsoft where he builds and improves virtualization as a core platform. Previously, he was Program Manager on the Windows Hyper-V team.

**TRANSCRIPT**

**Paul Biggar:** What do you like least about Docker?

**Taylor Brown: **I mean, I think the thing that's been the most challenging as we've worked with Docker and the Docker community is really bringing Windows into that, and that up-front was a bit of a hard sell.

These are people who are very, very, very Linux-centric, and explaining to them, "Windows is different." And it's okay that Windows is different. It's a different way of thinking about some parts of the system. But we can make the experiences the same.

That was definitely a bit of a challenge. Because of that, we've had to think differently about how we've had to work. It took some definite work between both sides to get over that. And I think there's still some folks in that community that are a little nervous about it and they feel like Windows is making them dumb down Docker.

**Edith Harbaugh:** Now would be a great time to introduce yourself. Because we're recording from [Microsoft Build](http://build.microsoft.com/) in Seattle.

**Taylor:** I'm Taylor Brown. My role is I'm the Windows server team and I'm a PM for developer strategy. As part of that, I own the container work. I've owned all the work that we've done to bring Windows Server containers and Hyper-V containers to Windows and all of the work that we've done in the Docker community to bring that to Windows as well.

**Paul:** I think we largely skew in the Linux-y world. Can you tell us what is Docker on Windows? And how do you use it? And why?

**Taylor:** It's actually exactly the same as it is on Linux. You start a container by saying, "docker run," but instead of saying Ubuntu, you say, Windows Server Core or Nano Server.

We really break down what Docker is: it's a management toolset. It's a framework for running containers, for managing containers. When we started working on containers originally, the first meeting we had with Docker, I flew down there all happy with, "Here's the API we're going to build. Do you guys want to make your Docker thing," this ELI, whatever, "work on Windows?"

Solomon got kind of excited and said, "You know this is all open-source. You guys could just make it work." And that was kind of a hard deal for us at first. This was kind of right at the point when Windows was starting to dabble in open source a little bit.

I was like, what does it mean for us to go work on an open-source project, as the kernel base team? We got over that, and we started working on it. Ultimately, our goal became, let's make this feel just like it does on Linux but with the Windows semantics kind of plumbed in.

**Edith:** How did that meeting happen in the first place? Why were you flying down to San Francisco?

**Taylor:** The Azure team had already been meeting with Docker a little bit, and I was actually down there for another conference. I was down there for PuppetConf, when we first met with them, and I was like, well, what's the harm? I'll spend a day. I'll go over, we'll talk to them. Maybe they'll want to put this Docker CLI on top of this Windows API that we were building and that would be great.

It'd make it easy for users who were using that to just keep using it, right? It'd been in Microsoft for a long time. It'd been on Windows for 13 years, I'm kind of used to it. We walk into a partner, we're like, "Hey, do you want to do something with us?" They're like, "Yes, what do we have to do?" This was a very different experience. It was like, "Yeah, it's all open, you can just go at it." That was a very very interesting experience for us.

**Paul:** You used Docker on Windows to run images of Windows servers, is that right?

**Taylor:** Yeah, that's what we have today. Now, we just, two weeks ago at DockerCon, showed Linux containers running natively on Windows as well.

**Paul:** Oh, nice. Okay, that was my next question. Can Windows containers then run on Linux and on Mac?

**Taylor:** No, they can't, not at this point, anyway. Because the way that we need a shared kernel. We need some kernel guiding us, right?

**Paul:** Yeah, yeah.

**Taylor:** The way we actually brought Linux across is by using our Hyper-V technology.

**Paul:** Right, right.

**Taylor:** We built this container type called a Hyper-V container, originally. Now we call it a Hyper-V isolated container. What that does is it spins up a special VM that we built just to run a container. Originally that only ran Windows kernels, but now we're extending that to run Linux kernels. We've got Red Hat, SUSE, Docker, of course, and Canonical all itching to give us kernels.

**Paul:** I feel like I read somewhere that Ubuntu ships by default in Windows 10, or something along those lines. Did I misunderstand that?

**Taylor:** We've got this experience in Windows 10 called WSL, the Windows Subsystem for Linux.

**Paul:** Okay.

**Taylor:** That allows us to run a bash prompt and apt-get and all of your traditional Linux tools.

**Paul:** Is it the Ubuntu apt-get? Which repositories are you pulling from?

**Taylor:** Yep, it is Ubuntu.

**Paul:** Okay, okay.

**Taylor:** Now, today in the keynote we announced that we're bringing a couple other discservs to that party. SUSE is going to be coming along, and then we're working on Fedora as well. So we'll expect that to come along pretty soon. You'll actually be able to choose, on Windows, whether you want to use Ubuntu or SUSE or Fedora. We announced earlier this week that we're going to bring all of that to server as well.

**Paul:** All right. This is all using Docker, or it's using the Hyper-V thing? That's similar to how you run Docker?

**Taylor:** It's actually completely different.

**Paul:** Okay.

**Paul:** The WSL work is all done through, basically, kernel emulation. We emulate all of the Linux sys calls and turn those into the corresponding Windows calls, so that it actually runs all formatted binaries. They're exactly the same image from Linux on Windows.

Now, that works really well for scripted environments, development environments, those kinds of things, but in production that causes some challenges because, if we don't have that emulation done just right, in production we're going to have a hard time emulating that.

So for production environments, that's where we use the Linux isolation technology. That allows us to run a real Linux kernel, the stock kernel from whichever distro you choose, to get you the exact same environment you're going to be running in production. So it's a kind of a great marriage of the two technologies.

**Paul:** The other question I had is, we were talking to Jeffrey Snover earlier, and he was telling us about PowerShell and how it's all different to Bash and that sort of thing. So I'm curious, is Docker that runs on Windows, is it a PowerShell-y structured data that can be consumed by other things?

**Taylor:** We made an open-source PowerShell module that wraps the Docker REST interface.

**Paul:** Oh, interesting.

**Taylor:** So, even on Linux, in fact we demoed that at LinuxCon two years ago, you can actually run PowerShell on Linux to manage Docker, if you wanted to.

**Paul:** The world is getting crazy.

**Edith:** The world is crazy. It's turtles all the way down.

**Taylor:** What we found, though, is that most of our users just use the Docker CLI on Windows.

**Paul:** Yeah, yeah, yeah.

**Taylor:** That's what they're familiar with. They're comfortable with it.

**Paul:** It's what all the docs say.

**Taylor:** It's kind of what we've tooled around in. But just being able to open-source that PowerShell module and get that feedback.

**Paul:** Does that module parse the output of the Docker CLI and then convert it into the PowerShell data?

**Taylor:** It uses the REST interface design.

**Paul:** Oh, the REST interface. You said that, yes, okay.

**Taylor:** We just snapped to that, and actually what became really valuable out of that is that there was an open-source wrapper for the Docker REST interface in DotNet. We brought that in to Microsoft. We got the original author of it, donated it to us. So we started maintaining that. That has been used a lot. While the actual project has kind of stagnated a little bit, the middle pieces of that have been adopted pretty heavily.

**Paul:** I don't know if you see it yet, but is the potential that you see here that people are going to run fleets of Windows servers with Kubernetes and Swarm, and that sort of thing?

**Taylor:** Yeah, we're seeing it already.

**Paul:** Okay.

**Taylor:** We talked at DockerCon. We had a couple good customers come up and talk about their experiences already. Northern Trust just moved a bunch of applications over, running them in containers. Microsoft IT just finished their 20th application that they've ported over already.

A lot of those are just taking an existing app, moving it straight into a container, no code change at all, and getting rid of an older system and consolidating systems together. What we're now starting to see is that people are starting to modernize those apps. They're actually starting to break them up and turn them into smaller microservices.

At DockerCon we showed the production version of Swarm running, so we could actually have a Docker-datacenter-managed environment of Windows and Linux hosts, side-by-side under the same management framework, with the same container images flowing back and forth.


<blockquote>Now a developer really can just pick the best image for their job, whether it's Linux or Windows, and marry them together. </blockquote>


**Edith:** What's driving this? I mean, that's a great use case, Northern Trust. What's what's propelling them to go down that path?

**Taylor:** I think we're seeing two things happen a lot. One, there's a ton of legacy code out there, especially in the Windows environments. People have built WCF apps, Windows services. There's thousands and thousands of them that they've got running on servers that are really not very well-managed. It's hard to re-deploy them. The deployment binder is gone.

**Edith:** Like a physical binder?

**Taylor:** Oh yeah, some people will remember those. I certainly do.


<blockquote>We used to actually write a three-ring binder on, "Here's how you deploy an app into production."</blockquote>


We'd sit down in the deployment room and walk through it with a piece of paper and pencil and make sure we got it all right. Those got lost, and so they don't even know how to redeploy their app.

**Edith:** Wow.

**Taylor:** They're afraid. If that server goes away, we don't know what to do.

**Edith:** Wow.

**Taylor:** Much less make a code change. So everyone's afraid. And now if we can get it into a container, we can get it re-deployable. Then that fear of making that code change just kind of starts to melt away. Because I can roll back. And so now, all of a sudden, that microservice architecture, it's possible. It's not going to happen overnight. I'm going to have to break it up over time, but I've given you hope. I've given you hope to move forward.

**Edith:** How common is that? How can you lose the binder?

**Taylor:** It's pretty common.

**Edith:** You'd think it would like be stapled somewhere, "Do not lose this binder."

**Taylor:** And then the person who stapled it left, and the person who cleaned out their office thought it was just trash and threw it away. The ninth Windows update that they took five years ago changed something, and someone went in and hacked the registry and made it work again. That person's gone or didn't document it or sent an email to someone to put it in something, and it didn't.

History happens, right? And then these systems have been made to just keep working.

**Paul:** Wouldn't their being converted to microservices, are people going full, 12-factor app on them, stopping them writing to disk and all this sort of thing?

**Taylor:** You know, a lot of those start to happen. What we start to see is, "All right, we'll take the monolith and we'll break out one piece at a time." So maybe we break out the authentication library. We make that its own microservice. Or the logging functionality, or something like that.

Our guidance to people is to try to go down the right road when you do that, to make that microservice consume and produce its own data. Give it its own data store, don't go write it back into the same SQL server as with everything else. But if you can't, if that's just really not possible, it's still valuable to break it out. It's better than nothing.

**Paul:** The Linux world there's this prevailing, let's say, best practice. And it's supposed to be not the only practice but the direction in which you're going, to have only one process running in a Docker container. My view of a Windows machine is that there's always hundreds of processes and things running. So does this change in Windows servers, is it more than one process or is it more Windows-y sort of way?

**Taylor:** Windows has always had a different architecture in terms of, we've moved a lot of things into user mode. I call them system processes. I think of a blank machine, something that's just booted up and has nothing else running on it, as just being system processes and then the kernel. And even in there, we have on Server Core, I think we have 18 processes running. On Nano Server, we're down to six, and we're re-factoring that even further.

**Paul:** What are the six? I'm really asking, is there a Windows update daemon in this somewhere?

**Edith:** Yeah, you seem pretty determined to get an answer.

**Taylor:** There was and it's gone. We've just removed it from Nano Server going forward. So we're starting to make Nano Server more and more of that feels a lot more like a Linux instance, in that it's optimized for a container. We're optimizing a lot of that work so that it's in that workflow.

So Windows update's gone. You pull a new container image. We're removing processes that aren't necessary. Like, all of the WMI processes from management are gone because you don't manage inside the container. You manage the outside. But it's taken us some time to get that really factoring in. One of the things I'm really excited about now is that we get to do that faster.

We're going to start shipping builds once a week. We're putting builds out through our insider program this summer of Windows server every week. We went from six months between a preview and about three years between a release, to every week we're going to ship a new build out.

**Paul:** Is that a new release?

**Taylor:** A new release every six months.

**Paul:** All right, new release every six months.

**Edith:** What drove the decision to do that?

**Taylor:** A lot of it was getting feedback from customers. As we went through the technical previews, especially from the developer side, as we started working with developers and having passion for our developers again, and containers.

**Edith:** Again!

**Taylor:** Yeah, well, I feel like we really did lose that for a while. It's been my charter now.

**Paul:** The Ballmer years?

**Taylor:** Well, it was just that period of time when virtualization was king. And the IT pro was king.

**Paul:** Right, right, right.

**Taylor:** And we had DotNet, and we felt good about that. We weren't really thinking about what's the next thing for the developer. In the meantime, they were finding their own next thing. So as we regain that, and talking to customers again, and developers, their feedback is awesome. But I've got to be able to give them changes quickly.

I've got to say, "All right, you gave us this feedback, how does this feel? Is this the right experience or not?" In order to do that, I've got to get builds out quickly, and at the same time we saw the feedback we're getting from the Windows 10 insider program and how quickly they were able to respond to feedback.

You put out something and you're like, I don't know if it's right or not, but I'm going to try it. And you ask people if they like it, and they tell you, "No, it's terrible. Go back to the drawing board." Or, "Yeah, that's great that's awesome. You should do more of that." I don't have to guess anymore. I just get to experiment.

**Edith:** What did you have to change organizationally to get from a three-year release to every week? It's a massive change.

**Taylor:** One of the biggest changes that I think we went through is resetting the expectations. Everybody came in with their feature list like it was going to be a three-year release. And they're like, "All right, we're going to go redo all of this and we're going to redo all of that, and all these new features." And they obviously don't fit.

You have to walk people back through and say, no, we've got to do this in smaller and smaller pieces. That feature that you want to build sounds great. What is the small version of that? What is the first step in that? And then how do we validate that we're on the right road?


<blockquote>The real nice thing about not doing it in these long chunks, if you start off on something and you're going in the wrong direction, you can figure that out before you finish it. </blockquote>


Because we get to the point where we're with these three-year release cycles, we would do a feature no one would ever use. Because at six months we made a choice, with the best information we had available, and we went the wrong way. And then we built a feature that's just kind of languishing there forever.

This gives us that opportunity to course correct and say, nope, that was the wrong path. Let's shift and move back over.

**Paul:** We've done, what, four, five podcasts today? The amount of times that the people have said the word "validate" is really really high. There's a whole load of, "We're talking to the customers." I don't know what the Windows world was like in 2003, but it certainly didn't feel like there was a whole lot of talking to customers back in the dark old days.

**Taylor:** I think the 2008 period was the time when I really felt it. I was actually on our quality team at that point. I was doing testing, and it was painful. We'd build an entire experience without ever finding out from a real person, is this something they want and were going to buy.

**Edith:** Let me push back on that for a second. I mean, the pushback is always like, if I asked somebody if they wanted a car, they would say I just want a faster horse. So how did you break free of that mindset of, it was actually good to talk to people? Because there's the cult of Steve Jobs of late.

**Taylor:** You do have to balance it, right? If you ask people every time, "Do you want it X or do you want it Y?" They'll be like, "Well, I would like both, please." So I do think you have to build some part of it out and see with yourself, how does this actually work? And then sit with them and understand, is this what you wanted? Why isn't it what you wanted? And that "why" question's always the important one.

It's not, "Do you want X or Y?" It's, "Here are some options. Why is this one better than that one for you? Why do you think this is the appropriate choice?" Because you find, as you go through that, sometimes they haven't thought about a different way of doing it.

And if you jump to that conclusion, and say, oh well, we've got a better idea, you've gone off of the rails again. You've got to then re-validate with them and say, what if we did it this other way? When you see their eyes light up and say, "Oh yeah, that would be really cool." You know you've got something.

**Paul:** When you were in that six-month period of, "We're building something and no customer ever sees it." How did you delude yourselves into that? I'm asking this so that people can recognize themselves in it, I hope.

**Taylor:** I think we always started out with the best of intentions. We'd go out, we'd get a customer list and we'd talk to a bunch of people. We'd look at our competition and we'd build a feature set and say, all right. To compete with this competitor, we need X, Y, and Z because that's on our checklist.

The salespeople told us we need this in order to compete with that. And you know, this customer had these bugs, and we really want to fix those. And boy, this new feature's coming out, this new architecture or whatever. You bring all that together, and you go, all right, here's the big pile of stuff we have to do.

**Paul:** You're not dogfooding or something along the way?

**Taylor:** Well, on these long cycles you don't really have anything that's worth dogfooding yet, because you're like, all right, we're going to go carve the statue out of marble and it's going to take a while.


<blockquote>You just really can't see the shape until you're done. The easy failure there is that, while you're carving it, the world changes around you. </blockquote>


Especially now, right? There was a point in time where six months was not that long. Yeah, it's pretty long now. So if you don't check back every now and then and say, are we still carving the right thing? You're going to go off the rails. Then, as you go through that, all the macro decisions are the ones that kill you.

It's not the, "Are we building the right feature?" ones. It's the, "Are we building it the right way?" Are we exposing this in a way that the user can actually understand how to use it? Are we exposing it in a way that makes sense to them? Or are we building something that because we're so familiar with it, we're so close to it, that we get it, but no one else will?

I have built those features. I've built features that were so complex that no human would ever understand them. The only people who understood them were the seven people who built it and the people who architected it.

**Edith:** I think you fall in love with your own features and you start to design them, and you're like, oh, but I need this other layer. And then it's very hard to let go of them.

**Taylor:** Right, it is. It makes sense to you, and you're like, I understand. I get it. Why can't other people understand it? I think when you can do these shorter cycles and you can layer things with people's feedback on them, sometimes it's a little disappointing. I built something, and I don't understand why people think it's the wrong approach.

But I'd rather have that macro disappointment and be able to respond to it and fix it than the big disappointment of, oh wow, we invested six years of someone's time into this thing and no one's using it, right? I feel personally accountable to our engineering team to make sure that they're doing the most impactful work possible. And every now and then, we're going to have to have a conversation of, "Sorry I steered us in the wrong direction."

We got some feedback. We need to go change that. That's a much easier conversation when it's a couple weeks worth of work than, "That whole vacation you had to cancel in order to get this feature done, and that late night and that weekend we had to work..."

**Paul:** Your kid's soccer game that you missed.

**Taylor:** Right, yeah. You know, tell Timmy I'm sorry. We didn't know.

**Edith:** It is Timmy, right? Not Tommy?

**Taylor:** Yeah. You know, that's a terrible place to be.

**Paul:** I like what you said about the world changing around you. One thing I'm very curious about in the Docker world is, where is this whole thing going? Docker seems to change all the time. How people use Docker changes all the time.

Seems right now that Kubernetes is sort of like the killer app in the Docker world, at least in my mind. So I'm curious, where do you think this whole Docker and DevOps movement is going?

**Taylor:** I think the core Docker experience hasn't changed a ton. The orchestrations base has been hot for a while and is going to continue to be hot for a little while. We definitely see a lot of interest in [Kubernetes](https://kubernetes.io/). We see a lot of interest in [Service Fabric](https://azure.microsoft.com/en-gb/services/service-fabric/). We see a lot of interest in Docker Datacenter.

It just depends on the customer, but we definitely see a lot of Kubernetes interest. I think that's a lot to do with the way people are thinking about software development now and breaking things down into smaller pieces. There's some value in the ways the Kubernetes community has thought about that. I continue to advise people.


<blockquote>I still think there's going to be more orchestrators before there's going to be fewer orchestrators. I think there's at least going to be one or two more that pop in. </blockquote>


**Paul:** An uptick, you think?

**Taylor:** Yeah. And then I think there's going to be a bunch that dies off. Then at the same time, we're seeing all of them move towards serverless and functional programming and all those start to come into play. What I expect to see is, I think we're going to see a mix.

I think we're going to see a lot of people who go, "Okay, what is the right layer for this particular part of my code?" And maybe for some it's paths, and maybe for some of it, it's going to be running traditional VMs. Some of it may be containers, and then some of it's going to be functions and more serverless compute.

**Paul:** It'd certainly be an interesting world if the major impact of Docker is that it allowed people to move existing loads into the containerized world, or let's say, a cloud-y world. But actually, all the new developments ended up on something that was serverless.

**Taylor:** So we're certainly allowing people to move their code around a lot easier. That's been one of the huge benefits. Whether they want to move to the cloud now, or if they think they would want to move some day, or they're afraid of getting locked in to one cloud or another. That's been pretty powerful, and I think we are going to see a lot of people experimenting with, what is the right layer to build the next piece of the app in?

We launched the functions on prem this week, as well. Because now I can actually run an Azure function using a container on Windows on my laptop. Not only can I harvest all that compute power that's around, but that means I can actually have an entire environment that is really completely disconnected from Azure, using both functional programming as well as containers side-by-side.

As we move into more microservice frameworks, whether it's Service Fabric or whatever other microservice framework, that's a really interesting option for new development as well. And then there's always the illusion of, well, what parts of it should just be paths? Do I really even need to worry about it? Or can I just sling up a website and let whatever cloud provider I choose run it?

I think we're going to see a lot of hybrid around that. I think we're going to see a lot of people start to build their new apps in the right way for whatever that goal state is, and they're less worried about the lock-in because those front-end pieces, they get rewritten pretty often anyway. They're smaller than they ever used to be. It's the middle tier and the back-ends that are really really important for them.

**Paul:** Any more directions in the future of Docker?

**Taylor:** I think you're going to continue to see them, and us as well as them, continue to reach out to more and more development scenarios. As we bring Linux containers over to Windows, we just had a really good meeting this week on what does that actually mean in some of these broader scenarios?

Like, "Hey, I'm a dev. I'm sitting down at Visual Studio and I'm building a container. Is that a container that's going to run on Linux or Windows? Well, what if it's DotNet core and it runs the same on Windows and Linux? Which container do I build that for?" Your mind starts to explode.

Well, maybe it should be both. What about if it's a multi-stage build, can I use a Windows container to build Linux? Or a Linux container to build a Windows image? That's kind of interesting. How do I specify that? How do I think about that? How do all of these experiences start to come together?

I mean, containers are still super early. We talked with a large retailer this week. They want to roll out containers to 70,000 locations in the next year. That'll be their backend for every location they have. Because today they have to run two physical machines with VMs on them, and they're running two or three VMs each, and the update to that means that they have to push an entire new VHD down to that store, over some dial-up connection in some cases, right? What they want to do is publish a new container image and have every store just pull down that container image automatically. That's a huge shift for them.

**Edith:** That's a really cool use-case, too. What surprised you most at your time at Microsoft?

**Taylor:** I think how much the company continues to grow and shift, even for a large company. When I started, 13 years ago, I started as a developer. That was my day job, was to come in and write code. And it was a very different company than it is now. I worked on very different projects. I worked on the Microsoft smartwatch at one point.

**Edith:** Is that a smartwatch?

**Taylor:** It is not a smart watch. It is a new smartwatch, which was a great project. It didn't really work out but it was still a lot of fun. And we actually learned a lot doing it, but just seeing how much the company grew and shifted between then and now and how fast it's changing, even now.


<blockquote>It just blows my mind for a large company to move as quickly as Microsoft has. It's pretty inspiring. </blockquote>


**Edith:** It's been really great to have you come by. Thanks for coming.

**Taylor:** Thanks for having me. This has been a lot of fun.

**Paul:** It's been awesome.





