---
author: andreaech
comments: false
date: 2015-09-23 20:11:17+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-evolution-of-continuous-delivery/
slug: to-be-continuous-evolution-of-continuous-delivery
title: 'To Be Continuous: Evolution of Continuous Delivery'
wordpress_id: 661
categories:
- To Be Continuous
tags:
- Agile
- CircleCI
- cloud
- continuous delivery
- deployment
- feature flag
- Joel on Software
- JSON
- Yammer
---

In this episode, Edith and Paul talk about what Continuous Delivery is and where it came from. They cover everything from SaaS and test-driven development, to lean startups and human evolution.  This is podcast #3 in the To Be Continuous podcast series all about continuous delivery and software development.

This episode of To Be Continuous, brought to you by Heavybit and hosted by Paul Biggar of CircleCI and Edith Harbaugh of LaunchDarkly. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com). While you're there, check out their library, home to great educational talks from other developer company founders and industry leaders.


Edith: So Paul, where did continuous delivery come from?

Paul: This is one of those things that evolved over quite a long time but I think that that major catalyst of continuous delivery was the fact that we moved to SaaS and that Saas now exists.

Edith: So what was it like before there was continuous delivery? What was it like when you were starting out?

Paul: The first company that I really worked for was a games company and I think that a lot of them are kind of in the same place now. You would release software on a disk that shipped to customers via stores and you had to have a gold master at some point. We were a startup so it was quite advanced.

We had a daily build server and we actually were selling middleware so we shipped software to those companies but those companies would ship at the end of the day, they would ship a disk that went out once and there was no updates at the time.

It was 2003, 2004, something like that. There wasn’t any way to automatically update on customers’ Playstation 2, unlike even games now have a little bit of continuous delivery but back then, that was, you got your chance to ship it and that was it.

Edith: Yeah, I just had a brutal flashback to one of my first summer jobs, which was installing Windows 3.1. This is back when you actually had a set of 35 disks so my job as a summer intern was to go to every computer in the office and just literally sit there. Disk in, disk out, disk in, disk out, and if something went wrong on the install, I had to start over at the beginning.

It was a two-hour long process just to get everybody up to 3.1 so in those days, there was no chance of a fix pack. I think everybody was going to be on this version until probably they got another sucker summer intern in there.

Paul: So if you imagine people and their, people installing, even modern or relatively recent version of Windows where you have to think about the service pack one or service pack two or what level are you patched to, that was basically the old way of doing software.

The first time that I remember realizing that there was a different way to do it was in a [Joel on Software](http://www.joelonsoftware.com/) blog. One of the major things that they could do is that there was a bug, they could fix it and in the cloud, it would be fixed.

Edith: Yeah, I think it’s good though to realize that the reason that there was so much emphasis back then on making sure that a build was correct was because there was such heartache and pain if it was wrong.

Paul: Yeah, it made sense to hold up the release for new features or for something like that if it was promised to a customer because then, there was no alternative. It would be three, or six or twelve months later when they got the next opportunity to go ahead.


<blockquote>I think frankly, building software in the cloud and having the possibility of doing a release at any time you like has actually just completely revolutionized how people make software.</blockquote>


Edith: I completely agree. So to go back to the old days, all the emphasis was on extremely high quality and extremely stable.

Paul: Right, right.

Edith: Because you basically had once chance. You were lobbing this thing out into the world.

Paul: And even things where they had quarterly release cycles or something like that, it was still, it felt a lot like one chance. I worked at Mozilla and I was there on the switch from Firefox 3.0 to Firefox 4.0. Firefox 4.0 took 18 months to commit and there was things that were ready to be released the first week of that release cycle and that had to be held up for all these unrelated releases.

I think there were problems with the JavaScript engine and there was memory bloat and that sort of thing that kept pushing it back. And Firefox, during the process, or during the time that I was there, switched its process and it switched to what they call a release train model where basically, they ship a new version every six weeks and it doesn’t matter what’s shipped or what’s not shipped.

They’ll hold it up for build breaking, if it just doesn’t work at all but basically everything else would make it go ahead. The cadence and the velocity that they’re able to get since that happened have been massive.

Edith: Yeah, so that was the first evolution.  It used to be let’s try to cram everything in and then you’d get this vicious cycle where it’s like well let’s just put this one more thing in and then you’d have to add on all the QA time.

Edith: So that was the other reason why releases would take so long is you had so much QA.

Paul: Interesting.

Edith: I talked yesterday to a guy who had worked at Microsoft and he said, you know, quality had to be rock solid for Microsoft going back to my disk example.

Paul: Right, and these are people who have unit testing, automated tests as part of their builds.

Edith: But even beyond that, you have to have a person actually try it and then you have to actually go out and try it on all these different systems.

Paul: On all the different systems, right.

Paul: So one of the things that made it possible for the browsers to do, to move to the release train model is that they had the alpha channel and the canary channel, or whatever it is they called it. In Firefox, it’s the Aurora channel.

That’s the super, actually that’s not even the super beta stuff, they even have a nightly channel. They have a million people using the nightly and that tells them whether things are broken and how they are in fact and in production. I guess it’s kind of the first evolution of feature flags.

Edith: Yeah, I mean let’s talk about that for a second.

Paul: Right, we probably need to, aren’t we going to define things in this one?

Edith: Yes, this is the definitional episode, Paul.

Paul: Right, let’s start with what’s a feature flag because I think we’ve already talked about six things that we haven’t defined but what’s a feature flag?

Edith: A feature flag is basically the ability to hide code but yet have it public. So it used to be that everything that shipped was visible. So a feature flag is just basically an if then that wraps a piece of code and says it might be shipped but nobody can see it until the software team decides that it’s visible.

Paul: Right, and so some examples of that could be in a browser that you change a preference and the preference is use the new version of this or another example might be in, that a feature goes out in Facebook that’s shown to 1% of customers in Northern California who are in this demographic. Yeah, and it’s very liberating.

Edith:


<blockquote>The very liberating thing about a feature flag is that if something’s not working, you don’t have to do a redeploy.</blockquote>


So to go back to the old dark days where you had all these disks out in the world, the feature flag is useless because you’re going to ship all these disks out to people and they’re going to install it. A feature flag is useful when people are consuming stuff as SaaS.

Paul: The way that I think about a feature flag is that it separates the active shipping code from the act of actually turning on that code.

Edith: Yeah, deployment from roll out.

Paul: Right.

Edith: Yeah, so it’s deployed, it’s available, but it’s not visible.

Paul: Right, so now that we know what they are, what were we actually talking about?

Edith: We’re working our way through the evolution of software so we got up to release trains. You should talk a little about how continuous integration fits into that.

Paul: So continuous integration, to define it, it’s basically the act of having an automated build server that runs every day or at some sort of cadence and tests that your software works.

So CircleCI, my company, makes continuous integration as a service and what happens there is whenever you push to GitHub, we’ll automatically check your code out, we’ll build it, we’ll run your tests on it, and we can also deploy it to your customers, which is called continuous deployment or continuous delivery, depending on exactly how you think about the world.

Edith: You make this seem so simple but it’s really revolutionary. I remember the days without this.

Paul: Sure, sure. I remember in my first job, we had a daily build server and so we would find out every day whether or not the code actually compiled, even though we could get it all compiling on our own machines or some modules of it or whatever, compiling on our own machines, there’d be all sorts of build artifacts and dirtiness in the code that meant that this code didn’t actually work when it was ready to be shipped to customers.

Edith: Yeah, or even worse, I remember it used to be a thing when you broke the build, it was very shameful. You would have to sing a song or you’d have to do something embarrassing and that just doesn’t really happen anymore.

Paul: Right, right. My co-founder used to forget to add new files to Git so it constantly wouldn’t work although it was perfectly working on his machine but there’d be a file missing somewhere.

Edith: The classic excuse of, “Oh well it worked on my machine.”

Paul: Exactly, yeah.

Edith: Yeah, I didn’t know about builds my first summer job. At my first summer job, I was programming in Visual Basic.

Paul: Okay.

Edith: I was basically making a war game. It was for a defense contractor and I was trying to justify a space based laser versus an airplane based laser and if you had all these missiles coming over from Russia. Okay, this is a long time ago.

Paul: Yeah, yeah.

Edith: How many could you shoot down? The thing worked perfectly locally and then at the end of the summer, they wanted it off my machine. I was just like, “Oh.”

Paul: Okay, you’d need to put it on a plane or in space or one of those things?

Edith: No, they wanted my actual files off my machine.

Paul: Right, yes, in order to put it in space or on a plane?

Edith: No, it was just a simulation. I wasn’t actually controlling missiles when I was 19. Though that would have been cool.

Paul: I had this absolutely terrible release process at this place that I worked. It was O2, which is a really large phone company in the UK, in Ireland, and I think they got bought by someone recently but whatever.  They were launching this feature called i-mode and i-mode is this massive thing in Japan that completely failed to take off anywhere else.

Edith: Are you saying it was literally big in Japan?

Paul: Literally, it was big in Japan. And so they tried to launch this in Ireland. Everybody in the whole world knew that this was going to be a failure, but that was how the process worked anyway. And the release process was they had all this code somewhere that was going to be deployed and attached in servers and when they did that, there’s a manual. I was part of the manual team that manually validated with handsets, clicking through handsets manually, and vouched that this stuff actually worked.

There was no automation. The entire release process had to be repeated dozens and dozens of times as they fixed bugs and they reconfigured. It was, it was just a complete cluster.

Paul:


<blockquote>When I moved to doing software that had any sort of continuous release cycle, it was liberating because you actually know the path from what you’re doing on a day-to-day basis to it arriving at customers. Everyone, every developer in the place can know what that path is and everyone knows how code actually gets shipped. You don’t have to keep it in a continuous state of you know, oh maybe one day I’ll ship this.</blockquote>


Edith: Yeah, I mean I think to go back when you had these longer and longer and longer release trains or even pre-release train, people got very relaxed.

Because it just was like oh, I’m just going to sit in the corner and code away and sometime in the distant future, it might ship.

Paul: Right, and then as you’re coming towards the end of the quarter, everyone is hammering things out as quickly as possible and maybe there’s a few things that shipped early in the quarter that never got cleaned up or never got quite ready.

Edith: What do you mean by shipped right now?

Paul: So I remember sometimes where you’d merge something into master because you needed to get it tested but it wasn’t quite production ready. It’s out with the beta testers or something like that, but in order for it to actually ship to hundreds of millions of people, you need to remove whatever hacky thing you put in place.

Edith:


<blockquote>I think one of the things that has driven continuous delivery is just the rise of test-driven development.</blockquote>


Paul: That’s interesting. Yes, I mean, I think it’s obvious. You end up in a situation where when you’re trying to move to continuous delivery, you’re saying I’m afraid and we talked about the fear last week.

In order to get past that fear, you need to have automated testing and I guess in the old days, there was manual release cycles and you can’t do manual release cycles 10, 20 times a day. It’s just not possible.

Edith: You can’t depend on having a fleet, like to go back to the Microsoft example, you can’t rely on having two QA engineers for every developer who will just fling out code and QA will find everything.

Paul: Even with two QA developers, you can’t have two QA developers when you push code every five minutes.

Edith: Yeah, they’ll never keep up.

Paul: Exactly and then they’ll never identify the change that actually caused the bug and so on.

Edith: Yeah, I think the things we’ve talked about so far, SaaS has unlocked continuous delivery, test-driven development has unlocked it. What else do you think is really a foundational thing?

Paul: I guess the other one is kind of this change in customer expectations. Customers, as a fact of some people doing continuous delivery, everyone else has had to do it so once you start to experience it a little bit, and you start to wonder why do other sites go down for six hours on a Sunday night, this doesn’t make any sense. Why do I have to download new versions of this software versus clicking the update version or why do I even have to think about this?

Edith: Yeah.

Paul: I think for the installable software market or the desktop software market, Chrome was that sort of killer app that everyone sort of realized that this has completely changed the game.

Edith: Yeah, it’s completely changed the game.


<blockquote>I think even now asking people to download a plugin seems too onerous. They don’t want to do it. They just want stuff to work.</blockquote>


Paul: It’s almost tied to a conversion funnel. If you expect people to install 31 disks to upgrade to the latest version of Windows, people are just not going to do it. You’re not going to achieve the conversion rate that you’re expecting. There are too many alternatives to your app that are out there.


