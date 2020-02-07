---
author: andreaech
comments: false
date: 2015-11-18 18:06:33+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-effective-team-structures-w-special-guest-kris-gale/
slug: to-be-continuous-effective-team-structures-w-special-guest-kris-gale
title: 'To Be Continuous: Effective Team Structures w/ Special Guest Kris Gale'
wordpress_id: 693
categories:
- To Be Continuous
---

In this episode of To Be Continuous, Edith and Paul are joined by [Kris Gale](https://twitter.com/kgale), Co-Founder and CTO at [Clover Health](https://cloverhealth.com/). They talk about what effective team structure for Continuous Delivery looks like.  This is episode #7 in the To Be Continuous podcast series all about continuous delivery and software development.

This episode of To Be Continuous, brought to you by Heavybit and hosted by Paul Biggar of CircleCI and Edith Harbaugh of LaunchDarkly. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.


Edith: So, Kris, what do you like best about continuous delivery?

Kris: So, I like continuous delivery, because I think it’s sort of the first step of building a learning organization. It’s sort of a fundamental capability that a team needs to be able to learn collectively about what it’s doing in the world. The first step is being able to sort of ship increments of value continuously.

The second, I think, is to be able to measure the result of any incremental change you’ve made, so you can back out of a bad path that you’re on, or sort of refine what you’re doing and know that quantitatively.

The next step then, is to move from a sort of historical corporate planning, so this is a our six-month milestone, our two-year roadmap, our marketing commitments for Q3 of next year, into sort of an assumption that if we are shipping continuously and learning continuously because we’re measuring what we’re doing, whether it’s quantitative or qualitative measurements.

The next step is really being able to assume that in your planning, and know you’re going to have more information in the future than you had in the past. So your plans that you made six months ago are necessarily lacking information than plans you would make today would have, so sort of institutionalize that.

And then kind of the last part, and this is all kind of enabled by continuous delivery, the last part is building organizational fluidity.

So as an organization, whether it’s your project planning structure, or your accountability to your work flows, are fluid, so if you learn something new, you’re not locked into, oh we have a sixth person, I don’t know, sign-up flow team, and we just discovered that we have no levers for moving engagement right now in the sign-up flows, so we’re committed to that and we’ve got this implicit prioritization that’s built into our org chart. So, to have organizational fluidity where you’re adapting the organization to what you’re learning continuously.

Edith: Oh. You know that’s fascinating. Paul and I have talked a lot about, I think, more the mechanics of continuous delivery. We put it as kind of the last step to software org, when you’re really talking about how that changes entire organization beyond software. So, this would be a great time for you to introduce yourself, and tell us more about you.

Kris: Yeah, so I’m Kris Gale. Most recently, I was the VP of Engineering at Yammer. I heard you talking about Yammer in a previous episode. I’d love to dig into any of that, if you’ve got questions. Currently, though, I’m the co-founder of a company called Clover Health. So, what we’re actually doing is offering health insurance for seniors, with the idea that we can fill gaps in care, and actually prevent hospitalizations.

We’re not trying to be people’s doctors, but we’re trying to look across their consumption of health care and say, “Oh, here’s an opportunity ‘to inflect the probability with which ‘this population of people will be admitted to the hospital.” So, for example, making sure they get treatments regularly, get follow-up visits with specialists, that particular bio-markers don’t deviate outside of a specific range. And all this stuff is really interesting to me, because the health care industry as a whole doesn’t change what it does continuously.

We’re sort of locked into what people learned in medical school, or what people learned on their first day on the job at, say a big health insurance company, or something like that. But, to be able to power workflow with software, you’re able to continuously iterate and continuously refine and optimize the intervention protocols that are leading to these prevented diseases.

Edith: Yeah, I mean, I heard that you were pretty good at data loops, and that this is just basically using data loops for good, I think is how you say it.

Kris: See, the way we were talking about data loops, we were actually talking a little bit before we walked up here, is this idea that there’s something you intend to do. There’s data that you collect in doing it. There’s your objective assessment of that data to determine whether you’ve added or removed value or improved something.

And then closing the feedback loop, to get back now to actually modifying what you’re doing, and form find out new data. So, that’s sort of the data feedback loop, is from doing something to measuring it and deciding to do something differently the next time.

The tighter you can close that feedback loop, the more opportunities you have to optimize in a short amount of time.

Paul: So, it’s kind of what you might call the shipping loop, if you implicitly believe that data is a key part of shipping.

Kris: Yeah, yeah, and I would say that I think I do.

Edith: No arguments here.

Paul: Well, I think it is interesting, because I think that a lot of people don’t actually have measurements as part of their feedback loop, and especially, I think this especially happens in a small organization, where you have a start-up that sort of comes out of a founder’s vision, or something like that.

And so, one of the questions that I’m very interested about is, you were doing a big thing, with lots and lots of people. And now you’re doing a very small thing with, I presume, a small handful of people. How much of what you’ve learned still applies at that very small scale?

Kris:


<blockquote>So, yeah, a lot of the project workflow strategy that we came up at Yammer was really about how do you maintain that agility, that velocity of value delivery, and ability to react to new information, and not be locked into, “Well, this is just the way we do it,” in the face of new information. At scale.</blockquote>


So, Yammer’s whole process was really about, how do you take these advantages we had, when there were like four or five of us in the really early days, and not have that big bureaucratic company, “Oh, we know we should be doing something better, “but we’re not,” because of momentum, inertia, bureaucracy, all these things. Like, how to break that. So, what’s cool about starting over with a much smaller team is, we’re just there again. We’re back at that five person size.

Edith: You’re a lot bigger than five people.

Kris: We are now, yeah. So, like nine months ago, we were. We’re like 65 people now, already. It keeps growing really, really fast. It’s been really helpful to me to have been through the process of scaling a software engineering team and seeing what that looks like. So, it’s like, “Oh, I’ve seen this problem before, “not worried about this.”

Paul: So, when you started, did you immediately set out organizational goals, and mission, and values, and that sort of thing that would help the company scale it?

Kris: Yeah, no, that’s a great question. I’m obviously a really big believer in the way we approached this problem space at Yammer, but I didn’t want anything to be dogmatic. I didn’t want anything to be–

Paul: You wanted it to grow organically.

Kris: Yeah, I wanted it to grow organically, to a certain point, but there have definitely been times where I stepped in and I said, “Nope, I’m buying a physical board “to track our projects, “because, just the way we’ve been doing this “with sticky notes, “I know that it needs this other dimension “of information capture. “I know that we’re suffering because it’s not there.

“So, I’m gonna actually pull the boss card and do this.” There have only been like three or four times I’ve done that in the last year, but it’s things where, like– Okay, I’ve seen where this goes off the rails, if we don’t address this right now.

Paul: And is that a result of knowing, sort of directionally, how the company should be doing things, or setting things up in some way that you didn’t get, that you didn’t end up in these bad places?

Or was it all sort of retroactive, and you know, a couple places where you pulled the boss card?

Kris: Yeah, it was mostly, like, observing patterns, saying, “Okay, we made this mistake three or four times, “and I’m noticing that our process or our approach here “is divergent from a known good approach “that I’m aware of.

“So, let’s at least–” I still wanna give the team full empowerment to iterate and own the process themselves, but let’s at least just pull the boss card, get it back on the rails, and then say, “Okay, let’s see how this works.” Just give everybody a chance to work in a way that I know to be okay for a few iterations, and then give them the keys again, and say, “Okay, take this where you want.”

Edith: Also, Kris, what I’m dying to know now is, what are those three or four key things where you gotta play that card?

Kris: Yeah, so, one is single project focus. Really, really important to me for software engineering teams. So, what I mean by that is, if you are on a project, that is your only accountability. You are not being split between three deliverables.

The other is that everybody work in cross-functional teams. So, that means not giving, for example, I might tell you, “Build out the back end for this feature, and I’ll do the front end.” So, in order for us to do that, we would have to agree to the abstractions ahead of time.

And again, I’m pretty opposed to planning, and locking in planning, because the information that we have now, when we’re trying to lock in those abstractions, is going to necessarily be incomplete.

Edith: I love that quote, because it’s so true. I think you put it more, it’s like you always know more in the future. It seems so obvious.

Kris: Yeah, I was actually– So, we had Parker from Pivotal Labs over at the office yesterday, and he said that there was this saying they had a Pivotal, that I really, really liked. He said somebody there would always say, and I wish I could remember who it was, would always say,

“You will always make better decisions with more information, and you will always have more information in the future.”

This is so much more concise than any way I’ve ever said that. But I think it exactly captures it.

Edith:


<blockquote>But, on the other hand, my old boss, Gregg Brockway the founder of TripIt, he always said, “A good enough plan today is far superior to a perfect plan tomorrow.”</blockquote>


Kris: Absolutely.

Edith: He’s like, “You just gotta start moving.”

Kris: Yeah, but I think the key is not locking yourself into that “good enough” plan. To allow yourself the mutability of changing that plan over time, so you’re not constrained by that.

Edith: Yeah, but that was TripIt. I mean, I think he’d seen so many, because he came out of the travel industry, where people just got paralyzed. Like completely paralyzed. “Oh, we need to plan for five years, “and what business travel will be like then.” It’s like, well, nobody knows.

Paul: I think the kind of key point to that is that in order to get that information, you have to get moving today with whatever information you have available. Otherwise, you’re just not gonna have that future information. You’re gonna be in the same place.

Edith: Well, look, sometimes, though, it’s painful. Sometimes you move backwards, then. Like, you don’t always move forward. Sometimes you start moving, and when you’re looking back, you’re like, “Actually we took, like, three steps back “before we started moving forward.”

Kris: It can definitely happen.

So to complete that thought, when we assign teams, we would always assign a cross-functional team with a business objective. So, it would never be I give you a back-end task, and I take the front-end task. It would be collectively, let’s accomplish this business goal.


<blockquote>So hopefully, we’re iterating day by day on the abstractions. So, we are collectively accountable to one another, and to this business goal we’re trying to deliver. Not onto some specific set of tasks that we broke off when we first decided to assign out the work.</blockquote>


So, that’s one of the other ones, is always cross-functional teams. Always single project focus within those.

Paul: So, there’s an interesting thing that you’re talking about there. It’s not just cross-functional teams, but it’s also that those cross-functional teams get put together for a specific project, is that right?

Kris: That’s absolutely right.

Paul: So, are those teams that will have worked together in the past? Is there explicitly trying to make sure that the people know how to work together?

Kris: Yeah, so this is one of my other core principles that I am pretty, pretty set on, which is rotation, is this idea that cross-functional teams are rotational and ephemeral. So, that would mean that maybe the three of us come together to ship a feature.


<blockquote>We’re all within the same organization, but when we’re done shipping that feature, we’re gonna break up.</blockquote>


You might be the back-end person that goes onto another iteration of this feature area, or maybe, you know, the two of us work on some other feature. Maybe it’s three completely different people. But constantly rotating people around, I think is really important in an organization.

I have totally heard the arguments about, you know, you can build high trust teams if they’re stable and stay together. But I’m trying to optimize for trust across the entire organization. So, across Yammer, we had 220 people in engineering. They would all rotate through these two to 10-person cross-functional teams together.

Which meant that you, basically within three to six months, would work with a pretty significant portion of those 220 people, and would start to build trust across the larger organization. Whereas had we just torn off four people and said, “You’re a team,” they would– And I’ve seen this throughout my career in engineering, where it’s like, “We do everything right, and that team has no idea what they’re doing.”

Edith: It’s their API’s are bad.

Kris: Yeah, yeah they use this weird language, or this approach, or we use this style guide, or whatever. So, it sort of forced that rotation, so that we’re all sharing best practices among one another and building, maybe lower trust, maybe not getting to that very, very, very highest level of trust among a group of four people, but across the entire organization, getting to like 40% or 60% of what’s possible versus 0% if you don’t ever work with those people.

Paul: So, interested in structurally how that ends up, because one of the things you got when you split people up by team is you end up with a sort of microservices architecture.

And this team works on this repo, or this project, or whatever works on this service or this API. And when you have those teams that are forming and splitting up and they’re ephemeral, and it’s only a small period of time, architecturally, what does that do to your application or your architecture, you know, across your entire product?

Kris: Yeah, no, totally. It was actually very intentional that we ended up with that kind of architecture for working this way. For two years, we had a big monolithic Ruby on Rails code base, and for two years we said, “This is a big problem. We should break this up.”

And everyone agreed, and everybody was on board with breaking it up, and two years later, we had never done it, because we continued to work in such a way that supported that sort of architecture.

So, the key for us was to say, well one of, the– So, something to dig into here a little bit, is these cross-functional teams are made up of representatives of what we call functional teams. So, front-end engineering might be one.

Paul: Right, right.

Kris: We had one called Core Services, which I actually owned the service-oriented architecture that you’re describing. Or there’s little micro-services that collectively made up our service-oriented architecture.

Paul: And this is sort of a matrix style, where you’re a member of the team, but you’re also a member of the back-end team, or you’re a member of the front-end, or the core services, or whatever.

Kris: Yeah, so I might be a member of core services. My manager is one of the core services managers. But all the work I do is going to be within the context of the cross-functional team, with the front-end engineer, maybe a client’s engineer, whoever’s necessary to get end-to-end with a value proposition.

And then, I’m always going to be a core services member, when I go into these cross-functional things, but it’s the fact that all the members belong to functional teams that makes that team cross-functional.

Paul:      Got you. Spotify has a fascinating article or a case study about this.

Kris:        Yeah. There’s a paper on this.

Paul:      Yes. I think there’s like 4 different dimensions of their cross functional teams. You might be on the front-end team and then you’re on some sort of guild that’s interested in a particular kind of area maybe designer or some particular part of that. Then you’re actually on the team. There’s another layer that escapes me right now.

Kris:        I don’t remember all of the details but it’s a similar concept.

Paul:      Right.

Edith:     It reminds me a lot of being a consultant.

Kris:        Yes. If we’re in this room with a bunch of people actually the conversation I was having with partner from Pivotal was that this is actually very similar to how they did what they did which was consulting.

Edith:     Well, because consulting ... I was a consultant and it’s very much based on a customer. You are a body shop. Customer’s going to pay $200 an hour for people that meet their needs. It’s kind of like how do we assemble the A team of a front end and a back end, a product manager, a designer, to suit their needs. It’s very mercenary but yet it works.

Kris:        Mercenary in ... Do you mean that in like a pejorative way?

Edith:     No, I mean it in a very positive way. I think what you were talking about how some companies start to have silos where you said like, “We’re the 6 person sign up team.” We know sign ups so we’re going to protect the sign up turf whether or not anybody really needs sign ups anymore versus what is the overall need of the customer?

Kris:        Right. One of the things we were optimizing for it to really high level was to ensure that all of our engineering cycles were going to efforts that the whole company would agree is our top and most important efforts.

Edith:     Not I like working on sign ups but ...

Kris:        Right. Yeah. We’re constantly fluidly right we prioritizing. Going back to those sort of 4 phases which by the way is stolen this guy Nate Fink who worked with us at Yammer. He actually took over my job there and ...

Edith:     You never steal anything. You just popularize ideas.

Kris:        This is completely stolen. His framework and these 4 ideas. I think it’s just a great way to put it. The fourth is this organizational fluidity that allows you to reallocate staff to the things that are most important based on what you’ve most recently learned. It was really to us that if our CEO walked into the room and said, “What are the engineers doing?” We can point at a single document or in our case it was like a physical project board and be able to point to the 10 projects that were staffed, all the names of people and be able to say, “We’re only doing these 10 things because we have single project focus.” We will do these in a small iteration and then after that we can reprioritize. A week from now some people will be rolling off 1 of this 10 and we can say, “Okay. What’s the next most important thing for us to put resources towards?

Paul:      It sounds like you always completed the projects once they started. Is that right? It sounds like there wasn’t a great deal of turn or just like this project is now important so we’re going to kill this one and move this one on the ... It sounds like people actually finish.

Kris:        I wouldn’t say we always finish it. If during the course of doing the project we discovered, “Oh. This is ...” For example, we would not say this is a 5 week project. Do 5 weeks of coding and then ship it at the end. When it was working the best and I think the best tech leads that were in these projects were able to do incremental validation throughout the 5 weeks. It might be 3 days in where Dark Launching a feature and we know that ... That’s right. Happy that I said that?

Edith:     Thanks Kris.

Kris:        A couple of days in we may Dark Launch an early, early iteration of it. The product manager can for the first time actually click it live with live data and maybe there’s no CSS on it, maybe it’s just like in a really sloppy form, but we’ll be able to see like, “Okay. Is this something that we want to continue to invest in?” If no or if we do an release of the feature to a small size of our users and then the metrics are really bad, we may just kill it without getting to the end of what was our initially spec as the feature.

Edith:     Yeah. I mean a real issue we have a TripIt was so we had the same sort of structure where we had we called “The most important tasks lists” which was like the projects. It was always about 30 projects of which the top 7 actually people on them. They would happen is if you were on the top 7, you didn’t want to let your people go. This project’s like tier thing. How do you know when a project is done? It’s like well, I have my engineers. I’m not giving them up.

Paul:      How are projects specified? It sounds like they were just very long-term projects that didn’t die?

Edith:     No. They were meant to be short so there would be something like improved sign up flow and then let’s pick on that one. That would bubble up to like the number 3 project and them whoever was the PM would just be like, “Oh, I have people. I’m going to just keep going.” How would you make sure that these teams were short lived?

Kris:        Yeah. One of the requirements of the products spec that would be the initial seed of a cross functional project was that that project spec have a definitive and finite done whatever that is. Maybe it’s like we come with a hypothesis that if we make this tweak to I don’t know message a replies will drive more engagement. Done is like when you’ve made that tweak and either confirm or disconfirm that hypothesis. Not keep flailing around and until you find something that works. That was really key for us is to agree ahead of time to what done is.

Paul:      One of the things I like about Project Based Teams is the idea that the Project Based Team can keep an eye on the parties within that thing. We’re going to fix this very, very small bug, a CCS alignment sort of thing or focus our efforts on a monumental rewrite. It sounds like you got the monumental rewrite taken care of. It’s obvious how that works. How do you take care of the we shipped it and it’s kind of like 95% perfect so we’ll call this done. There’s all these small tasks ...

Edith:     That’s what I meant what happened at TripIt and that’s why people clung.

Paul:      Right. How is it handled at Yammer?

Kris:        Yeah. You know it’s interesting. I think actually in complete honesty, I think we were not great about polish. I think there were some things that some teams would just polish and polish and polish other companies in a way that they produced a more polished result than what we did. I think there was a potentially logically coherent and rational argument that if we couldn’t measure the impact of that polish because there was no way to quantify that it had value, maybe we were actually doing the right things. Maybe the right thing to do was instead of doing the remaining 4, 5% of this project that’s going to make you feel really, really slick, maybe putting those engineering resources into starting to validate or invalidate some other hypothesis in some area. It’s going to deliver more business value faster. I would argue and I’m not saying that I know that for sure -

Paul:      Right.

Kris:        - that’s sort of the position that we took. Though on some features where polish was important, the definition of done could include that polish. It was fair for a PM to say, “No, no, no. This isn’t done until this is right in these ways and these pixels are lined up in this way. This all works. This edge case has to be dealt with. That’s part of the spec.”

Paul:      I guess the thing that I’m interested in is where the final results come out of. Let’s this put and wait for 3 weeks worth of user data or feedback or whatever. What happens to the team? Where does the polish get actually done? Is it in new project later down the line or how does that get handled?

Kris:        Yeah. My favorite way of addressing this was really just to elect the PM team. Not keep a backlog and I’m actually pretty opposed to like formalize backlogs we were talking about a little bit earlier. To have a general idea of the next time we revisit this feature area, I’d really like to clean up all these things.

Edith:     We’ll actually really love to hear you why you’re against the backlog.

Kris:        Backlogs are designed inventory. We’re talking about the definition of lean. I think lean at least in my mental model of it is about minimizing inventory.

Edith:     Definitely.

Kris:        I think if you have a backlog you have to committed to a bunch of design inventory. You’re saying that at some future point we’re going to do all this stuff. One thing that’s nice about not maintaining a backlog is you can actually choose never to revisit something. For example on this some of these polish questions, you might say, “Well, this interface ... It would be really nice if we fix this thing or whatever.” Then you do an iteration that just blows away that whole feature are. You never actually have to do that.

Edith:     That’s interesting. I sometimes like maintaining a backlog just to acknowledge that we’re explicitly not doing it. That’s kind of an anti-requirement. That in every meeting somebody’s ... Because somebody’s always going to pipe up, “Why don’t we do this?” Like, “That’s in the back log.”

Paul:      Right. In organizations that use bug trackers or where their entire thing goes into bug track because it’s very useful to have the bug that is marked as won’t fix so that you can always just refer to people we decided not to fix this for some reason.

Edith:     Because otherwise you could spend like half an hour in a mini rat holing on them, “Why are we doing this?”

Paul:      Right. You can start coming up with the same ideas again and again because you’ve blown away the institutional knowledge that it comes up from having that recorded somewhere.

Edith:     We’ve acknowledged that this issue exists and we’ve decided that we’re not going to do anything.

Paul:      You’re looking sort of cynical on this.

Edith:     Yeah.

Kris:        I almost think like deciding not to do something is potentially as harmful in that sort of like we’ve made a long-term plan. It’s deciding to do something.

Edith:     This is why you’re a great guest Kris.

Kris:        It’s just that argument.

Edith:     Of Course Kris has a new perspective.

Kris:        I like the rebubbling of things for reconsideration later when we know more. It’s like, “Yeah. We decided not to do that but we decided to that with incomplete information in the past.”

Edith:     That’s fair.

Kris:        “In the future we may have learned that some other feature area, this was actually really significant or something that looks like this feature was meaningful for our core metrics.” Now the next time this bubble’s up, we’ve got a fresh perspective on it. We can reconsider, “Okay. Are we going to do that or not?”

Paul:      One of the things I’ve seen that comes up with this is the sort of a constant back and forth between 2 non-optimal options. Say for example we can combine these things and we can separate these things. When they’re separated, it really looks like they should be combined. When they’re combined, it really looks like they should be separated. If you lose the institutional knowledge of this is why we combined them the last time, then you often end up with a whole load of like just spinning your wheels, getting nowhere on that. How do you avoid that?

Kris:        I think ... Yeah.

Paul:      I guess you’re not saying we’re just going to throw away all the institutional knowledge.

Kris:        This is another contrary position that I like to take which is I love losing institutional knowledge.

Edith:     Wait. Kris, you’re the best guest ever. You’re also our first guest but ...

Kris:        The most ridiculous one. I have some really good examples of ... I’m actually probably less informed about it. The question you’re asking is really about product decisions. Like product design decisions, UI decisions?

Paul:      I think it applies both to technical decisions.

Kris:        Okay. Let’s talk about the technical decisions. This is where I feel really passionate.

Paul:      Okay.

Kris:        There were a bunch of cases. I built most of the original messaging infrastructure at Yammer. I have strong opinions as a software engineer. There were parts of the code that I’d be like, “Hey. If you’re ever in there, ask me about it. There’s a specific reason it’s like that. I can justify all this. I would document it or there’d be really robust code comments. It said don’t touch this because it’s like this because of this.” Actually what I found was over time that super disempowering for future people. They don’t own the architecture decision. Some past person who wrote something down is dictating how they do their job now.

Paul:      Not the company anymore and you can’t actually talk to them.

Kris:        Maybe their now in some management role and they’re not available in that moment when you need to change the code because they’re off doing a one-on-one with somebody about something really important or talking to HR doing something. You’ve disempowered the engineers to do stuff. A lot of times what would happen is institutional knowledge often defends complexity. I really, really like losing complexity. I would rather people go to the code and say, “I don’t understand what’s going on here. All the test past when I stripped out this thing. I don’t know. Maybe I broke something. There was no test for it. Maybe it’s a weird edge case that just never comes up.” Let that bubble up again. Let the code shed the complexity.

It’s easier to maintain, easier to understand, easier to like into about and fix that bug if it comes up in the future. What really happens 99% of the time is by not having that institutional knowledge, the codes are simpler and that weird edge case that came up that 1 time that you wrote an elegant solution for, is actually just slowing everyone down and you’re better off for not having it.

Edith:     This is basically the buffalo herd of code. You know the buffalo herd? There’s a herd of buffalos, and the theory is you kill the weaker and the herd moves faster.

Paul:      Okay. The opposing view and I think something that most of my generation who have been educated with is this ... Jules Feiffer wrote this thing about the Netscape 4 rewriters or something where they just tossed it all away and then they had to rewrite the FTP module and they had to integrate with the 50 kinds of FTP service and no one had that technical knowledge, institutional knowledge whatever it is you’ll call it. I’m feeling some sort of like level of anxiety based on what you’re saying there. Yeah. It seems intuitively wrong.

Kris:        I think if you are forced to stop and rewrite and entire code base, you’ve done something wrong upstream. Like yeah, we can try to optimize for that case for ..

Paul:      Sure. Sure. I mean what you’re saying is we can take this module or this small thing and we can just discard the information that was involved in building it.

Kris:        What I’m talking about doing is getting to a situation where everyone is empowered to make fresh decisions to continuously re-factor and continuously modify the code without being disempowered by previous decisions. Potentially yes, trading the fact that we may temporarily lose some functionality and maybe the way to reintroduce it actually ends up being cleaner because now we’re free to do that re-factor or that cleanup or the simplication without .... That institutional knowledge is just so, so often used to like, “Don’t touch that because ... Don’t change that because ... We can’t move on to this new framework because ...” I never want those things. I would rather make the little mistakes and come back.

Edith:     I think a key part of this having a really good measurement system. I think Paul’s fear comes from like not just simply cross your code pace and then toss everything back out but have a lot of ... At Yammer, you had a lot of measurement. You had a lot of analytics. You knew that if you changed something and suddenly your conversion would down 20%, you even knew it.

Kris:        Test are obviously important for this. A well-tested code base. The test are to a certain extent found in institutional knowledge. The code should do this in this case or the product needs to do this in this situation.

Paul:      There’s then seem trade off there between ... You’re talking about test as 1 way to fix this and Edith’s talking about measurements. It occurs to me that tests are a sort of binary version of a measurement. The measurement is an actual business value whereas a test is a thing that someone wrote at some time in the past but that is black and white and irrevocable. You can’t break the test.

Kris:        No, I think you’re right. I mean the measurements are essentially a form of test that just aren’t so binary. Did we move engagement? Did we break our conversion ...

Paul:      It seems like the test are much lower value than by definition because the business value is measured in these KPIs or whatever the things are that you’re measuring.

Edith:     Yeah. I’d love to hear you talk a little bit more about Yammer’s measurement framework.

Kris:        Yeah. Yammer really cared about engagement, which was our most important KPI. We were sort of banking on the fact that as a kind of bottoms up enterprise tool, that the more people that use it and the more often they use and the stickier they were with the product, the more likely their companies were to buy the product in the future. That was really ... It’s pretty simple. It was like, “Does the user come back and continue to use the product if they’ve been exposed to this or if they’re in this group or if they have this functionality?” We obviously looked at other things like sign up rates and we can kind of break down so that when we saw that we had moved to the engagement numbers, we might say, “Well, is that because fewer people are making it through the sign up funnel? Does it mean that people who make it through the sign up funnel and do this 1 thing then don’t also this other ... You know whatever.” That really high level thing, the thing we cared about most was engagement.

Edith:     That gave you kind of the freedom to say, “Just find the re-factor code as long as we’re not touching this actual thing we care about.”

Kris:        Yeah. I mean ultimately like every project ... It’s a question of like they’re levels of where you’re looking at different things. If you’re re-factoring code, you’re really looking at test. I don’t think that engagement numbers are a useful tool for ... Because the latency in getting that data back is too slow. You can’t like, “I’m going to try to re-factor this and I’ll put this to production and I’ll wait a week for an A/B test result to come by.” I think that’s why tests are so helpful. You can run instantly. You can know just like did I break it? Whereas the engagement and the KPIs and those things are really around, did this increment of product change make the product better or worse? Better or worse was measured in terms of what we believe to be the most consistent leading indicator or value which was eventually sales. Was there a sense of tastes that was involved in that decision?

Paul:      What I’m trying to get ... You were talking about polish a little bit earlier. When you look at say a company today like Slack, one of things that really, really works for Slack is that it’s polished.

Kris:        Absolutely.

Paul:      I presume that there’s a human in there who’s actually making that decision. When you’re talking about the measurements and the engagement and the lack of polish. I'm interest in how was the taste measurement done?

Kris:        Taste measurement? Yeah. I think ... I don’t think quantitative product development is a substitute for product vision or product ... Yeah, vision I think is probably the best word for that. I think polish is very much probably a part of the Slack vision. I don’t know. I don’t know the product in there but it certainly is a use it seems like that’s the case. Yammer was very much about ... David Sacks was our original product person, the original CEO. There were certain things that I would considered polished. Not polished in the pixel perfect sense but in this feature really should be this simple or this should be as easy as this. That was very much part of his mentality when he was running product. We had other product leaders throughout the years who were optimizing for different things. I don’t think data ever replaced anyone’s vision of what Yammer should be. I think different people had different visions and probably differently valuable visions of where their product was going or what it should be. What the data really allows you to do is on your way to that vision that you have, being able to check your own assumptions and your own hypothesis.

It’s not like should it be polished or not is not what you’re going to get out of the data. It’s going be like, “Okay. I thought that working on this part of the thing would be more impactful but I’m not moving the metrics at all.” Somebody else had this idea that maybe actually we should be working on invites. That will be a nice viral hook. Let’s see if that actually moves the numbers. You can say, “Okay. Yeah. We’re moving the numbers a lot.” Sometimes like a negative test result was great signal for us. We tanked engagement by touching this. We know this is a lever. We know that okay, let’s continue to invest in this. Let’s try different versions of touching this. Because it’s in somebody’s product vision that this feature area needs to be improved but our first instinct actually made it worst.

Edith:     What was your first instinct? How did you tank?

Kris:        The inbox feature in Yammer was one where, I believe it was David, David Sacks, was sure that the product needs an inbox. We built an inbox and we tanked the engagement numbers. The first version of it was negative for engagement. If you’re really letting data drive and just had no vision and had no sort of belief about what’s right about the product, then you would just say, “Okay. Well, inbox is bad. We’ll never do an inbox.” We’re like, “No. We know this needs an inbox. This version of it isn’t what we needed so let’s try another iteration.” We tried a few iterations of inbox before we got something that was positive for engagement. It wasn’t about like what should we be doing, it’s about what is the right version of what we ...

Edith:     Yeah. That gets back to my original question about how do you know when a project is done?

Kris:        Right. Those were all separate projects. That was interesting. We didn’t just keep the same inbox team together for multiple flailing iterations of inbox. We said, “Here’s a hypothesis we’re testing.” Testing that first inbox hypothesis was a project. When I was done, when that was shipped, that team, if my memory is correct, it was years ago, that team broke up. Then that information from that failed test informed -

Edith:     The test was a success?

Kris:        - Well, failed in the sense that the engagement was negative. We didn’t roll it out. That information then went back into product planning to say, “Okay. We still believe in inbox. Now with this information from with this test result, now here’s what we believe to be a better iteration. Now we’ll prioritize that against everything else we could be building.” You can imagine like if that failed 6 times, that would probably lower itself in priority over time. I think we got it right on the 2nd or 3rd try.

Paul:      I have a question about the structure of that. Famously Yammer had 2 to 10 person projects for 2 to 10 weeks.

Kris:        Right. Yeah.

Paul:      You’re talking about these teams that are formed and then broken up and what I’m interested in is what was the structure that said, “This is going to be the team. This is going to be the thing. This is going to be the product vision.” What was the extra on top of all this?

Kris:        Yeah. Step 1 was that the product team would obviously have some vision about where Yammer’s going. Then they’d say, “Here’s an increment of product change we can bite off and build.”

Paul:      The product team wasn’t part of 1 of these projects? They’re like sitting to the side scoping and organizing and that sort of thing?

Kris:        Well, they would start. The product manager who built a spec that became a project would actually join the team?

Paul:      Got you.

Kris:        The product team collectively has a vision about where the product’s going. Then a particular PM says, “Here’s a thing I can design and have a team build.” That PM would do a spec and then we get to process we called “Spec Review.” The product team would actually ... Well, they had a process called “Product Review” where they would present it to the rest of the product team. Does this make sense? Does this fit our vision? Do we all believe this is right?

Paul:      How many people is the product team?

Kris:        I mean it grew from 1 person to I think ... At its peak, it was maybe 10 people?

Paul:      Okay.

Kris:        That sounds ...

Paul:      Not a massive team.

Kris:        Not massive. No.

Paul:      Okay. Was there more of the organization then that designed the projects and measured them and that sort of thing?

Kris:        Yeah. Let me walk through the sort of product life cycle. It starts it with here’s the thing we want to build. Here’s the incremental product change. Here’s the hypothesis we’re testing by doing this product change. That would then be approved by the rest of the product team. Yes, that’s something we think we should go forward with. Then it would be floated to the engineering them. We actually did this on Yammer, the tool itself. We would post it through a group called “Product Review” or “Spec Reviewer.” I forget the name of it.

Edith:     Yammer on Yammer?

Kris:        Yammer on Yammer. Yeah. We would post it on that group and then the engineers would chime in and basically say, “Okay. Given what you want to build, we think it does fit within our scoping constraints. We think we can do this between 2 to 10 weeks.” It’s going to require back end work, front-end work and someone from the client’s team. At least staff it with 1 person from each of those functional teams. Sometimes we’d say, “There’s just so much back end work to do here. We need like 2 or 3 back-end people.” That’s how we determine what the staffing requirements for the spec were. Then essentially spec would just be in the hopper and it wasn’t a prioritized backlog. It was sort of the set of like a fewish things we will do next when resources free up. Then every week we would walk over to what we call the “Big Board” which is our product planning board where all these projects are written down along with these magnetic tags that represent each of the people who’s staffed on the project.

Every week, things were finishing up from the prior week. We’d say, “Okay. These 4 people are freeing up. These 8 people over here freed up as well. Now we’ve got 3 specs that are approved. We know the staffing requirements. They’re ready to kick off as soon as people are free. Let’s just start slotting people into those slots and then the project would kick off.”

Paul:      Another member of the team would be analytics?

Kris:        We joined it to do the quantitative piece of this. Product engineering and analytics.

Paul:      Okay.

Edith:     What would you do if there wasn’t people exactly free like to your example of something needing a lot of back ends and they’re unfree right then?

Kris:        Yeah. This is the constant question people have is like there’s not always exactly 1.0 people units of work in back end and front end and whatever. They’re trying to optimize for efficiency. I think anytime you’re optimizing for efficiency in a research and development or product engineering org, you’re probably doing something wrong or making some bad trade off. If you’re like, “Well, there’s only 3/4 as much front-end work here as there is back-end work. We’ll let that person go early.” What inevitably happens is you’re getting towards the I’m buttoning it up, I’m getting ready to ship it. Oh, we just need to make this 1 front end change.” That person’s off with some other commitment so now you’re blocked. So now the throughput of the entire org, it seems more efficient because you’re capacity utilization is closer to a 100%. What really happens is you spend more time blocked. You go slower.

We’re not allowed to take that guy off the project that is gone because those are the rules. I’m not a front end engineer. If I’m on a project that’s got a little more front end engineering than back end engineering and I’m paired with somebody that I know to be good front end engineer, I can contribute value. I mean I know how to write code. I may not know the idioms of a particular java script framework but if you do and we’re working together, you can walk me through that and say, “Just stub out a subroutine that does this kind of thing or run use of the data in this way.” I can be useful. Which is really the values of cross functionality not just siloing tasks into people’s workflow.

Edith:     Cool. I have a big picture question which is Yammer, a huge success. Your most recent company Clover just got ... I called it a whopper amount of money. You know a hundred million. How does this kind of org scale up with so much money?

Kris:        Yeah. Clover’s interesting because we’re a health insurance business so it’s very capital intensive. I think like different from a SAaS business where we’re probably going to need a little bit more money right now at this stage.

Edith:     Well, you have it.

Kris:        Yeah. Thankfully. Really what’s interesting about Clover is it doesn’t stop with software because we’re not selling software to people. We have practitioners. We have social workers. We’re doing home visits. We have medical assistants that are doing clinical data abstraction out of medical charts. There’s a lot to do in a lot of different areas. I think this model like really helps us to do that because we can say, “We don’ have standing teams that are just working on the data processing for clinical abstraction. We’ve got engineers that maybe, yeah, they can do a couple of iterations on that.” Get the team of MAs spun up and pulling out important clinical signals from charts. They go off to work on a home visit logging so that the nurse practitioners when they’re in somebody’s home have a good tool on their iPhone for tracking all of the clinical observations they make in the home. We’re working on the data pipeline, data visualization or whatever.

We’re sort of fluidly moving around because as big as the team is right now and as many resources as we have relative to a startup of our age, we’re essentially trying to rebuild the whole software stack that powers healthcare in the US internally just for our own purposes. We’re constantly like reprioritizing and shifting so that organizational fluidity is super, super important to us right now.

Paul:      This seems like 1 of the key areas where you can dump the institutional knowledge of the healthcare industry as a whole because it’s so backwards and rethinking it from scratch is probably going to be a major advantage.

Kris:        You know it’s funny. One of our engineers, Jasmine, actually just recently said this in a thread. We were having a conversation about something we learned on a thing. She was tasked with organizing a bunch of for us it’s provider data, so the doctors that are in our insurance network. She was like, “The big lesson here is don’t trust institutional knowledge in healthcare. It’s misleading. It’s based on old assumptions. A lot of people have never even dug in to understand how this data flow.” Yeah. No, you’re absolutely right. We go about shedding industry in investor ... Institutional knowledge has been so, so important for us.

Edith:     It sounds it really is an interesting and important endeavor. What’s been the most surprising part to you?

Kris:        Surprising part of working at the healthcare space? There’s definitely been a lot. One thing is that so in enterprise software, if you were building something that had like self-service where people could just pay with a credit card, in your 2015 you would probably never build your own credit card processing.

Edith:     You use Stripe.

Kris:        You could use Stripe or something like that. In healthcare, we thought we would walk in with a bunch of that. Taking lab test results in this industry standard HL7 format, oh we’ll just use the official tools or the open source tools or the dominant IT vendor to do this. Almost every single time the answers been like no, no, don’t. Because all of everything is bad. It’s hard maybe for enterprise offer if people didn’t believe me that the right answer is rebuild it yourself because we’ve all been conditioned to like out of that not invented here sort of mentality. When you have upstream vendors that have no idea how to reliably give you a data stream or are dropping data or are misclassifying certain clinical things. It’s really, really important to get it right and to get it reliable. That’s why as an insurance company we’ve had to build such a big software team because data reliability is so important and data feedback loops.

I have a team of engineers that literally had to learn how Cobol codes integers because some of the upstream formats and probably not generated by a co-ball system still probably. I’m hoping but maybe. It’s just amazing how bad the state of healthcare tech is. I think that’s like such an opportunity for entrepreneurs who want to get into the space.

Paul:      It’s funny. I see this sort of thing where someone has made like a big generalization ... I’ll give a concrete example. When we were building Circle, Circle is built in [Clojure](https://clojure.org/). There’s very few libraries available. This library’s for HTTP but there’s not libraries for connected to GitHub using OAuth or something like that. We started building the front-end part of it where there was all these libraries for all these sort of things and we found that the time that we spent integrating those libraries was massive. Whereas the thing that we were actually trying to do which in this case was connect to get help with their Github via oauth was 3 API calls.

Kris:        Right.

Paul:      The time that it actually took to integrate these off the shelf vendor component, whatever the thing is, they’re built for a different problem than you’re trying to solve. They’re built for like a very abstract problem. You’re only trying to do a very specific subset of it. It’s often trivial to write that subset rather than try to integrate the thing that’s there already.

Paul:      Yeah.

Edith:     Kris, we’re really thrilled to have you as our first and best guest. Do you have any final thoughts?

Kris:        No, no. I think we’ve covered a lot of ground. I really appreciate you having me here. This was a lot of fun.

Paul:      This has been awesome. Thank you.

Edith:     Yeah. Thanks, Kris.

Kris:        Absolutely.

Paul:      Thanks for listening to this episode of “To Be Continuous” brought to you by Heavybit and hosted by me, Paul Bigger of CircleCI and Edith Harbaugh of LaunchDarkly.

Edith:     To learn more about Heavy Bit, visit heavybit.com. While you’re there, check out their library. Home to great educational talks from other developer company fathers and industry -


