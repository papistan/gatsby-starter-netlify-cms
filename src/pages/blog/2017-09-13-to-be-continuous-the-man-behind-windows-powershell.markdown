---
author: andreaech
comments: false
date: 2017-09-13 14:32:40+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-the-man-behind-windows-powershell/
slug: to-be-continuous-the-man-behind-windows-powershell
title: 'To Be Continuous: The Man Behind Windows PowerShell'
wordpress_id: 2053
categories:
- To Be Continuous
---

In the latest episode of To Be Continuous, Edith and Paul are joined by Jeffrey Snover, the inventor of Windows PowerShell. Jeffrey describes the tremendous cultural shift that was needed to shift Microsoft to a continuous delivery model.

Jeffrey recalls how he overcame the cultural challenge by finding the “coalition of the willing” and starting small. Jeffrey also recounts his inspiration behind PowerShell and talks about how today every layer of the technology stack is undergoing a revolution.

This is episode #37 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->

This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.







TRANSCRIPT







**Paul Biggar: **Okay, so what is the thing that you like the least about continuous delivery?

**Jeffrey Snover: **The thing I like least about continuous delivery is going through the painful cultural change to get everybody on that model. So I'm in Microsoft and we're Windows, and the previous version of Windows was a three-year release where we planned for a year, we coded for a year, and then we took a year to stabilize and then release.

**Paul: **Very waterfally.

**Jeffrey: **Three-year waterfall. And the model of, "Hey, now we have to go and do it in small batches and quickly." And from the OS side, that's very hard. What we did was we broke up some teams and we're doing it like that with the PowerShell team, trying to get into that model. And it is a painful thing. You know, you have to change your mindset. People want to stay in the past, like, "Wait, how do I do that?"

And so that's the hard thing. I mean, once you're through in that hole, it's a much better world. But getting from here to there is extraordinary painful and not everybody makes it. I mean, that's pretty painful.

**Edith Harbaugh: **So now would be a great time to have our guest introduce themself. We're podcasting from Microsoft Build and we're so honored to have you with us today.

**Jeffrey: **Yeah, howdy, I'm Jeffrey Snover. I'm a Technical Fellow at Microsoft. I'm the Chief Architect of the Azure Infrastructure and Management Team, so it's a pretty wide set of responsibilities, but mostly, I'm focused these days on both Azure Stack and of course management in PowerShell, which I invented.

**Edith: **Yeah, so cool. So, I'm so interested in what you're saying about this hard shift. So I've heard about the three-year process.

**Jeffrey: **Yeah.

**Edith: **How do you convince people to move from that, to continuous delivery?

**Jeffrey: **Yeah, well, it's hard, right? And a lot of times they didn't want to do it. But basically, what you try and do is you try and find something that they can get their head around. So for us, one of the key things was a shift to Nano Server. So, are you familiar with Nano Server?

**Edith: **Explain it for the audience.

**Jeffrey: **Traditional Windows Server translates to about a 10 gigabyte VHD. Server Core, the GUI-less version, is about six gigabyte VHD. I initiated a very dramatic refactoring of the operating system, called Nano Server, and that starts at about 400 megabytes. Windows Server in 400 megabytes. Well guess what, in order to run on that, you have to do dramatic refactoring.

Part of this was to move from Windows PowerShell being .NET Framework based to being .NET Core based. So that was a dramatic refactoring and the team didn't want to do that. Because they knew they were competent and successful in this world, and they had a group of customers that they knew and they knew how to give them the next set of things.

And what we had to do is just say, "Yeah, we want you to not do those things. Not meet those customers needs as we make this change to develop something." And they looked at me like, "Boy, that's going to be really hard, and in the end, it's not going to be as good as this thing because it's going to be a Version 1 of a new thing, and I don't want to do it."

**Edith: **Ha!

**Paul: **It's sounds very much like the innovator's dilemma. Keep doing what you're doing or break everything and maybe your revenue models as well in order to get where the puck is going.

**Jeffrey: **Exactly, and so, you do the traditional DevOp, what we in the community have all been learning, right?


<blockquote>Find the coalition of the willing, start small. Sometimes the coalition of the willing includes people who are willing to do work to keep their paycheck running. </blockquote>


They'll keep coming in.

But when they get there, like, "Oh, hey, this is cool," they get enthusiastic and build some momentum and build some success, and then you add to it and add to it and then at some point you just mandate the change. And then they're like, "Oh, yay." In fact, so I did this when I came to the company. We had this horrible division. Like, developers developed code and they check it in, and like, "Compiled or not compiled? "Well, that's a tester's problem."

Like, are you out of your freaking mind? No, we're not going to do that. Like, "Here's the deal. On this project, everybody has to do unit tasks." and they're like, "Well, that's a tester's job." It's like, "Well, it's a salary continuation program. Decide what you'd like to do because we're going to do this, and like, "Oh!" They're all angry with me. And then I had to explain, "Okay, wait a second, you are going to write the test at the same time as the code." "Well, no, I don't have time for that. I'll do it at the end."

It's like, "No, you're going to do it now." And it's like, "Okay, well, I guess I didn't explain. You've got to run the tests before you check in the code, and yes, they have to work. And wait, no, you have to run all the tests." "Well, why do I have to? You know, I changed this code and his test broke, not mine." "Well, did his test fail before you checked in your code?" "No." "Then, you broke it."

Each one of those things was like this big crisis and people were just not happy with me at all. Beause they knew how to do things. But then it was four, six months after, just did this. People came to me and was like, "Yeah, this was actually pretty cool. Every night we can self host. We've never been able to do that." And you go faster.

**Paul: **It feels a little like the transition from sort of Dev and Ops to DevOps. Where people used to have this ability which is sort of a good and a bad thing, to throw it over the wall to Ops. And so they had this benefit where they didn't have to deal with the opsy side of things and I guess it comes with the upside of like when you have to deal with opsy things, that you have new capabilities.

**Jeffrey: **Yeah.

**Edith: **So, you've pioneered both tester and development and DevOps.

**Jeffrey: **Well, within a little sphere, yes. And then, you're doing a little sphere and then you try and make it bigger and bigger, yeah.

**Edith: **So, I know that a lot of people are still trying to make these same transitions, what's some advice? I already heard like, "Get the coalition of willing."

**Jeffrey: **Yeah, I mean, that's part of it. You know, you want to find something where, your project has a good profile, right? Something that's in trouble. One of my jokes is you never see me on a project going well. You put me in the projects that aren't going well and that you want to go well. So, you want something that has an opportunity to improve, or go faster, be better.

Something where when you notice, when there is a change, you'll notice the change. And then you find that coalition of the willing. Often, like with the PowerShell to Linux, I got a couple guys right out of college and they were Linux guys and they were gung ho and one of the nice, meaty hard problem that they could claim as their own. It's like, "I've got something for you."

And man, they were rocking it. They did a great job. And then all of sudden people were like, "Oh, what, why are they getting all the attention? "Why do they get to show off their stuff to the executives? How do I get part of that?" And so then you grow, and you do it a couple times. You know, it typically requires an executive sponsorship because you will have, let's be clear. When you embark on this, failures will happen. I just gave a talk where I talk about this difference between incremental change and transformative change.

**Edith: **Yeah.

**Jeffrey: **Like incremental change, you know what you need to do, you just see they have to work harder or whatever. Transformative change, you don't necessarily know how to get from here to there.


<blockquote>In incremental change, you're going to succeed. In transformative change, you are going to fail. And it's all about how you fail and learn and keep going forward. </blockquote>


With incremental change, you keep all your people. With transformative change, you lose people.

**Edith: **Yeah, it's funny, I have a startup that was writing to a board member yesterday about a change we've done, and he said, "Well, are you moving forward?" I'm like, "Well, we're moving." I don't yet know if it's lateral or diagonal, but like, we're moving.

**Jeffrey: **Right.


<blockquote>We know in physics, the coefficient of dynamic friction versus the coefficient of static friction is much lower. So, if you can get things moving, you can change the direction. </blockquote>


**Edith: **Yeah, and then it takes sometimes a little bit of time to see whether you're actually improving but at least you're moving.

**Jeffrey: **Yes, exactly.

**Paul: **One of the sort of tenets of startups is that the team that you start with isn't necessarily the team that you finish with. And I never understood this when I started startups. Like, you want to try really hard to keep that early team, and you know, why must it be necessary that the early team leaves? But once you've realized that the way to do startups is to have a complete transformative change at every stage, so as soon as you hit product/market fit, you completely change into a company that is chasing traction.

And then once you have some traction, you completely change into a company that's pursuing scale. And it's like, those are major transformative changes for the company, and if you try to avoid them in order to keep things the same, to keep the early culture or the early people, then you risk being unable to transform and only being, you're a company that's try to scale that thinks like a pre-product/market fit company.

**Jeffrey: **Yeah, no, that's a great way to phrase it. And sometimes, people can see those changes and they have the skill to make the change. Sometimes, they can see it but they don't have the skill and those are people who can gracefully exit, bring in a new team. And then other people don't see the change and that's all bad.

**Edith: **I love the way that it's not about tools at all.

**Jeffrey: **Yeah, exactly.

**Paul: **I think it correlates very much to whether they've had the situation before. And in some cases when the first time that they went through this transformation that they may have ended up on the team that leaves, and now are bitter about it, or unhappy about it at least. But then they've seen that happen, they have several years to reflect and understand why it has to happen and then the next time it happens, they might be on a different path in that transformation.

**Edith: **So then, you've been at Microsoft, you must have seen several changes.

**Jeffrey: **Absolutely.

**Edith: **How do you think Microsoft has changed your time here?

**Jeffrey: **Well, right, so when I came in, you know, it was GUI, GUI, GUI, and I was the guy who came in and said, "We have got to do command line interface." That was a very painful experience, right? They were not ready to hear that. I had one executive say, "Exactly what part of effing Windows is confusing you?" And I said, "No, seriously, this is what is required." And in order to work on it, I actually had to take a demotion.

**Paul: **Wow.

**Jeffrey:**


<blockquote>I got demoted to work on PowerShell and it took me five years before I got my stripe back. </blockquote>


By that time, they realized, "Hey, this really was important. GUI was great when you got one machine or four machines, et cetera. But when we want to go manage data centers, we do need automation." And you know, we got 500 mouse clicks, like, how do I share that?

**Paul: **Right.

**Jeffrey: **GUIs are antisocial.

**Edith: **Well, I've tried to do automated testing like through, you know, and it's so painful. You have to click and then something changed, you're like, I can't click there anywhere.

**Jeffrey: **Yeah, and there's nothing you can share with people. Anyway, so that was a big change, going from GUI to command line interface.

**Edith: **Why were you so passionate about it?

**Jeffrey: **Well, I got hired in to solve their management problems, right? So basically, Bill was beating up all these teams and basically said, "We need some outside help, let's get in somebody who knows something about management." So, that's why they reached out to me and that's why he hired me. So it was my job.

**Edith: **And you cared enough that you got demoted for five years.

**Jeffrey: **Well, what happened was, I'd been driving a bunch of management changes and then I originally took the UNIX tools and made them available on Windows, and then it just didn't work. Because there's a core architectural difference between Windows and Linux. On Linux, everything's an ASCII text file, so anything that can manipulate that is a managing tool. AWK, grep, sed?

I brought those tools available on Windows, and then they didn't help manage Windows because in Windows, everything's an API that returns structured data. So, that didn't help. Anyway, I came up with this idea of PowerShell, and I said, "Hey, we can do this better." And that idea was clearly one of the best ideas I ever had and I just, at the end of the day, said, "Well, you know, I'm just going to view this as a startup.

"You're paying me a lot of money, and backing my play to bring this technology to bear." So I was willing to accept that. At the end of the day, you know, here's the reality. You are the level you are, and then it gets recognized at the right time. So, if they came in and hired me and they got it wrong, they hired me at too high a level, that doesn't help me and doesn't help them. So, if I'm lower level, fine, I should be a lower level.

On the other hand, if I'm at a lower level and in fact I'm at a really higher level, it takes time, but it'll eventually rectify itself. In my case, it took five years before they saw that. So, that was actually quite an expensive little detour, but it rectified itself and then I got my stripe back, I became a distinguished engineer, and then Technical Fellow. You know, Microsoft has over 120 thousand employees. We only have 8 Technical Fellows that are focused in on products.

**Edith: **I feel like it's an honor just to talk with you.

**Jeffrey: **Please, no.

**Paul: **So, I'm interested in PowerShell and a little bit inside Continuous Delivery and how those affected command line tools. So, in the UNIX world that I'm used to, you get an upgrade when every six months, Ubuntu releases a new version. Which isn't necessarily a great thing because you write scripts for the older version of tools and then things change, and so there's always a little bit of awkwardness when you're upgrading.

I wonder what that's like in the Windows world where you've got PowerShell, you're trying to automate the sort of structured data. And it's like, does the structured data change? What do your PowerShell scripts do? What does PowerShell itself do?

**Jeffrey: **Yeah, so


<blockquote>One of the great benefits of this is that the structured data and API is a stronger contract. </blockquote>


Basically, what happened, here's the heart of PowerShell, it's as simple as this. I said, "What is the UNIX compositional model?" And I said, "It's A piped to B, piped to C." That's the heart of it. And I asked myself, "Well, why do they do that?" And I came up with the answer. "Oh, because A didn't do what you wanted it to do."

Because other wise, you'd just type A. Well, that's obvious. But then I asked the next dumb question. Sometimes you realize to just give yourself freedom to ask dumb questions. So, "Why didn't then A do what you wanted it to do?" And there were two answers, the traditional UNIX answer: small tools, composition.

We all know that story. But when you really drilled into it, I realized that there was another answer. And the other answer was this: that A bound three separate steps into one. If A got a set of objects, it processes those objects, and then it output the objects as text. And then, because A didn't do what you wanted to do, what we're really saying is, "I didn't get the objects I want," or, "I didn't process them the way I want," or, "I didn't output them the way I want." Because if I did, I would just type A.

So, when you pipe into B and then C, what you're really doing is you're taking the text output to reverse-engineer your way back to the original objects to do one of those steps differently. And all I said was, "Just put the pipeline "in each one of those steps, and deal "with the objects." Move it earlier, it's smaller. That's why we call them cmdlets, they're small. It's a pipeline of objects and with the objects, you know, there's none of the prayer-based parsing. Because some people are good at this, I'm not one of those people. "You cut off three lines, or is it two lines? 27 comps, is that a tab, or is it twenty, I'm just horrible at all that stuff, right?

But when I see, "Hey, something's got a name, it's like, gimme the name, handle count? Gimme the handle count." And it's a much tighter, more resilient contract. And as you add things, now an object has more properties, that's a fine change. It's like adding things to an XML document. That's a contract that goes really well. Whereas adding things to the output of a text is like, "Ugh, now what do I do?"

**Edith: **I love that story because you basically, you were, do you know the story of 5 Whys?

**Jeffrey: **Yeah, yeah.

**Edith: **Because that's what you're doing, you're like, "Well, why is it this way? "Why is it this way, why?" And then by that, you suddenly got to the real answer.

**Jeffrey: **Exactly.

**Paul: **It's interesting how the world where PowerShell exists is one in which there isn't a culture of writing a massive amount of scripts.

**Jeffrey: **Right.

**Paul: **So, so let's say in UNIX, like the Build System is also scripted in Bash or similar enough to Bash. And so, I wonder how that affected the users of PowerShell and what ended up happening with that.

**Jeffrey: **Yeah, so, actually, it's been the same sort of thing. It's been a small community that's been growing and growing, and honestly, some of those things, some of those examples were not great steps forward. We had one partner that were very hardcore in Verb-Noun. Somebody thought that Citrix was a verb. Turns out it isn't. So, you know, we had to like, "Okay, we're going to have to enforce a little bit of rules here."

So the great thing about the UNIX culture is, because it's been there forever, people all know the rules of the road and you don't have to teach the rules of the road. They just know it because that's the rules of the road. And with here, there's got to be a lot more active evangelism as people get it. But indeed, it's been growing. So, like Azure Stack, so Azure Stack, that's where we take the heart of the public cloud, most the services, and allow them to run on customer sites, starting as little as four nodes.

I'm writing up the deployment, the configuration, the operations, the patching update. It was written all in PowerShell. So again, hundreds of thousands of lines of PowerShell code. And as we do something that large, then that has then brought about the next evolution of the tool. If you've ever read the Monad Manifesto, where I sat down and I said, "Here's what we're doing and why we're doing it," I talked about something that you would recognize.


<blockquote>In 2001, I wrote the Monad Manifesto where I talked about the need for a single tool that could be used by developers and operators, right? </blockquote>


**Edith: **Yes.

**Jeffrey: **Because when operators get in trouble, developers couldn't help them because they talk in different languages. You just couldn't collaborate well if you had different tools. So, in 2001 I addressed this as a problem that we sought to address.

**Edith: **This is way before the word, DevOp existed.

**Jeffrey: **Exactly, man, DevOps before DevOps was cool. Yeah go read it, it's out there, Monad Manifesto. Anyway, the reality is that in Version 1, we focused largely on operators, and then step by step, we've been increasing the more developer focus. With Version 5, put the petal to the metal on that where we introduced classes, we introduced test frameworks, unit test frameworks, introduced ScriptAnalyzer, integrate in with Visual Studio, and Visual Studio code with Rich Editors.

So really, you know, you can start off and do quick, ad hoc dirty Bash-style scripting with $args. You can be formal, you can be very formal, and now you can write systems code all using the same tool.

**Paul: **What's interesting is that the pattern on UNIX is you start writing it in some dirty Bash, and then you get 30 lines, and realize you're completely over your head, and so, you rewrite it in Python.

**Jeffrey: **Yes

**Paul: **Or in the old day, Perl, today, Python.

**Jeffrey: **And then it doesn't work so then you write it in C.

**Paul: **Yeah, that's terrifying.

**Jeffrey: **I think that might even be in the Manifesto. That was the story I told over and over again. You start with something, and then, my joke was everything's greatest strength is its greatest weakness.


<blockquote> UNIX's greatest strength is this compositional model. Now here's the reality, it's also a weakness. </blockquote>


Because what happens is when you have the shell and then, "Oh, well I need something," instead of like adding it to the shell, they went and added awk and sed and grep.

And then when that didn't do what it needed to do, well, instead of fixing awk, sed, and grep, you went and added Perl, etc. So, the not-so-friendly joke is to say, well, it's actually an anthology of failed tools, right? As each failed tool then brings about the other one.

And what I said was, "Hey, we have the opportunity to take a look at the sequence of tools and then produce the one that can address the wide range of things." And so, again, the point is that had someone said, "Hey, Shell doesn't need this, I need this.Why don't you add it to shell?" Shell would've been a much richer tool.

**Paul: **The way that I think about Bash, and UNIX Shell and so on, is that these programs are functions. So like awk and sed and grep and so on are functions in Bash as well.

**Jeffrey: **Yep.

**Paul: **And it passes primers via standard in and parses things by standard out, exceptions are thrown by the return value. But then there's no room for something like Perl in this model. Right, because now you've got this weird DSL, that's like a function that you can call and it makes no sense at all.

**Jeffrey: **Those are weird DSLs too, sed's a DSL. Awk's a DSL. Explicitly, the tiny language movemet.

**Paul: **But Bash thinks of them as functions.

**Jeffrey: **Uh, well, same thing with Perl. Perl would ask, you said binary with awk, grep, and sed.

**Paul: **I see what you're saying. So like, you're saying that essentially, you can write complete sed scripts or complete awk scripts.

**Jeffrey: **Right.

**Paul: **And the world that I live in, let's say the post 1999 world. I've never seen anyone write an awk script or a sed script.

**Jeffrey: **There you go, I got into it pretty early.

**Paul: **Yeah.

**Jeffrey: **Yeah, I was originally a UNIX manager. Yeah, so, I did learn UNIX, I was at Storage Technology doing Factory Control Systems, so that's why like all the stuff about, you know, the Japanese quality movement, man, we were living that stuff. Yeah, so Phil Cosby, Quality Is Free, Deming, Taguchi. I mean, literally, factory floor, I was doing disks and we have a UNIX-based factory control system.

**Edith: **Wow, so you saw one big shift which was getting PowerShell out. What was the next big shift you saw after that at Microsoft?

**Jeffrey: **Oh, yeah, so going to that, really it was the long period and new leadership under Satya. I mean really, it's the real deal and it's such a dramatic difference. He's such an open leader and basically what he did was when he came onboard, he said, "Hey, everybody, get out of your offices. Stop talking to one another."

**Edith: **Get out of the building.

**Jeffrey: **Go talk to the customers.

**Paul: **Because the world had changed in the Ballmer years.

**Jeffrey: **Absolutely.

**Paul: **And Microsoft, I guess, had not?

**Jeffrey: **Yeah, exactly.

**Paul: **Right.

**Jeffrey: **You know, very good at doing a great business job with the assets that we had. But what such had seen was that the world had changed and that our relationship with the world needed to change. So he said, "Get out of the offices, go talk to customers, find out what they need to be successful, and give it to them. It's that simple. He says, "Don't worry about the money. Do not worry about the money. If you're making customers successful, we will figure out how to monetize it. Don't worry about that, we got plenty of room to go there."

**Paul: **From the outside, I feel that a lot of my peers who would have been hardcore, never work at Microsoft, never interested in the Microsoft Stack, never any of those things. When Satya came in, it was like, "Oh, Microsoft's an interesting company again. I would totally go work at Microsoft, or, I'd totally be acquired at Microsoft."

**Jeffrey: **Yeah, well actually, I didn't want to go to work for Microsoft. When I got the call, I was working at Tivoli, then I'd basically said, "Yeah, I'm not that interested in talking to you," because you know, big evil empire, and I was a UNIX guy.

**Paul: **Of course, yeah.

**Jeffrey: **And it turned out that there's an executive, Dave Thompson, who I'd known and I just thought the world of this guy, and he said, "Hey, Jeffrey, I'd like you to come talk to me." It's like, "Okay, I'll talk to you." And so then when I came and talked to the people, the people were just amazing. There was some incredibly high IQ, passionate people and so, my joke was I never joined Microsoft, I joined Dave Thompson.

But yeah, then the observation was that, "Hey, the company's very good at identifying the things it's bad about." Right, they have the courage to admit these things and then put together a plan to address it. So at the time the management was terrible. I said, "Okay, well, if I can help fix that, and there's so many units out there, you know, you have an opportunity to have a huge impact. Anyway so, the new leadership under Satya is just great. You know that iconic picture of Satya against the background, Microsoft Hearts Linux.

**Edith: **Oh, yeah!

**Jeffrey: **Just set the tone, and it's real.

**Edith**: I love your story about moving from a three-year cycle to continuous delivery. What were some of the effects you saw in the team once it had gone through?

**Jeffrey: **Well, once we got through, all of a sudden, we're doing this now, I think the best of these projects is, I mentioned to you that when we went to Linux, we had a great editor on Windows that we couldn't bring over. So we had to do a new project, Visual Studio Code. Now in this one, with PowerShell, we bring it to Linux and we're open sourcing it. But I'm open sourcing Version 6, right?

So, there's not a whole lot of opportunity for people to say, "Hey, the fundamental design should be X, Y, or Z."


<blockquote>With Visual Studio Code and the PowerShell enhancements, they restarted that project in the open, with the community. </blockquote>


We have a Microsoft full time maintainer, and a community maintainer, right? And so, that's being done in the open. And these guys are just going quick. They're on Twitter, they're in GitHub, and as people respond, they're coding and they're going fast, and the community loves them and they love the community.

**Paul: **Is that people adapting, or is that sort of bringing in fresh blood who already understands the GitHub ecosystem and had to be Linuxy.

**Jeffrey: **Yeah, no he adapted it. Yeah. He was a systems center guy.

**Paul: **Alright, what was that like?

**Jeffrey: **Well, you know


<blockquote>The tools you have affect the way you think about the problem. So, one of the biggest challenges with GitHub is, "Hey, I've got to think about the problem differently." </blockquote>


And everybody does, in fact, I should get you a picture of this. Now one of the largest projects we have, Windows, is moving over to Git. And so, there are these posters up..

**Paul: **Wait, Windows is moving over to Git?

**Jeffrey: **Oh, maybe I shouldn't announce that.

**Paul: **Is it moving over to GitHub or just Git?

**Jeffrey: **Git.

**Paul: **Oh, okay. That would've been amazing. I thought that's what you were saying.

**Jeffrey: **So, they're driving this education and training and there's these posters on the wall, called, The Five Stages of Git, right? So there's the denial, and then there's the bargaining, and the anger, and the acceptance, and the, "Well, this is great." And so, that kind of sums it up. I should get you that poster, that would be awesome.

**Paul: **That sounds cool.

**Edith: **What's the bargaining stage like?

**Jeffrey: **"Maybe I could go to a different project, but keep using my old tools. Or maybe this will fail and then we'll go back."

**Edith: **What's the anger stage?

**Jeffrey: **"What the hell?" I think there's always that everybody's very passionate about delivering customer value, and so, sometimes, and this is great for your audience too, you're so passionate about that, it's sometimes hard to accept that in order to do that maximally over time, you've got to stop and change the infrastructure to work on your tooling, because you know, "Hey, here's the next set of things I could do," but you're not going to do them in order to do something. And then the first few versions of that aren't as good. But then, boom, you could do better after that.

**Paul: **Yeah, you have this problem where your world view, every time you hear something from a customer, you take it onboard and you sort of wedge it into your world view, and it's like, "Oh, we can slot this here." But the customer has a completely different world view and what you need to do overtime is like get out of your world view and figure out how you take all the stuff you're already doing to the worldview that the customers have instead.

**Jeffrey: **Yeah, it's the heart of the, one of the big challenges is, you know, stop thinking of yourself as successful and patting yourself on the back. Get out there and find out where the real pain is, and have the courage to address that pain.

**Edith: **Yeah, I heard a horror story about a three-year project where, you know, they got about two years into it and they realized that this feature was just not going to work out in the field. But everybody had too much invested in it. So they shipped it anyway. They're like, "Well, we can't kill it now." And it's just like they weren't thinking anymore about the customer, they were thinking, "It's too late."

**Jeffrey: **Yeah, well, and their careers.

**Paul: **If you were to be in that situation, I'm not sure I could honestly tell you to do it differently. Like, are you going to disappoint like half the team and people quit.

**Edith: **I've killed features. I've killed releases.

**Paul: **After two years in?

**Edith: **We were like four or five months until release and we had to kill that entire release but the CEO said, "Hey, this direction is not working." And I remember how painful it was. I literally had like specs and we had half-written code and we had to delete it all.

**Jeffrey: **There go, you know what? "Smarts is pretty common, courage is pretty rare."

**Edith:** And it was the right thing to do but it was hard.

**Jeffrey: **Yeah, because you do lose people.

**Paul: **So, you're on Azure Stack now.

**Jeffrey: **Yeah.

**Paul: **So, tell us a little bit about what Azure Stack actually is.

**Jeffrey: **Yeah, so basically, the heart of it is take the core of Azure, and this is the ability, we do it by scenario, so IaaS and PaaS, the ability to write cloud applications. Take the things required to do that and then run it on customers' data centers. A lot of people then hear that and they say, "Oh, great, I keep doing what I'm doing and I can call it a cloud." No. That's not the deal. It is an integrated system.

So, you should think about it like the cloud equivalent of a storage area network. So, a storage area network, you pick a vendor and you pick a capacity. This company, this size. That company then rolls it in, they do the systems integration, installation, probably would take a day, day and a half, and then you use it, right? And now, what you're doing is, with a SANS, you use SMB, or NFS, and then, there's a custom fabric administration experience where you just say, "Yeah, here's how I manage the storage."

Same things going to happen with Azure Stack. You're going to roll it in, configure it, and then you're going to use the portal and you're going to get PaaS and IaaS, and then there's a custom admin experience, right? And that admin experience has a light that says, "Replace a disk." Or a light that says, "Replace the server," or, "Add a server." and at no time do you say, "Okay, what's the admin password?" And then like login and, "I'm going to install my security agents on there," or, "I'm curious as to how you're doing DHCP. Like, no, no, no, internals are internal. You don't do master.

**Paul: **Oh, interesting.

**Jeffrey: **Yeah, because we're like, here's the model. What we're trying to do is we're trying to help people drive their digital transformation. That's about having developers and operators work together to deliver the things that drive the business forward, business applications responding to customers. No company, I guarantee you, no company sells more shoes or puts more people in airplanes because their IT can manage, you know, DNS better than the other guys.

**Paul: **Let's say for startups who are selling into this world, I feel that's a Microsoft luxury. That you can sell a black box and say, "No, no, you know, you're going to change your corporate IT policies. You now deal with this black box. But I know as a startup, if we were going in we'll say, "No, no, it's a black box. You can't run your virus checkers, or you can't go through your corporate security checklist like pentest something or get access to the database to verify something, they would say no. But I guess as Microsoft does, there's a lot more ability to sell blacker boxes.

**Jeffrey: **Oh I see, a startup selling that. Yeah, absolutely, right now, a lot of this has to do with confidence, right?

**Paul: **Yeah.

**Jeffrey: **This thing is wonderful from a security standpoint. And when people go and when they say, "Hey, I've got to go take my instance and certified," and have all the documentation from the technology side. Certification is people, process, and technology.

**Paul: **Like PCI.

**Jeffrey: **Exactly. From the technology stamp, we'll have all that documentation that you can fill out for you, so yeah.

**Paul: **Wow.

**Jeffrey: **Yeah, it's very cool.

**Paul: **So, as someone from the Linuxy world. So, I feel you had a really good pitch there for IT administrators. And you know, comparing it SANS and SMB and fabric and that sort of thing. In my world, the way that people are getting this sort of, the on-prem equivalence is they're going to like AWS VPCs. So how does this compare?

**Jeffrey: **Wait, VPCs are?

**Paul: **Virtual Private Clouds.

**Jeffrey: **Oh, ok.

**Paul: **So it's like, Amazon is running it but within your own sort of firewall to group and it's like you're own data center but in the Amazon cloud.

**Jeffrey: **So, where do the servers actually reside?

**Paul: **In Virginia like the rest of the cloud.

**Edith:** The cloud is actually base.

**Paul: **It's like a bunch of computers and yeah, that's the cloud.

**Jeffrey: **So, like, that wouldn't work for a submarine, right?


<blockquote>So, Azure Stack works for disconnected and Edge scenarios. So, imagine a cruise ship that is occasionally connected but when it's in dock, it has connectivity, but then when it's out at a port it doesn't.</blockquote>


**Paul: **It never occurred to me about a cruise ship might have a data center.

**Jeffrey: **Oh, they have multiple data centers.

**Paul: **Right.

**Jeffrey: **The point of sales systems and the customer loyalty programs and you know gaming stuff.

**Edith: **Yeah, and that's not even beginning to look at the actually navigation.

**Jeffrey: **Exactly, yeah.

**Edith: **Or like, fuel consumption.

**Jeffrey: **Yeah they have multiple redundant data centers on a cruise ship. So yeah, there's that or there's gravity, right? Whether it's data gravity or compute gravity. So imagine a factory floor. A manager, you get a bunch of sensor data, and then control robots. You do not want internet connectivity in that loop, right? You want to always be controlling your robots, right?

**Paul: **You mean from a latency point of view or security point of view?

**Jeffrey: **From a just reliability standpoint, right? Occasionally, some DDoS attack. Somebody's region goes down. Something goes wrong with the internet, you can't control your factory floor, that's a bad day.

**Paul: **Yeah.

**Jeffrey: **But latency is absolutely another issue. That's the Edge scenario. So we have some customers who are very interested in this because they've got a ton of data and they need to manage that data and react to it with absolute low latency.


<blockquote>The area where we're seeing a lot of interest in is, "Yeah, I want to do that,but I actually have a number of those sites. So I want to do that processing and then get aggregated data up into a public cloud to do cross site big data analytics. </blockquote>


And then the third is regulatory requirements, "I must have my data here." So we have one vendor who's doing a public cloud application for all their associates throughout most of the world. But then there are certain geographies where that's not allowed. So they're taking exactly the same application and they're going to run it on Azure Stack in those countries so that they compute and the data stays there.

So those are the three scenarios, sort of disconnect the durable scenarios, disconnect it in Edge, regulatory, and the third is modernizing things. So imagine you've got a main frame and you want to get off that main frame, whether it's a real main frame or it's a Legacy Oracle system. You want to put a modern front end in front of that thing and you want to put it next to it, right? Don't ship us your main frame. We're not putting it in our data centers. We'll give you Azure Stack, you can put it right in front of that.

**Paul: **So, I feel like a major transition in the modern microservices world, that we're in.

**Jeffrey: **Yeah.

**Paul: **Is that a bunch of microservices you don't write yourself. So you know, there's all these services that Azure provides, the AI stuff, the image recognition, Google and Amazon has all these, and all the startups have a particular API that does a particular thing, like background checks maybe is a good example. How does that ecosystem exist in the Azure Stack world?

**Jeffrey: **That's what's so exciting because you get this one Azure ecosystem. Because it's the same APIs and the same services, most of the things that you find in the Azure marketplace, you'll be able to, in fact, that's the mall, is you syndicate your marketplace with the Azure marketplace.

**Paul:** Syndicate them?

**Jeffrey: **Yeah, you basically make a GitHub branch, right? You say, "Hey, I'm here and here are the parts I want now," and then people use yours. So you always have control over which versions you're offering to your tenants. But you're getting them from the Azure marketplace.

**Paul: **I think I'm a little confused here. So, all these services that are currently available in Azure Cloud are going to be available in some sense in the stack?

**Jeffrey: **Okay, yeah, now I understand the confusion. So there's two flavors of these microservices, right? So the first are the native Azure services and there, we have a subset of those that'll be available. And those are the core things that most things are build on. And then there's the long tail. For instance, content distribution network on four nodes, probably never going to bring that one down to four nodes. But, container service, that's going to be available shortly after GA.

So we start off some with the core set and then we'll grow that, start working on long tail.

**Paul: **I guess I'm interested in more of the sort of the manage to services. So, some sort of like deep learning as a service thing

**Jeffrey: **Yeah.

**Paul: **Where's there's 100 people who sit in one building and like that is the product that they build. How do people who use Azure Stack interact with that?

**Jeffrey: **Yeah, so it'll be on a case by case basis. But the things I was mentioning to you are manage services. So, Blob, Table, Queue. Those will be managed by your fabric administrator.

**Paul: **Gotcha, and what about the ones that can't be brought in?

**Jeffrey: **Yeah, they're accessed from in the public cloud.

**Paul: **Gotcha, so it's just the same as you're normally doing, you're just making that API call from your Azure Stack in a sense.

**Jeffrey: **Exactly, so what we're doing is we'll work with the marketplace to find out what are the things that matter the most. So concretely, what we did was we took a look at the Azure gallery, and these are solutions. So these are solutions that say, "Hey, I want to have these many VMs," and you know, "here's the content, and I'm going to consume these services," et cetera.

And we saw what they need to be successful and that defined the Version 1 of Azure Stack. So what that means is as you go to these solutions in the marketplace and you pick one of them, an e-commerce or an elasticsearch, whatever. You pick those things, you deploy them, those are just going to work. And then we'll scale that over time, adding more and more services.

**Paul: **Okay, so, similar question. As someone who has had a product that we transitioned to on-prem, it was incredibly difficult to make it reliable. And so like, how have you guys gone about that? Like, how is it that you can take this set of huge services that have dozens of people working on them and that I presume are unreliable because they had distributed systems, and put it in a box that is reliable.

**Jeffrey: **So, the heart of Azure Stack is consistency with Azure. Now, let's put our architects hat on. How do you achieve consistency? There are two paths two consistency. One is compatible, definition of compatible is different. The other path to consistency is the same. As much as possible, whenever I have a choice, it's consistent because it is the same.

Some things, I can't be the same. So if you talk to Russinovich and you ask him, "Hey, Mark, how many servers does this take to start a storage stamp?" He'll tell you, "Hm, about 800," right? Turns out, not many people are interested in a proof of concept with 800 servers. So there, what we had to do is we had to take the lessons and design patterns and be inspired by those and put those technologies into Windows Server. So that's our scaled out storage spaces. And so, that's working really quite well.

**Paul: **So, it sounds like it's a reliable thing that you can just install.

**Jeffrey**:


<blockquote>Some of these services are not reliable. They are intrinsically designed to take advantage of the unreliable nature of systems. </blockquote>


So, there, what we're doing is we're mirroring the Azure scale model. The Azure scale model, you've got a single ARM, Application Resource Manager, that multiplexes all your REST APIs. Then you have regions, and then you have scale-out clusters and then with each scale-out cluster, you have however many servers you want. In Version 1, we have one region, one scale-out cluster, four to 12 nodes.

As we expand, the first thing we will do is to expand to have multiple regions. Why multiple regions versus multiple scale-out clusters? The answer is this: multiple regions is how some of these solutions address the issue that you mentioned, just to say, "Hey, I want to have a fault domain that is large." Like, this building might go down. If a building goes down, I still want to have something working, right?

So, if you have two racks next to each other, that doesn't do it, doesn't get the fault domains farther apart. So that's why we're choosing that multi region as the next step of increment.

**Paul: **Okay. It's interesting, it's the thing you immediately went to talk about was the sort of distributed system's reliability. As opposed to, you know, "We took 1000 people and we worked out every single bug and tried to make it right."

**Jeffrey: **Yeah, well,


<blockquote>It's the TCP versus SNA model, right? SNA tries to say, "I've got reliability at the lowest layer, therefore, everything could be simple above." TCP said, "I will have failure And I will deal with it higher and it's so much cheaper." </blockquote>


By that way, to your point, it is one of the biggest challenges I have. Indeed, in Azure I have big teams managing those services and when I take those things, I've got to transform that into a world where it's very simple to do. And turns out that's hard.

**Paul: **Yeah, yeah.

**Jeffrey: **There's no getting around that one.

**Paul: **Sounds like a fun challenge though.

**Edith: **You said something before about deciding where to build versus buy. Well, how do you make that decision?

**Jeffrey: **It's always judgment call, always judgment call. You know, basically, that's the, you always want to build the things that differentiate you and then buy the things that don't. That's a Geoffrey Moore, Crossing The Chasm model.

**Edith: **I love that book, by the way.

**Jeffrey: **He's a great thinker.

**Edith: **Yeah, well thank you so much for joining us today. Do you have any final thoughts or things, I mean, I feel like I got 30 years of history.

**Paul:** Yeah, of knowledge.

**Edith: **Yeah, I feel like we could talk for four more hours.

**Jeffrey: **Yeah, no, I'd just say that DevOps, talking about transformational change, and the thing about these transformational changes is that they're very painful. But the reason why you have the courage to go through these transformational changes is because of the other side of that transformational change, you're going to be in a much better place. You're going to be driving your business forward, your customers are going to be happier, people have adopted DevOps.

So the thing that struck me, I went to Enterprise DevOps, and I saw these people from like what you might think of as old, dusty companies up there, just middle-aged guys, like full of vim and vigor and like so excited, and they're like, "Yeah, you know, my career, I was dialing it in for years and years and years. And then they talked about this DevOps, I don't know, and it's wonderful!"

It is a great experience to go through these changes and succeed and drive your business forward and have happy customers, it's worth the pain. So I encourage listeners to go through it if they haven't already.

**Edith: **Yeah, well then I have one more followup question. So like, you saw command line, tester and development, DevOps, what's the next big change?

**Jeffrey: **Well, here's the gotcha. So, I'm an architect, my job's to answer these questions. This is the most exciting period in the history ever because in the past we all sort of knew what things were and then you'd have a big change.


<blockquote>Right now, every single layer of the technology stack is going to revolution.Revolution in the Silicon, revolution in the systems design, revolution in memory, optane, storage class memory, revolution in networking and storage and application design, in IP, in relationships. It's all moving all at the same time, all having revolutions. </blockquote>


So, getting that right, figuring out the right thing to do will be difficult, but that's my job. Exactly, it will be fun.

**Edith: **Awesome, thank you so much for coming in.

**Paul: **Thank you so much.

**Jeffrey: **It's been a pleasure.





