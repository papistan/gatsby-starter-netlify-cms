---
author: andreaech
comments: false
date: 2015-09-10 01:06:50+00:00
layout: post
link: https://launchdarkly.com/blog/continuous-delivery-podcast-the-next-episode/
slug: continuous-delivery-podcast-the-next-episode
title: Continuous Delivery Podcast, The Next Episode
wordpress_id: 253
categories:
- To Be Continuous
tags:
- CircleCI
- code
- continuous delivery
- developers
- dogfooding
- Edith Harbaugh
- engineers
- feature flag
- Geckboard
- HeavyBit
- LaunchDarkly
- Paul Biggar
- product manager
- Slack
- Spotify
- Yammer
---

What's so great about continuous delivery?  Find out in Episode #2 of "To Be Continuous," a podcast brought to you by [HeavyBit](http://www.heavybit.com/) about continuous delivery and software development.   "To Be Continuous," is hosted by Edith Harbaugh, CEO and cofounder of [LaunchDarkly](https://launchdarkly.com/?utm_source=launchdarkly_blog&utm_medium=organic) and Paul Biggar, Founder of [CircleCI](https://circleci.com/).



TRANSCRIPT

Paul: Before continuous delivery, there's often this idea that when you ship the code, you ship the product. There are rules about how one has to dogfood one's own software.

Edith: The dirty secret of product management is there is no such thing as a professional product manager.

Paul: Mm-hmm. Right. Hi! I'm Paul Biggar, founder of CircleCI.

Edith: I'm Edith Harbaugh, CEO and co-founder at LaunchDarkly.

Paul: And you're listening to To Be Continuous, a podcast about continuous delivery and software development.

Edith: You can get in touch with us at anytime at our Twitter handle [@continuouscast](https://twitter.com/ContinuousCast?lang=en).

Paul: The show is brought to you by Heavybit. To learn more, visit [heavybit.com](http://heavybit.com)., and while you're there, check out their library, home to great educational talks from other developer company founders and industry leaders. In this week’s episode of To be Continuous, Edith asks me, what are my favorite things about continuous delivery?

Edith: So Paul, what's your favorite thing about continuous delivery?

Paul: So my role is partially product manager and partially engineer. And so, the two favorite things I have about continuous delivery, one is the product manager stuff which is you're able to ship a basically broken feature to one costumer, two costumers or whatever, and do your product validation and get validation early rather than after six weeks of building the perfect feature, you get the validation after three errors and you've got two half-written ones will work for one costumer.

The other side of it from -- as an engineer, is being able to roll out features without having to calculate every single edge case and every single costumer possibility and roll that out to a very small number of people and I guess, it's kind of validation as well but it's more technical validation rather than product validation. You're able to find out, operationally, does this piece of code work rather than having to do a roll back or be worried about, have I written enough tests? Have I got enough coverage, feature flags and slow roll outs and that are kind of my personal favorite part of continuous delivery.

Edith: Yet, it's super frustrating. I was talking to a friend who, they spent literally $3,000 in server costs testing out whether this feature would scale and then they shipped it to their customers. They found out that it didn't matter because nobody wanted to use it. So they spent literally $3,000 on Amazon web services that were just throw away.

Paul: And the largest cost that I think exists and people ignore this cost a little bit is the cost of engineers that are involved in shipping these things. So if you build a six-week feature that took one engineer six weeks, two engineers three weeks or however it splits out and you're paying an engineer, let's say in San Francisco, then you just spent $90,000 on that feature.

Edith: Oh, my gosh. And people don't think of it that way.

Paul: Right. It's the same as meetings. No one thinks that this meeting is costing us $15,000 an hour or $1,500 or whatever it is. People think like, "Oh, we need to get this done. We need to build this feature. It needs to be the right color blue. It needs to be right. It needs to be perfect," rather than, "The cost of this is astronomical. How can we make this cheaper? And how can we get more bang for our buck?"

Edith: Yeah. I mean, to go back to Lean is, how can we reduce waste? How can we cut all the fat out of this being built and make it more efficient? But a lot of the push-back I get around at continuous delivery and Lean is like, "Why can't you just build it right the first time?

Paul: I think there's a bunch of reasons you can't build it right the first time and the first of them is the real world is complicated and the real world has error conditions that you don't consider and it has -- I guess I'm talking from a technical perspective here, but basically, if you try to push any feature, you will immediately find that it doesn't work for a bunch of costumers for technical reasons. There’s exceptions that you weren't expecting, clearly that's why they're called exceptions. There's a bunch of bugs that are going out. There’s edge cases that you didn't consider and then from the product side of things, there's exactly the same things. There's edge cases you didn't consider. There's customers who think about the product in a different way than you think about the product. So “Can I build it right the first time,” I think is just -- it's a sort of a naive position. It isn't possible to build it right the first time no matter how prescient you are, no matter how good of a product visionary you are.

Edith: And what I found myself is that sometimes I would overbuild a feature and miss the mark. I thought people cared a lot more about something that it turned out they cared very a little about. And back to what you said, that's extremely expensive not just in the raw cost of the engineer but in the opportunity cost of what you could have been building instead.

Paul: Right. Before continuous delivery, there was often this idea that when you ship the code, you ship the product. And so, people would have a marketing launch or -- well, a launch, but a launch is a marketing launch, that they would aim to coincide it getting the code into the code base possibly for the first time before that launch and this is always the most disastrous thing I've ever seen.

Edith: I have my own stories but let me hear yours.

Paul: I don't particularly have any great stories, just that I've seen it. I've seen people's launches that are like, "Oh, this doesn't work," or people talking about their death marches and like, "We're launching this in the morning. I need to get it finished tonight. It should have been finished last week. Or it should have been finished last month. And in like five costumers' hands for the previous month, you should have validated. Why you're trying to launch a thing that isn't validated?"

Edith: Yeah. There’s this whole school of software of the death march and then tell the product managers and the marketing engineers kind of go in this death spiral of artificial deadlines and must-ships.

Paul: Right. The two work -- I was going to say well -- the two work horribly together like the artificial deadlines, in particular, cause -- is it artificial deadlines? It's more, I think, the--

Edith: I'll give you an example. I was working at an enterprise software company and we had this absolute must-ship of October 31st. All summer, it seemed a long way away until suddenly, it didn't. It's August, September, and we're like, "Damn. It's on top of us," and really, what it was was, nobody's really waiting for October 31st. It was just that marketing didn't want it to slip into November and then December and then have everybody be away. And we just shipped this completely half-baked thing which people cannot migrate up to because that was literally the thing we threw away. It's like, "Okay. We don't have time to build everything.” So we launched this thing that none of our base could use because there's no -- it wasn't like that we have a half-baked, half-migration. It was literally we said, "Fuck them. They can't migrate.” I was in that meeting.

Paul: Right. This is awful.

Edith: And nearly killed the company because we just burned our entire base.

Paul: So how often were your releases end up?

Edith: Oh, in that time, we were considered fast because it was once a year.

Paul: So clearly, if you were doing daily releases or weekly releases, they wouldn't be that any of these problems at all. You could have released the thing long before October 31st. You could have been behind a feature flag in June. There could have been ten costumers in July. You could have had all ten costumers saying, "Well, we're not going to use this. There's no migration path," and then realize that the migration path was the most important thing.

Edith: To what you said of the code as the product. We said it wasn't. I think that's why I'm such a big fan of continuous delivery because I think it forces you to be more realistic. There's no mythical future out there. The future is now. The future is the people using your product.

Paul: I've seen this idea when I worked for a telecoms company that will remain nameless, that if you hit the deadline, then the fact that what you were shipping was a really bad idea wouldn't be your responsibility.

Edith: Yeah. Garbage in, garbage out.

Paul: Something on those lines, yeah. So that marketing gives you an unreasonable deadline. Product management doesn't push it up in front. The engineers are writing code according to someone else's schedule. And if you write the code that goes there, then it's not your fault that it's going to be a disaster even though you see it be a disaster. And maybe, the people on the ground can see it being a disaster. The people at higher levels are sort of like, "I hope this isn't a disaster and everyone thinks this is going to be awesome."

Edith: The healthcare.gov story.

Paul: Exactly. Healthcare.gov is a prime example of this. And if there had just been a sort of a continuous delivery thing, let's get this at its front, then what it builds is that the people on the ground end up with the same -- not necessarily on the same page but the same incentives as the people in -- the marketers, the project managers.

Edith: Yeah. I visited a costumer last week and they’d gotten LaunchDarkly and it was kind of funny and a little sad when they said, what they're most excited about using feature flags was just to show features to their executives.

Paul: Wow. So they would build things that the executives ask for only for the executives?

Edith: Well, no. Right now the executives have early -- look at features, over the time they saw them if they were bad. There was just all this--

Paul: That doesn’t sound so bad.

Edith: No. It's exciting.

Paul: Yeah. That sounds good.

Edith: Yeah, because they wanted to get -- because right now, the executives were at the very end of this long release process and they didn't have any way to give them an interim peek.

Paul: There's a big difficulty in terms of executives and management being involved in the product management process.

Edith: Yeah. I think it's fascinating that you called yourself a product manager.

Paul: Why was that?

Edith: I mean, you're also a founder and CEO...

Paul: Sure, sure. I've engineered things so that my role is far more product than -- I don't know -- finance and management and that sort of thing. So the primary thing that I worry about now is, is the product good enough? How can we serve our customers’ use cases? And it ends up being a lot more like product manager than -- Now, that is to say we have professional product manager so actually know what they're doing who help with this.

Edith: The dirty secret of product management is there is no such thing as a professional product manager.

Paul: Yeah, fair. But there's definitely people who have done it before and know how to validate and prioritize and make sure that releases don't slip and all that sort of thing. But the idea that an executive or that a PM would only see it towards the end is a really bad idea and the idea that they're going to completely spec it out upfront is also a really bad idea. The secret of good product which most really good project managers know and it seems that very few executives know and also very few engineers know is that it's successfully balancing the company goals with the actual dirty details of the implementation.

So there're engineers who will tell you that they're in the best position to build a product because they are actually in the code. They are in the weeds. They see how things can actually work. And there're executives who will tell you that engineers have no idea how to build the product because they don't understand that the business case behind the product. And the truth is somewhere in the middle. The truth is that the business case is -- it's not everything but it's a lot. If you try to formulate the business case with that understanding, the real product metrics and how people are using the product and how the code is architected and orchestrated then you can't possibly specify the product with that data.

Edith: Yeah. And I'll also add that as an engineer, you could fall in love with your own product. We talked about this before that you always know your product the best and you're always thinking of some way to make this little tiny bit better when it could be something that your actual users don't care about.

Paul: Right. There's a bunch of features in Circle that were basically implemented the wrong way and that was because -- largely because I fell in love with a particular concept or an abstraction or way of doing things. It turned out to be just confusing to customers.

Edith: And I think the only fix for this is, as you said, to share or to talk to actual customers. I'll give an example. I talked to a LaunchDarkly customer and I thought they were going to ask for a lot of stuff but what they actually really wanted was a Slack bot integration and it wouldn't have occurred to us at all because we use HipChat but they wanted basically a chat bot so they could roll features out to different users right inside of Slack.

Paul: So, one, that's an excellent idea. Our feature flags are all keyed from Slack and the -- I think that there's a real danger to dogfooding. If you dogfood really, really well and you get a lot of insight from your product that way, then you don't develop other techniques for getting feedback from your products and getting back from your customers.



Edith: You become convinced that you are the customer.

Paul: Right. And you're never the customer.

Edith: You're a customer.

Paul: Right.

Edith: So back to your product manager, you're a customer with very specific needs.

Paul: And often, you are the most knowledgeable customer or, I mean, you are always the most knowledgeable. We have probably used features that none of our customers even know exist. There's features that we built for other customers to use but for ourselves, first behind the feature flag, that actually never got launched and if they become part of our work flow, and customers are saying, "Oh, there's some kind of thing. How do you solve this?" "How is that a problem? We don't experience this problem. Oh, yeah we never launched that feature."

Edith: Well, Paul, I'm going to devil's advocate you a little bit about some of the pushback I get at continuous delivery because when you're talking about the customer right now, the classic one is Slack which came out of [Stewart Butterfield](https://twitter.com/stewart?lang=en). He used chat and wanted to build a better one.

Paul: I missed the -- what was the question there?

Edith: So that's held up as an excellent product and it was all dogfooding.

Paul: Yes. So I think these are different stages of the product. There's the -- so here, I’ll give you an example. Slack has excellent onboarding. The Slack team onboarded once at most and so, in order for that to have become the amazing product it is, someone, somewhere has a job of making sure that onboarding is awesome and they are not dogfooding onboarding everyday. The whole team is not dogfooding onboarding everyday.

Edith: That would be kind of horrific if every day they have to come in and reinstall.

Paul: Exactly. And Slack has tons and tons of integrations and you add rooms and the experience to run all these things is really, really good but no doubt, Slack is only using one video integration. They're only using -- they're not using Google Docs and Dropbox or -- maybe that's a bad example there. They're not using the Microsoft tools and the Google tools or whatever. They're not using multiple [continuous integration](https://circleci.com/continuous-integration/) services. And so, how do they know that the integrations with those services are amazing? They must have a process that lives outside of their own dogfooding.

Edith: Yeah. I totally agree. I think if you get too far from dogfooding, you end up with a product that nobody, not even the people who built it, love and that's very dangerous. The joke is like, nobody uses the Microsoft Zune. I remember my friend -- my friend who worked at Nokia who carried around an iPhone because he didn't want to use the Nokia phones.

Paul: One of the reasons that people start to use products -- this happened a lot when I was in Mozilla. People didn't want to use Chrome at Mozilla because, well, they felt that Chrome solved problems for them. In particular, memory usage was a particular problem and for people who used a large amount of tabs, Chrome was just a better solution at that time. But there was a loyalty aspect to it. You didn't want to use Chrome because you want to be loyal to your company or to your team or to your -- the mission that you believed in. And as a result, people don't experience other products and they don't see how much better the world could be and they just kind of get stuck into the, "We're using this and we're putting up with the shit in this because we have to."

Edith: [Stockholm Syndrome](https://en.wikipedia.org/wiki/Stockholm_syndrome).

Paul: It's a little bit Stockholm Syndrome, definitely. Every time you tell your customer a hack, that's a small amount of Stockholm Syndrome. You're saying there's a way of doing this and the way of doing this is, well, it's a little bit hacky.

Edith: Which is not always bad because sometimes then a customer feels like they have this insider track like customers like feeling like you're giving them something special.

Paul: There are two sides to that. So at the start, yes, they love the specialness. I talked about this in the previous week where you want your customer support team to be able to say, "Oh, thanks for the report. We just fixed that.” Or "Thanks for highlighting this used case. We just built it in the last ten minutes just for you.” And that's great until you get about six months into using the feature and they're still using the hack and they're worried that it's going to go away. And we had this with a customer recently. We built something for them -- a special way to control notifications. And we didn't want to build it into the UI because we're going to change how the UI work and so we put it somewhere that we didn't document and that was in an experimental section of their configuration. And then, they're like, "Okay, this is in the experimental section. We're worried that it's going to go away. We're a big customer. How do we make sure that this doesn't go away on us?"

Edith: Yeah. That's the way that a lot of people are using feature flags actually.

Paul: Go on.

Edith: So originally, we thought people would use feature flags just for rolling out a feature and what you said in the beginning, for rolling it out to different users, verifying that things didn't break, things didn't implode, the dragons didn't come down and set fire to the universe. What we found is that people were also using feature flags for really long term controls and it was precisely that use case.   It’s like you have this customer who wants access to a feature and you want a way to know that these five or six costumers have access. And that's something that you want to know so that when you're doing new updates, you don't actually overwrite that but it's not something that you want to -- it’s not something you want at code level. It's something you want a higher level.

Paul: One of the dirty secrets of enterprise software is that you have dirty hacks for customers.

Edith: Oh, my gosh. Everywhere. Everywhere.

Paul: So many people have told me that the "if" statements that they have, if customers equals Google or whoever, then we're going to do it this way. And feature flags provide a nice little abstraction above that.

Edith: And the abstraction is — and this is what our costumers is using it for is that then at least everybody else knows, then there's this thing in there.

Paul: So then, you also get metrics around abstractions to that so when you decide to sunset something, you should be sunsetting these features or finding better ways of doing it or something that actually solve their use case. You should be moving them away from that abstraction and having a counter, a graph, a recency indicator of when these features are used. It's essential to actually getting those features sunsetted.

Edith: Yeah, or even out on the late. What would happen in enterprise software is you'd have -- one config files somewhere that one person knew about and that person would leave.

Paul: Oh, wow.

Edith: And then, all of a sudden, everything would break and nobody even knew why, or like stuff would be always implemented at the wrong layer no matter where it's implemented, it's always at the wrong layer. So I'm going to play devil's advocate again. The pushback I get is we shouldn't ship buggy software.

Paul: I would argue with that shipping. All software is buggy. Every piece of software that you ship is buggy. You just don't know what the bugs are yet.

Edith: So we put people to the moon. There are no bugs on that.

Paul: I mean, if you want to spend ten years or an entire decade shipping your feature, you can ship it without bugs. If you're in a thing that can tolerate, well -- let me put it this way. There was the Challenger disaster. There's the multiple car recalls that are happening at the moment. So even people who have incredibly long cycles with strong validations and static analysis and all these things, even they can't ship non-buggy software. Nobody can ship non-buggy software. The only reliable way of getting software that is in any way, reliable, is to ship an early version which is known buggy and if you don't ship an early version that's known buggy, you're going to ship a late version that's unknown buggy. And when you ship that, you find what are the actual things that are happening in practice.

So I shipped a feature last week. It was a long one feature. It took a lot of building and we shipped it behind a feature flag and all the tests passed and everything and I just turned it on for one customer, which is us on one branch and there was an immediate obvious bug. This is great because I didn't ship it to 10,000 customers to discover an immediate obvious bug. I shipped it to one customer and that customer is me and I can go fix the bug now before we ship it to any more customers.

Edith: Yeah. I mean, we did the same at LaunchDarkly. We were shipping something new and we do absolutely everything with feature flags because we have to. And we found this--

Paul: There are rules about how one has to dogfood one's own software.

Edith: Well, there was a rule and then we got really busy and we got very sloppy and we stopped doing it. And then, we tried to do a big release and it wasn't a disaster--

Paul: Wow.

Edith: What?

Paul: I find it hilarious when continuous delivery companies do big releases. I mean, everyone does it at some point but it's still funny.

Edith: Well, for us, it wasn't huge. I think it was like two weeks of accumulated stuff, which for us was quite big and then--

Paul: You don't deliver every day?

Edith: It depends on what we're working on. So we do mini pushes but most stuff is behind the feature flag.

Paul: Of course, yeah.

Edith: So the two-week release was kind of our come to Jesus moment of like, "Wow! That was a big pain.” Because we hadn’t feature flagged stuff adequately. We had to spend a lot more time in QA which was -- it was stressful.

Paul: There's a bunch of features that -- any time that there was real stress in the product team was when someone have built a feature without feature flags and someone said, "I'm not sure about this. Can we maybe test it? Can we push it out to only select customers?" And these are things that were either big product changes so people have been working on them for weeks and we're very happy with them and really wanted to get out there. And so it led to a lot of frustration, led to just people being generally unhappy and harsh words being said and--

Edith: No.

Paul: I mean, harsh for -- still professional. Harsh as in like, I really want to ship this today. "I really feel that you shouldn’t ship this today.” That level of harsh.

Edith: If you've ever been in an enterprise software, there are many harsh words said and usually they're along the lines like, "This customer promised us $750,000 this quarter. Where the fuck is my release?"

Paul: Right. So there weren't quite those harsh words because there wasn't any customer who promises $750,000. If there had been, then I'm sure, words could have been harsher.

Edith: I like what you say. When you descale the stakes, it gets a little bit more civilized.

Paul: Right. Developers get frustrated when they can't ship their stuff. The only thing about -- causes people to be really unhappy is the idea that they're blocked behind a thing and they get frustrated.

Edith: Yeah. I've met some guys from England. They're from Geckoboard. They're here for a Lean meet up. And they took it to extremes. They said they broke out everything down into day-long and no longer.

Paul: So they have to ship at the end of the day?

Edith: I don't it was at the end of the day but it couldn’t be more than a day's worth of work. And they said this was very good for morale because everybody always saw their stuff continually getting out.

Paul: And they ship behind the feature flags?

Edith: Yeah. They have built their own system.

Paul: I guess they must just have gotten good at building a day's unit of work.

Edith: That's what they said. They said that they were very much into kanban and they just tried really hard to scoop it that way.

Paul: Got you. So at the start, it was difficult and they just have gotten into the groove and--

Edith: Well, for employee morale for the reasons you just gave. It's funny because they were so bought into it. If I told them about the old days where releases took years. I think their heads would have just popped off in a very British way.

Paul: I like this idea of one day. I was reading about -- this was Spotify. Spotify? No, actually this wasn't Spotify. Whoever it was, they did -- every project was a two to ten person team and two to ten weeks. Those were the rules of how things got shipped.

Edith: Yeah, Yammer did the same in the beginning.

Paul: That was Yammer.

Edith: Oh, it was?

Paul: Yeah.

Edith: One of the project managers, Ron, he did a guest post on our blog about how methodical they are, just everything must fit in -- must fit, must be data-driven, must be hypothesized.

Paul: Oh, the hypothesis. This is an interesting thing. So every project would have a hypothesis for what the data was going to show?

Edith: So you can read more on my blog. He says it better than me but he talked about -- I was trying to get people to upload more picture to Yammer and the hypothesis was that, if there were more pictures on Yammer, there would be more engagement. So they did a lot of improvements on their photo uploader to make it a lot easier to upload photos and they let the experiment run and no more photos were uploaded. So they were going to not ship the new feature just because it didn't improve days engagement but they finally did ship it just because it got rid of some technical debt. But literally, if something doesn't move their engagement, they don't ship, like no matter what their feature is, if it doesn't improve engagement...

Paul: It's interesting for consumer companies that have to focus on engagement like that because I think that there's a lot of B to B companies who would very sternly say, engagement isn’t as important as costumer experience or -- something that's qualitative rather than quantitative.

Edith: Yeah, they're very strict and they're B to B, Yammer’s kind of… Yeah.

Paul: It's definitely on the line. Its mass B to B, has more B to C characteristics, I think, than B to B.

Edith: Yeah, but it was interesting because they are so very strict about it and they actually have the analytic groups is entirely separate department from product and engineering to keep them honest.

Paul: Oh, interesting. It's very easy to skip the rule when -- we know this one is going to work. Let's just ship this and we don't need test it. We don't need to validate it.

Edith: Or we shipped it then we tested it and it didn't improve or maybe actually made stuff a little bit worse but we have this sunk cost of we already built it so it degraded engagement by 5% but what's 5%?

Paul: Right. So I think that's definitely my favorite things about continuous delivery -- the product validation and the technical validation.

Edith: Yeah, just doing it quicker.

Paul: Thanks for listening to this episode of To Be Continuous brought to you by Heavybit and hosted by me, Paul Biggar of CircleCI, and Edith Harbaugh of LaunchDarkly.

Edith: To learn more about Heavybit, visit [heavybit.com](http://heavybit.com). While you're there, check out their library, home to great educational talks from other development company founders and industry leaders.
