---
author: andreaech
comments: false
date: 2017-07-17 15:42:37+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-common-developer-monetization-mistakes/
slug: to-be-continuous-common-developer-monetization-mistakes
title: 'To Be Continuous: Common Developer Monetization Mistakes'
wordpress_id: 1745
categories:
- To Be Continuous
tags:
- Amazon
- AWS
- Brad Feld
- Docker
- Fabric
- Gitlab
- Heroku
- identity politics
- Meteor
- monetization
- Red Hat
- RethinkDB
- Scott Raney
- serverless
- VCs
---

In the latest episode of To Be Continuous, Edith and Paul examine how monetization approaches vary depending on the developer market you’re in.

They discuss how developer markets can be divided into four spaces and examine the companies operating in each space. They also consider the pitfalls of startups that push their product in too many directions and consider how to go about evaluating the threat of Amazon cloning your service. This is episode #34 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->

This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.







TRANSCRIPT






**Paul Biggar**: So, you want to talk about developer market. What is the developer market?

**Edith Harbaugh**: So I think the very word developer market is a misnomer.

**Paul:** Okay.

**Edith:** I think if you look at an engineering organization, there are many different kinds of developers who have different roles or responsibilities who care about many different things.

**Paul:** So you're saying that there is no one developer market.

**Edith:** I think there's not only one developer market. I think there's many different dimensions of a developer's market. I think it's on a flatland but even an n-dimensional problem.

**Paul:** So when we say a developer market, do we mean the dev tools market or do we mean broader than that?

**Edith:** I think they're kind of lumped together. I think when people think of developer tools they initially think of, something like a GitHub or Atlassian.

**Paul:** Okay.

**Edith:** But however, there's also database developers.

**Paul:** Right, there Cassandra as a service is a developer tool.

**Edith:** Yeah, the wants and desires of a database engineer are completely different than a JavaScript developer.

**Paul:** So, [Scott Raney](https://twitter.com/sraney), when he was on [the show](https://blog.launchdarkly.com/to-be-continuous-scott-raney-of-redpoint-ventures-on-why-continuous-delivery-matters/) a long time ago, divided the developer market into four different spaces, right? Do you remember this? There's the as a service.

**Edith:** You're stressing my memory.

**Paul:** I know, mine too. There were four. What the fuck were they? So, there's like editors and like language tools. There's SaaS tools like Stripe that are sort of developer first but are providing a non-code service. And then there's SaaS tools like yours and mine that are sort of developer productivity. I've forgotten the fourth.

**Edith:** Shaun made a big impression on us.

**Paul:** Scott. Sorry, Scott.

**Edith:** Scott, yeah. This kind of came up recently cause RethinkDB just did a really good [post-mortem](http://www.defmacro.org/2017/01/18/why-rethinkdb-failed.html). I'll sum it up by. Well they summed it up by, they didn't get, they didn't monetize and they had to shut down.

**Paul:** Okay, yes. Well, if you don't make money you have to shut down. I think that's a usual, a very standard approach to business.

**Edith:** I don't know, some people continue to lose money for a long, long time.

**Paul:** Well, I mean, if you're Facebook, you can lose money for as long as you like because you have, you have numbers that go with it.

**Edith:** Yeah or I suppose like [Medium](https://medium.com/) who very recently, though they had, I think, I don't know their numbers but I think they had pretty good numbers, just realized that ad support wasn't going to cut it.

**Paul:** Right, I think they also have a lot of money in the bank.

**Edith:** Medium.

**Paul:** They're cutting long, long before they hit the runway. You know, clearly it's thinking several years in advance and projecting that far and realizing this path is not the right one.

**Edith:** Yeah, ad supported businesses are really hard.

**Paul:** Yeah,


<blockquote>There are almost no developer tools in the ads to developers space. </blockquote>


I mean that could be a viable monetization unit, ads to a specific niche audience but no one sells ads to developers. So, as I understand it, I hope this isn't private information Joel, apologies if it is, they make way more money off careers than they do off ads.

**Edith:** That makes sense, I mean at TripIt, so we had ads but it was basically breakeven, even with 10 million users. How we really monetized was through our premium products, through TripIt Pro and the product I started, TripIt for teams, for business.

**Paul:** Yup, I've been thinking of sponsored builds and that sort of thing, at Circle, paying to advertise to developers and we didn't go too deep into the numbers, but it wasn't really a thing that you could monetize too well.

**Edith:** It really starts to decay very quickly. When I was at Concur, and I think this was long ago that I can talk about it, they tried this experiment where they would sell ad spaces within an expense-reporting tool and this hugely pissed off their customers. And also, by the way, the ad revenue was pretty minuscule. When you start to decompose it, like say TripIt has 10 million users and now I'm just going to make up numbers because I don't remember the real ones.

Say two million of those are active in a month and you're getting 10 impressions per user. That sounds great. That's 20 million impressions, except for if you're getting 0.1 cent per thousand impressions, obviously this is not much money at all. And that was with a huge base of 10 million users.

**Paul:** Yeah. So you gotta make a bunch of money, ads is a shitty way. What was Rethinks?

**Edith:** Their monetization, they said they never really succeeded in it, that they couldn't really convince people to pay for anything.

**Paul:** And so I find that this is a common thing in the space that Rethink is in. So they've got an open-source product and they find it hard to monetize licenses and so they created a hosted product and I think in Rethink's case they were right up against Meteor.

So Meteor created not a database but a realtime service and Rethink was trying to catch up with that and Firebase had that too. So Meteor has all the traction behind it. Firebase has all the customers behind it.

**Edith:** And not to mention the deep pockets of Google.

**Paul:** Deep pockets of Google, right. So certainly now and when was that acquisition, last year?

**Edith:** It was a while.

**Paul:** 2014 maybe.

**Edith:** To Google they could be bleeding money but the scale of bleeding money at Google's scale is very different than you or mine.

**Paul:** So Rethink has to deal with those two big competitors and it seems like they were kind of going in all three directions at once. They're building this essentially a better MongoDB and they're building the realtime enabler portion of it and the cloud. And they, I guess, never hit monetization in any of them.

**Edith:** Yeah, I mean that's what they put on their own post-mortem which was that they were just, they were just spread too thin.

**Paul:** Yep, those are I think three really interesting ways to look at how you sell to developers and developer market. So there's this open-source plus plus plus.

**Edith:** Which I'd say like GitLab is trying to do.

**Paul:** GitLab is trying to do it. I guess mySQL was the original one of these right, cause I feel [Red Hat](https://www.redhat.com/en) was a different sort of model, but yeah, Mongo, MySQL, both database companies.

**Edith:** JBoss?

**Paul:** That was an application server on top of a free something.

**Edith:** Yeah, this was back in like 2002, 2003. They were an applications server and Citrix acquired them as I recall.

**Paul:** Gotcha. Were they profitable, made lots of money?

**Edith:** I don't know. To be honest, they either could have released their numbers but it was long enough ago that I've forgotten or they could have never released them.

**Paul:** So MySQL was licensing plus around the open-source product. Was there an enterprise version of MySQL?

**Edith:** I don't remember.

**Paul:** What's Mongo doing?

**Edith:** Services.

**Paul:** Services, okay. That's a shitty business.

**Edith:** Or, well no, so Mongo actually had this huge thing where they were trying to key some features out and keep them at the enterprise level and their base rebelled.

**Paul:** That's going to be difficult.

**Edith:** Their base just rebelled and it was actually a lot of very ugly hacker news posts. Well that's always the dichotomy if you're open-source.

**Paul:** Well James Lindenbaum has a very good view on this and he talked about [Heroku](https://www.heroku.com/) in the day. What goes into the enterprise product and what goes into the developer product and what he said is, "Anything that developers "feel is developer-y, has to be available "in the developer product."

And in their case that was a freemium product. So you want to do a git push, you want to support HTTPS, those are developer-y things. If you want to have SLA's, access control lists, you want to have data retention policies or data destruction policies, all that is enterprise-y and you're happy to charge for that.

**Edith:** Well, I think that's a very good way to look at it because it differentiates what an end-user cares about, and I'm saying the developer is the end-user, versus what the company cares about.

**Paul:** Right.

**Edith:** So an individual developer, to be really blunt, doesn't care at all about data retention. And I don't mean that in a harsh way. It's just like, they are individual developers, like job to be done.

**Paul:** I don't think it's just a job to be done but I think developers like to think about technologies and not necessarily about policy.

**Edith:** Yep.

**Paul:** So if it's policy it goes in the other one but I think


<blockquote>Developers buy tools like they're building their side projects. </blockquote>


**Edith:** Yeah, they're all about individual productivity for it.

**Paul:** Right. So actually, so John Sheehan from Runscope has this excellent tweet where he describes what the developer market is and he says, "It's a consumer go to market "with enterprise dollars behind it."

**Edith:** Totally agree and I think where you get lost is where you're building something and I say lost in that eventually gravity hits, and you could have something that many people love but if you're not monetizing it.

**Paul:** Right, so I guess the two ways to fail then at being a developer company is to build something which doesn't or can't have consumer like adoption or that can't have enterprise dollars behind it.

**Edith:** Yeah and those are a little bit, to go all greek mythology, like the [Scylla and Charybdis](https://owlcation.com/humanities/Scylla-and-Charybdis).

**Paul:** I don't know that myth.

**Edith:** You kind of have to thread this needle of you need to get enough developers to love you that the enterprise will pay money for it.

**Paul:** Right, okay.

**Edith:** Because if the enterprise loves it but developers hate you.

**Paul:** Yep. So, developers loved RethinkDB but they didn't use it, they used Mongo, and people hated Mongo. I guess anyone who really looked at it hated Mongo, it was like, it's this marketing machine. And the product didn't work that well and it had all this random crap in it that, I don't know if you saw people dissecting? It logged randomly, so there was like a call to random in the logging.

**Edith:** Non-deterministic?

**Paul:** Non-deterministic, it was like, if rand is less than 0.1. So the idea was that it would log 10% of the time.

**Edith:** Well, I know why they did that to be honest.

**Paul:** Well, yeah, there's a certain amount of sanity to it.

**Edith:** Well, it's funny because logging features like that are extremely expensive from the supplier side.

**Paul:** Yeah. I keep hearing you talk about how analytics are really expensive and the only people who make money on analytics are AWS.

**Edith:** Well, we haven't actually talked about this on the air.

**Paul:** Oh, okay.

**Edith:** I mean like, I think,


<blockquote>Analytics are extremely expensive. You have to log every single event that's happening and then store and process it somewhere. </blockquote>


**Paul:** Yeah.

**Edith:** And then the other flip-side of it is that Google Analytics has completely commoditized this. Like, so the price of Google Analytics is free.

**Paul:** Right, logging in a database is important. I feel you should log, I feel a database should log when something goes wrong but deterministically. Well like, getting a non-deterministic log just sounds like the most irritating thing in the world when you're trying to debug something.

**Edith:** I can see why they made that decision though because it's really expensive, cause you're just generating so much content. I'm not defending them, I'm just saying I'm sure the logic of it. So my background is content management and if left unchecked it could generate a lot of content.

**Paul:** So, I would suggest that rethink did not fail because they logged every message but they were generally regarded as, you know, what Mongo should have been.

**Edith:** Yeah so, a side-story about why I feel this way is, so I used to work at a big content management system and we had an analytics product. The analytics logged such that, it would log basically a day worth of content and it would take roughly 26 hours to process this data. So it was like one of those laws of physics, they were constantly falling behind and their customers were getting more and more pissed off at them.

**Paul:** It's getting worse.

**Edith:** It's getting worse.

**Paul:** By two hours every day.

**Edith:** Yeah, by two hours every day, so at some point you're like literally months and then people were just basically declaring logging bankruptcy and wipe everything out. So, it's a tough problem about what to retain and what not to retain.

**Paul:** So, in terms of business model, it sounds to me that that and I don't remember everything that Slava said in the rethink blog post but they clearly didn't hit the licensing around an open-source tool.

**Edith:** Which is hard.

**Paul:** Which is hard. Has anyone done a really good job there?

**Edith:** The one example people hold up is Red Hat.

**Paul:** But they sell consulting around the tool, yeah?

**Edith:** Yeah, besides that it's just really difficult. And so we go back to MongoDB, they tried to retain some stuff in their enterprise layer and the people in the open-source community who'd worked on that part were up in arms.

**Paul:** Oh right, yeah, if you got open-source people to write it then obviously.

**Edith:** And they were like, well, not even that they'd written that part. Basically the thing was, "Well, we've contributed so much "to your free side."

**Paul:** Oh okay.

**Edith:** You know and then gets, you know, we've helped you get all this free stuff going, we kind of looked at that as barter was the contributors feeling

**Paul:** Wow, so they're not selling additional services on top of the free product? So, the next step you go to is hosted and I know Mongo didn't go in this direction so there's MongoHQ which is Now Compose and there was MongoLab, which I think also has a new name, that actually provided hosting and, I think, does Amazon have a Mongo hosting now or someone has a Mongo hosting.

**Edith:** Amazon's really all about Dynamo these days.

**Paul:** Ah right, that's their NoSQL thing?

**Edith:** Yeah.

**Paul:** So rethink could have gone hosting and didn't.

**Edith:** What they said, and this is all a kind of second-hand reading the same post, is that by the time they tried to go there, they were just spread too thin.

**Paul:** Right.

**Edith:** They tried to do that but you can only do so much. I think one of the most important things that a start up can do is say no.

**Paul:** Right, so if you push yourself in three directions, you're kind of fucked. And so they were trying to do the real-time stuff as well as the, yep.

**Edith:** So they pushed in three directions and they end up executing maybe 40% of all three. Instead of just picking one.

**Paul:** Course, that means you have to pick one.

**Edith:** And we've talked about this before, the lack of a decision is a decision.


<blockquote>They said all three of these look like viable paths, and all three of them could have been market winners, so they went down all three paths and the net result was by not making a decision about one they could not execute well on anything.</blockquote>


**Paul:** Right, they needed to make the decision far earlier.

**Edith:** Yeah, but that's tough cause you probably within the company they had people strongly advocating for each of these.

**Paul:** So, I actually interviewed at Rethink.

**Edith:** Paul, I love how every story collapses down to that.

**Paul:** Yeah! I've interviewed at a lot of people. So yeah, just when we were starting Circle I interviewed at RethinkDB and back then, so this is before they had their Mongo replacement, the premise of Rethink DB then was a database that ran on SSD's. And every other database ran, back then, on spinning discs and there was no optimization for how SSDs worked.

And I think they got out of that but when I went in to talk to them and I eventually got an offer was roughly around the time where I needed to make the decision of was I going to start CircleCI and I think I was still in the, "Okay, I'm going to work "somewhere for a little bit to see if Circle gets legs." and I didn't want to commute to Mountain View.

**Edith:** Such a killer commute.

**Paul:** Yeah, it really was.

**Edith:** And so you went to Looker instead?

**Paul:** Lookout, yeah.

**Edith:** Yeah, I made many similar career decisions based on commute. It's easier now but I remember it used to be harder to find a job in the city.

**Paul:** Yeah and so I think people started moving to the city around 2009, 2010?

**Edith:** Yeah.

**Paul:** People really hadn't started moving up here by, certainly when I was doing YC, 2010.

**Edith:** Yeah my litmus test as I remember, at the time I didn't own a car and I actually had to borrow my friend's car to drive down for an interview in Mountain View.

**Paul:** Right, you lived in the city?

**Edith:** I lived in the city and I drove down there and I interviewed and they actually made me an offer, it was just a hassle just for the interview.

**Paul:** Yep.

**Edith:** And same, I interviewed in South Salito.

**Paul:** Oh jesus, yep.

**Edith:** South Salito I could kind of justify because it's beautiful.

**Paul:** Yeah, you could have a nice brunch overlooking the bay.

**Edith:** Yeah and I could ride my bike.

**Paul:** Yeah.

**Edith:** Except for when it's raining and hailing.

**Paul:** And when you want to go back uphill.

**Edith:** Yeah, but I think people underestimate how big of an issue commute is.

**Paul:** Yep, I know we're getting tangential but I drove down to Palo Alto today and I was driving against traffic both ways so it was totally fine but.

**Edith:** You drive?

**Paul:** I learned to drive to fundraise.

**Edith:** When?

**Paul:** When I was raising the Series A.

**Edith:** That's right.

**Paul:** So I learned to drive to be able to drive down to Sand Hill Road.

**Edith:** Is it confusing?

**Paul:** Being on the wrong side? No, I didn't learn to drive when I was in Ireland so I've only really driven in America.

**Edith:** That's amazing, so did you go to driving school or what did you do?

**Paul:** Yeah, I got someone and I drove dozens of hours and then I did the test. It was like four weeks from when I started I did the test and I passed.

**Edith:** Did you make a conscious decision, like I need to go fundraise?

**Paul:** Exactly and I needed to be able to drive down to Palo Alto to fundraise or else it's too difficult because when I did the seed, I was taking the Caltrain and then I was cycling to Sand Hill Road. I remember walking into VC's offices dripping with sweat because Sand Hill Road is a hill, it's a real fucking hill.

**Edith:** There's no sand but there's definitely the hill.

**Paul:** This is where you see the VC's mountain biking on their $10,000 bikes and then all their spandex around there because it's really difficult to cycle around there.

**Edith:** So that's a great story so you wouldn't pause in the parking lot and kind of towel off?

**Paul:** Sometimes in the bathroom, yeah, it was a disaster. I wasn't in my spandex, I was wearing my shirts and my jeans and converse. I was commuting, there was just a hill in the way.

**Edith:** So the cool thing about when we, when we fundraised, I ran my bike everywhere and what I really liked, even between the seed and the A, is how many more people were up in the city.

**Paul:** Oh yeah, that makes it a lot easier.

**Edith:** So South Park is now like a mini Sand Hill Road, down to like, they're all cheek and jowl.

**Paul:** Cheek and jowl.

**Edith:** Redpoint is right next to Shasta, it's right next to Sear, you know that.

**Paul:** Oh right. They're on the same, like 101 South Park or whatever?

**Edith:** Yeah but it really saved so much time.

**Paul:** So I learned to drive to fundraise and then I hadn't, I learned San Francisco driving, which is not difficult but it's not freeway driving and so I wasn't comfortable on the freeway and so whenever I arrived down in their offices, again, drenched with sweat, because of the fear of dying on the freeway. So, in the end, I ended up Uber-ing up and down.

**Edith:** I thought you were going to say like you took El Camino Real all the way down there.

**Paul:** Oh, that would have been a good idea but what I discovered is that there's an infosec leak with Uber drivers. I think it was a Lyft, I Lyfted a lot at the time. A friend of mine was coming to my house and he said, "Were you down fundraising "in Palo Alto today?" and I was like, "Yeah, how did you know?" and his Lyft driver had told him.

**Edith:** What?!

**Paul:** That there is an Irish guy that he dropped off here earlier. Yeah it was crazy, a $80 fare down to Palo Alto and then I waited and then I drove him back.

**Edith:** Well, it could have been the intercom dudes, how did he know it was you?

**Paul:** Because it picked up from that building.

**Edith:** Yeah but I mean that it was an Irish.

**Paul:** I don't think I lived in the same place as the intercom dudes.

**Edith:** You're not the only Irish guy in the city.

**Paul:** But I was the only Irish guy who lived, I wasn't actually the only Irish guy who lived in that building but, fundraising, it was a reasonable guess.

**Edith:** Oh yeah, I remember we were going down to pitch and we were pitching different firms. I realized that I was going to pitch the two firms, like they're all right next to each other on Sand Hill Road, and they were literally in the same building.

**Paul:** I'm surprised that they don't have something set up in their wireless routers to know when an entrepreneur connects to their wireless thing, that they've maybe connected to it before. Wouldn't that be smart?

**Edith:** No but they all have their own individual Wi-Fi.

**Paul:** Yeah but if you're in the same building, you can see all the next door Wi-Fi's.

**Edith:** Oh, but I don't think you can see that somebody else has connected.

**Paul:** No but maybe you connected to what you've, your computer's been connected to before?

**Edith:** Can they sniff that out? I don't so.

**Paul:** So, if you're in like Redpoint and Trinity are in the same place and Sequoia's in there as well. So, you go to Trinity and you've previously been to Sequoia and you connect to Sequoia's Wi-Fi because your phone automatically connects to it.

**Edith:** Ohhh, well the nice thing about SoftTech was our C investor and then I kind of ran on South Park so I always had kind of plausible deniability if somebody saw me around there, I was just like, "Oh, I'm just visiting."

**Paul:** Yeah, okay, nice.

**Edith:** I'd just hope somebody wouldn't see which offices I was actually going to.

**Paul:** Right.

**Edith:** My deep fear was that I wouldn't be paying attention and I would open the wrong door.

**Paul:** Oh and just walk into the wrong office?

**Edith:** Because they're all like. So I was like what if I walk into the wrong office, because a couple of times I would walk out and I would be unlocking the bike and someone maybe would walk by.

**Paul:** Yeah.

**Edith:** Because I would ride my bike.

**Paul:** I feel like people know when you're fundraising anyway, like oh you're having a meeting in The Rosewood? I think you're fundraising.

**Edith:** Well that's a pretty. I mean, like, maybe you're just I don't know, hanging out?So you don't believe in innocent meetings with VC's?

**Paul:** No, I mean, you need to have those relationship building meetings. In fact, I'm having innocent meetings with VC's right now. So fundraising for my new thing, except I'm not fundraising. I'm just starting it off, getting feedback, all that sort of thing but like, inevitably it's the start of a relationship that is going to turn into a fundraising cycle at some point.

**Edith:** Yeah, that was the same strategy I followed. To me, an investor is a big deal. This is somebody who is basically as important as a founder to your company.

**Paul:** Yeah, except at seed when they're disposable. I'm joking.

**Edith:** No, you're not.

**Paul:** No, I mostly am, but you see a lot of people with the party rounds where they're like, where it doesn't matter, you know, they've got 40 or 80 people in there thing and I doubt they would know an investor if they ran into them in the street.

**Edith:** Oh yeah, like I heard horror stories. I heard this actually at a conference we went to together, I sat next to the guy and there was this trend, about five years ago.

**Paul:** For the big party rounds?

**Edith:** Yeah and people were just dumping money and so he met one of the partners at some event and he's like, "Hey, your firm invested in me." and the guy just ran away. Because they weren't going to do the follow on and he just didn't want to deal with this guy he's like, "Remember me? I'm here."

**Paul:** Give me more money, please.

**Edith:** Yeah, he said like literally the guy bolted. So, to get back on topic, I think you have to eventually monetize.

**Paul:** Yeah, I mean that's how you make a business.

**Edith:** Yeah, I think VC's will give you money at some point for just your promise but eventually that check comes due in terms of what have you done for me lately.

**Paul:**


<blockquote>I think the most obvious way to monetize is to host it and I'm surprised at people who delay this. </blockquote>


So like Mongo could have been the Mongo host. RethinkDB could have been the RethinkDB host. Meteor is obviously the Meteor host, Meteor actually is the Meteor host.

**Edith:** I think it makes sense for some things and not for others. Then there's extreme outliers, so our advisor Sean Byrnes' company, like I just totally said advertising never worked. Advertising is what worked for them.

**Paul:** Right, this is Flurry?

**Edith:** Flurry, because they had sufficient domination in the mobile market that the economies of scale worked out for them to do mobile advertising.

**Paul:** Gotcha.

**Edith:** So I said, TripIt was 10 million, I don't know their exact numbers because they weren't public but I think they literally had some huge numbers.

**Paul:** Ten times that?

**Edith:** Well, no because they had an SDK the app developers installed so think how many average apps there are on somebody's phone and let's just back that out, say they had.

**Paul:** So 0.4, the average number of apps that I think most people have is less than one. I'm being facetious. People that actually install apps.

**Edith:** Yeah, so just say they had 50% of the overall mobile analytics market and multiply that worldwide and suddenly that's a lot.

**Paul:** Yeah, that's a lot of users.

**Edith:** That's a lot of users, that's a scale when you can actually be successful in advertising.

**Paul:** Who did they exit too?

**Edith:** Yahoo! bought them.

**Paul:** Yahoo! bought them? I'm sure they made good use of them.

**Edith:** You know sometimes I'm not sure if you're sarcastic.

**Paul:** So this to their Verizon now?

**Edith:** Yeah, which is funny because Sean actually started off at Verizon but he's not been there for a while. Sean is great, his thing is that everybody eventually tries advertising.

**Paul:** Right, I guess Rethink didn't try advertising. Maybe they should've tried it. I'm joking.

**Edith:** I think advertising works if you have immense, like, Google makes a ton of money.

**Paul:** So hosting, I think, is this strong model. Firebase is pure hosting, right? There is no way to use Firebase without it, is there an open-source Firebase?

**Edith:** I don't think so.

**Paul:** Okay, I wouldn't be surprised if someone tried to make an open-source Firebase.

**Edith:** I wouldn't be surprised if somebody is, right now, trying to make an open-source LaunchDarkly or CircleCI.

**Paul:** Right, yeah, there's like 12 open-source CircleCI's. So the problem you end up with an open-source product which is hosted is you spend a lot of time building the hosting and you aren't open-sourcing the hosting and there's a challenge for your customers. If they're going to run it themselves because they don't have the migration part of it. So Heroku Postgres was a hosted version of an open-source product and they ran stock Postgres but the tool that they actually built is their infrastructure tool around Heroku Postgres, which was not open-source.

And you kind of expect the same is true with Meteor and with all the other database hosts and that sort of thing. But Firebase went and just said, " the service isn't open-source at all, the whole service is the database and, you know, you can download the libraries because the libraries are open-source but the thing that makes Firebase Firebase is it's hosted".

**Edith:** That's kind of very similar to LaunchDarkly to be honest. Our libraries, our SDK's, are open-source. We love people who want to modify our SDK's but the core of LaunchDarkly is all closed. Our advisor today was like, "Why don't you have a "swift SDK?" and we're like, "Why don't you build one?"

**Paul:** Also I guess my point is that if the core of LaunchDarkly was open-source, what would that mean? So, you've got some data store which someone can run on their own machine but then when they need to scale it up, they hit an inflection point or a multiple of 10. That would be extremely difficult for you to build a product that allowed customers to do that migration themselves. In fact, it's probably challenging enough for you to do the migrations yourselves and controlling the whole architecture.

**Edith:** Yeah, that's something I'd said today was I'm not smart enough to build a successful open-source dev and monetize it, I'm just not.

**Paul:** I can't think of anyone today who's doing that successfully. So a big big unicorn at the moment is [Docker](https://www.docker.com/), in the dev space.

**Edith:** They're not monetizing.

**Paul:** I don't think anyone knows how they're going to monetize and I talked to a whole bunch of investors and the investors like, "It might be zero." investors are, typically, incredibly shrewd about this sort of thing.

**Edith:** Well everybody thought they were going to be the next VMware so they're definitely, I definitely think containerization will continue to accelerate. I don't know if it's monetizable? And now just Docker, and I know many people who work at Docker and I like them but they have this issue that they have such a high valuation. It's very hard for them to get more money.

**Paul:** Where do they go?

**Edith:** So I think they're a good example of something that can be extremely successful with developers but...

**Paul:** But not have anywhere to go?

**Edith:** Yeah.

**Paul:** It might be that the people who make money, I mean, hosting, so right, the people who are going to make money on Docker are AWS and Google, in particular Google.

**Edith:** You don't think Microsoft?

**Paul:** Microsoft, but Google owns Cooper Netties and so you can kind of think of Google's Google Container Engine, GKE, as the de facto Cooper Netties--

**Edith:** Google compute engine or container engine?

**Paul:** Container engine.

**Edith:** Okay.

**Paul:** But that might be where the money goes and that it's spent on infrastructure.

**Edith:** Yeah, I don't know. So I went to both AWS Reinvent and Microsoft Connect and for them it was just all about the core, core--

**Paul:** Services?

**Edith:** Yeah.

**Paul:** The computer you mean or just everything?

**Edith:** Azure is where Microsoft is bidding their future and that's another factor that's played into the dev tools market, is like, Microsoft is basically giving away now Visual Studio. Because they're like, we don't care about the IDE, we care about where you host it and we want that to be Azure. And that's an incredible competitive pressure, similar to Google giving away Google Analytics or just bringing down prices, it's like, well, if you have Microsoft giving away IDE's, how do you charge for an IDE?

**Paul:** This is I think going to be


<blockquote>A major problem in the developer tools space going forward is that Amazon is going to someday clone your service. </blockquote>


**Edith:** Oh, I wouldn't be surprised if they're doing it right now.

**Paul:** I didn't specifically mean LaunchDarkly but absolutely, I'm sure they'll have a terrible name for it. AWS Flags.

**Edith:** They actually had flags.

**Paul:** Oh, okay.

**Edith:** They did have flags. However, what they didn't have is flag management.

**Paul:** Oh wait, they had flags?

**Edith:** Yeah.

**Paul:** What do you mean by flags?

**Edith:** They had Amazon flags.

**Paul:** Oh really? Did they kill it?

**Edith:** They killed it.

**Paul:** Oh, they never kill things.

**Edith:** They killed it.

**Paul:** Wow, I guess you got lucky.

**Edith:** No, I think they weren't making any money off of it, it was expensive.

**Paul:** Yeah, but I mean, I guess you got lucky.

**Edith:** A bullion is incredibly simple, like a single flag. What we do is managing a bunch of them and controlling all the different case statements and actually the business logic of it.

**Paul:** This is the segment of the episode where we plug LaunchDarkly for a while.

**Edith:** I wasn't plugging LaunchDarkly, I just looked across at your LaunchDarkly t-shirt.

**Paul:** Of course.

**Edith:** And it looks so good on you.

**Paul:** It's a great t-shirt.

**Edith:** It's a wonderful t-shirt. But I think this goes back to what you're talking about, about Heroku. It's the same division of stuff that's valuable to enterprises or the management layer.

**Paul:** Right, something I find keeps coming up in, in these discussions is that Heroku wasn't a success.

**Edith:** Depends how you define the success?

**Paul:** Sure, I believe Heroku was a success, so it had massive impact, changed how developers did everything and sold for over a hundred times revenue.

**Edith:** We're in the house that Heroku built.

**Paul:** We are, Heavybit is the house that Heroku built and it looks very, very similar to the house where Heroku currently lives.

**Edith:** I wasn't saying that facetiously about success, so Heroku exited for hundreds of millions of dollars.

**Paul:** Founders got very wealthy, they changed the world or our small part of the world which is not an insignificant part of the world.

**Edith:** And then they did something which was either selfish or selfless, which they said, "Let's give back and invest in more companies." and they started Heavybit.

**Paul:** Right but the investors will say that that outcome wasn't a meaningful outcome.

**Edith:** Ohh

**Paul:** And I guess to a certain extent it wasn't, a 200 million exit.

**Edith:** I think it all depends on what scale you're operating.

**Paul:** Well, exactly, so the seed investors and we share an investor, we share a couple of investors but I remember Steve Anderson.

**Edith:** Oh, you and?

**Paul:** And Heroku.

**Edith:** Okay, not we, you and LaunchDarkly?

**Paul:** No, so Steve Anderson from Baseline was in and I don't know the exact way that his fund works but I remember finding out that a Heroku exit for a fund of his size was fantastic.

**Edith:** And that goes back to fund dynamics, so for an angel, a typical angel investment is between five to 50k, so for them to get even a double or triple is good.

**Paul:** Right, so they, an angel investor who got into Heroku, at the time valuations were probably around the three million mark so they sold for 60 times that with say a 40% dilution. So you take your 25k and you've turned it into half a million?

**Edith:** That's pretty meaningful.

**Paul:** That buys you a nice house.

**Edith:** That sends your kids to college, that buys your Tahoe house.

**Paul:** Yeah, actually we're in San Francisco so that doesn't buy you a house.

**Edith:** Well, it buys you a Tahoe house.

**Paul:** Does it, can you buy a house in Tahoe for 400k?

**Edith:** Like in Kirkwood, a condo.

**Paul:** Oh, okay. Or you could move somewhere.

**Edith:** Our producer is nodding his head

**Paul:** You could buy a Tesla.

**Edith:** In San Francisco it gets you a parking spot

**Paul:** Yeah, I think that's it.

**Edith:** I think it's just, what you said by meaningful outcome, it all depends on the dynamics of what your valuation is at the time. So for Docker at this point, which is probably, I think, valued at over a billion?

**Paul:** Last I heard.

**Edith:** So for Docker to get sold right now for 300 million would be...

**Paul:** Yeah, it would be terrible and in fact, they've probably raised in the ball park of 300 million so no one would take money out.

**Edith:** Yeah but versus, you know, so a smaller company like Trello for example, who just got acquired.

**Paul:** 425 million.

**Edith:** This is actually a great example so they had only taken, and I think eight to nine million, got acquired for 400 million, that's pretty meaningful. So


<blockquote>I think the word meaningful really correlates to how much money had been taken in at what valuation. </blockquote>


**Paul:** Right and when you're talking to people who, who have 300 million dollar funds then Heroku does not look meaningful. They always want to make back a funds worth on a single investment and so Heroku looks like meh and that, in the eyes of those developers, they start to think, "Oh, dev tools is not going to take off" They think Heroku didn't get the value that they created.

**Edith:** I think that comes back to money in versus money out and fund dynamics.

**Paul:** So, you can look at your decision to invest or not invest in, in a hosting company, a little bit as you know, "is Amazon going to come and kill this? Where is your defensibility where are your network effects? And GitHub is a really good example because GitHub survives, right? GitHub has all the network effects, GitLab is struggling to get anywhere near it.

**Edith:** They don't have the same developer love.

**Paul:** Right and, I mean, there is some love there but AWS built their git hosting thing because I guess they could and I'm sure it makes meaningful money for them but it doesn't meaningfully impact GitHub's git market.

**Edith:** I'm not sure it makes meaningful money for them. So I mean, here's a big company problem, I was working at a company and I'd started, what to me, was a huge success. I'd grown my business unit from literally zero, I started it and I had done the customer discovery, we'd built the product, gotten it to a million dollars in about a year.

**Paul:** Yeah.

**Edith:** Which to me was huge.

**Paul:** Yeah, absolutely.

**Edith:** Like a huge success, I was super stoked, to the rest of the company, they were like, "Oh, it's not big enough to be meaningful."

**Paul:** Yeah.

**Edith:** "Your total addressable market is probably going to be, "like, 15 million." and at that time I didn't really like that at all but know looking back is, that company was absolutely right. So they wouldn't invest anymore in my product line and it was hard and that's why you really have to match not only developer traction, enterprise love, but also total addressable market.

**Paul:** Right.

**Edith:** Which I hated at the path but now I get.

**Paul:** I think that that's true for most, so most companies who are on the dev tool space are coming at it as a one product company, right?

**Edith:** And, "Oh, people like us so we'll make money." When I'm like, "People can love you "and you can make zero money."

**Paul:** Well, what I'm getting at is, you have to be able to extract the value if you're a single product company. Whereas Amazon is a many, many, many, many product company. AWS alone and like Amazon itself, in fact, they have a game studio, I saw the Amazon movie, "Manchester By The Sea" the other day.

**Edith:** They're n factorial.

**Paul:** Yeah, it's crazy town, so when Amazon, or when AWS makes a product their driver is "does it drive usage of their other products?" So they don't necessarily care about making money on that product itself or even having a positive gross margin.

**Edith:** Well, that's why I mean that


<blockquote>Google Analytics has killed the rest of the market because they care about driving revenue from Google adwords. </blockquote>


**Paul:** Right.

**Edith:** So when the price is zero, you're literally making a loss.

**Paul:** Yeah.

**Edith:** But if it makes people buy more adwords, that's the same with Microsoft and IDE's, why they're giving away visual studios, they're like, if this is driving Azure because we're making it very easy for you to build and then deploy on Azure, that's what we care about.

**Paul:** So, how do you build a company in a space where Amazon is just going to eat you?

**Edith:** Well, Amazon can't eat everything.

**Paul:** It can eat anyone who gets successful enough for them to eat. No, that's not true. So I have an opinion on Amazon products have I shared this with you? I think I've avoided saying it on the podcast but I'm cool with it.

**Edith:** If you're cool with it, go ahead but I'm never going to make you do anything.

**Paul:** I think Amazon is great at products that it builds itself.

**Edith:** Yes, I totally agree.

**Paul:** Lambda, wonderful.

**Edith:** Amazing.

**Paul:** Alexa, EC2, they built that and Amazon is terrible at products where it copies someone and I don't even know how they go about copying it but I guess they take a PM, they say copy that, and then it gets built.

**Edith:** I've been in markets before, so TripIt had many copycats and they would copy our mistakes. They would copy our false starts. They would copy the things that we were ashamed of.

**Paul:** So in the developer market, we talked about the fact that it's consumerization, it has consumer adoption and that means that it has to have that consumer level innovation. If you're not innovating in the developer tool space, you probably haven't got a really good product. You probably can't own the market if you're not the innovator in the space.

**Edith:** And further on that I think, to go back to Amazon, if it assumes you're on AWS to use it's tool, there are a lot of people that for various reasons do not want to be on AWS.

**Paul:** I think there's a lot more people who have to be on AWS.

**Edith:** A surprise, so Walmart as a policy will not use any AWS tools.

**Paul:** So, this gets interesting because Walmart and people like Barnes and Nobles.

**Edith:** Target.

**Paul:** People who, Amazon is competing with them in some way but Amazon is competing with everyone. They've got a games studio, they've got a movie studio, they're making TV shows, they're competing with Apple.

**Edith:** Do they have a CI tool?

**Paul:** They have a CI tool.

**Edith:** Oh, what's it called?

**Paul:** I don't know, you shouldn't even look it up.

**Edith:** I won't mention it again.

**Paul:** I think they've tried three times to build a CI tool and, I don't know. And this is my point, they copy actual innovation and it doesn't end up anywhere.

**Edith:** Well, so you go back to, of course Amazon is going to eat everybody but I completely disagree. I think if you're doing something that's officially undifferentiated--

**Paul:** So, in the open-source space, if you're building an open-source product and it's easy to host, Amazon will eventually host it.

**Edith:** Yep but if you're building something that has some level of delight. Like, pleasure in using.

**Paul:** Right.

**Edith:** People like using Circle.

**Paul:** So this is interesting because I think there's the infrastructure market and you were talking earlier about the developer market is split up, right? So, if you're hosting Cassandra, it doesn't matter whether Amazons doing it or whoever else is doing it.

**Edith:** And in fact, that's what you're trying to obscure with hosting.

**Paul:** You don't care. Amazon has Cassandra now and it has Kafka and they are, Amazon is the infrastructure company and they will continually be the infrastructure company and if you're trying to build an infrastructure startup, Amazon may kill you but if you're trying to be a product startup, Amazon is not as good at developer products.

**Edith:** I know there's only so much we can talk about but why do you think they've tried three times to build a Circle and failed?

**Paul:** They launched this thing that only works with Java, so developers have a consumer mindset, that means they like products with good UX, that have good usability. If it feels like dropbox, you're probably on the right track and if it doesn't feel like dropbox, I know Amazon has some disk space thing that I wouldn't even try using because I know that it's not going to be like dropbox.

**Edith:** Yeah and yet you use AWS for all your hosting because?

**Paul:** Because its commodity, right? It doesn't matter to me where the machine comes from. And in fact, Amazon invented that whole market, right? So, it did it better than anyone else because it was inventing it and then other stuff it just copies and it doesn't do as well.

**Edith:** I think it blindly copies.

**Paul:** You think it blindly copies? Yeah, I'm not surprised, and where there's differentiation to that, with let's say Amazon Kafka, there is differentiation that Amazon are extremely talented distributive systems engineers who can really build and Kafka kind of looks the same, regardless of how you use it.

**Edith:** Yeah, Kafka's Kafka. I thought of a bunch of puns but I just sucked them all back in.

**Paul:** Okay. Going back to RethinkDB. So we talked about hosting and we talked about the business model around the open-source thing, what was the 3rd one they tried?

**Edith:** Real-time.

**Paul:** Real-time. Okay, so they tried a new product direction as a Hail Mary, I guess?

**Edith:** It was unclear from my read what order they were trying them in, they just said that they tried all these. They said the inability to monetize was more a symptom of a disease.

**Paul:** More symptom of a disease?

**Edith:** Well they said, "People said we shut down because we failed to monetize." and it's like, well that's the symptom.

**Paul:** What was the disease?

**Edith:** That they tried all these different things and none of them worked.

**Paul:** Gotcha, okay. We talk a lot about validation here, we talk about people validating business models and so on. I think it is difficult to approach a developer market without knowing in advance what your monetization is going to be.

**Edith:** I completely agree. I've even had people we both know, companies recently, founder or shutdown, they were the ones who thought I will build something cool and then magic will happen. I will go even further because I just gave advice to a friend, in a totally different market, it's in sales automation. It was so painful because I talked to him about six months ago and he had salespeople, he had engineers, I've talked about this in podcasts, and he had no marketing and no product manager.

**Paul:** Oh, of course, yep.

**Edith:** And my advice to him back then was you know, maybe think about doing some marketing, and he'd said a classic thing which is, "Oh, we'll worry about that later." and now it's six months later.

**Paul:** He hired a marketer?

**Edith:** No, he's running out of money.

**Paul:** Of course he is.

**Edith:** He's running out of money and he's like, we have a product that, we have some early pilots, but no meaningful revenue, so you can't go out and raise on the back of revenue. We need to get money in so that we can try marketing campaigns.

**Paul:** Oh my god, it hurts.

**Edith:** It hurts and it hurts so bad because, and so this is not a developer tool, totally different space. He's like, we don't have any proven marketing channels, we have a couple of pilots that are doing decently well but no significant money and that's when I really crystalized that I think you have to do sales, marketing, product not in serial but in parallel. You should always be trying those together.

**Paul:** Did you see [Brad Feld](https://twitter.com/bfeld)'s essay recently?

**Edith:** No.

**Paul:** So its called [The Three Machines](https://www.feld.com/archives/2017/01/the-three-machines.html) and the three machines are the customer machine, the product machine and the company machine.

**Edith:** I totally agree. You should constantly be, hey does this sales motion work? Does it work with our marketing motion? Does it work with our product? And making fine-tune corrections. I was putting together a talk I want to give at Heavybit on category creation and originally I had it broken up to, like someones talking about how I had gotten businesses over a million, and originally I broke it up to well we built the product, then we did the whole market and then we did this and I'm like no.

**Paul:** Yeah, that's right, you did it all at once.

**Edith:** And you have to.

**Paul:** My new thing that I'm starting at the moment, I've built almost nothing, I've a shitty little prototype.

**Edith:** As well you should.

**Paul:** And I'm spending a significant time at the moment thinking about my go to market.

**Edith:** As you should.

**Paul:** Because the go to market completely affects what we build first, which version of it, which generation of it. It's a huge product that we're looking to build, or a huge platform or whatever and we need to pick a subset of that, we need to reduce scope to something that gets us a proof point that de-risks a certain part of the product or of the market or essentially, how we make money, whether we're going to be a big business.

And it really matters which one we do and if we just sat and built we'd be completely fucked. The temptation, and there's a lot of companies who sit and build and somehow get away with it.

**Edith:** Give me an example.

**Paul:** So, Meteor, Slack. It's not exactly the same, right? You never end up in exactly the same situation as those people. So, Slack is successful. Founder, big, big, successful founder who was able to raise a lot of money and they had the time to wait on the basis of, the thesis of, this beautiful product that people love. Generally, as a first-time founder, you're not in that situation.

**Edith:** Spontaneous combustion does not happen.

**Paul:** Spontaneous combustion rarely happens as it is and when it does is usually something very special about it that you can't see.

**Edith:** Or some combination of factors that might be completely temporal. Like you can't make a Snapchat right now. So another friend I thought was really smart, I saw him, oh it pained me this one also. So two person company. I talked to them about six months ago, they had two very promising early pilots, paying pilots, for like tens of thousands of dollars and my advice to them then was go raise immediately.

**Paul:** Yes, that sounds like excellent advice.

**Edith:** Yeah, I saw them six months later and I said, "How's it going?" And they were like, "We should've taken your advice."

**Paul:** Oh no.

**Edith:** They had not been able to get anybody else.

**Paul:** Pilots.

**Edith:** And now it's six months later--

**Paul:** They can't raise. So what was it a dead end? Was it a product dead end that they just happened to sell two of?

**Edith:** They don't know, so the smart thing they did was they said, we're going to stop building. They pulled both of them and they said we are going to go out and try to sell this. And we are going to figure out if we have a sellable product because if we don't, maybe these two were just.

**Paul:** Were flukes?

**Edith:** Were flukes, were friends that were doing us a favor.

**Paul:** And that's a disaster that you can be taken down the wrong road by.

**Edith:** And the part that pained me was, both of these pained me because my advice had been raised immediately on the promise of these two paying pilots and now they can't because six months have happened now and they can't.

**Paul:** Is this a developer tool?

**Edith:** It was something around developer yes.

**Paul:** Okay.

**Edith:** And the other one, the sales automation, he's like we need some money to go get some marketing campaigns going but we're running out of money.

**Paul:** So, we've talked a bit about Rethink but for the overall developer space, you said at the start: there's selling to developers, then there's selling development tools and then there's selling infrastructure and it's interesting that they have different metrics around them and what it means for success. So if you're a SaaS company at the moment, and many developer tools companies are SaaS, to raise a good Series A is, $100 to $250k MRR is the expectation.

**Edith:** As a counter point, Tomasz Tunguz says that 27% of Series A companies have zero revenue.

**Paul:** So this is exactly my point, right? They're not all SaaS. Is Tom Tunguz talking about SaaS companies specifically?

**Edith:** He's just talking about general companies.

**Paul:** So the infrastructure companies, you can't have a 100k revenue around your Series A.

**Edith:** I know, for a fact, two dev companies who've raised far more than that with zero money.

**Paul:** Sure and not every company is built the same depending on the founders, depending on the markets, there's a lot of things.

**Edith:** They raised significant money with zero but it was basically similar to Docker and people were betting on the total addressable market.

**Paul:** Right, what were these companies? Can't say? Okay. You'll have to tell me after. Is Famous one of them? I know you wrote that mocking thing about Famous.

**Edith:** It wasn't meant to be mocking, it was meant to be kind.

**Paul:** Hmm, that's not how I read it. Did they shut down yet?

**Edith:** I don't know, I honestly don't know.

**Paul:** So, my point is that,


<blockquote>Series A looks very different depending on the type of business you are in.</blockquote>


If you look at RethinkDB when they raised their Series A, they're a database company, right? So, what do you raise a Series A on? You raise it on technology. You maybe raise it on early customers, if there's an enterprise sales motion. But you don't need to raise it on revenue because that's not the expectation.

**Edith:** And so this is the challenge that I faced when I raised for LaunchDarkly is that people would say, "What's the total addressable market?" and I'm like, "I don't know." I can do back of envelope with backing out stuff but it's not like RethinkDB were they can say well the database market is blah per year says this analyst, this other analyst says that. I was basically creating the feature flag market.

**Paul:** Right, it's a SaaS developer tool, it's not a developer tool, it's a PM tool but.

**Edith:** Oh for LaunchDarkly?

**Paul:** Oh yeah and yeah.

**Paul:** How did you back into, what numbers did you back into or what segment of the market did you try to make it a metaphor of.

**Edith:** I just would like to make a joke, why do all VC's wear sweater vests or vests?

**Paul:** Because they're not allowed to wear suits.

**Edith:** Ahh and they're cold?

**Paul:** No, Silicon Valley, much like the rest of the world has this identity politics, right? Founders wear casual clothes and the suits don't want to seem like suits. Right, so the VC's are the suits of the valley and they need to look like they have money and they need to look respectable and professional and they need to be recognized as the money in the corner when the talent comes to visit. But at the same time, they can't wear suits because they're mocked as being the suits. So, what are you going to do? You're going to wear a sweater vest.

**Edith:** But why a sweater vest why not just a sweater?

**Paul:** I don't know.

**Edith:** Because everybody else, all the techies wear hoodies.

**Paul:** It's their identity marker.

**Edith:** But, why no sleeves?

**Paul:** I actually don't know, oh I have a theory. Being VC's, they have a lot of time to spend at the gym and so they have killer arms that they want to show off.

**Edith:** But they wear a shirt under these vests.

**Paul:** Oh then I can't help you. I went on the Silicon Valley Bank ski-trip last year.

**Edith:** Oh, I really wanted to go.

**Paul:** It was really good.

**Edith:** I really wanted to go.

**Paul:** So, its a bunch of founders and it's a bunch of VC's and some bankers and we went skiing in Squaw and there was really good snow and we got a really good ski in. I've been skiing since I was three.

**Edith:** So if you had to pick between skiing and driving down to Sand Hill Road?

**Paul:** I would ski there, yeah. So I was thinking I'm going to be an amazing skier in the group because these are old bankers who live in California but that's what they do with their time. They go up to Tahoe every weekend, we're building companies and shit and they're skiing.

**Edith:** I mean, they bought their Tahoe cabin.

**Paul:** Right and I'm generalizing a little bit but I was expecting to be above average and I was not even close.

**Edith:** Wow.

**Paul:** Yeah and all of them, all the VC's, everyone can ski.

**Edith:** Oh and very well and the pride themselves on this. I didn't know you were such a good skier.

**Paul:** I've been doing it a long time.

**Edith:** Where are there mountains in Ireland?

**Paul:** They're in France.

**Edith:** Oh. That's why you also speak very good French.

**Paul:** Oh, I grew up in Switzerland so I was skiing young and then I lived in New York so skied there.

**Edith:** So why do you have an Irish accent then?

**Paul:** Because I grew up in Ireland.

**Edith:** But I thought that you just said.

**Paul:** I grew up in lots of places, including Ireland.

**Edith:** There's a lot of growing up. I'm a mediocre skier because I grew up in Virginia and the biggest mountains were in Pennsylvania which were not really mountains at all. It's more like a big hill with a sheet of ice.

**Paul:** Well Tahoe kind of isn't mountains either, except this year when, apparently the snow's amazing this year. But when, the first few times I went skiing in Tahoe was during the drought and that wasn't snow.

**Edith:** That was misleading.

**Paul:** Yeah, okay, so Tahoe's better than that is what you're saying?

**Edith:** Yeah, Tahoe in her good years is pretty good.

**Paul:** I'll have to try Tahoe this year.

**Edith:** Yeah it's funny so, maybe that's where all the vests come over us first.

**Paul:** Oh right, well there is this sort of North Face culture going on here so maybe it's related to that?

**Edith:** Well it is funny now that I think about it like the cult uniform for a founder is a hoody and a VC it's not a hoody.

**Paul:** But they're dressing for their uniforms, like we are.

**Edith:** I don't know.

**Paul:** You need to get like a hoody dress. Like a dress with a hood on because you wear a dress all the time.

**Edith:** Everyday.

**Paul:** Don't you need to fit in the uniform somehow? Get your people to recognize that you're a founder?

**Edith:** I think there's a bigger issue than that.

**Paul:** I think if you got a tailor to put some hoods-- some like gray American Apparel hoods onto your dresses, you could really start a new trend.

**Edith:** The hoody dress. I do wear my LaunchDarkly hoody with my dress sometimes.

**Paul:** Oh okay, good.

**Edith:** I think a hoody dress is kind of wildly impractical because nobody ever actually puts their hood up.

**Paul:** That's absolutely true. I've been living in New York and you put your hood up there, its fucking cold.

**Edith:** But in San Francisco you know it's cold when people put their hood up.

**Paul:** Almost never.

**Edith:** Almost never, occasionally you'll see somebody like, woah.

**Paul:** It must be cold out.

**Edith:** My favorite hoodies were Takeepi.

**Paul:** Oh they had like, the ears in them or something? They had a monster logo thing going on? Do they have tails? Do their hoodies have tails at the bottom?

**Edith:** They're all different creatures.

**Paul:** Every hoody is a different creature.

**Edith:** So they got a creature for each person who got an individual hoody.

**Paul:** Oh, wow.

**Edith:** I don't know.

**Paul:** That's VC money well spent.

**Edith:** I think it's well spent if it makes people feel loyal to the company.

**Paul:** I actually totally agree.

**Edith:** That they're part of something bigger.

**Paul:** A friend, you know him, Sean Lynch referred to some startups as venture backed social clubs.

**Edith:** Tell me more.

**Paul:** Just that, you know when you're building a startup, some people build venture backed social clubs. A place for their friends to hang on VC dime.

**Edith:** Yeah, it's funny, so we raised our A and it felt really good but like I said it kind of raises the stakes.

**Paul:** I think a lot of people, when they think of, oh I want to take my developer tool and I want to build it out. They're doing it because it's kind of like the thing to do, right? The overlap between tech and startup is super high at the moment. And Hacker News is where we all hang and this is like 50% start-ups, 50% tech, and so you've got a nice product idea or whatever and so you think that the startup trajectory is the one for you.

**Edith:** And actually it's funny, I talked to a friend who I won't name and he was really impressed by us. He said you actually care about making money and I said of course, my employees, my teammates, they want to feed their families.

**Paul:** Yeah.

**Edith:** They got kids.

**Paul:** You can only eat VC money for so long.

**Edith:** Yeah and our customers want us to stay in business, I don't see it as a bad thing.

**Paul:** To make money. Only in a consumer space.

**Edith:** Talking about what?

**Paul:** The delaying of making money until much later it really only happens in the consumer space.

**Edith:** Yeah, I think the primary responsibility of a CEO is to make sure there's money in the bank. Because it does nobody good, like RethinkDB, their customers are all pissed off at them because they...

**Paul:** Well, there's a movement around RethinkDB, the open-source product now and the same happened with Cyanogen. I guess that's not a developer tools market.

**Edith:** Yeah and even like, we interviewed somebody the other day who'd worked at a company who's entire focus was going public.

**Paul:** Okay.

**Edith:** And then, for various reasons, they could not go public and he said the company morale just disintegrated.

**Paul:** Wow, was it because of revenue?

**Edith:** There were very legal issues which made it, it was impossible for them to go public but that had been their entire North Star is, let's go public.

**Paul:** Holy shit, yeah. If the values of your company suddenly gets decimated like that. Yeah versus like, so Josh Stein is our investor and he was in box and then they went public and then the real work begins.

**Edith:** Yeah. It's a step in the journey, it's an event.

**Paul:** They call it an initial public offering.

**Edith:** Yeah, it's not the end of the story and the same for us with our seed and our A, it was an exciting moment because it meant that we could begin a new chapter but it wasn't the end of the book.

**Paul:** Well this is on of the, one of the challenges that faces, let's say naive founders, which I think is almost everyone who gets into the game. The game never stops.

**Edith:** No.

**Paul:** So, people talk about exits, right? And there's no such thing as an exit because you're exiting to someone who has expectations.

**Edith:** Well yeah.

**Paul:** If you IPO you're exiting to people who expect you to grow more than 30% a year.

**Edith:** Yeah.

**Paul:** If you're exiting to a strategic investor, the exit money is connected to golden handcuffs that expects you to hit growth targets or integration targets or whatever it is you have. And you now have new tools at your disposal, their distribution channels, to help you get there and then if you're not exiting then it doesn't matter what you did last year, it's what have you done for me lately? It's, okay great, you double last year. Double this year, double the next year, double until the end of time.

**Edith:** Like lily pads in a pond.

**Paul:** Yep.

**Edith:** It's funny so along that vein, you read that [Fabric just got acquired by Google](http://fabric.io/blog/fabric-joins-google/)?

**Paul:** Yeah that was interesting, so Fabric got acquired, from Twitter by Firebase.

**Edith:** Yeah, I wonder whether it was just basically an acqui-hire? My impression was that Fabric wasn't really making any money for them.

**Paul:** If I had to guess, which I will, because I have no information.

**Edith:** I have no inside information either.

**Paul:** I mean Twitter had to get rid of it basically?

**Edith:** Well, it was a distraction, this goes back to what we were talking about earlier about meaningful. They're trying to focus on, tweeting.

**Paul:** I've heard many people suggest that it is not that they are focusing but that they have no idea what they're doing. And so they're flailing around in all sorts of directions and people are ascribing, some, whatever strategy they think is associated to it, to like the meanderings of a madman.

**Edith:** Is it a blind man.

**Paul:** Yeah, exactly.

**Edith:** Actually blind people have a very good sense of direction.

**Paul:** Okay, well it's pretty clear that Jack Dorsey's not blind.

**Edith:** Well, I'm just saying, like the joke, like a blind person.

**Paul:** Because he has no sense of direction. Oh, so good.

**Edith:** Don't make me start punning. Let's draw a veil over this.

**Paul:** Okay, so Twitter sold Fabric, to Firebase who I guess has something that they know how to do with Fabric.

**Edith:** Yeah and I honestly don't think either of them are making much money.

**Paul:** Firebase and Fabric? I don't know any Firebase metrics.

**Edith:** I don't either, they don't break them out.

**Paul:** Google expects the Google Cloud will be as big as their ad. So a hundred billion dollar revenue?

**Edith:** Yep if not more.

**Paul:** And they bought Firespace for a very nice amount as I understand it?

**Edith:** I think hundreds of millions.

**Paul:** I believe it is in the nine figure range.

**Edith:** Trés commas.

**Paul:** Yeah, seven to 11 figures probably. So yeah, so they care about it, and so I would say that it doesn't necessarily need to make money by itself but it's driving underlying business.

**Edith:** And that's, and we keep coming back to the same thing.

**Paul:** Right, so we don't know which it is, but it's certainly making Google money and it may not be making Google money by a line item on Firebase although I wouldn't be surprised if it does, but it's making Google money in the line item in the cloud business.

**Edith:** So at TripIt we looked at all out free users as a marketing expense. We would get in free users in a certain amount and then monetize onto there, premium products. I think that the, I keep saying the same thing, I think Microsoft and Amazon are looking at these dev products as similar, that they're getting people in the door, on their platform, and then using it.

**Paul:** And then they're just selling infrastructure.

**Edith:** Yeah, so they're basically using them as a freemium model.

**Paul:** That's interesting because you can't get away from the fact that physical computers exist. What I'm getting at is


<blockquote>Software is free, it replicates for free, hardware does not and so you can always give away software for free but there's a unit cost to selling hardware. </blockquote>


So when you're selling computation, if your business is marking up computation because of the software, someone can make the same software.

**Edith:** Or you could argue that all Heroku was doing was making it easier to use AWS.

**Paul:** Right and then they're marking up by like eight times.

**Edith:** Yeah.

**Paul:** And AWS had three different product offerings that tried to kill Heroku, or that tried to be their Heroku one, and they probably eventually hit it with Lambda, which will probably be a very big business for them.

**Edith:** I think Lambda's huge.

**Paul:** That's funny because I heard the opposite.

**Edith:** I heard customers of us who have already gone whole in on it.

**Paul:** As I understand it, there's a very limited subset of people. The amount of people who talk about how they've gone all in on Lambda is like very, very low.

**Edith:** Well, I think it goes back to like, like any new market, are we seeing the beginning of a wave or a little ripple that's going to die?

**Paul:** I think we're seeing the beginning of a wave.

**Edith:** Yeah that's what I think.

**Paul:** But I think that we're at the very beginning of that wave.

**Edith:** I wrote another article about serverless and why it matters.

**Paul:** Okay, serverless is interesting. So [Serverless](https://serverless.com/) the company?

**Edith:** No, I just meant the concept.

**Paul:** No, but I think, so, there is a company called Serverless, they're on the second floor here.

**Edith:** Yeah, I'm friends with them. So I was actually talking about just the movement.

**Paul:** Well, I understand, but they named their company after the movement, it's genius.

**Edith:** Which is clever except for it's not.

**Paul:** Isn't it?

**Edith:** But it's working for them.

**Paul:** Why isn't that clever?

**Edith:** It's clever if you can sufficiently dominate that term. So, I had a friend who had actually had a company called Cloud Native.

**Paul:** Okay, ah yeah, that's not going to work, everyone's calling things Cloud Native. Well, that sounds like it's two words, Serverless sounds like it's one word.

**Edith:** Yeah so you have to be very careful about can you own this? Because serverless was originally basically the JAWS framework which is not nearly so catchy.

**Paul:** What was it called?

**Edith:** JAWS framework?

**Paul:** JAWS, okay.

**Edith:** I forget what it stands for.

**Paul:** Serverless, great rename.

**Edith:** Yeah, great.
