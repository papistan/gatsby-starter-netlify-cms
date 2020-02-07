---
author: andreaech
comments: false
date: 2016-10-14 18:19:45+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-specialization-in-organization-design/
slug: to-be-continuous-specialization-in-organization-design
title: 'To Be Continuous: Specialization In Organization Design'
wordpress_id: 1284
categories:
- To Be Continuous
tags:
- AWS
- Dropbox
- full-stack engineer
- javascript
- mongo
- Pokemon
- specialization
- stripe
---

In this episode, Edith and Paul dive into the question of specialization. They discuss the pros and cons of working with specialists vs. generalists, and how your decisions in this area can have a wide ranging impact on your product and company._  _This is episode #25 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.



TRANSCRIPT

**Paul Biggar:** So, what are we going to talk about today, Edith?

**Edith Harbaugh:** We’re going to talk about the chocolate, but that’s for the end of the episode.

**Paul:** And how coconut is a desiccant?

**Edith:** So you’ve been told. Even doctors learn new things now and then.

**Paul:** So, the topic?

**Edith:** The topic is specialization.

**Paul:** How so?

**Edith:** I think there’s a lot of talk about full stack versus full-stack engineers. And I’ve heard both sides of this argument, even on our own podcast.

**Paul:** To define that, a full-stack engineer is someone who can write JavaScript, knows JS and knows Mongo?

**Edith:** Well, that’s one definition. I think the definition is usually just somebody that can write an entire application.

**Paul:** Sure.

**Edith:** [Kris Gale](https://twitter.com/kgale), who was [one of our guests before](https://blog.launchdarkly.com/to-be-continuous-effective-team-structures-w-special-guest-kris-gale/), talked about how he rotated people between different teams because he didn’t really want them specialized too much.

**Paul:** Stripe talks a lot about two shapes of people, people who are very, very broad, and then very deep in one specific topic. Like, some of my people are particularly good at AI but still know how to write a web stack or reuse one, at least.

**Edith:** I am of two minds of this. I actually got two degrees. I got an engineering degree and an econ degree. Part of my econ degree, we actually went back and we read The Wealth of Nations by Adam Smith, which pretty much kicked off all of econ.


<blockquote>Basically, a specialization is what allows industry to happen.</blockquote>


Originally, you had a farmer and his wife, and they would grow sheep. They would go out, they would herd the sheep. They would get the sheep fat. They would trim the sheep. The wife would sit, she would spin, make a sweater. Great.

**Paul:** Very specific gender roles there.

**Edith:** Maybe it was the wife who went out and tended the sheep, and the guy stayed home and spun.

**Paul:** Maybe.

**Edith:** No judgments. So, this is basically artisanal sweater-making. It is also incredibly inefficient because basically you’re talking a minimum of two years per sweater.

**Paul:** We’re definitely getting back to software at some point here, right?

**Edith:** It’s getting there. With industrialization, instead of saying, “Hey, instead of having one family unit make a sweater every two years, let’s have some people make the sheep, some people trim the sheep, some people card the wool. And let’s have machines that will actually spin it, and then another machine that will make a sweater.”

With this you can make a thousand sweaters in an hour. Are they handmade with love? No. They’re made in a factory somewhere, and the factories are probably geographically distributed from the sheep.But it allows intense scaling.

I think software has come from the same place where originally you had one person who basically coded everything, who made the database, who made the front end, who made the back end.


<blockquote>This made them understand the entire system and to be able to tweak it, but it was very inefficient.</blockquote>


**Paul:** Interesting. So the obvious thing here is that there’s many kinds of software but there’s at least two kinds that I’m concerned about. There’s software that is new and there’s software that scales. So there’s zero to one and the one to n, almost.

**Edith:** I think there’s a very important place to go on.

**Paul:** If you’re creating a new product, a new startup, a new software category or something like that, you’re probably going to build it with a very, very small team.And the very small team has to be able to do all the things, because you want the same people to hold it in their minds.

**Edith:** And also to be able to tweak very quickly.

**Paul:** Right. Your whole point is validate and iterate.

**Edith:** And to do that in a very short time.

**Paul:** Very short amount of time, yeah. So it’s much more like creating this artisanal sweater, assuming your sheep are already grown or something like that.

**Edith:** Well, even then you have a really quick feedback loop. You could say, “Hey, that wool was really dirty. Don’t take them to that pasture anymore.” And you have that control.

**Paul:** I feel our analogy is breaking down here a little bit.

**Edith:** No, I feel like the analogy is only getting better.

**Paul:** When you’re building a new thing, you need to iterate very quickly and get in front of people. But the industrialization, the spinning on the looms part of the analogy, is when you have a hundred million people using your product, or even where you have 10,000 people building your product, and you start to say, “We need to optimize the web stack. We need someone who actually knows something about databases to take this part over,” or whatever.

**Edith:** Or our onboarding emails, they were fine for where we were right then, but now we actually have the ability to start to optimize them.

**Paul:** Sure. And you can go several layers down, too. You start by, “Oh, maybe we need to rewrite the web server to lower latency.” And then it’s like, “Oh, maybe we need to rewrite this in C.” And then it’s like, “Oh, maybe C isn’t really that good. Maybe we need to make a new programming language that’s better.”


<blockquote>You just go lower and lower down the chain until you hit the order of magnitude that you’re able to hit with that change.</blockquote>


**Edith:** To go to talk about Dropbox for a second, there’s this big trend right now where people are either moving on or off AWS. Dropbox moved off AWS because they felt like it was something they had to take back in-house. But they were at the scale where it made sense.

**Paul:** Right, exactly. They got to $10 billion valuation, I think, and then it’s like, “Okay, AWS no longer makes sense for us.” Because they have the specializers.

**Edith:** They have the specializers. So I’ll argue and agree with you. I think people sometimes confuse what stage they’re at and they prematurely optimize either for scaling up, or they think they have to continue to do everything in-house.

**Paul:** I think this is the role of the full-stack engineer, or why people are so into full-stack engineers. When you’re super early, you need to not have to pass a feature to several different people to get it done.

Because that’s a lot of communication overhead. You really want to say, “This is a feature we need,” and someone who can bring up the AWS instance, configure the database, write the code, write the front end, and then there’s a feature that comes out of it.

**Edith:** That’s why I’m absolutely opposed to outsourcing when you’re an early stage startup, for your core engineering, if you’re a software company.

**Paul:** Absolutely. Outsourcing is ludicrous. I keep meeting these people who tell me that they have a great idea for a product and they just need to get it to a good outsourcing team and then ship it. And it’s like, “And then what happens after the first iteration or the first round of feedback? What are you going to do then?” And they talk about outsourcing to people who are in a different time zone.

**Edith:** Different language, different culture.

**Paul:** Oh my god, just imagine the feedback loop on someone in a different time zone.

**Edith:** I’ve done that. We outsourced before, to India, and it’s a different culture. Every iteration took at least three days.

**Paul:** Wow.

**Edith:** I think


<blockquote>people fail to realize how much in a startup how much of the product is everything, not just the code, but everything around it, like the documentation.</blockquote>


A lot of our customers read our documentation before they sign up, and they say, not to brag about or docs, but people say, “Your docs are lovely.”

**Paul:** Well, for a dev tool company, docs are marketing material.

**Edith:** Yeah, they have to be good. And so people think, “We’ll just ship our product and then the money comes in.” I am arguing passionately for non-specialization, but I think people cling to that for too long and then they realize that there is a point where it makes sense to start to break apart roles.

**Paul:** I think the first area that you start to see that that specialization is around the front end. Typically, you’ll get someone who can do some portion of the front end, so they can either design UXes, so the role of the designer, this UX designer, this graphics designer.

**Edith:** Interaction designers.

**Paul:** Interaction designers and typically on the front end of a web stack, you end up with a PM who’s doing some sort of UX or maybe that’s the founder or something like that. And maybe that role goes in with the engineer as well, who is particularly skilled at that. And then someone is writing the JavaScript and the app portion of it, and then someone’s constructing the CSS that styles it.

You end up with this conflict because usually a designer and an engineer, or let’s say a founder-type person or a PM-type person, all have overlapping skill sets and all feel that their contribution or ownership is around a certain part of it. You end up with feelings like a designer who is being told to “style this and make it a bit pretty,” or something like that. I think it’s how it usually manifests itself.

**Edith:** Oh gosh, you just opened up 15 years of memories in a second.

**Paul:** Oh no, anything you want to discuss or shall we leave that for your therapist?

**Edith:** This podcast is my therapy. I think there’s too much to say in a single sentence, except for,


<blockquote>I think people need to feel ownership of a particular area and they need to have boundaries and ownership.</blockquote>


Sometimes the worst part is that you have somebody in a role who is absolutely the wrong person for that role and that’s incredibly difficult.

**Paul:** Yeah, I guess the important part of that is that there has to be team ownership in the sense that, if one person individually owns it then someone else can’t own it, right? That ownership is a unique thing that someone has and that’s the point. That at the same time the team has to own it but there has to be someone who’s making a decision. You can’t just operate on consensus all the time.

**Edith:** That’s interesting, because I’ve heard of some companies that seem to operate on that. I’d say that my own company, LaunchDarkly, we are pretty consensus driven.

**Paul:** There’s nothing wrong with being consensus driven, but at the end of the day, you have to have one vision and you have be going in one direction. And that’s true at a company level. It’s also true at an individual feature level or at a product level.

**Edith:** And I think we’re about to go into Edith’s therapy, so let me talk about more general things.

**Paul:** You talked about front end and back end and that sort of thing as specialization. How else do you see people specializing?

**Edith:** An entire organization, once you start to get bigger, you start to specialize. You start to have people that just read emails. You start to have people that just do analyst relations. You start to have people that just do PR. You just start to separate out these various roles.

**Paul:** Within software, we talked about front end and back end. The things that seems obvious to me is that there’s now the people who build mobile front ends, there’s the people who scale and who focus on the dev ops side of things.


<blockquote>One of the points of dev ops was that the developers know how to do ops, right? And I think that’s died.</blockquote>


**Edith:** Oh, it’s funny because I’ve been going to a lot of dev ops conferences, because feature flags is part of dev ops and every dev ops conference I’ve gone to, people say, “Dev ops has no definition.”

Originally it was the fact that devs did operations, and now people like recruiters say, “We get a lot of requests for dev ops people in Atlanta. Do you know any dev ops people?”Which is a total perversion of the original intent.

**Paul:** The way that I thought this was going to go was that we would stick dev in front of everything and there’d be dev sales and dev marketing.

**Edith:** Well, that’s a dev evangelist.

**Paul:** Well, dev evangelists evangelizes the… You’re right. Exactly, so you stick dev in front of everything and then once you’ve got dev legal and dev janitor then everyone realizes there’s dev in front of every role and you drop it, and then it’s just “janitor.”

Because the world of dev ops has become so large, there’s so much to know around AWS and Google Cloud platform and OpenStack and cues and reliability. And it goes all the way down to how many ops are running into this thing and all the way up to how to write an ansible.cfg.

So the ops, now dev ops side of things, has become so large that I think you can definitely have a small team that starts to build their own at the start. But it really doesn’t take that many years before you start getting a need to specialize around that.

**Edith:** Yeah, I’d say, though, it has gotten easier. I remember we used to have a dedicated ops person just to tend to your server. You used to physically have somebody build you boxes.

**Paul:** Sure.

**Edith:** And you just don’t have that anymore.

**Paul:** Right. Yes, until you’re Dropbox’s size. You’re Dropbox who has someone who’s building servers.

**Edith:** Yeah, but that’s immense.

**Paul:** Yes, it is. It’s funny that there’s this feeling around 2000, that it took a lot of money to build a company. So people were raising $5 million Series A, because you had to build the boxes and you had to put them in your servers and someone was actually racking things and so on.

Then around, I would say, 2009 to 2011, there was this time where you could build a startup from very, very cheap. People are raising rounds of 500k and you’re getting somewhere with that. I think that that has completely changed again, because the size of the ecosystem that people are building for is just immense.

Now when you start a company, you need some dev ops stuff, you need someone to write a front-end thing which is really quite separate from how people are writing back end, and you need iOS, you need Android. They might be two separate people.


<blockquote>I think we’ve gotten to the scale of things where it’s gotten fat again. It’s not so much the lean, scrappy companies where two founders build it all themselves.</blockquote>


I think we’ve gotten to the point where the standards and the sort of things that people expect are actually much, much larger than that again.

**Edith:** I agree with you, but I disagree with you. I think you do need more than you used to have. I do think that’s true. I think you can be very choosy about where you invest first. I think you can either say, “Hey, we’re going to be mobile first, or we’re going to be web first.”

**Paul:** You do need to make that decision.

**Edith:** I think Android is not making money for people, so you can go longer without an Android app.

**Paul:** Interesting.

**Edith:** Unless you’re specifically making a decision that you’re going after the Android market.

**Paul:** I haven’t seen that. I don’t have an Android. Are people just leaving the Android app for some time later?

**Edith:** It depends solely on what you’re doing. If you’re a consumer app, I think you do have to invest in platforms. But even when I was at TripIt, we never built a Blackberry app.

**Paul:** Right, of course.

**Edith:** We looked at the numbers, and we were like, “This does not make sense for us.” We had a third party who used our API to build a Windows app, but it never made sense for us to build it internally. So you could still be choosy about what you’re doing, even if you’re a mobile app.

**Paul:** The flip side to this is that while the platforms get much, much larger and many more of them, the tooling around them get much better. I was reading today someone’s tweet about how they built their iOS app in nine months, and they built the Android app in one day because they use React Native.


<blockquote>I heard the term recently, ‘JavaScript fatigue.’</blockquote>


While the breadth of things you need to learn is getting broader and broader, at the same time there’s consolidation around things, and React and the world around React is one nice consolidation at the moment.

**Edith:** I think people don’t realize how good they have it, that stuff is in the cloud, and you don’t have to build and install stuff. We used to have to worry about app servers, web servers and databases.

**Paul:** You don’t, now? Well, I guess you don’t need to deal with app servers so much anymore.

**Edith:** No, what app servers, web servers, and databases our customers had.

**Paul:** Oh, okay. Yeah. I remember build scripts that dealt with 20 different Unixes.

**Edith:** We had an on-prem solution. It wasn’t on-prem back then, it was just our software, and I was in charge of the platform which was literally what version of Sybase and WebLogic we would support.

**Paul:** Oh, that’s a disaster.

**Edith:** Yeah, and a lot of our effort was just making sure that we worked on different platforms. We don’t have to worry about that anymore.

**Paul:** Everything is HTTP-based API, basically. Until it’s not. The thing I was playing with recently was the Slack API. To talk to Slack is not actually an HTTP-based API anymore.

It’s a WebSockets-based API that, I don’t know how it works because there’s a library, but in order to hold the conversation with a Slack partner, I guess it’s for latency reasons, it’s a WebSocket connection. It’s not really HTTP-based API anymore.

**Edith:** I got an engineering degree also. I was hanging out with my engineering friends who were doing robotics engineering and they were talking about a really interesting break point in their company, which is where they made a prototype, a working prototype, and now they’re trying to scale up to make thousands of these in China.

**Paul:** Oh no.

**Edith:** And just what a different mindset it is.

**Paul:** Oh my god, I looked into this. That world is fucking crazy.

**Edith:** So my friend is the VP of engineering and he’s classical, “Do you think I’m a curmudgeon?” This guy is a curmudgeon. And he’s like, “They need to stop taking parts off my prototype. We’re trying to document everything and get it to China where it’s going to be in an assembly line where people are going to have to put these parts together.”

What you were saying about how, at the very beginning,you have all this time to make all these decisions about tweaks? When you’re assembling something on a machine line, you have the exact opposite.

**Paul:** That’s a really interesting world, and a lot of the continuous delivery things around hardware devices are super, super interesting. You can be building a hardware device in San Francisco and you can solder things and fiddle with them and all that sort of thing. But when you need a component, you often have to wait a week or two.

Versus when you go to Shenzhen in China, a new component is like, you go to these massive components warehouses and you get a component an hour later. So it’s all about the turnaround time.

You can get the turnaround time to be super, super low, prototyping in Shenzhen versus prototyping in San Francisco. And then if you’re prototyping in Arkansas or something, you’re even more fucked. And then it’s the same thing with when you want to get a thousand of something, then when you get a million of something.

You can use companies that outsource, like a company called Flextronics, or you can use small-scale factories that will produce thousands of them a week or something like that.

Or you can go the whole way, to produce a CAD design and talk to a bunch of different factories in China that will give you competitive things. And you just go for dinner with the factory owner, that’s how you know that you’re actually getting into the factory. It’s fascinating. The whole world is fucking mental, and I’m so glad I build software.

**Edith:** That’s funny. I worked for a hardware company, we made basically a Fitbit for plants.

**Paul:** That sounds like something the world needs. It sounds like the punchline at the end of a Silicon Valley episode. “What are you guys making?” “We’re making a Fitbit for plants.” “I’m making a Tinder for dogs.”

**Edith:** “A killer for mosquitoes.”

**Paul:** Nice.

**Edith:** So it was before the Fitbit really existed, but we helped people grow better plants, which is actually a very human deep urge. And that’s how we stopped becoming hunter gatherers and became a higher civilization.

**Paul:** It’s valuable, I’m sure. You definitely didn’t waste two years of your life on that.

**Edith:** I found it incredibly useful because I learned so much. People still use our Fitbit for plants.

**Paul:** All six of them?

**Edith:** Oren bought five himself.

**Paul:** No way.

**Edith:** Yeah.

**Paul:** The quantified self, in some form.

**Edith:** Oren was the persona we had, the gadget guy. So Oren bought a bunch for the Heroku office.

**Paul:** Right, right, of course, for the Heroku office. The Heroku office is the definitive gadget guy.

**Edith:** Yeah, I had the gadget guy who wanted to measure his plants.

**Paul:** If you’re any company that’s building any gadgetry, the Heroku office is an excellent first customer. They will buy whatever you have.

**Edith:** You should just go over there, outside. And if they don’t buy it, perhaps you have a real issue.

That’s where really I learned that hardware was hard and software was soft, because we had to manufacture in China. We actually made it at a doll factory. They were making little dolls and then we did a run of about 10,000 units.


<blockquote>Something went wrong with those units, and it was a hassle. We had to open every single unit and fix it, whereas with software, just ship something else.</blockquote>


**Paul:** The analogy of architecture and engineering to construction or civil engineering is like if you want to rebuild the foundations of a bridge, that’s a thing you will never ever do. Whereas if you want to rebuild the foundations of your software architecture, that’s somewhere between a one- and a three-week project.

**Edith:** Well, I’d say that this runs into trouble because sometimes it’s actually a three-year project. Sometimes business users and even software users think that everything is mutable, when it’s not.

**Paul:** Right. Well, it depends how good your API contracts are. To a certain extent you can lift up a house, redo the foundations, and then put the house back down.

**Edith:** That’s a good metaphor. It depends how much you’re redoing versus elevating that house.

**Paul:** Putting it on stilts or something like that.

**Edith:** Or maybe putting an underground pool and a water slide. All right, we’ve tortured this metaphor to death.

Specialization, I think, is all about the right stage. To go back to the robotics example, they had a working prototype. They proved that people liked it. I think if they prematurely scaled and started putting something they built, that wasn’t very good, into the hands of everybody, it would not have done them any good.

**Paul:** It’s interesting to look at the thing as sort of the stages of VC financing. You have a seed round to build something, and it’s a small seed round, and it’s to validate that there’s some kind of market for something, or that the product can be built in some cases. And that’s the thing where you need very little specialization. You might need one specific specialization.

If you’re building AI, you might need people who are super into AI or know something about that, probably, whereas when you get to the next stage and the stage after that, it’s really about expanding. It’s really about getting much more specialized people who are able to do that specific job much more specifically.

In the hardware example, the seed trend is often to cobble something together and then you do your Kickstarter as the next source of funding. And then you do your Series A to really bring that to market in some more meaningful way.

**Edith:** I think people underestimate how hard Kickstarter campaigns are.

**Paul:** It seems really hard now.


<blockquote>I think there’s probably some Kickstarter guru out there who’s the marketer that you bring in to make your Kickstarter campaign work, and everyone else is just guessing.</blockquote>


**Edith:** Another guy who went to my college, [Dan Shapiro](https://twitter.com/danshapiro?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor), has a couple of the most successful Kickstarter campaigns ever.

**Paul:** He’s the Kickstarter whisperer?

**Edith:** His current company makes 3D lasers, [Glowforge](https://glowforge.com/). He wrote a really good blog article about just how much work it is.

**Paul:** You need to get PR for your Kickstarter campaign. You need to have a viral marketing thing.

**Edith:** You iterate on your video.

**Paul:** Of course. Multiple times, I’m sure.

**Edith:** I think people have this misconception that virality just happens on its own.

**Paul:** There’s a wonderful essay, I think it was either Joel on Software wrote it or it was on the Joel on Software forums or something along those lines. It was about the guy who was a software engineer and he deeply loved building products the right way and all that jazz.

One day he quit his job and he sat down in a room to write the new piece of software, and he wrote something beautiful and elegant and gorgeous and all that jazz. And then he set it out there for people to come.

**Edith:** The better mousetrap?

**Paul:** I think it’s not important what it was, but he set it out there for people to come and then nobody came.

**Edith:** Paul, haven’t you ever heard of that story?

**Paul:** The better mousetrap?

**Edith:** “You build a better mousetrap, the world will beat a path to your door.”

**Paul:** No, I haven’t heard that.

**Edith:** Oh, that’s a famous American saying.

**Paul:** It cratered and ruined my story. So, the guy has built this thing and he makes a website for it and nobody comes.

**Edith:** Bettermousetrap.com?

**Paul:** And then he goes back to his job a little bit sadder and a little bit wary about the world, and he goes back and does the same thing as he was doing before. But now the spark is gone. And I feel that this is sort of the analogy, obviously it’s for why you need sales and marketing.

But in the Kickstarter world, it’s not just that you need a little bit of sales or you don’t just need a little bit of marketing.


<blockquote>You need to totally dedicate yourself to your go-to-market, and a lot of people find it much, much easier.</blockquote>


A lot of engineers in particular who want to start startups find it much, much easier to building more code. “When something’s not working, let’s write a bit more code,” versus, “Something’s not working. Can we get a co-marketing post with this larger channel, or something like that?”

**Edith:** Yeah, thank you publishing our blog post when we were very young.

**Paul:** That’s the thing people need, right?

**Edith:** Which was the “[Joel Test for Continuous Delivery](https://circleci.com/blog/joel-test-for-continuous-delivery/)”

**Paul:** Right, yeah. That was a great article.

**Edith:** I think it’s interesting when you were talking about Kickstarter, because even Kickstarter campaigns are specialists.

**Paul:** Oh yeah, right. Heaven forbid you want to do some other campaign that’s like Kickstarter.

**Edith:** Like an Indiegogo?

**Paul:** I don’t specifically mean Indiegogo. You can do a Kickstarter campaign, but there’s also a much larger world of crowdsourcing and viral campaigns of some kind where you’re doing it without the Kickstarter channel, I guess, if you’re trying to do a Kickstarter campaign and you don’t have Kickstarter.

**Edith:** I think people also underestimate total addressable market versus value of their product. There are many products that are meant to be valuable but have a very small number of people that want them.

I think we talked about this in other episodes. Like, you might have 100,000 people who really, really want your product and will pay a lot of money, and Kickstarter is more suited perhaps for something that millions of people want.

**Paul:** There’s an interesting set of polarizing things. There are some markets where a very polarizing product succeeds: U.S. presidential election at the moment, right?

**Edith:** I don’t know, I’m really going to need therapy. You can always go back to Ireland.

**Paul:** No, I’m thinking of Canada, actually. It looks very nice up there.

**Edith:** I hear it’s cold.

**Paul:** I hear it’s very free up there.

**Edith:** I hear it’s cold, particularly in the winter.

**Paul:** Well, maybe the winter, I’ll go to Mexico. I’ll alternate between your neighbors.

**Edith:** Also when the snow melts, there’s a lot of mosquitoes.

**Paul:** Anyway, certain election systems like the one in the U.S. favor in polarizing a candidate. In Kickstarter, it’s a polarizing product as well. You have to have something that people really, really love, and it’s okay if 95% of the world hates it. But you’ll still succeed on Kickstarter.

If you want to succeed in the world at large, you have to be something that everyone loves and not just a very, very small number of people will love.

**Edith:** Well, it depends on what the product is.

**Paul:** Yes, if you’re targeting particular niches or that sort of thing.


<blockquote>The lesson is that if people hate your product, but a small number of people love it, that can still be a really good thing.</blockquote>


**Edith:** It’s a classic Dave McClure thing, “It’s better to be hated than to be ignored.”

**Paul:** Pokemon Go is a lovely example of this. There’s a bunch of people who fucking love that thing, and there’s a lot of people who seem to really, really hate it.

**Edith:** Who could hate Pokemon?

**Paul:** I think there’s a lot of “get off my lawn” mentality going on.

**Edith:** Who could hate Pokemon?

**Paul:** I guess people who have lawns.

**Edith:** I think I’m at peak Pokemon.

**Paul:** You think you’re done with it?

**Edith:** I’ve caught all the interesting things.

**Paul:** I tried it and I really didn’t get anywhere. I was away when Pokemon Go came out and I expected that when I got back to San Francisco there would just be Pokemon people fucking everywhere and I’ve barely seen any.

**Edith:** It was scary when I was in Sydney. I was in Sydney for a conference, and I went down to Sydney Harbour, and there are literally Pokemon zombies.

**Paul:** They were just wandering around into traffic?

**Edith:** There was this light rain and there were about 500 people all playing Pokemon, and you knew they were Pokemon players because they had the battery pack and they had the app open and they’re all sitting there killing all the Pokemon. I would silently judge them, except for when I was playing Pokemon, too.

**Paul:** Is it my imagination or is this not really a thing in San Francisco? I’ve seen there was something in Fisherman’s Wharf. There was some event up there. And there was an event in Dolores Park where 30,000 people went, but I don’t see it on a daily basis.

**Edith:** I think there’s concentrations where there’s more Pokemon, and that’s where those people doing it are. I would go running through the botanical park in Sydney, and there was this one area where there was just a lot of people hanging out playing Pokemon.

**Paul:** All right, we’re 27 different tangents off here.

**Edith:** Well, we specialize.

**Paul:** All right, our next podcast next week will be a little more generalized, I think.

**Edith:** Let’s sum up. I think specialization is good at the right time, and Paul is going to…

**Paul:** And cut.

**Edith:** You never heard of a better mousetrap?
