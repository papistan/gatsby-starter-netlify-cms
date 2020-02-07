---
author: Kimh
comments: false
date: 2019-04-10 21:48:20+00:00
layout: post
link: https://launchdarkly.com/blog/trajectory-after-liftoff/
slug: trajectory-after-liftoff
title: Trajectory After Liftoff
wordpress_id: 193830
categories:
- DevOps
- Team &amp; News
tags:
- chaos engineering
- DevOps
- experimentation
- feature flags
- feature managment
- progressive delivery
- release management
- SDLC
- test in production
- Trajectory
---

This week we hosted our first conference, [Trajectory](https://www.trajectoryconf.com/). Many thanks to everyone who helped make it an amazing day! We are so grateful to our speakers and sponsors for bringing amazing conversations to Oakland. We spent the day sharing, discussing, and learning how different teams test in production, utilize progressive delivery methods, gain observability, experiment, continuously deliver, and incorporate chaos engineering into their dev cycles, among other things.

The two-day event kicked off with a half-day technical training session that focused on LaunchDarkly. Our intent for Trajectory wasn't to focus specifically on feature flagging, or even our own platform. Trajectory isn't a user conference. Our vision for Trajectory is to be a space for conversation around better development and release practices. Inspired by [Gremlin's ChaosConf](https://chaosconf.splashthat.com/) and [Honeycomb's o11ycon](https://o11ycon.io/), we wanted to bring together some of the leading teams currently using modern development practices and give them a platform to share learnings and strategies. That said, we know LaunchDarkly users are always happy for best practices so we also offered a focused training session before the main full day event.

If you were able to join us, we want to thank you for making the day so amazing! Being our first year, it took a lot to build the Trajectory brand, and we're so grateful to everyone for your support. If you missed it, don't worry, [we recorded the talks](https://www.trajectoryconf.com/home)! Check back in a few weeks for those videos. In the meantime, here are some of the highlights.


### Keynotes and Breakfast Burritos


As promised we started the main, full-day conference with breakfast burritos (chorizo, vegetarian, or vegan—this is Oakland after-all!) Our keynote speakers, Adrian Cockcroft, VP of Cloud Architecture Strategy at AWS, and Cindy Alvarez, Principal PM Manager at Microsoft, started the day with talks on how to effect change within organizations. Adrian focused on the metrics of innovation, or how to measure the effectiveness of your efforts. And Cindy discussed how to create a healthy culture of curiosity that supports innovative intent.


<blockquote>

> 
> Someone at [#TrajectoryConf](https://twitter.com/hashtag/TrajectoryConf?src=hash&ref_src=twsrc%5Etfw) just asked [@adrianco](https://twitter.com/adrianco?ref_src=twsrc%5Etfw) about small, continuous delivery for critical systems like Boeing (alluding to 737max). He didn't mention it, but the biggest blocker in "critical systems" isn't resistance to fast iteration, it's to transparency.
> 
> 
— Jason Yee (@gitbisect) [April 9, 2019](https://twitter.com/gitbisect/status/1115661683387592705?ref_src=twsrc%5Etfw)</blockquote>





<blockquote>

> 
> [@cindyalvarez](https://twitter.com/cindyalvarez?ref_src=twsrc%5Etfw) mentioned at [#TrajectoryConf](https://twitter.com/hashtag/TrajectoryConf?src=hash&ref_src=twsrc%5Etfw) that her teams send "two things you're still worried about" emails each Friday. What a great way to encourage happy teams that address small (or big!) hangups quickly and democratically so they can focus on progress.
> 
> 
— Cameron Savage (@CameronSavage) [April 9, 2019](https://twitter.com/CameronSavage/status/1115673106951991296?ref_src=twsrc%5Etfw)</blockquote>




Next we saw Sr Dev Manager at IBM, Michael McKay, share 'Learning to Do Deployments At Scale in 6 Easy Steps.' He showed us how the IBM Kubernetes Service builds and deploys micro-services to Kubernetes clusters around the world.


<blockquote>

> 
> . [@McKayMckaymic](https://twitter.com/McKayMckaymic?ref_src=twsrc%5Etfw) talking IBM Kunernetes scale w 100,000 deployments [#trajectoryconf](https://twitter.com/hashtag/trajectoryconf?src=hash&ref_src=twsrc%5Etfw) [pic.twitter.com/oH8T6dMMuu](https://t.co/oH8T6dMMuu)
> 
> 
— Edith Harbaugh (@edith_h) [April 9, 2019](https://twitter.com/edith_h/status/1115673091986714624?ref_src=twsrc%5Etfw)</blockquote>





### Breakout Talks: Gotta Catch 'Em All


Talks were divided into two main tracks–future vision and best practices. In the best practices track Josh Willis (Slack), Arjan Franzen (Maxeda DIY), Emily Voigtlander (Seesaw), and Vijay Ramesh (Demandbase) shared how they use feature flags within their architecture, became data-driven, enable teams across their organizations to use feature flags, and feature flag machine learning architectures.


<blockquote>

> 
> Interesting uses for flags by legal and sales presented by [@evoigtlander](https://twitter.com/evoigtlander?ref_src=twsrc%5Etfw) at seesaw. [#TrajectoryConf](https://twitter.com/hashtag/TrajectoryConf?src=hash&ref_src=twsrc%5Etfw)
> 
> 
— David Lawrence Evans (@owlmonkey) [April 9, 2019](https://twitter.com/owlmonkey/status/1115731962826649600?ref_src=twsrc%5Etfw)</blockquote>





<blockquote>

> 
> "...and how do I feature flag changing the feature flag engine?" - [@josh_wills](https://twitter.com/josh_wills?ref_src=twsrc%5Etfw)
> 
> 
type questions at [#TrajectoryConf](https://twitter.com/hashtag/TrajectoryConf?src=hash&ref_src=twsrc%5Etfw)

— Cameron Savage (@CameronSavage) [April 9, 2019](https://twitter.com/CameronSavage/status/1115691675618164738?ref_src=twsrc%5Etfw)</blockquote>





<blockquote>

> 
> Vijay Ramesh: Analyze feature importance by adding and removing features [#trajectoryconf](https://twitter.com/hashtag/trajectoryconf?src=hash&ref_src=twsrc%5Etfw) [pic.twitter.com/QbliiGiAe4](https://t.co/QbliiGiAe4)
> 
> 
— Cindy (@_cindyylinn_) [April 9, 2019](https://twitter.com/_cindyylinn_/status/1115746387709190144?ref_src=twsrc%5Etfw)</blockquote>





<blockquote>

> 
> [#TrajectoryCon](https://twitter.com/hashtag/TrajectoryCon?src=hash&ref_src=twsrc%5Etfw) [@ArjanFranzen](https://twitter.com/ArjanFranzen?ref_src=twsrc%5Etfw): Culture change: Be oriented to the company and the team. Embrace feature management, continuous delivery, experimentation, and require that all features prove their effective and useful.
> 
> 
— Heidi at #DevOneLinz (@wiredferret) [April 9, 2019](https://twitter.com/wiredferret/status/1115700083864023042?ref_src=twsrc%5Etfw)</blockquote>




And in the future vision track Emma Humphries (Mozilla), Ramin Keene (Fuzzbox), Jason Yee (DataDog), and Ellie Day (Atlassian) talked about the culture of experimentation, techniques that support effective experimentation, the value in running chaos experiments, and thinking about ways to reduce friction when adding/maintaining/analyzing flags in a codebase.


<blockquote>

> 
> “Do you involve and empower your designers with feature flag access and experiments?”, asks [@heyellieday](https://twitter.com/heyellieday?ref_src=twsrc%5Etfw) [#TrajectoryConf](https://twitter.com/hashtag/TrajectoryConf?src=hash&ref_src=twsrc%5Etfw)
> 
> 
— David Lawrence Evans (@owlmonkey) [April 9, 2019](https://twitter.com/owlmonkey/status/1115760671373684737?ref_src=twsrc%5Etfw)</blockquote>





<blockquote>

> 
> [@triagegirl](https://twitter.com/triagegirl?ref_src=twsrc%5Etfw) “voting is a rotten way to prioritize features” [#TrajectoryConf](https://twitter.com/hashtag/TrajectoryConf?src=hash&ref_src=twsrc%5Etfw) [@LaunchDarkly](https://twitter.com/LaunchDarkly?ref_src=twsrc%5Etfw) [@thenewstack](https://twitter.com/thenewstack?ref_src=twsrc%5Etfw) [pic.twitter.com/x47FRtLgQT](https://t.co/x47FRtLgQT)
> 
> 
— TC Currie (@TCCurrie) [April 9, 2019](https://twitter.com/TCCurrie/status/1115690563922042880?ref_src=twsrc%5Etfw)</blockquote>





<blockquote>

> 
> Experiments aren't isolated, they are part of a program.
> 
> 
Thinking about how requests move through your systems as a way to organize and orchestrate experiments. [@rmn](https://twitter.com/rmn?ref_src=twsrc%5Etfw) [#trajectoryconf](https://twitter.com/hashtag/trajectoryconf?src=hash&ref_src=twsrc%5Etfw)

— Emma (@triagegirl) [April 9, 2019](https://twitter.com/triagegirl/status/1115700142416392194?ref_src=twsrc%5Etfw)</blockquote>





<blockquote>

> 
> The advantage of cloud is being able to easily spin up new instances. But it is NOT a guarantee against failure. [@gitbisect](https://twitter.com/gitbisect?ref_src=twsrc%5Etfw) [#TrajectoryConf](https://twitter.com/hashtag/TrajectoryConf?src=hash&ref_src=twsrc%5Etfw)
> 
> 
— Dawn Parzych (@dparzych) [April 9, 2019](https://twitter.com/dparzych/status/1115722330339024896?ref_src=twsrc%5Etfw)</blockquote>





### Panel Discussion


The day wrapped up with a panel discussion that focused on the new tools and trends in application and service delivery. The panel included Preeti Somal VP of Engineering at HashiCorp, Kolton Andrus, CEO & Co-Founder of Gremlin, and Rachel Stephens, Analyst at RedMonk.


<blockquote>

> 
> A3: [@rstephensme](https://twitter.com/rstephensme?ref_src=twsrc%5Etfw) Locus of control of " I can build really cool stuff"iot can have a large outcome in terms of cultural buy-in, teams enthusiasm to pursue a project, and what you ultimately end up building. [#TrajectoryConf](https://twitter.com/hashtag/TrajectoryConf?src=hash&ref_src=twsrc%5Etfw)
> 
> 
— Dawn Parzych (@dparzych) [April 9, 2019](https://twitter.com/dparzych/status/1115760359158116352?ref_src=twsrc%5Etfw)</blockquote>





<blockquote>

> 
> A2: [@psomal](https://twitter.com/psomal?ref_src=twsrc%5Etfw) Ecosystem looks at security and consistent workflow. Building the ecosystem and partnerships to reduce strain on customers figuring out what solutions work together. [#TrajectoryConf](https://twitter.com/hashtag/TrajectoryConf?src=hash&ref_src=twsrc%5Etfw)
> 
> 
— Dawn Parzych (@dparzych) [April 9, 2019](https://twitter.com/dparzych/status/1115756475786260480?ref_src=twsrc%5Etfw)</blockquote>





<blockquote>

> 
> "Engineers want to do the right thing, but you have to make it easy to do the right thing" - [@KoltonAndrus](https://twitter.com/KoltonAndrus?ref_src=twsrc%5Etfw) at [#TrajectoryConf](https://twitter.com/hashtag/TrajectoryConf?src=hash&ref_src=twsrc%5Etfw)
> 
> 
— Cameron Savage (@CameronSavage) [April 9, 2019](https://twitter.com/CameronSavage/status/1115759945415254016?ref_src=twsrc%5Etfw)</blockquote>





### What Comes Next?


It's official, Trajectory is here to stay. We even have our first fan art:

[![](https://blog.launchdarkly.com/wp-content/uploads/2019/04/trajectory-fan-art-1024x512.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2019/04/trajectory-fan-art.jpg)

Hosting our first conference is a huge milestone! We believe when teams aren't inhibited by the fear of breaking things, they can collaborate more effectively, get feedback sooner, validate their ideas and have control over the software they’re putting into the world. And the fact that a strong lineup of prominent personalities in the software development space were willing to come and talk about how they do that within their teams, really reinforces that.

As mentioned above, we recorded these talks and hope to have them on the LaunchDarkly in a couple weeks. You can [sign up here](https://www.trajectoryconf.com/) to be notified when the talks are ready, or if you want to be the first to hear when we've announced the date for Trajectory 2020.
