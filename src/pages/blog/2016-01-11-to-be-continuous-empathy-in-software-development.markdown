---
author: andreaech
comments: false
date: 2016-01-11 00:52:47+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-empathy-in-software-development/
slug: to-be-continuous-empathy-in-software-development
title: 'To Be Continuous: Empathy in Software Development'
wordpress_id: 759
categories:
- To Be Continuous
tags:
- continuous delivery
- continuous deployment
- LinkedIn
- LXC
- microservices
- product manager
- Rapportive
- Sam Stokes
- UNIC
---

In this episode of To Be Continuous, Paul and Edith host Sam Stokes, cofounder of Rapportive, to discuss empathy in software development, the tendency for micro services to become mini services, and the act of constantly updating software in a constantly updating world. This is episode #9 in the To Be Continuous podcast series all about continuous delivery and software development.

This episode of To Be Continuous, brought to you by Heavybit and hosted by Paul Biggar of CircleCI and Edith Harbaugh of LaunchDarkly. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.

**Paul:** Alright, Sam, so what’s your favorite thing about continuous delivery?

**Sam:** I like to think about it terms of shortening feedback loops. A lot of things that startups do can basically be looked at as doing something and then waiting to get some feedback on it, and then deciding whether to do more of that thing or to do a different thing.


<blockquote>And continuous delivery is, people talk about sort of reducing the batch size and also about shipping stuff faster and clearly having some kind of automation. And continuous delivery is going to help you with both of those things.</blockquote>


**Paul:** So is this specifically on the, sort of on the journey of a small startup towards product market fit? Is that kind of the sense you’re thinking of it as?

**Sam:** I see it as applying to teams of different sizes. So for sure in a small startup you’ve got you need to iterate fast, you’ve got all these product ideas. But I think even if you’re a small team in a big company as I was recently working on, and still have a lot of the same pressures you have, product managers who want to try new ideas, you have customers who are sending in feedback all the time—some of which you want to listen to, some of which you want to tune out.

It’s sort of, in some ways, a lot like being in a startup. At least, ideally it would be. And a lot of the problems you can run into are basically about not being able to close those loops quickly enough.

**Edith:** Sam you’re someone who knows a lot about loops, so now might be a good time to introduce yourself.

**Sam:** Sure, my name is Sam Stokes. Until recently I was working as a staff software engineer at LinkedIn. And right now I am, I guess a freelance software consultant, thereabout.

**Paul:** I feel there’s a little bit of history missing there.

**Sam:** Alright. Going back in time a little bit. So I was a co-founder of a startup called Rapportive. That was a plugin for Gmail that when somebody emailed you, would show you a social profile of that person in the right-hand side next to their email.

So that you could get some insight into who you were talking to and put some more humanity into your communications with people—that’s sort of the way we saw it.

**Paul:** That’s still the only plugin to Gmail that I use.

**Edith:** I use it, too, and it’s for exactly that reason, ’cause I do a lot of customer development, and it helps so much to do, to empathize. To see that this—

**Paul: **Right, right, yeah is a real person.

**Edith:** You know, to see their face and you feel a connection.

**Paul:** It’s interesting just with kind of customer communication. One of the tools that we use is Intercom. And once I started using Intercom it was the same sort of feeling I got the first time I used Rapportive, that like I feel that there’s a human at the other end of this and I feel I know who that human is and it just changes how you communicate with the people.

**Sam:** It’s really motivating to hear and to see other examples as well. We really felt like email and sort of a lot of business communication in general can be sort of cold and formulaic.

Yeah, just bringing that human element, even just seeing a face. I haven’t used Intercom but I’m guessing they have some similar ideas.

**Paul:** Similar, when you send out messages or reply to someone it does the person’s face there.

**Sam:** Right, we had a sort of plugin API in the, it was a sort of private beta version of our product and one of the things people used it for, so this would let you plug into the sidebar, people would plug it into their customer database and so they could see something like, they’d get an email from a customer it shows them how long they’ve been a customer, how much they’ve spent in their store—

**Paul:** Right, right.

**Sam:** What version of the app they’re running, that sort of thing.

**Edith:** Was your original idea to do that sort of empathy or was that something that just you iterated into?

**Sam:** The empathy was where we started. There were lots of ideas about taking all the information from all these different sources, you know public sources like, truly public sources like Google, quasi public sources like a Facebook profile if you’re friends with them on Facebook, and then private sources like stuff in your company database.

All stuff that you would be able to search for if you could be bothered to go and do the searching but doesn’t necessarily bring itself to you while you’re talking to that person. And yeah, it was very much, what should you know when you’re talking to this person in order to make them feel like they’re interacting with a real person and an empathetic one.

**Paul:** So I remember when you launched Rapportive it was like, or it felt to me like it was, an instant hit and maybe that was just the overnight success that comes after years of trying. I had a doco and what was the kind of software delivery process of that?

**Sam:** Hmm, that’s a great question. I guess there’s two parts to that really. So how did it get there and what was our process that allowed us to survive it? So I guess how did we get there, it was a certain amount of luck in that process as there probably always is. We built our prototype and it was a pretty minimal prototype.

You know, it had the functionality that was like this awful demo website up. The only reason there was a website up was we were trying to raise a seed round at the time, we were applying to OIC. Y Combinator requires that you have a demo site that’s public. They don’t like it to be password-protected. And so we had this thing up where you could install it and we had like 20 users. One of our friends decided that he was going to email a friend of his at one of the blogs, I think it was ReadWriteWeb and say, you know, hey you should check this out.

And his friend checked it out and it turned out that one of the demographics that really liked the product that we built was journalists because they get a lot of emails from people they don’t know and they want to sort of know an extra nugget. I guess that was one of our takeaways was like, if your startup is really useful for journalists, that’s a great way to get some early press.

**Edith:** That’s what worked for TripIt because journalists travel a lot. So TripIt just got all this free press basically ’cause journalists used it, loved it, and blogged about it. Unfortunately, journalists do not do continuous delivery so much.

**Sam:** So how do we survive that? ‘Cause what happened in that 24-hour segment was that we went from 20 users up to 20,000.

**Paul:** Wow.

**Sam:** So I guess one part of it was our CEO had made the original platform choice. His name’s Rahul Vohra, he has a computer science degree, he’s an awesome technologist, but his focus is not generally on writing the software. He’d been writing the prototype, and he was like, ‘I need the quickest thing that I can get to get this market, so I’ll put it on Heroku.’

Which turned out to be a life-saving decision because when the 1,000 X traffic spike arrived we just added some more dynos. So that was how we didn’t burn down. What did we do after that? I guess in terms of software process we were pretty young as a company, so it was pretty much hack away, read all the tweets. But there was a lot of, what you might call customer development more than software development at the time. So we pretty quickly decided that we were going to try and respond to every single tweet and every single email and so on to like try and live this idea of a good customer experience.


<blockquote>And I think that helped to sort of amplify the viral effect of that press spike because people were sort of retweeting the things we were saying and getting a generally good feeling about us.</blockquote>


And so a lot of those tweets were like, ‘Oh I wish I did this,’ or ‘I wish I did that,’ or ‘I wish you could see Twitter profiles in there.’ So it was a little bit of sort of customer support-driven development. Which obviously doesn’t scale but it can be a pretty good way to build some goodwill early on.

And I think a lot of our users were sort of quite passionate about using us, ’cause they felt like they got that personalized attention.

**Paul:** So did the, when you scaled the dynos did it just work?

**Sam:** It worked perfectly until we hit the rate limit for the API that we were getting all our data from.

**Paul:** The LinkedIn API?

**Sam:** At the time we were using a service called RapLeaf.

**Paul:** Oh yeah, yeah, I remember them.

**Sam:** It wasn’t their main product, but they provided an API which … So basically the thing that Rapportive does, which is take an email address and produce social profiles about that email address. At the time that was entirely just UI wrapped around RapLeaf. We ended up building sort of our own version of that.

And so we’d been using their API on a sort of demo basis. Because again, 20 users. Yeah, we immediately had to learn about things like request queues, so that our app wasn’t just falling over waiting for their API, and then frantically Biz Dev-ing to try and increase our rate limit, while at the same time figuring out the best ways to get around the rate limit without upsetting the Biz Dev deal. Yeah, we didn’t really have much of a sort of continuous delivery process at the time.

But I guess not as many people were talking about it—this was 2010. I think the first blog post had come out from Iron View and so on, but I think it wasn’t as, you know, there weren’t full startups supporting it. What we did have was the Heroku deployment model, which was basically like within five seconds of writing the code you can deploy it to production.

Which if you squint at it, kind of is continuous delivery because you’re saying, all of the bits of your deployment that you have are automated. We didn’t really have many tests at the time, so the tests we had were automated ’cause there weren’t any. Our deployment was absolutely, you do it get push, you don’t have to like move any servers around or anything like that.

**Paul:** Seems like the testing model around, or the continuous delivery model around a Gmail plugin is probably going to be a fairly difficult process anyway.

**Sam:** We never really had a good answer to, you know, what happens when Gmail changes their UI. The surprising part was it didn’t happen that often. We thought it would be breaking every week and we’d need all kinds of canary accounts and end-to-end testing to monitor that kind of thing. In the end, it happened rarely enough and we noticed quickly enough that we could usually just fix it on the spot. So even when we got better at testing and that sort of cycle of things.

**Paul:** We had a problem or I guess solution with GitHub. So GitHub used to be super flaky around two, two and a half years ago, when they were still on Rackspace. And whenever something would go wrong with GitHub we would find out immediately. All of our, all the developments would start failing and so before they knew that there was a problem, we knew there was a problem.

And we would often like, declare on Twitter, oh we think GitHub’s having a bit of an issue and two minutes later their status would tweet us and then we would retweet their tweet.

**Edith:** So they were using you for their free testing.

**Paul:** Well, our customers at least.

**Edith:** No I mean you were acting as their tester and telling them that—

**Paul:** Well, I mean it was very, you know, automated on our but we didn’t have necessarily automated fixes at the start. It kind of happened every, you know, two or three months and they would swear this is the last time and—

**Edith:** It’s always the last time.

**Paul:** And in the end it happened like six or eight times and by that time we had built a thing that allowed, you know, certain fixes, but it wouldn’t be quite, you know, fully automated process that you would expect if it was happening all the time ’cause it always seemed like it was gonna be the last time.

**Sam: **And it’s probably always happening for a slightly different reason or in a slightly different way. It’s actually, it’s an interesting question to me in the subject of continuous delivery in general. People always talk about every time you commit you run your tests, every time you commit, you deploy.

But that’s actually only one of the kinds of events that you’re dealing with in a software life cycle, right, when something’s actually running. I mean, sure you’re changing the code but also the world’s changing around you. And I feel like you always end up needing a little bit of both—you need something that’s gonna trigger when you change it, but you also need sort of an eye on everything you depend on. And, of course, even figuring out what all those things are can be interesting.

**Paul:**


<blockquote>So I wrote a blog post about this on the Heavybit Blog, I think a while back, and it was about third-party APIs you know, how do you test third-party APIs. And the conclusion that I came to was that, so if you run the tests as part of your test suite, then if something breaks, your test suite will be broken, but also some things will just like randomly break in production.</blockquote>


And then of course you can’t deploy because your test suite is broken. So you’re in kind of the worst of both worlds. And so what I considered is, is that you need something which, you know, is just permanently monitoring. Like whatever API things you do constantly hits your personal accounts or your test accounts for those things, and then stub it out in your test suite.

And that way you kind of get that best of both worlds, your test suite doesn’t fall over and you get an actual monitoring event when the third-party service goes down in production.

**Sam:** I can tie this to an experience from LinkedIn, actually. So LinkedIn has the model where there’s a staging environment and a production environment. And the staging environment is—I don’t know if it’s technically called a staging environment because it’s not exactly production-like, but what they actually call it is early integration. Because it’s the environment in which teams integrate with other teams.

And so the idea is you deploy your stuff into EI, early integration, as soon as you can so that if any other team depends on you or vice versa, you can find out there before the thing hits prod. But what you’ve effectively got in EI is this constantly changing environment full of dependencies and you have exactly this problem and different teams which using different solutions to, well, let’s write some integration tests which actually hit the dependencies and then we’ll run them in our test suite when we deploy to EI or when in the build step which—

**Paul:** I can’t tell as you’re describing this whether this is a good thing or bad thing.

**Edith:** Yeah.

**Sam:** I think there wasn’t a clear conclusion, but my conclusion is that it doesn’t work for the same reason that you’re saying.


<blockquote>You need to know that if your test suite fails, it fails because of something you did. And then you need something else that can fail because of something someone else did.</blockquote>


But if you’re ever unsure which of things it is, then the signal is lost for both systems.

Edith:     Yeah. When I was in London, I talked to somebody. They don't have a staging system at all for kind of these reasons. It's just easier to put everything in a production, feature flag it, and just know whether it's an issue or not. Maintaining a staging system is sometimes even much more work.

Paul:      Yeah. Yeah. It honestly is. There were actually significant amounts of effort put by every team into just keeping their stuff running, then the EI instance of their stuff running. And to some degree making sure that if you had any data that your service needed to run that there was a representative set of data in EI that the teams that were depending on you could use. This isn't production data, right?

Sam:       Yeah.

Edith:     Yeah.

Paul:      For use of privacy reasons, this is all fake data, which means you now have to maintain a fake data set for every single service.

Sam:       Right, right, right.

Paul:      Very few teams have the bandwidth to do that.

Edith:     Also, then you always have to remember Oh, let me go to staging. Then it's just this drudgery.

Paul:      The tools have ensured that you did it in that order.

Sam:       I think the problem is having a single staging. I don't think that there's necessarily anything wrong with the concept of deploying something and possibly pushing a small amount of traffic into it or pressuring it.

Edith:     I think it should just go directly to production and feature flag it all.

Sam:       Okay. I guess to a certain extent, they're the same thing. You can have a staging environment and a small amount of traffic is mirrored into that, which is essentially a feature flag situation.

Paul:      I've heard the word used for that is the dark canary. It's canary in that it's deployed into a real production machine, but it's dark in that the users aren't actually seeing it.

Sam:       Right.

Edith:     Yeah.

Paul:      The interesting question then is what if that is right traffic? It works great for reads. You can just mirror them, but if you're mirroring rights, you may have double rights.

Edith:     Yeah.

Paul:      Maybe there's a bug in that thing you just deployed.

Sam:       Yeah, yeah, yeah.

Edith:     Yeah. That's why I argue for to just put it all in production.

Paul:      Right.

Sam:       Yeah.

Edith:     Just the effort to maintain a system to test on is huge.

Sam:       What we do is people can spin up their own staging environments. It will just spin up a whole staging environment so you can do some tests on it. People do that very often for load testing or they put traffic against it of their own creation. One of the problems that we often run into is how do builds interact with other builds and if you're doing anything that that involves LXC or any of the more platform as a service kind of things or cues. Those are very difficult things to do in production. At least, if you do it in production and you fuck it up, then you're in real trouble. Those are things where we'll have people spin up staging instances. We've set a script to set up you're own staging instance, but you can have multiple staging. They don't talk to each other. It's not an early integration situation.

Paul:      Right.

Edith:     That's interesting. Those are actually one of our early company ideas, which was allow people to do builds on demand. We called it continuously. Anyway, enough about me. What was the biggest difference you saw between moving from a start-up style up to LinkedIn? What was the difference in cultures?

Sam:       I'd say a big part of the difference is in a start-up, at least in the size we were at. We were five people at the time of our acquisition. You feel like you're one integrated unit that ... You know who's doing everything. To a certain extent, everyone is doing a bit of everything. Certainly you always know where to go if you want something done and if you want something prioritized. As a start-up scale and certainly when you're a big company, you very much specialize. You split off into these groups that do things. As I eluded to when I was talking about this early integration environment, that's just teams within the company. LinkedIn adopted a version of the microservices model, which as I've heard it described is, it's not a way of writing software. It's a way of running software, because what microservices gave to LinkedIn was the ability to divide their software by the team structure.

Rather than saying we have this gigantic monolith and this is your bit of the code base, it's still got to be deployed in the same way.

Paul:      Yeah.

Sam:       Teams could make their changes in an environment that was somewhat controlled. They controlled their deployment schedules. They could go continuous deployment if they felt like their tests were ready for that. They could do their manual deploys if they couldn't or if they had some extra-special deployment requirements. You had all these different teams often ... LinkedIn is a very big company, often in different buildings or sometimes even different time zones, that would be doing the thing that you were currently thinking about. We got a URL and we want to see the contents of the news article that URL represents. You may have to talk to at least one other team, if not two other teams, to get that, which is a really interesting and powerful model because it means you can make progress on all of those things in parallel. You get these very interesting problems of sort of knowing what's going on between these different teams.

There's the technological drift of you've changed this thing and now we're not compatible, but there's also the really subtle mission drift. At the start of the year, we all decided that we were going to do this thing. We were going to build this feature, which required all three of our teams or all nine of our teams, to work towards this thing. We were going to implement this feature, which we're going to depend on in three months so that the third team can do this thing. It turns out that two months in, the first team realized that to do exactly that was going to require some significant refactoring they weren't ready for, so they slightly changed their plan. They didn't realize, because it's hard to tell, that that change was going to disrupt other people. They continued along the track that they were going on. When team two was ready to start integrating, they found that it doesn't support this thing that they were depending on.

Paul:      Interesting.

Sam:       You then get these escalations or backpedaling. You get some very good discussions coming out of it. Usually, it happened for a good reason.

Paul:      Does that seem parallel here? In Amazon's, in one of the learning's of having a microservice model or, at least a services model, is that when something goes down, it often takes a long time to find the team. There's an escalation that follows to another escalation to another escalation as people try to figure out what service is actually responsible for the outage. It seems a problem of communication structure.

Sam:       Absolutely.

Paul:      When people change their things, it's a new person that has to be talked to, a new team that has to be reached. Maybe you go through several teams before you find out that the API and point of using is actually served by another team, which is served by another team.

Edith:     It's turtles all the way down.

Paul:      Right.

Sam:       In some ways, the team model you can seem as an abstraction layer. In theory, you would actually have teams, which in software terms you might call an adapter or a proxy.

Paul:      Right.

Sam:       You would have teams, a large part of whose job was to effectively route calls between different other teams. The team I worked in was doing a lot of interesting things. One of its roles was to integrate work from lots of other teams. We would get questions from all around because, as the integration point, we were the most visible. A lot of the questions we would get were things we weren't fundamentally in control of. We would be like oh you need to go ask that guy or we would ask that guy for you. It was an interesting place to be, especially when people don't necessarily realize how much you're delegating things down to other people.

Paul:      Why was that the split point for the service or the team? Sorry. I'm interested in the question of when do you create a microservice. All right. In this case, or LinkedIn's case, since you create a service for each team. Why did that team exist?

Sam:       There's an interesting corollary to create a service to each team, which is if you really need a service which performs an integration role, you sometimes need to create a team for that service. At least, that is a natural, cultural assumption.

Paul:      Yeah. Yeah. That's how your company works. That's how it works.

Sam:       I don't think that's exactly what happened here, but you do have is sometimes you have a team that needs to do things, but the service they own isn't really micro anymore. Sometimes, you have a service which is in an important request path or whose job is fundamentally gluing things together.

Paul:      Right.

Sam:       It's job can become more complicated than you can necessarily represent in this sort of idealistic UNIX model of it just does one thing and that's what it does.

Paul:      Yeah.

Sam:       Let's say you're taking data from a bunch of different content sources, and you want to blend them together in some way. You could say we'll just have a service that does that sort of stacked together in aggregation. Then we'll give it to another service to apply some ranking on top of that. Then we'll give it to another service to apply business rules, like filtering and abuse detection. Except it turns out if you're doing that many hops, first of all, there's the inefficiency of having to throw all this data around. Sometimes, it's large amounts of data, especially if what you want to do is some kind of relevancy ranking on that data. Relevancy is being a broad term for figure out what the user really wanted to see. In the ideal case for relevancy, that requires access to all the data you could possibly have about the user of the article, users like that, user, and so on.

If you need to bring that into more than one place, that's usually pretty relatively hard even to get into one place. If you need more than one service with access to that kind of thing, then that gets a bit nightmarish. A natural thing is to collapse a lot of those responsibilities into a single mini-service.

Edith:     So a microservices become mini-services. Do they eventually just grow up and become services.

Sam:       One of the really interesting things I saw, LinkedIn started off with monolithic services, moved itself to microservices, iterated back and forth along the spectrum a few times. There's a strong tendency for a microservice to grow up into a monolith again.

Edith:     Yeah.

Sam:       As soon as you have 20 people committing to the microservice wise, it's a monolith now

Edith:     Yeah.

Paul:      I think there's this interesting question that you see a lot of people who are new to microservices, not really know where do you put or what is a microservice and where do you put the service boundaries. There's a lot of pragmatic things that you can do. You can say there's a team boundary. There's a very obvious API boundary. There's things that have different deployment schedules, things that have different reliability or uptime requirements. I think those are the kind of major ones. It's interesting to hear where that breaks down. If you have a model of your one team/one service, then you're not going to have a microservice anymore. You're going to have teams managing a bunch of different microservices, and then they have to become a bunch of different micro-teams to manage those microservices.

Sam:       I think the way that LinkedIn structured it was actually pretty interesting in that regard. That's kind of why I said sort of microservices at the start. The actual model LinkedIn used was based on it went all in on a RESTful model. What they actually talk about is REST endpoints. So you would have an endpoint, which is defined pretty much by the name of the URL at that endpoint. I should probably say resource. You might have a resource, which is members. You might have a resource, which is articles. There's a registry that says if I want to access this endpoint, what physical machines do I go and ask? Services clear it out at run time. If you want to get something out of a member's resource, you do that look up at the time that you are making the request. What that means is, you are not actually talking to a service. You're talking to a resource. The choice of whether, for example, more than one resource might live in a single service. That's up to the team that owns that resource.

Paul:      Oh, I see.

Sam:       If that team wants to have three similar resources live in the same service, because that worked for their team model iteration speed, their optimal requirements, etc., they can do that.

Paul:      Standard computer science solution, just add another layer of direction.

Sam:       Yes. You had some big services, some very small ones that just earned a single resource.

Paul:      I wasn't clear whether you were hitting at a big one or a small one.

Sam:       Right. I guess the view was you didn't really need to know.

Paul:      Right, right. In fact, it's great of you don't know.

Sam:       That sort of helped with knowing who to talk to, as well. You could use the registry to figure out ... I think there was an earner's list for every resource. You could start on hitting numbers, numbers as returning in error.

Paul:      It's almost odd to have registries keyed by URLs. You would think that the URL is the destination.

Sam:       I'm not sure I see the distinction.

Paul:      You would think ...

Sam:       Oh, I see what you mean.

Paul:      Yeah. A URL is the place that you go. Whereas ...

Sam:       I guess there were two levels. There was the resource, which is sort of a logical URL.

Paul:      Right.

Sam:       It would be named after ... It wouldn't even have a host name in it. They called the service D2. It stood for Dynamic Discovery. The URL would be literally D2, colon, slash, slash, numbers.

Paul:      Right, right, right.

Sam:       That would be the whole thing.

Paul:      I do think this is very interesting. People tend to build their microservices. Every service has a URL. If your URL has an actual machine name, maybe not a machine name, but something with a DNS name.

Sam:       Probably it's a load balancing name.

Paul:      Exactly. It has a load balancer in front of it. You're providing these endpoints to users under some other URL scheme, you have to have an actual load balancer in front of it rather than a thing that can be contacted asynchronously. There's a thing through which traffic is routed rather than a thing, which tells you where you're going. That's the difference between a load balancer and a DNS resolver.

Sam:       Right. This went along with also having a library that everyone in the company used, which did client-side load balancing. Almost nothing sat behind a physical load balancer.

Paul:      Oh, interesting.

Sam:       Part of this D2 resolution was figuring out what host should I use in my client-side load balancing.

Paul:      It told you the set of hosts and the client-side load balancer picked randomly between them or something.

Sam:       Yes. It may have told you the path and zookeeper to subscribe to so that you would be notified if the host went down, etc.

Paul:      Got you.

Edith:     This was a lot of microservices. I had a macro question for you, Sam. You have some interesting ideas around testing.

Paul:      I have some interesting ideas. I think a lot of people missed the point of automated testing.

Edith:     Oh. Paul might know a couple things about this.

Paul:      I'm excited to see what this is.

Sam:       I think that the word testing confuses people because it sounds like a thing that you do to a piece of software or to a product in order to find things that are wrong with it or a thing that you do to prove that the thing works.

Paul:      Yup.

Sam:       Of course, there's lots of quotes about how testing cannot prove the absence of bugs. That's still what people talk about when they're talking about testing.

Paul:      Definitely.

Sam:       I think that causes two kinds of problems that come from the same root problem, which is people don't understand the value they're meant to be getting out of testing.

Edith:     Interesting.

Sam:       I might be generalizing. I think a lot of people think they're doing testing to find bugs or to ensure quality. One thing people do as a result of that is they've seen testing being done somewhere and there were bugs anyway or the quality wasn't great anyway. So they concluded well I don't need to do testing. It's clearly just a waste of time, and it's not going to find my bug, so why should I even bother?

Paul:      What is the purpose of testing?

Sam:       There's this great quote from a kind of obscure source, which is one of the people on the Debian Project, who had run WMMX.

Paul:      A software known for it's reliability.

Edith:     Paul? Paul, did you make a joke?

Sam:       What they were trying to do was ... The title of the post was A Proposable for an Always Releasable Debian. Debian has a hold project that maintains an operating system and tens of thousands packages, was trying to move to a continuous delivery model. They used to do deliveries every few years.

Paul:      Yeah.

Sam:       People loved them for their stability, and at the same time, mocked them for how all their packages were because they released every few years. They were like we have tens of thousands of things. They interact with each other. We don't own any of them. How the hell can we possibly ...

Edith:     That's open source.

Sam:       Right. It's open source. This was a proposal to adopt a lot of the ideas around continuous delivery by saying we're going to have a trunk that consists of a known releasable version of every package. We're going to write a big suite of tests that essentially sets, the phrase he used was a minimum acceptable level of quality, I think. Yeah, I think. It's not to prove that there aren't bugs. It's to set a bar that everyone understands and can rely on and replicate. If you do find another bug, okay sure. You can add it to the test suite. In the meantime, everyone knows what is known to work and where the gaps are.

To me, testing is about establishing areas of confidence and about increasing the confidence that you have in what you've built and how it interacts with other things.

Edith:     Kind of like the known knowns, the known unknowns, and the unknown unknowns.

Sam:       Right. If you have a test and it passes, that's a known known. If you have a test and it fails, you probably shouldn't ship that, but at least you know it fails. If you don't have a test, that might be fine because you might know that you don't have a test in a certain area.

Edith:     Yeah. We used to call that 40% coverage or 50% coverage.

Sam:       Right. There's always some part of your system that's really hard to test. Sometimes, it just isn't worth the effort to figure out how to test that. It's useful to have tests everywhere else so that you know if something goes wrong, it's probably in that area.

Edith:     When we were just moving fast, our QA would just complain. We only have time for 50%. You pick.

Sam:       Right. You have to prioritize your effort in it. Just to complete a thought there, I think that area of testing being about increasing and establishing areas of confidence. It makes much more sense in the context of continuous delivery. I think that's part of why people have missed the point because continuous delivery is also kind of new. People are doing testing in the context that the tests are going to be run occasionally by developers when they feel like it or maybe by a QA team whose job it is to effectively do a really slow continuous delivery process and date releases.

Paul:      I'm a tiny bit confused by it. I guess I just don't get the implications. In fact, I'm not 100% sure what it means to increase the ... I'm sorry. Say that again.

Sam:       Establish areas of confidence

Paul:      Right.

Sam:       Increase your confidence in ...

Paul:      What does that mean? Confidence that it works? Is that ...

Sam:       If I was to take an extremist view point, I would say the point of testing is to allow you to do continuous deployment. In which case, it's confidence in your ability to release this stuff.

Paul:      Got you. Got you. Yeah. I don't think that's too controversial at all. I don't think I've heard it said that way. The other ways I've heard it said are reducing the risks of deploying software, which I guess is very similar.

Sam:       To me, that's the flip side.

Paul:      Yeah. Or to prevent regressions, which is again very similar, a very similar concept there.

Edith:     I think every time you release, there's some risk though. Every time you change something, by a varied difference, you're increasing the risk

Paul:      Right, right, right. Yeah.

Sam:       But do you know where you're taking risks? And do you know how much risk you're taking? Often the answer is, we'll see what happens.

Paul:      Generally, when you're taking that idea, it's not just the idea of increasing the confidence that you have in your software. It's not always testing. That's the solution to that. Monitoring is the thing that I find is particularly. Slow rolling and feature flags, which I don't know if you know, our company provides feature flags as a service.

Edith:     Yeah. I was super excited.

Sam:       It's not a company called LaunchDarkly, by chance?

Edith:     I think so. Paul, Paul.

Paul:      This is now me almost every ...

Edith:     Thank you, Paul. I'll also point out that Circle CI is now using us is now using us for their own feature flagging.

Paul:      That's awesome.

Edith:     Yup.

Sam:       Woohoo.

Edith:     This station break is now over. Back to discussion.

Paul:      The monitoring and feature flags and that sort of thing are all part of this idea of can I reduce the risk, what is the confidence I have that the software goes at?

Sam:       This is exactly the conversation I wish people would have with, for example, their product managers. When they said we need to write some UNIX tests for this, the product managers say why because you have bugs anyway and we don't have time. We have to ship now. I wish people would talk about the package of things you do to increase confidence. We got to need some testing here and we're going to need some monitoring here.

Paul:      Right. I think, as well, when there's that conversation, I feel those kinds of parallels in the security world, that you're having that conversation with Pms. There's this sort of moral reason for doing it.

Sam:       Right.

Paul:      We're developers, and we're the sort of developers who write tests or who value security or whatever those things are. We refuse to release something which isn't properly tested or whatever that thing is. That conversation with a PM inevitably goes sour. I see comments on hackneys where people hate product managers or describe all sorts of mal-intent to product managers, which is never a feeling I've had.

Edith:     Never?

Paul:      No. I've never ... Anyway.

Sam:       Woah, woah, woah, woah.

Edith:     Paul's like I refuse to get dragged into this.

Paul:      Yeah. If the conversation is not ... We write UNIX tests because tests are important or 80% coverage is the thing that God wrote on the stone tablet and we shall do it. This helps us maintain confidence. We know that next week's release is going to be on schedule because we are confident that we won't be breaking these releases.

Sam:       That's exactly it. I think the reason I like using the word confidence here is I think it's common ground. The developer wants to be confident that what their being asked to support ...

Paul:      Right.

Sam:       Will work to the degree they think it's going to work. The product manager wants confidence that what got built is actually what they wanted. They want confidence that they'll actually hit the milestones that people have told them they're going to hit. All of those things are impacted by things like technical data and the complete lack of testing.

Paul:      Right, right.

Edith:     Yeah. I think you're talking about product managers kind of as a monolith themselves.

Sam:       That's fair.

Paul:      Is there a microservice model of product management.

Edith:     No. You have this axis ... It's actually three axis, quality, time, features. At any given time, a good product manager is trying to balance between all three.

Sam:       Right. I think you can have a conversation like, "Hey Jane developer. We really need to get this extra feature into this coming launch because there's a customer that really wants to see it." I'm Jane developer. I'm not going to change my voice. "I don't think we're really going to have time to ..." Sorry. "I don't think we're really going to have time to get this feature because it's kind of late in the cycle and we'd have to do a rush job. It's going to be really important to hit the windows." "It's just one customer so we don't necessarily need it to be at 90% confidence. Is there anything you can do?"

Paul:      I see what you're saying.

Edith:     Yeah.

Sam:       "To get it done at a 50% level of confidence for now and we'll acknowledge that we'll have to fix that up later if we want to take more customers on." That might be the end of the conversation. Or Jane might come back and say, "Well, I think we could do that, but it might impact some other part of the system because we'd have to make a change to this service. I'm not sure it would stand up under the load, so it would actually reduce my confidence in the other part of the system that affects all customers." Neither answer is right or wrong.

Paul:      Right.

Sam:       That's something that both sides can.

Edith:     Yeah.

Sam:       Both sides can take part in it.

Paul:      It's interesting that your use of like a scale of confidence there. You do see this concept. You hear people talk about a minimal viable product.

Edith:     Yup.

Paul:      Which is a lower confidence model. Tracer bullets is another one.

Edith:     MVP is one of the most misused terms. I hate it at this point.

Paul:      It's interesting that this kind of provides a figure that you can adjust. There isn't just is this a minimal viable product, there is do we have 10% confidence that this works?

Sam:       Right.

Paul:      Do we have 50% confidence that this works?

Sam:       I think the numbers people will pull out of a hat that people can have some common ground on vague numbers.

Paul:      Yeah, yeah, yeah.

Sam:       Everyone roughly knows what they mean by 90% confidence.

Paul:      Yeah, yeah.

Edith:     I think it also comes down to the culture. I've been at companies where everybody says we're fine with stuff breaking and stuff breaks ...

Edith:     That's when people start not trusting oh it's fine to have 50% coverage. You can have 50% coverage, but if this thing breaks, I get yelled at and perhaps even fired.

Paul:      I think a lot of this comes back to the team dynamic and whether you have a good faith belief that the promises that you're making are believed to be understood in the same context in which you're giving them. If you have a boss, a product manager, a colleague, whatever it is, and you tell them 50% and they hear oh great that's going to be 100% and I'm just making whatever promise, it's not going to work. That's going to end up being a disaster in the future. Good faith, I think, is a very good term for this.

Edith:     Yeah.

Paul:      If your team works and people are good colleagues to each other and there's a good team dynamic and people hear what you say when you say it, I think that works very, very well.

Edith:     Yeah, I agree.

Sam:       I guess one interesting thing is people to have tendencies to over-report or under-report their confidence in something. That can depend on the culture and also their personality.

Paul:      Right, right, right.

Sam:       You have people who are always reluctant to sign off on anything because they know there is more they could do.

Paul:      Right.

Sam:       Or they're used to having their promises taken at more than face value in the past.

Paul:      Right, right, right. Does the standards drop where someone says how long will it take to deliver this feature, and they say two months, and then someone says, how about one month? They take their estimate and ask them to cut it in half. If instead, the conversation is we can get 90% confidence in two months. And someone else says I don't need 90% confidence. I actually need 35% confidence. Would we be able to get that in a month? Maybe there response is you can have 35% confidence tomorrow. Or something else along those lines where people actually working towards a common goal.

Sam:       Yeah.

Paul:      Rather than there being conflicts between what people are asking for and what other people are delivering.

Sam:       That's huge if it's no longer two differing interests trying to find a compromise, but if it's two people with different skill sets working towards the same ...

Paul:      Right.

Sam:       Working towards a business goal, or even figuring out what the correct business goal is in the space of these constraints.

Edith:     Yeah.

Paul:      There's a framework that I used early in Circle where often when developers are talking to each other, they talk about implementations. They say I think we should do it this way. Someone else says I think we should do it this way. People throw out lots of reasons why they should do it their way or their favorite way or whatever.

The way that we overcame this is we started by stepping it back a little bit. We had three levels. We had problems, also known as goals sometimes, solution, and implementation. Whenever we'd be discussing things on the implementation level, we'd take a step back. What is the problem we are trying to solve? Get on the same page with the problem that we're trying to solve. Then, decide, based on the problem, what is the solution that we're trying to achieve? That can include things like confidence levels and that sort of thing. Then, when you get down to discussing implementation, that intends to be relatively trivial because you've agreed on the problems or the goals or whatever. You've agreed on how you're going to achieve them and then the implementation just kind of falls in naturally. Implementation is kind of the conflicting schedules, trying to reach a compromise, and the problems and the goals is more everyone on the team getting aligned around a common purpose.

Sam:       Alignment.

Edith:     Yeah. Alignment particularly backs the time. Sometimes, it turns out that there really wasn't an understanding of when something was needed.

Sam:       Right. Yeah. People don't even necessarily communicate that on either side.

Edith:     Yeah.

Sam:       Actually, I wanted to ask you, Edith. Since you stood up earlier for the internal reality of product managers as not just a monolith, what do you wish you heard from the teams you've worked with that you weren't necessarily hearing?

Edith:     It's funny. I started off in engineering.

Sam:       Right.

Edith:     I started off in engineering, and then I moved over to product, so I've been on both sides.

Paul:      That's what every product manager says.

Edith:     Well, you're a product manager now, Paul.

Paul:      Yeah.

Edith:     When I was an engineer, I was just like "Oh my God. Here comes a product manager again, asking me for more stuff. We're already totally overbooked, realistically a week behind schedule, lucky if only that." I was working at Bigger Enterprise Company. Also, what happened is we would get a lot of bugs from the field. It was this constant thing. Not only did we have to build new features, we had a platform burning out from under us because we were installed software and we had to do an update every time somebody came up with a new app server. We would have to do a major rev.

Sam:       And probably a convincing reason why each of those things were urgent.

Edith:     Yeah. So when the product manager came up, we were just like, "No. It doesn't matter what you're about to ask for. Just no." Then I became a product manager and I was like "Oh."

Sam:       These things are actually happening.

Edith:     Yeah. I think the best thing to semi-answer your question is empathy. I think it's also very good to have some tension between product engineering.

Sam:       That's interesting. Why's that?

Edith:     You got to ask for stuff. I remember once, we were like a month late on something, and the VP of marketing asked for one more thing. We were already a month late. I was just like, "No." He said very nicely, he was Irish. He said, "I don't know till I ask."

Paul:      Okay.

Edith:     In marketing or products, sometimes you don't know how hard something is.

Sam:       Yeah.

Edith:     Sometimes, in engineering, we would be like why don't you just ask for that? It's actually really trivial. When you're on the other side, something you thing is hard could be easy.

Paul:      Right.

Sam:       I've even seen the extreme version of that where asking for the next thing makes people realize that they misunderstood wanted for the previous thing.

Paul:      Yeah.

Sam:       Now that you're asking for that thing, they're like well why didn't you say that in the first place? We can do this whole thing so much simpler.

Edith:     Yeah. Exactly. Again, I'll go back. I think all problems are basically not tools, but just empathy and having a team. Unless you ask for something, you don't know.

Paul:      Running out of time here. I'm sorry. At double speed if possible. Did you have a question about Hadoop?

Edith:     Yeah. Sammy, you said that you could do continuous deployment in Hadoop, but I wanted to hear more about that.

Sam:       The interesting thing about Hadoop is you're sort of deploying into an environment in the same way that you're deploying servers. The only difference is, instead of deploying something that's going to be constantly being hit, you're deploying something that might run immediately, or you might even be deploying something so that it can run on a schedule. If you squint at the problem, it's actually very similar. You may have a staging environment where you want to run your Hadoop jobs first. You may have a battery of tests you want to run.

Where it gets interesting, is a lot of these things are sort of new to the Hadoop world, so a lot of the ways people are writing Hadoop jobs don't actually have great testing support, or it's at least a new thing. This whole field is sort of figuring itself out. To make it a bit concrete, at LinkedIn, a lot of Hadoop jobs are named Pig, which is this sort of sequel-like dialect for writing maps for these jobs basically, which sounds great because it's nice and easy to read and write. You don't have to think too much like a programmer, except until you imagine that people are writing hundreds of lines of basically sequel. Now that this thing is powering, it's an equal open product. Because it looks like a sequel query, it's not obvious to figure out how to test this thing. People are starting to write unit testing for mWorks that can test a Pig job. People are moving to frameworks, like Scalding and Spark, which have better unit testing sort of built in.

Then you've got some tests. The question is who's going to run them? When are we going to run them? Are we going to make sure that we don't deploy stuff that doesn't pass the test? Now you're in what looks very much like continuous innovation situation.

I guess another interesting place where, especially continuous deployment starts being actually really useful. You have this very common problem with Hadoop jobs that the standard workflow is somebody writes it. They test it on some data they have. They build it up into a big double and double it into the grid. They just took the double they had on their machine and ran it on the grid. Let's hope it did the right thing. Let's hope it had everyone's changes in. Maybe it ran, and these things run for hours overnight. It failed. How do we debug that? Has anyone got the code that ran them? Often the answer is no. If a team wants to get away from that situation of people just uploading whatever they've got lying around them and the machine and maybe have the concept of versioning, for example, so you can say it was build number one three two or that's this version of the code. It's really useful to have a centralized point plan that these builds go through that can assign a version of those two things.

Actually, moving to a sort of trunk model with continuous deployment point plan is in some ways even more valuable for Hadoop flows. I feel like the team is doing any kind of deployment, I've already got a solution to that problem. It's probably not worth running in production.

Edith:     That's fascinating.

Paul:      It sounds like exactly the problem that the rest of the world has dealt with. People used to deploy whatever the hell was on their machine.

Sam:       Right.

Paul:      Moved into a standard CI pipeline and promoted things and so on. It kind of feels like the work that they have to overcome this, I feel like people will move on to the next thing after Hadoop rather than actually solve the problem.

Sam:       Let's say there is a lot of work going on in this area at LinkedIn. LinkedIn has a big continuous deployment set of tooling.

Paul:      Yeah.

Sam:       It's actually been written in a reasonably generic way. They're working on extending it to work directly with Hadoop jobs and set it into the same ...

Paul:      Oh, interesting.

Sam:       The same pipeline and the same workflow everyone else is using. There are sort of company leverage benefits of all the teams using the same tools, even if we're writing real time services and we're writing these offline data crunching things. It's still quite nice if you can move somewhere between those teams and they still know how to the work flow works.

Paul:      Right.

Sam:       That's the other big thing of continuous deployment, right? You never need to educate someone about how to deploy your stuff again. The more different your deployment is from what people are used to, the more useful it is.

Paul:      Right.

Edith:     Interesting.

Paul:      I wish we could keep talking about this forever, but I think that is time, unfortunately.

Edith:     But it was just getting good, Paul.

Paul:      That's the same problem every week.

Edith:     The same problem every week. Thanks, Sam. We really enjoyed you coming by.

Sam:       Yeah. I really enjoyed being on the show. Thank you for inviting me.

Paul:      Thanks for listening to this episode of To Be Continuous, brought to you by Heavy Bit, and hosted by me, Paul Biggar of Circle CI and Edith Harbaugh of LaunchDarkly.

Edith:     To learn more about Heavy Bit, visit HeavyBit.com. While you're there, check out their library, home to great educational talks from other developer company founders and ...


