---
author: andreaech
comments: false
date: 2015-12-04 00:37:13+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-continuous-delivery-and-mobile-development/
slug: to-be-continuous-continuous-delivery-and-mobile-development
title: 'To Be Continuous: Continuous Delivery and Mobile Development'
wordpress_id: 751
categories:
- To Be Continuous
tags:
- A/B testing
- Acompli
- continuous delivery
- CSS
- Google
- iOS
- Kevin Henrikson
- Microsoft
- mobile continuous delivery
- mobile development
- Outlook
- QA
- techcrunch
---

On this episode of To Be Continuous, Edith and Paul are joined by Kevin Henrikson, Partner Director of Engineering at Microsoft, to discuss what's necessary to be successful with continuous delivery in mobile development. This is episode #8 in the To Be Continuous podcast series all about continuous delivery and software development.

This episode of To Be Continuous, brought to you by Heavybit and hosted by Paul Biggar of CircleCI and Edith Harbaugh of LaunchDarkly. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.


Paul: All right, Kevin. So, what’s your favorite thing about Continuous Delivery?

Kevin: Good question. So, Acompli started kind of the approach, when we first started was just a couple people. And our deal was like, “Hey, you’re trying to get this thing to work, send emails.” So it was like, keep checking it in, get closer and closer to kind of the definition of it was working.

And then as we started to experiment farther out, we said, you know, “What’s the right sprint cadence?” And we’d come from kind of traditional enterprise companies, where, you know you ship every six weeks or every four weeks and we’re like, oh, we can go faster.

People are doing this agile thing. It’s like two week sprints, and we tried two weeks and realized that most of the work came in on Thursday afternoon or Friday kind of thing, ’cause the end of the second week and so what if we just do one week then most of that work will come in, you know, the first Friday. And sure enough, it worked, right? So 80% of the work still comes in on the last day or kind of completes on the last day or gets to the point of ready. And so, what we liked is that it gave us a much smaller kind of chunk of deliverable, right.


<blockquote>So, like the train keeps moving but the size of what’s on the actual boxcars is smaller and so if you have a problem, it’s easier to roll back, easier to fix.</blockquote>


Or if you have a problem, you can just patch it quickly ’cause you’re used to moving quickly.

Edith: Wow. Okay.

Kevin: So unlike in a traditional world where you ship something every six weeks, you’re like oh, we made a mistake, we need to go patch this. Like, the patch felt like an exception and you’re like, your muscle memory for patching was not there, right? So you’re like do we do it now? Is it worth it?

And then it’s like well, if you’re five weeks in and you discover that thing, it’s like well, the six-week thing is out there where with, if you’re shipping every week, you’re like oh let’s patch it. We shipped yesterday? We just click the button again, and it builds and it goes. So you’ve built the muscle memory to move quickly, right. And so I think, what I like the most, kind of going back to the specific question, is just the fact that it lets you get good things done quickly, but also correct mistakes quickly.

Edith: Wow. So this is a good time for you to introduce yourself.

Kevin: Cool. So, Kevin Henrikson. I currently manage the Outlook, kind of non-Windows teams at Microsoft. So Outlook for iOS, Android, and Mac. Previously, I was VP of Engineering at Acompli, which was a mobile startup, focused on iOS and Android.

Edith: Yeah so you had a lot of good thoughts right then. One of the things I wanted you to talk more about is why do you think 70-90% of the work is always on the last day?

Kevin: Yeah, I think people are kind of deadline driven. I think generally they want to work until the last minute and I think software development ends up being this thing where you’re never done. And so the only way to define done is to actually draw a line and say this is done and then still some things miss that line. And so the tighter you give the window for things to get done, the more often they’ll hit that window because you’ve kind of broke things into smaller chunks.

And also, because software’s kind of this long-lasting thing that never is kind of done done that you end up with, if the chunks are small, people are able to estimate and think is that going to take me a day? Very rarely does somebody think something’s going to take them a day that takes months.

But very often, like if you think something will take months, it may take many, many months. Because it’s hard to guess, there’s so many variables, so many things are going to change in the environment, turn what you’re doing before you get there.


<blockquote>So, I think the short answer is if you start with a smaller window and more discrete small tasks, those tasks are easier to estimate, they’re easier to consume, they’re easier if you get disturbed, like oh I’m going to go down and get a soda, or somebody asks me a random question ’cause some fire comes up, I can kind of make it up because I was only expecting to spend half my day working on that anyways.</blockquote>


So, I think that kind of works out in our favor.

Paul: So, there’s an implication with what you said there, that the tasks sort of grew because it was two weeks, rather than–

Kevin: Yes.

Paul: So, I guess the phrasing is, when it was two weeks, was it that a one-week task had grown to two weeks? Or was it that things got cut when it got shrunk down to one week, and you ended up with technical debt, or something along those lines?

Kevin: I think it was a couple combinations. I think if you feel like you have two weeks to work on a task, you’ll spend more time polishing or potentially doing things that aren’t on the critical path to getting it done.

And I think that’s natural, right? Like, maybe it is you’re paying off too much technical debt, right? In the start-up world, you have to have that lever. And even just in general software development, like, you have to have a lever. We’re not launching the space shuttle here. There’s room for some wiggle room and imperfection.

And I think breaking it into small pieces lets people focus on, “Hey, I’m only gonna do this” and “I have this much time to do it.” Where you say, “Hey, it’s got two weeks,” you may be deep into the second week and saying, “You know, I just don’t like my approach. I’m gonna change it.” And you basically end up throwing away a week’s of work, whereas, if you’re thinking that “Hey, the deadline’s coming in a week,” you’re gonna make that kind of epiphany, like, “Oh, I made a mistake,” or “I’ve taken the wrong path” much quicker.

So, I think it allows you to break your decision-making and optimize on getting it done, because the window is kind of quickly approaching, being a one-week spread versus two.

Edith: This might sound like Seven-Minute Abs, but why not two-day sprints?

Kevin: Yeah, so I think in two days we– or one-day sprints, right, how do you continue to make it faster? So, for us, there was sort of one artificial gate, which was the fact that you really can’t ship quicker than about a week with Apple.

And even then, it sometimes slips by, because, you know, four or five days, and then during a peak season, if there’s lots of apps, like a Christmas holiday, or around a platform update, you’ll see a spike in the review times. So, Apple kind of, and we run iOS app first before we port it to Android. So that ended up driving us towards a little bit to a week. Cause it was like, if you shipped on Monday, the app would get in the store some time end of that week. And that was a natural cadence to start the next one.

So, it’s really hard without pushing the emergency release button, which Apple only lets you do once or twice a year, to ship more than once a week. And then, we kind of let the rest of the team fall behind that. If you’re only shipping the app once a week, let’s keep the new chunks of new work, or big bug fixes to that path on our service.

The way our architecture is, and we can talk about that more, we spend as much, you know, 77% of the logic of the app is down deep in the service, because that we can update all the time. So, when we push a release and don’t wanna fix something, we fix from the service the same day.

Edith: Interesting.

Kevin: So, that allows us to have a much more agile approach, because the service is constantly being updated, but the app is kind of gated in one-week chunks.

Paul:


<blockquote>So, what you’re saying is that the biggest impediment to your shipping frequently is Apple.</blockquote>


Kevin: The platform, yeah. The platform, basically, Apple’s– And specifically, it’s the fact that Apple has a review process, which is great. That Apple review process generally keeps the bar of apps better and puts some good discipline inside of the wider range of development, people that are coming to the Apple platform.

But, it also, when you wanna move quickly, you can’t. The platform itself kind of enforces this four to seven-day lag in shipping.

Paul: So, you’re now running teams that are shipping on non-Apple platforms. Did you guys make any changes to your release cadence as a result of that?

Kevin: Yeah, so I think on Android, for example, we still kind of keep to the one-week junk of we plan a sprint. Build for a week. Release to our beta group or dog feed users, and then release to production. But Android gives you this advantage where you can do percent-based rollout.

So, with Android, we end up releasing usually two or three times a week. So, you’ll release kind of The Release on Monday, at like 1-2%, kind of walk that out three, five, 10%. Usually at five or 10%, you can pick some new signal of crash or behavior that you wanna adjust, make a hot fix, push another release, start at 10%, 20%. Oh, you see another one you wanna tweak at 20%. And finally, from 20 or 30, you end up going all the way forward.

Paul: Do those Android users help you on the other platforms, as well? Are they finding crashes that also exist on the other platforms?

Kevin: Today we’re 100% native on both, so there’s no shared code between iOS and Android from the mobile app perspective. Obviously from the service, it’s 100% shared code. So, what we’ve actually done in the past, is when we launch a new feature that we think is either controversial, or has a high chance of risk, for example, when we launched iMap support.

We launched generic iMap support on Android first, knowing that we could patch it quickly, and adjust if things went wrong, simply because there was no way to test the millions of random iMap servers in the world and get any kind of focus. When we talked to Gmail or Yahoo, or– Single point.

Paul: That’s really interesting, actually, the idea that because the rollout, or the sort of safety features are only supported on Android, that people will end up building features there first.

Edith: How deliberate did you have to be about putting stuff in the service, versus in the apps? Was this the lesson that you learned?

Kevin: So, we had always thought of the service as the place where we always wanted to do as much of the logic that could break us– You just don’t wanna do it twice. You don’t wanna implement active sync twice. You don’t wanna implement an iMap stat twice.

And it also allowed us to pick a protocol between our cloud service and the mobile app. It was optimized for mobile. So, think of the API, the shape of the API looks closer to the screen of the app. There’s a request for “Get my inbox,” and then make a change. Where, if you think of iMap, or the mirror out of email protocols, that we talk today, they don’t have that very linear type of approach of “Give me this screen. Give me that screen.”

They’re thought of in a way where you’re going to sync all the mail down to your desktop client, and then manipulate it locally, and then sync changes back up in some either connected or disconnected state. So, the service was basically set to put complex logic, but also to allow us to get leverage, ’cause everything we could build in the service was one less thing we’d have to do twice on the client, because we picked a path that we didn’t support. We didn’t basically have a lot of shared clip or clients, essentially none, just the API.

Paul: And it’s the same service that sits behind all the different clients?

Kevin: Yes, so we have a single cloud service that basically powers both the iPhone client and the Android clients.

Edith: It’s interesting, so at TripIt we had a lot of similar issues. Like, we were at one time one of the biggest, a lot of our users are Gmail.

Kevin: Okay, awesome.

Edith: People would sync their Gmail with us, and their calendars. Did you find there was a difference between the you or the app experience that Android and iOS wanted? How much did you bifurcate that?

Kevin:


<blockquote>Sure, so, a lot of people ask is like, “Hey, did you launch a feature first on Android or iOS, “or do you always have to make them “come out identical?” My answer to that is pretty simple. Most normal people carry one phone. They’re either an Android user or an iPhone user.</blockquote>


So, they don’t know that you released it first on Android or iPhone, because they don’t carry both phones. So, we think of that, from a feature point of view, that when they’re done, then we ship it. Now, if we’re trying to line a press event around something, we’ll wanna make sure they’re both there before we do the press event. One may come out a day or two before the other. But, generally speaking, we don’t try to, you know, legislate you have to do it this way, ’cause it works on iPhone.

In fact, we actually took a different approach, where we said, We wrote it one way on iPhone and then we went to Android. It wasn’t just like, “Oh go port all the screens over.” It was like, “What would this screen look like for an Android user?”

So, we want our apps on the mobile device, and most mobile users wanna look at an app and feel like it fits in with the rest of their phone. So, the way that an Android navigation works, the way that people use the back button, or not, is very different on iPhone and Android. The fact that there’s widgets, and the way the widgets are exposed on Android, and the way that those people want to integrate deeper into the platform.

Those kind of things we let go with the platform. Our view is write it in native code, ’cause it allows us to take advantage, and move quickly to the platform-specific features. But it also lets us tailor the experience, and the UI and UX to whatever that user base wants.

Paul: It’s interesting that’s, that you talk about it that way, because in the old days, kind of ten years ago, when people were making multi-platform applications, there was a tendency of people to try to make it all match the same, the Firefox is an example here, or Chrome one of those tools that people use on all platforms, was designed to look the same on every machine, even though people didn’t have that machine.


<blockquote>I think one of the nice things that’s happened with the mobile ecosystem is people have thrown away that concept, and they’ve made it feel actually native for each of the platforms.</blockquote>


Kevin: Yeah, and I think that also goes to feature set, right? Like, you would think that the traditional app is like, “Oh, if it works this way on Mac, “or on Windows, or on the web, you would expect kind of 100% feature parity between all those platforms. And today on mobile, we go and select where you actually use it. There’s features that exist in mobile only.

Because mobile has all this additional context of your location and where you are, and what you’re doing. Are you running? Are you driving? There’s other sensors in the devices today that allow you to build specific features that are richer. So, we always thought of a commonality.

So, rather than sending more emails, send better email, right. Don’t say, “I’m running late.” Say, “I’m running late and I’m here,” and send a quick tap of a button to put the map and show you that, “Oh, I’m 20 minutes away,” or, “I’m on the train,” or, “I’m at the train station,” so that people can understand you don’t have to type out how many minutes it’s gonna take. You don’t know. Or, you walk in, or you drive in–

Edith: Plus, people lie all the time. Like, “I’m on my way” has a pretty loose meaning of anywhere from “I might leave my house in 30 minutes” to–

Kevin: And depending on the context, right? What that person’s thinking, so yeah, good point.

Paul :     One of the interesting things that you said there is that it might take a day or two ... When you're trying to launch something, they might actually land a day or two apart. On this show, one of the things we try to do, is we try to pitch Edith's business, which is feature flags as a service, LaunchDarkly.com.

Edith:     I never knew you did that, Paul.

Paul :     It would seem to me that, kind of, best practice there is to release the code and not have the code be a blocker on the launch. The code is there, but it's behind a feature flag. Do you guys do that much?

Kevin:    We have feature flags. We have flight. We call it flightings, same idea. We launch all kinds of dark features on the server, in particular. There's all kind of things that we've built that are currently in production on the service that the production app may not take advantage, right? Great example is like we launched Avatar Support and it fit with the UI of Android better. We turned it on there and didn't turn it on in iOS. We're still working through how we want that UI to lay out. In that kind of case, and maybe we'll turn it on for some percentage of users and test it. We basically think through like, what are the features that make sense?

I think the one piece that we're a little different than people that kind of go crazy with tons of feature flags is that we actually try to like think through, like, "Is this something we're going to want to potentially toggle on and off, rather than adding a flag for everything?" Simply because when you end up with a large number of flags, the interdependencies, the combinations, become very hard to test. Even at the scale we're at with millions and millions of users, you just can't get to the combinations, and then you make a mistake and developers are like, "Oh, well you didn't have XYZ default on. You weren't running experiment 3." Those kind of things.

For certain things, we don't feature flag and the fact that we always ... People used to ask in the early days, "Well you guys do A/B testing?" We're like, "Yeah, we do A/B testing every Friday. We ship a new build." As a startup, we were able to, we would just make the change. Now the user base is bigger with millions and millions of users using the app, we need to be a little more thoughtful in terms of how you roll that out. In this case, we are using some more flighting type of feature flag stuff, too. Enable the users to see features in kind of waves.

Edith:     Let's walk through this. I think it called, "Shipping Friday." Every Friday you shipped. What would you do if there was a bad release out on the field for a week?

Kevin:    I mean, it'd be very hard for it to ever show up in a week. We would notice it ... Our process basically is, we plan the day on Monday. Review kind of the previous week's work. Code Tuesday through Friday. We ship to testing on Friday. Test Friday night, Saturday night, Sunday night. We have a team that basically does testing overnight on those three days. Monday morning we get the report and then we decide to push it. We push it to our beta users. There's a lot of gates. There's a set of QA and kind of manual testing that happens over the weekend. There's a beta test, kind of dogfood, that happens the first few days of the week. Then we kind of push it live. Like I said, those kind of things, if it's a really ... We can split the platform. If it's an Android bug, we usually can fix it within an hour. It's very quick to push a new Google app or Android app.

With an iPhone issue, or iOS issue, we have to determine the severity of it. If it's something that needs a critical fix, we'll push the red button with Apple that says we need an expedited review, which usually can bring the time down from a week, down to about 24 hours, but no guarantees. It's just best effort. That's what we do. Now, there's many cases where we disable features. iMap for example, we turned on. We started seeing a lot of problems. We turned it off to a few countries that we saw more problems from and it was very popular iMap servers in those countries we didn't support.

Edith:     Oh, interesting.

Kevin:    We just disabled it in our geo basis. There are places where we've turned off things were we had put a feature flag in place to do that, but it really depends on the feature. Some big UI changes are hard to feature flag, so those you have to deal with. Fortunately those cause a lot less crashes because UI's just not as in-stable of code as the, kind of, coursing code.

Edith:     Is there ever something that you really wish that you'd put a feature flag on that you didn't?

Kevin:    Yeah, I'm sure there is. We shipped iOS9 on the day iOS9 launched and had a crasher. There is a migration bug. I don't know how you could have turned off iOS9. Some of these things, you're just ... Then we pushed the button. We had ... It took us 2 days, so we had to eat 1 store of use for 2 days, which was super painful.

Edith:     They hurt.

Kevin:    Yeah. They're pretty permanent.

Edith:     Well, they hurt and then they write mean things and it just stings. I got, you know, at TripIt that we were overall 5, but when you get 1 star, you feel the pain personally.

Kevin:    Yeah. You get thick skin.

Paul :     You were saying, you're releasing something to testers over the weekend and then it goes out to the beta channel the next week. If the testers gave you a bad report and you needed to pull it, then you end up in the situation of, I presume, of instead of a week's changes going ahead, you're going to have two weeks' changes going ahead, and if that's bad, it might stack up with three weeks' changes and then suddenly, you're out of continuous delivery. You've got a big risky release going in. Any experiences with that?

Kevin:    Yeah, we've had that frequently. Usually what happens, though, is because you've only written code for 4 days, we usually always say, if it takes us 4 days to write the code, we should be able to fix it within 4 hours. We fix it Monday and just ship it and take the risk that, "Hey, we thought we'd ..." Extra code reviews, very aggressive look. Then we ship it to dog food. We usually very rarely skip an entire week, where we pull through that. We almost always find a way to ship it. Everybody kind of rallies around that as cultural thing. As like, "Hey, if there's something wrong, or a crasher comes through and we can't fix it," it's kind of all hands on deck to sort that out.

Paul :     Got you.

Kevin:    One thing that I did miss is we internally dog food every check in, right? The way that our system works is when you check in code, whether it's on the app or on the service, within about 3 minutes, it's pushed to your phone, or the service has been updates. Service is constantly updating with every check in. Things that are very critical, like ... We say, "What's a critical bug?" Well I can't send email or I can't reply, or forward, or a button doesn't work. That stuff's found within minutes of it being checked in because there's a ... Dev team's relatively large and we're all running that app, so we're seeing those kind of things. Like, "Whoa, I don't like this." Jump on chat and tell everybody like, "Hey, let's go look at this."

Paul :     Got you. You just stop shipping your things if there's a problem. You're like all hands on deck to fix the actual problems.

Kevin:    Yup. Like I said, usually when you've only had 4 days of change, kind of at the maximum, usually within a few hours we can figure out what's going on and either disable it ... For example, in the case of when we shipped the iOS9 crasher, it was with spotlight indexing, it was the new indexing feature in iOS9, we just disabled spotlight indexing. Cut a new build and we shipped it within an hour. Most ... Again, it's never perfect, because software's an imperfect trade, but most things we can figure out soon enough, or be able to roll it back or disable it.

Paul :     Right. One of the big releases that I was part of that went badly on this kind of thing was the Firefox 4 release. It took 18 months to go from Firefox 3 to Firefox 4. The main reason was, there'd be a big feature that would go at ... The big feature would be foggy and would need a lot of work. It just wasn't ready to go ahead. In the meantime, other teams are working on their own thing, things are getting included. In the end, something that was supposed to be, I think a 6 month release, ended up taking 18 months before it went out.

Kevin:    Yeah, it's rough.

Paul :     There was stuff that was ready, new CSS features. The sort of thing that you don't want to wait 18 months to be released.

Kevin:    Yeah, compatibility stuff.

Paul :     Yeah. That was the catalyst for completely changing to the continuous release model.

Edith:     You talked about dogfooding. How much do you dog food? Do you require everybody to only do email on their mobile?

Kevin:    We don't. We've actually, there were cases where we block, we could block, or we don't. Fortunately, everybody uses mobile email and so, I mean, it's a pretty light ask. It's not like we're building an app that people would not normally use on their daily basis. I think the biggest thing is that generally developers on the team don't have the email volume that matches with our user base. Generally developers don't get crazy long 120 message threads and kajillion attachments and super long complex HTML in the messages. I think the bigger problem is not about people using the app. It's about the data, kind of the representation of the data, matching our wider user base.

Edith:     I ask because Facebook legendarily does not allow people to use Google products. For example, they use Microsoft Bing instead of Google.

Kevin:    Yeah. I mean, I think companies have those rules. I think for a long time, Microsoft, they would only pay for your cell phone if you used a Windows mobile phone. I think these are common ways of trying to encourage folks to use what's ... I think those are great and they work. I think there's always exceptions to the rule. I think that you also can come blind to competitors by only focusing on your own stuff and you end up with tunnel vision of saying, "Hey, all I know is how my stuff works with everything else. I've never worked in a "real world universe" where everything's different." Where are you live in now ... You have Mac. You have Windows. You have this phone. I have Android devices. I have ...

With Android in particular, there's how many different versions of Android that are out there in the wild today on all kind of different hardware? Even from the same vendor, there could be ... We can see bugs between Samsung devices. I think we encourage people to use what they have. People are allowed to expense or buy whatever phone they want. Lots of the team members, especially those of us in support that are dealing with customers, have multiple phones. We have different tablets and phones that our personal devices that are connected and we're using them, kind of switching between them, because that's what customers are doing. They're looking at all these platforms. Being familiar with them is one, but also just being able to catch issues.

Paul :     One of the questions that ... One of the things that we talked about with Kris last week, was the trade off between doing continuous delivery and delivering polish. Acompli had this reputation as being this incredibly polished product that people loved using. It was the best Gmail app, I think, on an iOS, was the description I've heard. How do you feel that trade off works, where you have something with just such a high degree of polish, how does it affect what you're shipping and how you ship?

Kevin:    First of all, thank you, it's awesome. We've got lots of accolades for our polish and I think we always thought that we could do better. The founders were all kind of like plumbers. We all worked on infrastructure and back end systems. UI wasn't our thing. The thanks really goes to the folks on that mobile team, the experts we hired in that space, that really just like to own their craft. It was a constant tension. There's always this notion of the startup lever of you have to get function and utility. We're building a utility. We're building an email client. If it's missing big features, people just can't use it. If delete is missing and reply all is missing and certain features are missing, you can't use it. No matter how polished the send button is, it doesn't matter if you can't do reply all and it doesn't support BCC and those kind of things. There was always this tension between how do we get polish and utility. I think we could have got a more beautiful app, but potentially a less functional app and who knows how that would have affected the outcome if we would have spent more time on polish and vice versa. I think what I've learned now ...

Another team joined Microsoft just after we did, called Sunrise. It was a calendar. They were like world renowned design. Really, really beautiful design. You ask them how they kind of went to their sprints and delivery and their model was more like every 6 weeks, 7 weeks. It was done when it was beautiful, was kind of their mantra. Versus us, it was done on Friday. They brought to ... Now we kind of have a combined team, we're working together. They brought this notion of, "Oh my gosh. They basically spend all this time getting the design perfect and honing it, but we're able to ship it every week." The way that we do that now is the design starts about 2 or 3 weeks ahead of the actual work.

We're allowed to get the designs much more time to kind of allow that polish to happen and those designs and locks to come back very, very high fidelity, so that when we implement it, we know what we're doing. Where Acompli kind of did design and implementation, almost in the same week, we would design stuff. Spec it on Monday. Design it on Tuesday. Build it on Wednesday and Thursday. Quick, kind of put some paint on it on Friday, and then ship it on Monday. It just didn't give you time to get to complete beautiful. I think now that with the Sunrise and integrating that process and the team that they've brought over is really up to our game on the UI side.

Paul :     If you're looking for beautiful, you know it seems ... If you're looking for functional and beautiful, I guess, then shipping constantly would seem to be a helping hand there. They literally just spend 6 or 7 weeks working it internally?

Kevin:    Yeah. They would work it internally and continue to polish it and get the feature and the UX just right until they decided, "Hey, now this new chunk of work is done."

Paul :     Would that involve like user testing and data?

Kevin:    Tons of data. User testing, data research and then it also helped, because as a startup, you become immune to the press. If you're releasing every week and you're like, "Hey, look at this, look at this, look at this." The press stops writing about you. The Sunrise did an amazing job of packing up that 6 week with something a little bigger and dropping a bigger hammer and saying, "This is something big and amazing. Write about it." A lot of the press and the attention they got was because they were able to drop these slightly larger release, than a traditional one week bite, that gave them the additional attention.

Paul :     I think that's really interesting. I remember one of the sort of software marketing 101 things, I think Joel Spolsky talked about years and years ago, was that the biggest thing that they could do to get press, was just increase the version number. If FogBuz moves from 5 or 6, would get a

Just got a 20% or 30% customer increase just by existing. Now with continuous delivery, we've kind of killed that. No one talks about the new version of, almost anything. I don't think anyone's ever talked about the new version of Facebook. There's the new news feed and things you can yell about, but it's not like we've gone to Facebook 37 now and it's amazing.

Edith:     I disagree with, Paul. I think what's gone away is the notion of versioning, but yes, Facebook does a very good job about announcing new features. So does Twitter. They push moments. Nobody ... The number's an arbitrary thing, but they're definitely still pushing at least functionality.

Paul :     It feels like it's not ... Sorry, I think there's two things I'm saying. One is that releasing features feels like less than releasing a whole new version. The second thing is that companies of Facebook's size, and that sort of thing, and Google size, do good jobs of it. Whereas small startups, it is very difficult for small startups to be able to do the same thing when they have that continuous delivery cadence.

Edith:     I think it's just hard for small startups to get press, period.

Kevin:    Yeah, you basically need ... You talked about moments. We always talked about, what's the next product moment? Even inside of a company like Microsoft, that's important too. With Microsoft, you have different competing events, which is ... There's always lots of things to talk about. Aligning your moment with, "Oh, they're launching Windows 10, or they're launching Office, or their launching the new Xbox." There's very, very large events that are like, "Oh, the NFL is switching to the next version of Surface. These are huge product moments and like, oh, I want to talk about my little feature in my app. I say little, but even at the scale with millions and millions of users, it's still, in the scale of the like the NFL switching to the new Surface Pros, like that's pretty cool. You have to kind of ...

There's a marketing strategy and PR strategy and how that aligns with continuous, it's tough. I think we struggle with that all the time, of trying to pick when to turn things on and when to say, "Oh ..." What things you groups together and what's the story? We always hear it as a startup. It's like it's not about the feature or the moment or what version you are, it's the story you're telling. The version was the easiest way to tell the story 10 years ago. Today the story's about, "Oh, we're launching this new capability, or this new feature, or this new thing." That's the story now.

Paul:      I think it's very easy for companies like Apple and I see AWS doing this as well, that they just have this event that everybody pays attention to. Everybody listens to. They get to announce, in the list of features, but they ... I remember I was on Monster. Some changes to code deploy in the last reinvent. I don't know if people really care that much about the new features that has gone into code deploy, but it got a mention because it got packaged in with all this, all the other 50 other changes that happened to AWS. All of the press and everyone was paying attention to it that week.

Kevin:    Yeah, I think they do a great job of focusing their moments and having a train of moments. Say, "Hey, this is going to be train week." They get people to come show up. They've got a writer that's assigned to sit in every session and write about it, they're going to write about it. There's nothing else they're going to do all day. I think that they're able to create that.

Paul :     You almost have to justify the fact that you've sat in this session for the last hour. You have to write something, even if it's the worst thing ever.

Edith:     Yeah, it goes back to a lot of startups get paralyzed by fear. They're like, "What if we release a feature and TechCrunch writes about it." I'm like, "TechCrunch is not going to write about your feature."

Kevin:    Right, right. Generally speaking, right? There's just too many other things to write about. They're more interested in writing about the startup you've never heard of that got 5 million bucks. That's more interesting than your feature. They've already wrote about you and people roughly know what you do. You're not completely changing the world.

Edith:     On a detour from press, back to something interesting you said ...

Kevin:    Sure.

Edith:     You told me that your app was loved by users and by IT. In this world of rapid builds, how did you also win the love of IT?

Kevin:    Yeah, so our view in coming from the enterprise world is that you don't get to choose what software you use at work. We felt that that was kind of a big sea of change that's going to come over the next couple of decades. That people, especially with mobile, are getting to choose what apps they run on their phone and using them for work, whether IT has sanctioned them or not. You look at the drop boxes of the world, obviously ...

Paul :     Consumerization to the enterprise.

Kevin:    Consumerization, right? As you do that, you say, "Okay, well let's go build things that people love." I think, again, Dropbox is a great example of building something that people love, but they've had trouble convincing IT that it's the right solution, where box, I think, has done a better job of that because box went down a much more IT checklist. When I look at it, there's a security and IT checklist that's required to get to the IT person. There's no checklist, or easy way to get to users to love you. We spent the better first year, first year and a half, focusing on getting users to love what we built and iterating like crazy and moving continuously to get them there. Then the plan and kind of the thinking was is we had all these enterprise trials and one very large enterprise customer with Acompli, [before Microsoft acquired us](https://techcrunch.com/2014/12/01/microsoft-buys-email-app-acompli-for-200m-will-still-support-gmail-and-other-competitors/), was, "Hey, we're starting to work down the enterprise checklist."

They're going to tell you what they want. It's very clear. Like, "I need this SSL thing. I need this HIPAA thing. I need this Fed Ramp thing." They're going to tell you what those requirements are they're not fun, but they're very explicit of, in fact, your choice for them to negotiate, "Hey, can I do a smaller version of that?" I think the mix there is ... Once you get it in there, one of your sales angles is, "Hey, oh by the way, our users already using this for home or on their work accounts. They’re going to love it when you roll it out. It's by far the best thing you'll trial in kind of a bake off." That was our strategy to go to market, was to say, "Hey, let's make it so users love it. Spend a bunch of time on that. Use that for press and branding and then go to the IT folks and get them to buy it."

Edith:     Did they ever challenge you on the weekly build and how that would affect the stability?

Kevin:    They didn't. I think the challenge was more around security and data locality and things of that nature, was initially the ... Speed of change, didn't seem to be a huge deal. In mobile, in particular, like I said, the actual thing that the users were touching. People are so used to mobile apps updating that that's not a problem. I think it was more around data, data security and compliance around the data platform. We had strategies to deal with that, either keeping the data ... Accessing it through a secure line, or VPN or dedicated lines, or using dedicated tenants in AWS or Azure and those type of things. There was ways to kind of get around the compliance thing, but the key thing was really where the data was and data compliance and less about how quickly you were updating it.

Paul :     Awesome.

Edith:     Well thanks, Kevin, for coming in. Do you have any final thoughts around software development or continuous delivery?

Kevin:    I think it's cool. My thing is that, the faster you go, things break, but the right things break. I think when we got acquired by Microsoft, everybody's like, "Well no other team can ship every week. This is ..." Like, "Good. That was fun. That was fun as your little startup thing." I had this deck that I present where it's like, "Hey, we ship every week. We drink beer on Fridays and release on Mondays." They're like, "That's cool." It was like a novelty thing. They were like, "It'll just never work." Things that were like, "It's going to take a week to sign the bill because we have all these special requirements." Yes, but at the end of the day, we're going to push a button and it takes 22 seconds. That's what it used to before.

They're like, "No, no. We'll give you a special deal. It'll be like one day." We're like, "No, that's not possible. We need 22 seconds." We finally got it to work, but those kind of things, we had to break these internal processes and reviews. A lot of times it wasn't just a process but a team involved, to kind of help. That you can't have humans involved in some of these processes. A lot of the continuous thing is how do you automate and say, "Look, we'll do everything you're asking us to do, but just let us codify it, so that we can push the button and it does it. We'll trust that we're doing what you asked. That's the way we kind of got back to that high speed delivery. We're shipping 7 days in a very, very large company.

Edith:     Wow. I'd love to hear a little bit more about the tools that make all this happen.

Kevin:    Yeah, so there's all kinds of craziness in there. A lot of the tools that were involved were tools that most of us know today. It's Perl Scripts and Shell Scripting and Power Shell and .NET. It's just code. What does it take to sign an Apple build? You have to run the Apple's code signing tools and have to have the CERT and you have to have access to it. A lot of it was network VPNs to be able to have the right access to the CERTs, on the right boxes when you're making that. You used to have to use a smart card. We need a two-factor auth to sign the bill. You have to literally stick your smart card in my Windows laptop, to get the thing to get the CERT to sign the Android build. Those kind of things, we said, "Look, there's got to be a way to automate this. How do we go get two developers? We're going to do two factors. It's going to be and Paul and we're going to both say the build shipped and it's been reviewed. Then the automated process kicked off." Those kind of things, we just had to kind of re-envision. The beauty of setting like, "No, no. The goal is 7 days. We're going to ship every 7 days."

Just finding all the thing that that broke and going after them and just breaking them. Saying, "Nope, we can't do that. We can't do that. We need this access. We don't need that access." This step was like, "Oh, we need to review like political correctness and make sure that there's no offensive words, because we ship to so many different countries. How do we do that?" Well, there's tools for that and that requires somebody to get to this team and waiting. It's like, "No, no. At the end of the day it's going to be a code and run. How do we just ship that over there and automate it?" It ends up being an automation thing. It's just much like DevOpss today. There's teams all around the world with one or two people running thousands and thousands of servers with automation. If you kind of box the requirements into ... It has to go quickly and it has to just work, you have to just kind of write the code to close that gap. That's kind of what we did.

Paul :     When you're making that transition, I guess when you went in, you were shipping once a week.

Kevin:    Yup.

Paul :     Did you just refuse to break that once a week thing, or did you submit to their thing and then try to get it back to once a week?

Kevin:    We refused. When we first got acquired, we were still shipping as Acompli, under our own rules. We kept shipping. In parallel, we knew we were making the switch to re-brand as Outlook. As we started to re-brand, it took us about 6 weeks to go from re-branding to get to Outlook to ship. We knew that as that was going ... It's taking us 6 weeks. We're like, "Well, where's the CERT at? How do you reign in this? What font should you use? Where's the logo file?" A lot of things were one time things and those did take a while. I think the first couple weeks, we were probably shipping more like every 10 days. It was a little longer. There was a lot of manual elbow grease and escalation emails and phone calls and things that were just kind of more elbow grease than required to get us through the process. Where, we got it to a point now where it's like ... It wasn't fun developing the first ...

Paul :     Right, right, right. Did you have any stuff where, on your end, it was automation, but the API that you were hitting was a manual process?

Kevin:    Multiple. Yeah. Just send us an email and we'll sign your build. We're like, "No, no. We need ... Well, what are you going to do?" It was literally kind of interrogation, like, "Okay, when I send you an email and I ask for this request, or I fill out this form, what actually happens?" You had to sit there and pull on the string and say, "Okay." Then you copy it to this. Then, okay, so you have a password for this thing. How does this thing work? Okay, great. Then you're going to copy it to here. Say, "Okay, great." It ends up needing to go into this directory that only you have access to. Okay, we need access to that directory and we'll copy it there. Okay, great. Then the tool automatically picks it up and signs it. Oh, okay, perfect. A lot of it was figuring out the human mechanics of it, for sure. Then figuring out where the code is that we can go write it.

Edith:     So, Kevin, you felt so strongly that the 7 days versus 10 was worth it.

Kevin:    For sure. No, it was incredibly valuable to our getting to where we were at Acompli. We felt that if we had any chance of hitting the goals that we had set for ourselves and that the board had set for us when they acquired the company, in terms of growth and, we had to get to 7 days and basically iterate as quickly. Otherwise, the targets we set were going to take us 3 or 4 times longer because if you ... For every time you lengthen the development cycle, I'm a pretty firm believer now, that it takes you that much longer to actually get your results. The whole game is how many shots do you have on the goal. If you can do 50 a year, you're a lot better off than the team that can only do 20. I think that was the fundamental thing, is that we can 50 changes a year. The size of the change is not as important as how many you can make and how quickly you can iterate on that.

Edith:     Well, great. We really enjoyed you sharing your stories.

Paul :     Yeah, that was great.

Kevin:    Cool. Thanks for inviting me.

Paul :     Thanks for listening to this episode of, "To Be Continuous," brought you by Heavybit and hosted by me, Paul Biggar, of CircleCI, and Edith Harbaugh of LaunchDarkly.

Edith:     To learn more about Heavybit, visit Heavybit.com. While you're there, check out their library, home to great educational talks from other developer company founders and industry leaders.


