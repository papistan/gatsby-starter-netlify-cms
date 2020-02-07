---
author: andreaech
comments: false
date: 2015-08-25 14:42:26+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-a-new-podcast-about-continuous-delivery/
slug: to-be-continuous-a-new-podcast-about-continuous-delivery
title: A new podcast about Continuous Delivery
wordpress_id: 241
categories:
- To Be Continuous
tags:
- Agile
- Apple
- CircleCI
- continuous delivery
- developer
- dogfooding
- Edith Harbaugh
- feature flag
- Firefox
- Gregg Brockway
- HeavyBit
- Heroku
- Joel Spolsky
- Marty Cagan
- Paul Biggar
- SaaS
- static analysis
- technology
- TripIt
---

We're pleased to announce “To Be Continuous”, a new podcast about continuous delivery and software development. Edith Harbaugh , CEO and cofounder of Launch Darkly teams up with Paul Biggar, Founder of Circle CI to give a frank and humorous take on the subject.

In this first episode, Edith and John talk about why people are doing continuous delivery as well as its benefits and barriers. Also, why you should never ask to see Paul’s PhD thesis.

The show is brought to you by Heavybit. To learn more, visit [heavybit.com](http://heavybit.com) and while you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.



TRANSCRIPTION

Paul: Okay, Edith. What’s your favorite thing about continuous delivery?

Edith: Just making people happier, quicker.

Paul: That is not where I was expecting to go with that.

Edith: Well, I think it comes back to -- I’m an engineer and part of an engineer is you want to see stuff out there. You want to see people using your products. You want to see them happy. You want to hear if they’re not happy. You want to fix bugs. You want to ship features.

Paul: So one of the really nice, kind of, happiness things that we saw was support tickets. So people would come in and they have a support request and we’d be able to ship a feature change or whatever it was to that, that went out like, you know, 20 minutes later.

Edith: Yeah.

Paul: And you’d be able to say to them, oh, sorry about that, it should be fixed now.

Edith: Yeah. I mean we do the same. We’re very young company and if somebody complains, “Oh, we’ll fix that right away.”

Paul: And nothing diffuses a Twitter rant like, “It should be fixed now”.

Edith: Yeah. I think, part of it though is a consequence of us, quite frankly, being very small and not having as many customers yet. Like when I was at TripIt, we had 10 million users.

Paul: Right. I think that’s probably a different kind of situation.

Edith: Yeah.

Paul: I presumed they did continuous delivery.

Edith: You know we did a weekly release and then we would do patches.

Paul: And this is mobile software.

Edith: This is mobile, yes. We had a whole different release streamed for mobile, mainly around the Apple store.

Paul: Right, right, right. Yeah, the great destructor of continuous delivery.

Edith: Yeah. I’d say the number. think there’s all this urge and want to be more reactive in mobile and there is such a huge “thou shall not pass” sign that Cupertino push up which is basically like your app might be great, but it’s not happening.

Paul: So I wrote this -- I wrote this blog post, I think that was on Pando Daily or something that talks about how Apple was responsible for this glitch, this kindle glitch that went out. So, Amazon released a new version of kindle that, I think, deleted all of your e-books or something like that and they weren’t able to turn it around super quick. They got a special exemption they got turned around within a day. In the end, it was fine but really the problem and the reason that that was caused was the lack of a continuous delivery process meant that they couldn’t just ship the new code and have it turned off and then gradually turn it on and you know, that sort of thing that we do on the web but they weren’t able to do on mobile.

Edith: Yeah. And I think it’s funny because mobile has its reputation of being so much faster and more modern, but in terms of delivery to end-users, it’s five to ten years behind and it’s all Apple.

Paul: Yeah. It’s amateur.

Edith: Yeah. It’s all Apple. Like, we saw that so many times a trip that we will have a fatal bug out in the field, and we would have a patch ready, and Apple would say, “Well, you know, we got to review this.”

Paul: And so that’s the thing like…

Edith: And then we were a good customer. We were the number one travel app.

Paul: Developers can write a fix in five to ten minutes once they know the thing. I mean it depends on the fix but yeah, very often, five or ten minutes. And anything that like -- anytime that you add on for that is the thing where more customers notice, more customers are affected, more customers’ workflows are disrupted and it’s just pure overhead. Like, Apple is just introducing overhead but also not having a continuous delivery process in your organization, releasing quarterly, having someone who needs to click the button, something on these lines are all more things that can just add barriers like fixing customer things.

Edith: Yeah. So, this goes back to something we’re talking about before about how you said everybody wants to ship stuff faster. I said, no there are a lot of people whose--

Paul: Whose job is shipping makes slower?

Edith: Yeah. So I mean, Apple does not really care if you ship stuff faster. Like Apple gets dinged if stuff is --

Paul: Is broken or —

Edith: Or bad. At least that’s their viewpoint. But then they put up all these processes, where you like, I have a broken build just let me patch it.

Paul: So, this is one of the great, sort of, falsehoods of software delivery: that trying to make sure that it’s perfect is better.

Because, actually what happens is, it’s trying to make sure it’s perfect means not got shipped. And actually, shipping things and and iterating on it gets better or it’s what makes better. And startups understand this, the whole Lean movement was built around beside this idea, Agile is built around this idea. And everyone is pretending to be Lean, everyone’s pretending to be Agile.

Edith: Well, it’s kind of like you asked me whether you are Agile, what am I going to say, no?

Paul: Yeah, right. I tend to ask you for the Agile with a capital A. And that implies they follow the full Agile process. And nobody, nobody follows the full Agile process.

Edith: Yeah. I think so go back on one of the major tenants of Agile which is people over process. But I think, one of the whole bags of effective continuous delivery is there are people whose bias is to have stuff be perfect as you said.

Paul: Right, right. And they like processes that enforce, that enforce that. So, I mean, Apple obviously likes a process that enforce that. Well like a human that makes sure that there’s no nudity or whatever is against the roles on the app store. But I think they also have like business reasons for not doing it. So what everyone would like to do is just ship a web view in a native container and then just like update it off the web. And Apple doesn’t let you do that because they’re trying to make you build native apps and they’re trying to make it all in a thing that they control, where they control the ecosystem, where you can’t just easily take an app and move off to Android or whoever else can be in the ecosystem if Apple allowed that.

So they have like a very strong business reason to keep people from having a really good continuous delivery workflow.

Edith: Yeah, it all comes back to money. They want to monetize off the app store.

Paul: Apple wants money.

Edith: No, really? They didn’t give you that computer for free? But if everything is off web views, they can’t enforce their 30% cut.

Paul: Right. They can’t control the ecosystem. We may as well ship it to Android then.

Edith: Well not even that, it’s like if you sell something through in app, they get 30% right off the bat.

Paul:   Okay, right, right and they can’t enforce that.

Edith: If you sell it via a web view but it’s just, by say, you have a web view and you’re checking out, there’s no way for them to take 30% cut.

Paul: It’s funny how many different sort of -- I tend to look at the world through incentives, it tends to be one of the lenses through I look to the world. And whatever incentive, you get someone with -- there tends to be a lot of incentives not to do continuous delivery, even though like if you  But there’re a couple of anti-patterns that I see and one of them is fear. People are just afraid that things will break. Then the other one, I guess this is kind of fear as well but there’s this anti-pattern in product management of like why I wasn’t shown this or why didn’t someone check with me. You also see this in ranters on Twitter.

If you have continuous delivery, things going out all the time, then there isn’t always necessarily a human who can validate that like, oh we’re doing it right or at least if your process isn’t set up in such a way to allow this to happen.

Edith: I completely agree. I think a lot of continuous delivery is accepting kind of decentralized authority.

Paul: That is a really interesting concept.

Edith: You know, so the whole idea of a release train was a monolith with these many layers of approval. Everyone has to be checked as --

Paul: There’s a human, there’s a release manager who’s validating that’s good enough at each time.

Edith: And even beyond that, then the marketing reviews it then you have legal and it’s very hierarchal whereas continuous delivery is anybody could push it at any time. That’s very decentralized.

Paul: So continuous delivery is anyone can push anytime but it’s not necessarily everyone releases every single push or at any particular time. There’s kind of two models that -- there’s kind of two related words that people get confused with this, the continuous deployment model of every piece of code that you push is shipped and then it’s continuous delivery model of every piece of code that you push is possible to be shipped.

Edith: Yeah, I think it’s shipped versus shippable.

Paul: Yes, yes. I think web versus mobile is a nice example of this, like certainly most of our customers every version of their IOS app that they build on CircleCI is shippable, there’s a binary that you can download to your phone, that you can upload to your over-the-air updater or whatever it is that is actually shippable. And Apple is putting that barrier in you to prevent it being shipped.

Edith: That goes back to the decentralized versus hierarchy.

Paul: Oh yeah, if anyone if hierarchical, it’s Apple.

Edith: Then it goes back to who does this ultimately serve because then you have all these people with broken phones out in the real world.

Paul: Right, right. We probably shouldn’t keep going on about Apple but I think it’s an interesting model that they tend not to get things too broken. It allows you to make sure that people aren’t really violating the rules too much. So, you can’t sneak in viruses.

Edith: Yup.

Paul: There can still be viruses but they’re harder to sneak in which you would get with continuous delivery or in particular web view model of continuous delivery. You can’t sneak in things that against the rules, gambling and porn and whatever else. Apple doesn’t want in its ecosystem. And the expense of that is innovation. I’m doing air quotes for people at home around innovation. But you just can’t ship things as fast. People who work in your ecosystem can’t ship things as fast and you’ll find that a lot of startups who are trying to do something super interesting that doesn’t really require being on a mobile will do it on web because they can just ship way, way faster.

Edith: Yeah. It’s basically to your point: perfection is at the cost of speed.  My old boss, Gregg Brockway, who was the Tripit co-founder, he said a perfect plan tomorrow is not as good as a good-enough plan today . He said that to me because I was -- I had built this new future. I didn’t feel it was good enough to ship and he gave me some really good advice. Which was let was let’s just ship it. If it’s broken, we’ll fix it.

Paul: I guess, yeah, obviously that relates that then as feature flags and to sort of points toward your company slightly. Edith, of course, the CEO of LaunchDarkly.

Edith: Thanks Paul. Paul is the CEO of CircleCI.

Paul: And feature flags as a service, but feature flags were, I think, really the innovation that made continuous delivery like properly possible  and the idea that you’re just going to ship code separate from shipping features.

Edith: Yeah, it goes back to shipped versus shippable. Like you had everything all bundled up and kind of ready to go either out in the field but hidden.

Paul: Right, right. There’s a bunch of features that we have that are maybe 80% shipped that we sent them out to customers and we determines that’s it just wasn’t good enough for some reason. Maybe there’s a software bug, maybe there’s an edge case that we haven’t considered, that actually comes up in production. But I don’t think that we could realistically do continuous delivery if we weren’t shipping things in their off stage.

Edith: That’s cool. Can you talk about an example of a feature like that?

Paul: So this thing that we’re rolling at the moment and it totally exists and like anyone, any customer could use it if only then knew about it.

Edith: It’s like the secret sauce at In’N’Out?

Paul: Exactly, exactly but I mean, when we’re not telling them about it, but it’s going to be the super awesome feature but it’s a big feature and the foundation is built. And the foundation is like part of every single build. And if you know the super-secret invocation, you can get it. And so we’re going to start by like rolling that out to customers who actually need it and we’re going to validate it against in the first five or ten customers and very standard like product management thing of like validating the business case, validating the customer case, make sure that the thing that we’re shipping is a thing that’s really valuable to our customers before we announce it, before we tell 100% of our customers.

So maybe 10%, 20% of our customers will have experience it before we announce it. And actually a whole lot of customers will experience it without knowing that they experience it and I think that’s kind of the ideal way of shipping things, validate the product first, validate the technology first, make sure that it all works and only ship it to customers once or only have like the marketing version of the launch long after the code is validated in production.

Edith: Yeah, I mean we did the same thing at Tripit. So one of the biggest features I ever worked on was scraping people’s inbox for emails. So Tripit basically, it takes emails, strips them of interesting things, and then gives you a beautiful itinerary. You used to have to forward stuff to plans at Tripit. What a lot of our customers were asking for was that we could just scan their email and get their emails out for them. Sound simple until you think about it. Well, actually, this is a pretty massive undertaking like you have to get the right emails, like people we found that would have like 10,000, 20,000 emails. You have to pick the right ones and only the right ones. So we dark launch this. Like we only did it to people who opted in. And they gave us really good feedback, you know, we made a lot of really simple mistakes at the beginning because there’s a ton of logic we would pick up like Turkish Airlines had like a travel to Istanbul and we thought that people were traveling to Istanbul. They make a trip and so we have to get smarter, smarter, smarter about our filtering and then we got to the point we’re like, “Okay, this is good enough that we can release it to entire in a million plus base.

Paul: So that there’s a bunch of validation techniques that -- did you know [Marty Cagan](https://twitter.com/cagan?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor)?

Edith: Yeah.

Paul: So it for the people at home. So for people at home, Marty Cagan is like this product guy who runs Silicon Valley Product Group. He’s well-known and in the Valley as like the product guy. And he runs a seminar and a bunch of Circle people went to the seminar. And he talks about product validation techniques. And the product validation techniques are basically the things that enable you to do continuous delivery really well. It’s two of my favorite ones and one of them is the button on the app that doesn’t actually do anything.

Edith: I love that because nobody ever pushes it, don’t build the darn thing.

Paul: Exactly, exactly. So in order to that, you really don’t want to show that button to everyone because what if everyone loves that button. You want to ship that blank button to a smaller number – to smaller number of people and then a small – larger number of people to make sure that the volume does not exceed. So if you show to a thousand people and a thousand people all click it, you don’t want 10 million customers who would really love that feature being, “I fooled you, feature doesn’t actually exist.”

Edith: Well, let’s say forwards, what usually happens is nobody clicks. Because I’ve run that experiment many times and nobody clicks it and then you just do stuff like you try different wording. “Let’s make that button bigger.” “Let’s make the button be the entire page.” All right, nobody cares. “Let’s make that button be a pop up that like – you know.” I’ve pushed hard on features that just turn out just to be dead ends, but it’s better to find it out early.

Paul: Yup, that’s one that works really well with continuous delivery and the other -- I like this in almost entirely for the name, the Wizard of Oz feature. So this is where you build a button or something like that and someone clicks. Let's say it’s your check your inbox for trip things. You the click the button and you get told, “We’ll get back to in 48 hours with this feature.” And then there's a human who’s like aggressively filtering -- I guess that they’re not going to be aggressively filtering through your inbox. But the maybe it doesn’t work in that case but someone is like checking it as used case. They're uploading the spreadsheet manually. They're entering the data, they’re validating it.

But it’s really not possible to launch that kind of feature its scale either because if 10 million people click it, you really don’t have ability to satisfy the volume of that could possibly be there but you’re almost certain isn’t there so you need to scale it up to the level that you can actually tolerate.

Edith: Yeah, and I think this ties back to Lean. I think people have a misconception of Lean that it means lazy or like just throwing shit at the wall. When Lean really just means that let’s not be wasteful.

Paul: Right.

Edith: Like let’s not build out this whole feature until we've established a need for it.

Paul: One of the core tenants of Perl, the language and Perl, the community is laziness and they mean it in the same way as Lean. Don’t build shit that you don’t want. What’s the other phrase that comes up from Agile: you ain’t gonna need it.

Edith: Yeah and I say this because it’s so painful like I’ve built features that nobody uses and it’s just sad.

Paul: Yeah. People get angry at the features. You’ve never experienced this? Like, there's a feature that nobody uses but that somehow is like deeply embedded in your code base and people want to rip it out all the time but they can't for whatever reason.

Edith: You mean engineers, internal engineers.

Paul: Engineers, yeah. Engineers want to rip out and maybe they can't rip it out because it’s a – because there're some important customers using it or because there wasn’t a new workflow for it or maybe just like there's political thing, you know. Someone worked hard on that and no one internally wants to say –

Edith: This is a loser.

Paul: No one uses that feature.

Edith: Yeah, I think it keep coming back to – I think software is really more about people than processes or tools.

Paul: Well, continuous delivery is about the process.

Edith: I think it’s about people buying into the process, that it’s better to have proof points. It’s better to admit that you can be wrong than put all your effort into trying to be perfect.

Paul: So one of the areas that people tend to come up with problems with continuous delivery is this idea that the code they’re going to ship is known or not known as in – you don’t need permission. You don’t to go through a product manager or whatever. It’s just whatever code get ship actually gets deployed out. So how do people deal with this kind of problem?

Edith: It goes back to decentralization. I think you have to have some, and I keep coming back to, people. You have to know and trust your engineer and know and trust that they’re doing the right thing. And I think this goes back then I'm not even going to touch this debate for right now like the whole offshore versus onshore.

Paul: Yeah, let’s not touch that one. We’ll just move on. So perhaps the different way of stating is you have team members in remote time zones sometimes and the PM isn’t online at that particular moment to validate that particular feature needs to go out but there's a customer who’s demanding it and it’s like, “What do you do?”

Edith: I don’t think there's any right answer to this one.

Paul: Like all people problems.

Edith: You know how good is the developer? How important is the customer? Is it really something that needs a judgment call from a PM or is it just that the PM needs to feel like they need to be there?

Paul: Right, right, this is something that I personal suffered a lot of, did the whole -- how come this wasn’t run by me, sort of thing. It’s a really difficult thing when your product is your baby to see stuff going out that isn’t necessarily the right feature or that isn’t necessarily done in the right way or I mean some cases it’s just the way that you would do it versus the right way.

Edith: Yeah and I mean this is – I’ll say again Paul. This isn’t much really to your software. It’s more just about overall management and decentralization.

Paul: So I think the reason it’s important is that customers –

Edith: I'm not saying it’s not important. This is in fact I think one of the biggest decisions you can make as a company.

Paul: Whether to decentralize?

Edith: Yeah, I mean so you can end up with the probably hierarchical

Paul: I don’t think it’s necessary to decentralize?

Edith: I don’t think it’s necessary but if you don’t – you could say, “Okay, I'm going to be the Salesforce model which is very top down.” Or you can be Facebook which is extremely bottoms up or I can come up with something that’s –

Paul: Even in a bottoms up organization like you’re going through product managers, you’re working with people who are actually validating that that customers actually want these features. And, especially if you're an organization that values A/B tests, and experiments and feature flags, there's a process that you can create where everyone is happy with the things you ship. And we’re –

Edith: Well, nobody is ever happy all the time.

Paul: Okay, okay. I think what I'm trying to say is –

Edith: And I think I’m being devil's advocate.

Paul: You are. You're just totally fucking with me.

Edith: Not totally, maybe just like – maybe –

Paul: Eighty percent.

Edith: Maybe like 10% roll out.

Paul: That’s slow burner. My sense is that there’s really this kind of overlap between continuous delivery and product processes. That is quite a complicated one to navigate. When people are switching to continuous delivery, like often the problems that they're going to experience are not technical problems. It’s not just the fear of what might break if we deployed six times a day. But it’s like how do we overcome the – or what do we need to do, what do we need to like setup sort of the – the people equivalence of the scripts that you check into your repo that does the deployment to make sure that we are doing things safely and that we’re doing the right things for our customer and for the organization.

Edith: Yeah and also how much risk are you willing to accept your –

Paul: Risk is super interesting for – like the whole continuous delivery thing is all about risk.

Edith: And I think part of continuous delivery is saying the biggest risk is to move slowly. Like I think, for example, Pacemaker should never do continuous delivery.

Paul: Because the risk is super high.

Edith: Yeah, you're installing medical devices in somebody’s body.

Paul: Right, I used to draw this – I remember when I was in the first seed round in like 2012 or something for CircleCI. I’d draw this graph of what level of safety do you need for – I think the question that comes up is like what level of test covered should you have. And it’s not a question that you can necessarily answer without knowing the complete context, like if you're making medical devices, sending people to the moon that sort of thing then that’s the sort of thing where will you write provably correct code, where you run like – why can't I think of –

Edith: Static analysis.

Paul: Those are particular – but there's a particular subset of static analysis- -

Edith: By the way, he got his PhD in static analysis.

Paul: But yet, it’s only been like five years and I can't think of any of the words that applied to it. So there are particular subsets of static analysis that are really like programs that are provably correct. And if you're flying on an airbus, you're flying on software that has been built by like the leader, the guy who invented entire fields of – like provably correct programs. On the other hand, if you're making a consumer app, if you're making an early stage start up, hell if you're making Facebook, that’s what the internal culture is. You can ship things with a much greater degree of risk. And the risk that you're really –a greater degree of kind of software or breakage risk or edited risk or whatever that is -- because what you're saying is as an organization is that the real risk that we wanted to prevent is moving slowly, is being stagnant. It’s not getting products to market. It’s not getting products to our customers.

Edith: Yeah, exactly. So I remember I had dude who’s now very senior at Hortonworks, he drew triangle was quality cost and time. And he said, you just move around this axis, like you can have extremely high quality thing that takes…

Paul: But never ships.

Edith: Or you can decide we’re going to skimp on quality because we want to ship faster.

Paul: So I’m going to disagree actually. I think that the idea of the extremely high quality software that takes a very, very long time to ship, I think that that’s not possible. I think that when you take a very long time to release software, what you end up is to get code, to perfect, you have to ship it. You have to put in to the real world.

Edith: So Paul, I have to say, I was about to disagree with you but now I complete agree. Because I think the lesson that I’ve learned is that you cannot internally test the used cases that the real world sees. Particularly, and to go back to mobile, particularly with the rise of mobile, just that there are so many devices out there and so many situations with low battery, low signal.

Paul: There are entire startups that are dedicated to like simulating your mobile device with like all this kind of different conditions.

Edith: People are out in the real world and there suddenly have something you never thought off. Well actually, I heard of something really interesting. I chatted with the Facebook director of engineering and they said they could not simulate Facebook’s load. The only way that they could really see if something could stand up to Facebook’s load…

Paul: Is to put in to production?

Edith: Yeah. They’re talking about Facebook, which has billions of users, only in the world.

Paul: Yeah, I heard they’re quite popular.

Edith: I hear the kids dig it.

Paul: So on the topic of things kids dig, it seems that if ever going to make something that’s popular, it’s never going to be popular on the first go. There’s always going to be like a nugget of something that you got right and in order to really get from there to something that grows rapidly, that is the quintessential Silicon Valley success story.

You need to be able to iterate, ship new things everyday, ship new experiments everyday, be able to validate what was right there.

Edith: I completely agree and validate on real users.

Paul: Yes, real users are tough people. I was chatting to the product folks earlier today about this kind of topic, and dogfooding was the issue and this is a little bit of a tangent but so we’re developer-facing company we’re a very technical company, all of our first eight or nine or 10 or 14 or whatever, people are engineers, and we used the product heavily from the start. But when you dogfood, you’ve assumed that everyone has the same workflow that you do, the experience of product in the same way that you do and you’re not actually getting what the customer really experiences.

Edith: Yeah, I hear you because at LaunchDarkly, we dogfood our dogfood, our dogfood, it’s like this chain of turtles so LaunchDarkly is feature flags as a service and so we use feature flags ourselves. So something that actively try to guard against is we’re like, “Okay, we can build a lot of stuff right now for us because we’re the most advanced user out there.” But we need to dial it back and build more and better onboarding.

Paul: Right, right. Yeah, yeah onboarding I guess you have a business there that needs to be.

Edith: Yeah, I’m very pro-dogfooding but I think you just always have to be cognizant that if you dogfood your stuff, you’re probably the power user.

Paul: Right. It’s exactly what I was getting at that you’re not the exact target user, you’re not learning at the right rate and that the stuff that you end up shipping is stuff for you which is great but not necessarily the stuff for your customers because they have different workflow or whatever it is.

Edith: I do believe in dogfooding your stuff and figuring out the pain points like I think --

Paul: I think dogfooding is great. The success of product especially at developer-facing companies is realizing that or making the entire company realized that the workflow that they use is not the same, or whatever customers informing people about the edge case and the product that are not experienced by the main product team.

Edith: That’s really interesting Paul and actually this might be just me being selfish, but some feedback I’ve gotten on LaunchDarkly is that we should be more prescriptive about what workflow people should follow with feature flags, and I wonder if you get the same at CircleCI about being prescriptive about how to do [continuous integration](https://circleci.com/continuous-integration/).

Paul: So when we were starting, the most popular thing and the best sort of designed developer product was Heroku. And Heroku had this logic of you will get an amazing experience if you conform. The big one was read-only file systems. People would just not conform. You can’t use Heroku because of read-only file systems and Heroku actually changed the whole world around that model.

We felt that we weren’t able to do the same thing. One was that we were small kind of startup and we did not have the same sort of attraction that Heroku had at the point that were answering this but also we felt that every developer is a special snowflake, every developer workflow is a special snowflake, so the kind of product principle that we came up with is if we follow best practices and every developer community out there where we know subsets of those, they all have like ways of using the tools in the ecosystem in an idiomatic way.

So if you follow those best practices, Circle will just work and it will be this just amazingly beautiful experience. If you deviate, we still want to use the product and we still -- and so we provide escape hatches for almost everything and we’re working hard to make sure that we have escape hatches for the things that are left.

Edith: Yeah, I think that’s really important. I think we fall in love with our own products and we think people want to turn every knob and twiddle every dial when really they just want a lot of stuff.

Paul: Yeah, they just want it to work out of the box and yeah, it’s funny that there are so many ways to implement feature facts and we’ve ended up -- we’ve had homegrown feature flags since before you guys were around. We’ve just kind of ended up in the situation of the feature flags that you have or -- I mean really, the product that you use constrains your workflow, so we have three different ways of doing feature flags and we’re always trying to make our continuous delivery process fit into those three buckets.

So like I have the ability to ship a feature flag that runs on a specific machine or for specific user but only randomly or for specific project but manually set. So those are kind of the three things that solve like 90% of our use cases but we ended up with -- we want to do continuous delivery in a way that doesn’t really work on those three kind of ways of doing it and so instead, we need to do something else and we find different ways of deploying and different ways of getting the product out there to customers that fit within those things, and sometimes, it’s not pretty.

Edith: Like what’s the use case that you had to jury rig?

Paul: So we were disabling a field from our API and we were pretty convinced that no one used this field. So we set up a feature flag for the field and then we turned it all for our own project. And ideally, we would have scaled it up. It wouldn’t just have been listing for ourselves, listing for -- let me explain how they did and then what we were ideally like have done. So turn it on for ourselves and then waited a day or two then turned it on for a random smattering of 10 customers who are building right now.

I waited couple of days. No complaints, turned it off for everyone, waited a week or two, no complaints and then we actually deleted the code. But that manual process of first of all, turn it off ourselves then we’ll pick 10 customers and actually type the project names into our chatops thing in Slack --

Edith: Oh, you’re one of those chatops people.

Paul: Yeah, yeah. It’s awesome. I couldn’t recommend it more. So yeah, we do that and then really what I want is the -- we scaled it up to 10%, to 20%, to 30% but we can only do that on a randomize -- we can only do that on a randomize basis. We can’t do that on a static like once customers are in, they’re able to do it. So we weren’t able to use that particular feature flag mechanism first.

Edith: Paul you know, you can use LaunchDarkly on feature by feature. No, on a feature by feature basis.

Paul: Yeah, yeah, no.

Edith: I mean you could keep your homegrown system and then just use us with really important features.

Paul: That’s an interesting idea. I haven’t thought about that.

Edith: I mean you could just use us for those features and then keep your old system in place. Then gradually, all your features belong to us.

Paul: It’ll get there. The other one, we were talking a lot about SaaS software and obviously continuous deliver is this thing which came back because of the prevalence of SaaS software. We’re launching on premise software as well as CircleCI, you can buy CircleCI enterprise and that’s like literally things that we shipped, that run in your own VPC or that run on prem. We can’t really ship the same things to do testing. For a start, we’re not allowed to ship our analytics code in there, so we don’t run Mixpanel in the staff that we shipped to enterprise customers and so we can’t tell who’s using what parts of the features. It makes the whole continuous delivery model much more difficult.

Edith: Oh yeah. I mean so we talked before it’s like so with Apple’s a gatekeeper, On prem a gatekeeper, like really the rise success.

Paul: Really, that’s what they’re trying to be like. They deliberately trying to be a gatekeeper.

Edith: I think continuous delivery and SaaS are so tightly intertwined because one enables the other.

Paul: Right. There was this blog post that I read kind of in the dawn of SaaS -- it was by Joel Spolsky and Joel on Software blog where he talks about searching Fog Creek, a downloadable thing that runs on some things to being actually on the web, being a web application.

One of the things he talked about is being able to ship things that customers don’t see yet, being able to ship things that fix customer bugs immediately after they start. And being able to get notifications about error messages or about errors or whatever it is immediately instead of being sent by bug report or being sent by an actual customer via an email that they catch, replicate or whatever.

Edith: We used to be so blind Paul.

Paul: It was fucking awful. I’m trying to write software in -- so I worked in the games industry briefly when I finished college the first time. Shipping code that runs on a console, that is going to be shipped like on a gold master disc in six months from now and that you’re never really going to be able to validate, that was like -- games aren’t even shipped that way now but like that was fucking awful time of trying to understand all the different ways of -- that software could break and all the different ways that your code might not just work quite literally shipped to millions of people at once.

Edith: Yeah, to tie back to something we’re talking about before, that’s when you got this feature and scope creep to the point where like Duke Nukem never shipped.

Paul: Our particular problem in the graphics engine and anything that involves like a state of the art graphics engine, things will just fall back until they don’t ship.

Edith: Yeah and then all of a sudden, I mean it goes back and then you have all these issues with people’s computers themselves have moved on.

Paul: Right, right, the expectations are different as well like if you’re shipping Duke Nukem and it’s been seven years now. The thing that you’re going to have to ship is going to have to be amazing. It will have to be life changing or as people will wonder what it is going on.

Edith: Yeah, you’ve just been trying for the past seven years is just to like --

Paul: Ship anything. I’m very, very glad to be in the SaaS business.

Edith: It’s liberating. I think analogy is between the transition between books to newspapers, to online.

Paul: Right, because people are -- the news cycle changes as a result of it.

Edith: Yeah. If you can publish multiple times a day, you just publish.

Paul: Yeah and of course, you can continually go back and edit those articles in case you --

Edith: Or put a retraction or correction or unlike a book -- like once a book is out in a bookstore like you know it’s there.

Paul: Yeah. The biggest thing that I’ve ever written -- or the longest thing I’ve ever written was my PhD thesis. And I have a paper bound copy in my living room that I never look at. But occasionally, someone will come and they’ll be like, “Oh, here it is.” They’ll open it to random page and looking over their shoulder I see a typo. Whatever page they open, there’s some type -- I’ve read that thing 50 times. But somehow, I didn’t manage to get them all out.

Edith: That’s really funny. Are they terrible typos or just many ones?

Paul: I mean its things that a spell checker would have caught sometimes.

Edith: Oh did you make it in some like terrible LATEK or something?

Paul: Of course it was LATEK.

Edith: Yeah of course, oh yeah. So it’s probably beautifully formatted.

Paul: It looks amazing, Garamond font.

Edith: So it looks beautiful but it’s riddled with --

Paul: Minor punctuation errors.

Edith: Yeah. I remember, this is a total aside but I wrote an econ thesis which I’m really proud. I took it home to my parents and my parents -- my mom has a PhD in English, my dad is an editor and started pointing out like you used an M-dash when you should have used an N-dash. I was like, “You’re supposed to be admiring like my deep economic thought not copying editing.”

Paul: So apart from doing a therapy session for that, what else have we got in the continuous deliver event? And the deep parental scaring. Looks like we’re all out of things to talk about this week.

Edith: No, I think we open it up. You asked me what I like about continuous delivery, and you said I was surprised by my answer.

Paul: What was your answer again?

Edith: I like getting product to people faster and making them happier.

Paul: Oh yeah, I thought you were going to talk about employee morale.

Edith: I mean I like employee morale also but I don’t think that’s the -- I think they tie together. I think employees were happy because customers were happy.

Paul: Right, right. Personally, having worked at Mozilla during the awful Firefox 3 to Firefox 4 conversion or the Firefox 4 launch which took 18 months and things just kept slipping and things just kept being added and feature creep and there are these things that the web was waiting for that would be held back by Mozilla being unable to ship Firefox 4.

And people were not happy. The entire organization was particularly unhappy. When we switch ed to the release train model, it’s kind of few months before left I think and actually I hold the singular distinction of being the first person to fuck up the Mozilla continuous release train model.

Edith: It wasn’t where I thought you were going to go there Paul.

Paul: No. In fact, I forgot where it is on but I think I can probably get there.

Edith: How did you fuck up the release train?

Paul: So I shipped a feature just before the deadline and that’s the whole thing that you’re supposed to avoid when continuous delivery. It’s never about shipping for deadline but now, I was determined to get this feature. And this feature was one where we had argued considerably online on BugZilla. And I said, “Look, I’m just going to ship this and we shall see.” And the feature was going to be an amazing one. So in Java Script, there’s no way to get submillisecond precession. There’s a feature called date.now and date.now returns the number of milliseconds since whenever.

I said, “Okay, we can make this a floating point number and that can give us submillisecond precession.” Unfortunately, people were using this to basically as a random name generator and they were creating DOM nodes that have the name of the number of milliseconds. It was terrible, terrible idea doing it but DOM nodes can’t have dots in the name so I turned it to floating point number. Everything broke and the first thing that broke is Gmail. So Gmail upload used this feature, feature, I spit on that feature. Use the thing and so I broke Gmail for about a million people who were using our nightly releases.

Edith: Well, Paul, I’m not going to give them your address so that they don’t talk about how they really needed that email.

Paul: But because continuous delivery it rolled back. There’s no big deal.

Edith: And I think that also plays into a bigger point that we’re making that until you push a feature out into the field, you can’t really know how people are using it.

Paul: So actually, in this particular case, I think we could of predicted it. In retrospect, there were some things out there but yeah. Once it goes out, it’s settles the question for once and for all. Lots of people who knew what they were talking about were saying this is going to break the web and I said, “No, no it will be fine.” And really, we just put out there and it broke the web and we rolled it back.

Edith: Yeah, I mean that’s one of my major tenants is users always beat testing. And users beat assumptions.

Paul: Right. Products need to be validated, code needs to be validated.

Edith: And the sooner you get them out to real people the better.

Paul: Right. Did we talk about risk yet?

Edith: We talked a little bit about risk. We talked about pacemakers.

Paul: Oh yeah, yeah. The thing that’s important I think is with risk and continuous delivery is smaller units are less risky. You can ship a tiny, tiny piece of code and validate that it works or doesn’t work with significantly less risk than a whole quarter’s worth of work.

Edith: And I think it’s risk at every level.

Paul: What do you mean?

Edith: It’s risk at market level. So I think you were talking very narrowly about just like --

Paul: Code risk. And breaking our customer or being able to -- you can’t roll back a quarters worth of stuff. We can roll back one commit.



Edith: Yeah. To me, it goes even bigger, like the biggest risk and we talked about the biggest benefit of continuous delivery is the biggest risk is always just you’re building the wrong darn thing.

Paul: Right, right. Tell that to your CIO.

Edith: Well, you spent 18 months or 24 months going in a direction like to your thing about the game discs, to build a game that nobody wants or cares about.

Paul: Right, right. Well, on that depressing note. We are going to be back in two weeks I think.

Edith: Yeah, two weeks.

Paul: And we’re going to be talking about more continuous delivery stuff. We don’t know exactly what so send us a note.

Edith: Edith [at] launchdarkly.com and I’m on Twitter [@edith_h](https://twitter.com/edith_h).

Paul: And I’m on Twitter at [@paulbiggar](https://twitter.com/paulbiggar) and we shall see you in two weeks.

Paul: Thanks for listening to this episode of To Be Continuous brought you by Heavybit and hosted by me, Paul Biggar of Circle CI and Edith Harbaugh of LaunchDarkly.

Edith: To learn more about [Heavybit.com](http://heavybit.com). While, you’re there, checkout their library, home to great educational talks from other developer company founders and industry leaders.


