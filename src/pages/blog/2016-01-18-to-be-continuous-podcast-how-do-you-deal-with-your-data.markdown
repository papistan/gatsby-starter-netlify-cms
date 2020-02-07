---
author: andreaech
comments: false
date: 2016-01-18 01:25:55+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-podcast-how-do-you-deal-with-your-data/
slug: to-be-continuous-podcast-how-do-you-deal-with-your-data
title: 'To Be Continuous: How Do You Deal with Your Data?'
wordpress_id: 769
categories:
- To Be Continuous
tags:
- continuous delivery
- Elixir
- Elm
- Feature Flags As A Service
- Haskell
- Heroku
- javascript
- Peter Van Hardenberg
- Zynga
---

In this episode, Edith and Paul are joined by [Peter Van Hardenberg](https://twitter.com/pvh?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) from Heroku. The group discusses how continuous delivery works with and against organizational structure, databases, and the pricing of your product. This is episode #11 in the To Be Continuous podcast series all about continuous delivery and software development.<!-- more -->

This episode of To Be Continuous, brought to you by Heavybit and hosted by Paul Biggar of CircleCI and Edith Harbaugh of LaunchDarkly. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.



TRANSCRIPT

**Paul:** So Peter, it’s traditional to ask you, what do you like best about continuous delivery?

**Peter:** Well, I’m increasingly old and I’ve done a lot of jobs and so I remember delivering Gameboy cartridges to the market and a Gameboy cartridge is a physical device that goes into a Gameboy, hence the name, and that process involves physical manufacturing and you get one shot and so there’s a tremendous amount of basically wasted and un-fun energy that goes into making sure you never make any mistakes.

My favorite thing about continuous delivery is the ability to make mistakes and move on with them.

**Paul:** Nice.

**Edith:** This would be a great time for you to introduce yourself.

**Peter:** Yeah, hi, my name is Peter van Hardenberg. I’m a Heroku old-timer, I’ve been with Heroku about six years now and I co-founded the Heroku Postgres team and have built a lot of products since then.

**Edith: **So it’s funny you’re talking about the Gameboy because Paul and I were just talking about that.

**Peter:** About Gameboys.

**Edith:** Because I said one of the things that had fueled the rise of Zynga was continuous delivery.

**Paul:** That’s the first thing we found about continuous delivery that was actually bad.

**Peter:** So I guess they’re probably still continuous delivering somewhere. In the great startup in the sky. They’re still around, aren’t they?

**Paul:** They’re still around, they’re still public and,

**Peter:** Farmville will never go away, I’m sure.

**Paul:** I think they’ve moved into other lesser things.

**Peter:** Developer tools.

**Paul:** Imagine.

**Peter:**** **Gamified developers. Well actually, it’s how all developer tools are becoming now.

**Edith:** Github is gamified. How many chickens do you have, can you make a nice pattern out of them.

**Paul:** New watches.

**Peter:** It’s a bit like a game except if you’re losing the game, you lose your job.

**Paul:** Or you just can’t get new jobs.

**Peter:** Well, that’s actually probably more accurate, yeah. Yeah it’d be a weird company if they let you go because you didn’t have a long enough commit streak.

**Paul:** On open source projects that weren’t your job.

**Peter:** I like that, actually, let’s make that a game.

**Paul:** We were talking in the last episode, as well, about open source funding models, or the anger over lack of open source funding models.

**Peter:** That’s a tough problem to solve.

**Paul:** That would be an interesting one. You get fired if you don’t have enough contributions.

**Peter:** Yeah, just put it on your quarterly review, current Github streak.

**Paul:** Let’s put this suggestion on Hacker News and see if people agree with it. I can pretty much picture how this is going to go.

**Peter:** I try not to read the comments.

**Edith:** So what do you think is liberating about the ability to make mistakes?

**Peter:** Well, I mean, more important than the ability to make mistakes is the ability to try things, right, I mean we, I’m so accustomed now to being able to see in great detail because of a SaaS model, sort of the reality of what my product is in the market and then vice-versa, I can turn that around and say, well, basically live and in real time, what’s happening if we put something out there, do people care?

Does it help with adoption? Is it suddenly throwing a bunch of errors? And if there’s a problem, you can roll back very quickly. You know we run a database product and so availability is really, really important but only for a very small core of the service. People are generally pretty understanding as long as your, sort of, problems and outages are brief.


<blockquote>Small and, sort of, blast radius and quickly remediated and I think that they prefer to get features vs. stability, sort of, at the periphery. At the core, they need stability over features, so, you know if you’re a stripe, right, you need to keep the payment processing online but if some ancillary piece of your API has a problem that’s probably not as big of a deal.</blockquote>


**Paul:** The dash part is less important—

**Peter:** Right.

**Paul:** than the payment going through.

**Peter:** Well, and responsiveness and progress are so important, and I think because we’re in such a changing market, the ability to drive forward is at least as important as the ability to keep things stable but you can’t do both in the same place, basically, right?

I think continuous delivery is cool because it’s separated, sort of, a slow-moving core from a fast-moving periphery.

**Paul:** So when you’re creating a software product, you really want every single component of it to be continuously deliverable, which means you want to be able to migrate from the thing that you are doing now to the new thing.

And so it’s interesting, or there’s an interesting thing about databases because databases, I think, were fundamentally not built for this model.

**Peter:** They’re heavy.

**Paul:** Right. We had a problem recently where we deleted an index.

**Peter:** Ah, yeah.

**Paul:** And, whoops, that index was in use. And we thought it wasn’t in use but it was in use.

**Peter:** You should’ve been using Heroku Postgres, it would’ve told you.

**Paul:** Oh so, that’s interesting. So the thing that I wanted was to be able to, you know, partially delete that or let’s run all the queries without that and then after an hour, I can actually delete it. What does Heroku Postgres offer you?

**Peter:** Well so we have a number of diagnostic tools where you can see exactly how often an index is being used. In addition, next time you’re trying to delete an index, wrap that in a transaction, so say, begin and then drop the index, then do whatever and then say, rollback, and that way, you can actually test as though you didn’t have the index because Postgres MVCC model means that all that stuff is totally transactional.

**Paul:** So you’re, when you say do all the stuff in between, what do you mean?

**Peter:** Whatever queries you want it to run. Also, and we’re getting into minutia and then some baseball here but you can actually disable indexes specifically, sort of at a session level as well.

**Paul:** Oh, interesting. This is all Postgres or Heroku?

**Peter:** Yeah, that part’s just Postgres I mean, we built the tooling around it so that you can do these things, kind of, the easy way but, I’ll tell ya, if you read that 3,000-page Postgres manual, you’ll find some real gems.

**Paul:** Well so part of the problem might be using a thing that’s not a real database?

**Peter:** Oh, you’re not using a real database?

**Paul:** We’re not—

**Peter:** Oh, that’s right, I forgot.

**Paul:** I mean we are using a real database, we’re using many databases but that particular one was not in a real database.

**Peter:** Well you know, even baby databases grow up to be real databases someday.

**Paul:** Yeah, well, fingers crossed that that particular database that starts with an M and that we shall not discuss.

**Peter:** Oh, we don’t like to speak ill of anything.

**Paul:** No, no not at all, especially Mongo.

**Edith:** No, you said the word!

**Peter:** You said the M word! So coming back to, sort of continuous delivery of every part of the stack, yeah, it’s interesting, I mean we’ve had some interesting challenges with databases in particular and I actually gave a talk at Heavybit a while ago about, kind of, how we treat databases less as part of a service in sort of the classical sense but more like a factory.

So basically what happens is when people request databases from us, we stamp one out and then, you know, we try and keep it pretty low entropy from that point on so we have a lot of tooling and support services around the database but the actual database itself, once it’s given to a customer, we mostly try and keep our hands off it.

Now if there’s security issues or performance issues or whatever, we’ll go in and we’ll kind of warm it up and do some work on it. But even still we mostly prefer to actually replace the database. What we do is we create a replica, bring it up to speed and then we transition the load over to it. And that’s kind of a form of continuous delivery for data services, which has been surprisingly powerful as an abstraction.

**Edith:** So you’re basically, you’re treating them as cattle, not pets.

**Peter:**


<blockquote>Oh absolutely, it’s all about the cattle and model and when you’re farming a very large crew of livestock, you can’t really afford to give each one their own personality.</blockquote>


**Paul:** This reminds me a lot of, I think, what started out as an IMVU way of doing data migrations, I’m sorry, of doing schema migrations without locking a whole table. For our people at home, I’ll describe this.

So when you want to add, let’s say you want to add a new value and it has a default to a particular table in your schema. There’s a possibility of that if it’s a particularly large table, for it to be locked while that happens. At least this used to be the way, I think modern databases are much better at this now.

**Peter:** I believe for some default values, it’s now the case that you don’t need to do a table lock but that might be pushed until 9.6 or Postgres, at least but it’s a common and challenging operation.

**Paul:** And so what IMVU started doing was instead of adding to a schema, they said that for every table, that schema is immutable and instead they created a new table and then they migrated the data from that table so every time you want to read from the user, you’re reading from user table 38 at the moment and then you start to read from user table 39. If the user isn’t in user table 39,

**Peter:** You fall back to 38.

**Paul:** fall back to 38, find it, migrate it, write into 39 and then do the thing. Then you have a background process.

**Peter:** If you have any listeners who are listening from the world of the Internet and would like to try implementing this technique for themselves, Postgres has something called a schema search path so you can actually, basically make each schema its own version and then you have a search path so if the table wasn’t in the newest version, it would use the last version’s search path.

**Paul:** Oh, wow.

**Peter: **You could set a version on your code then basically, as you make new versions of the tables and the new schema, you can kind of move them forward. This actually sounds like it would probably work. Now it’s really easy to say that from sitting around a table here in beautiful San Francisco but you have any listeners out there who do give this a try, have them send me a note.

**Paul:** I was not expecting this to be a session about continuous delivery databases and the intricacies of modern versions of Postgres.

**Peter:** I have to say, it’s one of the hardest things is basically, how do you deal with your data? I mean, data is sort of fundamentally heavy, I mean I think about it as having mass, which is to say, if you’ve got a few terabytes of data on a disk somewhere, just getting it out of that server and into another server is gonna take hours.

**Paul:** Right.

**Edith:** Right, just querying the data, loading it all into memory, that’s gonna take time and so this is really a challenge for continuous delivery and people have tried all kinds of schema versioning and replication strategies and sharding strategies but, you know, the old question, okay you deploy a new version of your code and it needs the new column but the new column’s not there yet. Okay so you move the data to the new column and then you deploy your code but then the old code doesn’t have it.

**Paul:** Right, right.

**Peter:**


<blockquote>And these are hard problems and no one’s really done a great job of answering them. So far, sort of the state of the art is, you know, you continuously deploy the new version of your code that supports both schemas then you continuously migrate your database and then you deploy yet another version.</blockquote>


Now without continuous deploy this is even harder—

**Paul:** This has to be tough on a Gameboy cartridge.

**Peter:** Oh yeah, let me tell you, I think we had 4k of RAM or something like that so at least it was fast. But yeah I think data and continuous delivery are both challenging interactions for sure.

**Paul: **We end up at this problem in the testing world when large customers, in particular, large enterprises use the old way of testing, which is you actually use a dump of your production database as part of your test suite and one of the major challenges we get when we’re looking at older companies who are coming to the new world, is, you know, your server’s over here, my server’s over there and I want to get a 5 Gig database dump onto your server to run my tests, how do I do that?

**Peter:** Right and it’s trying to, like, move a bathtub through a straw. So how do you do that? You just wait, right?

**Paul:** We wait until they stop doing that and then they can become our customers.

**Edith:** So do you turn customers away then?

**Paul:** We don’t turn them away but we don’t really support that use case, they’re going to have a miserable experience.

**Peter:** I mean there’s data migration again, right, just coming back to the physics problems. There are things that are getting better so,

**Paul:** The speed of light is improving?

**Peter:** the speed of light has gone up 13 percent in the last year, did you know that?

**Paul:** I don’t know if you’re joking, I presume you’re not.

**Peter:** It absolutely has not, yeah. They call it a constant for a reason. I suppose it could.

**Paul:** I thought there might be something about, like,

**Peter:** Dark matter, no but it was very convincing the way I said it, wasn’t it?

**Edith:** Like this is Hindenburg’s Principle?

**Peter:** It’s uncertain. So anyway, the logical replication scene is getting better. Amazon’s just launched a new service, it’s three letters long.

**Paul:** Oh really?

**Peter:** Yeah, uh, got it, hang on. DMS, Data Migration Service. And so through black magic and probably by not working very well, it will move all your data from one database to another in sort of a streaming online way which is really cool if it works.

**Paul:** Okay.

**Peter:** But, you know, moving from Oracle to MySQL

**Paul:** So you can talk to this service as if it’s MySQL and it will pull it from—

**Peter:** The way it works is you basically set up a migration job and if you think about it, it basically queries one database and writes to another and it’s a little bit of a hack job in the sense that you have to run, like, a desktop client if you’re moving from a local machine. It’s all very complicated and kind of baroque but,

**Paul:** So it’s an Amazon service? It isn’t you’ve used Amazon before, I gather.

**Peter:** But yeah, no, it’s what everybody’s always wanted which is to move their data from one place to another without having to think about it and, of course, it’s never gonna work.

**Paul:** Okay.

**Peter:** But, you know, it’ll help, it can help, things could be less terrible. I think ultimately that’s what got me into databases was the understanding that no matter how impossible it would be to make things good, at least we could make them a little bit less bad.

**Paul:** Right.

**Paul:** The soul-crushing misery of writing software could at least be slightly less crushy.

**Edith:** I feel like writing software is one of the greatest joys in life because you get to create something from nothing.

**Peter:** So you don’t work in databases.

**Paul:** I’m not sure you work in software.

**Edith:** So what are the biggest changes you’ve seen in continuous delivery?

**Peter:** Oh, ubiquity, certainly. It’s rare to meet someone these days that, maybe I’m just lucky enough, I live in San Francisco.

**Edith:** You hang out at Heavybit.

**Peter:** And I hang out at Heavybit with a bunch of other crazy people but I guess I would say growth then, right, I mean we’re seeing large enterprises practicing continuous delivery—we’re seeing small shops practicing continuous delivery, it’s not, sort of, a bleeding-edge concept that only, sort of, a small cadre of, like, sort of, avant-garde developers are doing. It’s really, I think it’s kind of the mainstream. Which is exciting, because the thought of going back to the old ways of doing things is sort of terrifying.

I was trying to come up with sort of a mental model for how the cost of software integration has changed by continuous delivery. I'll spare you all the math, but I actually did do some I promise.

Basically I concluded that, if you believe that more complex changes require more testing and that there's more cost from integrating those changes, which I think is fairly uncontroversial, basically deploy speed becomes one of the most significant factors to the success of your business.

You're ability to put software out there ... The amount of time it takes you to go from, "This is good code and we're ready to deploy it" to "This is out there in the world," the shorter you can make that time the faster everything else goes because if that time is long, then you're going to have a problem.

Paul :     You're going to have many changes and there's going to be a lot of that complexity.

Peter:    And it's going to create an incentive to bundle more and more changes together, which then means you'll take more manual testing and there'll be more integration overhead so you'll put more checks and balances in place and you get kind of a horrible feedback loop.

Edith:     Yeah.

Paul :     This is Firefox 4.

Peter:    This is Firefox 4.

Paul :     And many, many other releases.

Peter:    This is all the classic Enterprise software. This is basically how you end up going from hacking away on your laptop to doing annual releases.

Edith:     Annual or semi-annual or bi-annual.

Peter:    I mean how often is there a Windows version?

Edith:     Oh.

Peter:    To be fair to them it's a pretty big product. Although I did actually ...

Paul :     I think it has a lot of users as well.

Peter:    Yeah. Were you in the Windows 10 beta? I was in the Windows 10 beta. It was kind of neat.

Paul :     I haven't used Windows since 2003.

Peter:    You should give it a try. They're making a bit of a comeback.

Paul :     Okay.

Peter:    It was kind of cool being in the beta because it felt a lot of like a continuously delivered software package.

Paul :     Oh. Interesting.

Edith:     They wrote a blog post about it. They actually had different rings of beta releases.

Peter:    Yeah. Yeah. I tried to get to the innermost ring I could. It was just a game laptop. I was fine with it if it got trashed. It was just kind of fun to be close to the middle of that.

Paul :     Did it get trashed?

Peter:    Just the once.

Paul :     Okay.

Peter:    But I think that might have been my fault.

Edith:     In the article they talked about how they stopped actually giving release dates.

Peter:    Yeah.

Edith:     Because they said giving release dates would just cause them too much angst. Like if they said something had to come out on March 1st and they would defer features or split up features ...

Peter:    Yeah. You can cut scope or you can move dates, those are you're options.

Edith:     Yeah.

Peter:    Or I suppose you can…

Paul :     You could just delete dates and then you're sorted.

Peter:    Right. It was funny. I was talking to some engineers at Heroku recently about ship dates. I've been on death marches before. The games industry is quite famous for them. I was saying, "Well, surely you must be opposed to having shipping dates for projects in the early stages." I was actually surprised to hear that they didn't. I think that maybe the pendulum swung so far the other way that, to some extent, I think creating a date kind of gives you the focus and clarity to …

Paul :     There's certainly benefits to shipping dates.

Edith:     Like we had Kevin from Acompli and he said they shipped every Friday.

Peter:    Yeah. That's not really continuous, I would say, but it's really on him. It's on the right path.

Edith:     He was mobile, so that's ...

Peter:    Oh yes.

Edith:     ... that's when they cut the bill to give to Apple.

Peter:    Yeah. You know who doesn't have continuous delivery?

Edith:     Mobile.

Peter:    Apple.

Edith:     Yeah.

Peter:    If you're on Android, you can just ship all day long. You probably shouldn't, but you could.

Paul :     No one will notice anyway.

Peter:    Ohhh.

Edith:     Ohhh.

Peter:    Android users exist.

Paul :     I know, but we're in San Francisco

Peter:    I know this is because you're in San Francisco. Hang on. The audience can't see it, but for the record I am holding up an Android phone.

Paul :     Oh wow.

Edith:     And you're wearing ... a LaunchDarkly T-shirt.

Peter:    I am wearing a LaunchDarkly T-shirt.

Paul :     As are we all.

Peter:    What an amazing coincidence. It's a beautiful shirt. It's a beautiful shirt. If you don't have a LaunchDarkly T-shirt, how do you get one, Edith?

Edith:     Info@launchdarkly.com

Peter:    That's great. You should get one of those.

Paul :     And if you need Feature Flags As A Service, also launchdarkly.com.

Peter:    This is what I've heard. What are Feature Flags As A Service?

Paul :     We just do this every episode.

Peter:    Oh, that's fantastic.

Paul :     Yeah.

Peter:    Well, it's not really important.

Paul :     If you're a listener of the podcast, you will not be unaware of what Launch Darkly is or how Feature Flags As A Service work.

Peter:    That's great.

Edith:     So you came out of the gaming industry. You saw the death march. Then you just said something interesting about how the pendulum might have swung too far.

Peter:    For me personally, maybe my own pendulum swung too far. Having been in kind of a very conservative and very single-release, get-it-right kind of world, coming to the world of online service software I really appreciated the ability to try to experiment, to put things behind a feature flag and give it to a few users or give it to a lot of users and to do those kinds of roll-outs. I think I got so used to that that maybe I kind of came to reject the idea of specific dates in general and maybe took it too far.

I wouldn't say that I'm happy to sit around for a year on end, but I think I'm coming to realize that the dates are valuable scoping tools. You can always slip a date. You can't always slip a date; it depends on your partners, but you can usually slip a date if you have to. It's a helpful and clarifying tool to set you on a path towards delivering a larger project.

Paul :     I think that there's a lot of people who came from the school of "We'll ship it when it's ready," who maybe didn't have the sort of constraints that actually allowed them to ship more quickly.

Peter:    Yeah. And ready is impossibly to achieve if you don't have something that's really forcing you to converge.

Paul :     Right, right, right.

Peter:    You see these kind of ... I've seen friends who had startups that kind of tried to take that mentality, but because they didn't have that date, they didn't have that driving pressure to get out the door ... Maybe continuous delivery just depends on like incredible impatience as well.

Paul :     I think part of the source of this sort of "We'll ship when it's ready," comes from companies and work flow processes that we've seen that look to be successful but aren't necessarily replicable. There's a lot that opensource has to answer for in terms of the way that they ship software. The PR that has to be perfect and the semicolons have to be in the right place before they'll get accepted even though, in a company, you might take it because it actually makes the world better.

Peter:    Right.

Paul :     The other influence I see on this is GitHub. A lot of people took their lead from how GitHub made software. GitHub has a unique set of circumstances that other software companies, small startups don't have, which is they're massively successful and have just so, so much revenue that they're able to make all those sort of mistakes that your small company isn't able to make.

Peter:    I think GitHub had a significant learning experience organizationally.

Paul :     Well put.

Peter:    The "Everybody works on whatever they want and nothing has a date" kind of mindset was very appealing in a kind of egalitarian, like "We trust each other, no one has to be the boss" kind of way, but I think that as the company grew it became probably increasingly difficult for that to really work because it turns out that you don't necessarily want someone bossing you around but it's really helpful to know what you're supposed to be working on. GitHub is interesting.

They're an unusual company in a number of ways, but not least among those is that I think their kind of punk-rock ethos didn't necessarily scale as far as they'd hoped it would. I think that, while they built a lot of great software, I think that ... People talk about the tyranny of structuralistness, right?

Paul :     Yeah.

Edith:     Absolutely.

Paul :     That's a wonderful paper.

Edith:     Yeah.

Peter:    I think that GitHub today has come to appreciate the incredible usefulness of everybody in an organization of knowing what you're supposed to be working on, when, who's supposed to be working on it, and who to ask when you have questions, or "Who makes a call when there's a disagreement?"

Edith:     It's like the saying, "People who say we don't have a software process ..."

Peter:    It's just not documented.

Edith:     If you say, "We don't have a management structure ..."

Peter:    Then it's just not written down.

Edith:     Yeah. It's still like, "Oh, so and so is friends with so and so," then it's actually even more ...

Paul :     There's always a hierarchy even if it's …

Edith:     ... and it's even more insidious.

Paul :     Yeah.

Edith:     ... because you think you're a peer but you're not.

Peter:    I'm a huge believer in transparency. A well run company will have a formal power structure or a formal reporting structure that mirrors, kind of, the informal one.

Paul :     You mean the closer a formal structure is the actuality the better?

Peter:    I would say so. It's never good if you have someone who's kind of secretly in charge, but not really in charge and kind of meddling, but doesn't really have the authority to do things. One, you should probably recognize that person, or two, they should ... Things are not behaving well if you have that kind of thing.

Edith:     That's kind of like the concierge in mafia terms.

Peter:    Right. Exactly. A consigliere.

Edith:     Peer of peers is better.

Paul :     Going back to GitHub, I think that GitHub's organizational woes were things that they overcame and it sounds like everything is working pretty well now, but they're the sort of things that, if GitHub hadn't been massively successful, would probably have killed it.

Peter:    Certainly. I think we only see the survivors. If you look at opensource projects, the 99% of opensource projects that are started never become a 25-year old Post Crest database, for example.

I think that also emulating late-stage, mature projects with an early stage project is a huge mistake for the same reason that you wouldn't go download a copy of IBM's employee handbook for a two-person startup. You don't want to use the same software processes for a small project that you would for something that spans 200 engineers. It just doesn't make sense.

Paul :     The size that you have allows you to do things like continuous delivery much, much easier.

Peter:    And I think continuous delivery has different values in large and small organizations. It comes very naturally for a small organization. I think larger organizations have to make a bigger investment, but I think they can see commensurate returns when they do.

A good example would be Etsy who deploy thousands and thousands of times a year with an engineering team of ... I can't remember. ... 150 or something like that. That's just their model. They kind of came up that way and their not afraid to make changes and occasionally break things in the sort of service of trying to improve the product.

Paul :     One of the things I wanted to ask you about is you've just gone through this big pricing change at Heroku. You gave a talk at Heavybit about it last week. Heroku is a company that obviously does a lot of continuous delivery.

Peter:    Absolutely.

Paul :     I'm curious about a big change like pricing, how does that fit into that whole model?

Peter:    Yeah. Pricing is difficult because it's something that's very important to all your customers.

Edith:     Perhaps the most important thing.

Peter:    Perhaps the most important thing. As I said the other day, pricing is product. People really understand your product through its price. The pricing page is one place where you really have to be very careful about being completely accurate all the time because no one wants to find out they're not getting what they thought they bought.

When you're making changes to your pricing, at least for us, this meant basically touching every part of the company: the marketing, the sales team, documentation, but also a lot of internal systems. With a pricing change, you tend to roll this out gradually and so when we did our pricing change we actually went through a number of ever-increasing groups of users in order to improve the process and to improve the final product.

I know we spoke about this the other day, but of course, for the listeners, the early alphas of the product look wildly different from the final pricing. Indeed I think we learned a lot through that process and people were pretty happy with the end result because of the things that came out of that.

Throughout the system, we were constantly shipping small and incremental changes usually burying them being opt-in beta flags and so on and so forth. One of the great benefits was, by the time we went to GA, we had thousands of users in the new pricing giving us feedback, testing all their software against it, so we were extremely confident on that day. What we really spent the GA day doing was just making sure the blog post was how we wanted it to be. We were very confident about the software.

Edith:     So you'd done a canary release of your pricing?

Peter:    Oh yeah. Absolutely. Yeah.

Paul :     And people were able to opt into the new pricing or opt out?

Peter:    Right. In the beginning it was just strictly invite only. People got the option to opt in. As we kind of expanded it out, we gave more and more people the ability to opt in. Eventually we gave everybody the ability to opt in. Then for our GA, what we said was "New users and new apps just got it by default from then on."

This worked pretty well for us. I think because it was largely a price cut ... We sort of moved some things around, which was sort of challenging, but in the end almost everybody's prices came out lower, which if you're listening to this and you aren't one of those people, I'm sorry.

Edith:     You can write info@launchdarkly.com for a T-shirt.

Peter:    Or you can tweet at me at @PVH and I'll apologize. By the time we went to the public, the final kind of release, we knew who was happy, who was unhappy, we know what worked and what didn't. Some people had been using it for six months and been very happy with it. I think you can't always do that, but when you can do it it's great.

Paul :     It sounds like it was very much a continuous delivery process.

Peter:    Oh, absolutely.

Paul :     ... like the same as ...

Peter:    Yeah. Continuous pricing.

Paul :     Right.

Edith:     Yeah.

Paul :     Obviously a lot of it was actually software and actual product changes. A great deal of it seems to have also been analysis and data collection. It sounds like it's just another part of the product.

Peter:    Yeah. Your pricing is just another part of the product.

Edith:     Yeah. Just like your email communication is part of your product.

Peter:    Yep. If you're not treating it that way, you're doing it wrong.

Edith:     Or even just like your support and even your tweets are part of your product.

Peter:    One of the hardest things, I think, is, as a team scales, making sure all those pieces move together. Some of it is good data. A lot of it is just learning to work in the large. When the person who writes the tweets doesn't know the person who wrote the software, how do you make sure that the message carries through? These aren't new challenges.

Edith:     A famous story I heard about Steve Jobs was he got into an elevator with an engineer and he asked the engineer what he was working on. The engineer kind of hems and haws and says something and Steve Jobs is like, "That's absolutely wrong. That's not our message at all. You're fired."

Peter:    Wow. Poor management style right there. Don't do that. If you're listening to the podcast ...

Paul :     I hear he was lovely.

Edith:     And I turned it around. I'm like, "It's Steve Jobs' fault that he was not communicating down ..."

Paul :     Absolutely.

Edith:     "... the chain." It's not the poor engineer's fault to have the vision. It's Steve Jobs fault that he's not saying, "This is what we're doing," and passing it down.

Peter:    The burden to communicate is on the person doing the communicating, not the person who's trying desperately to understand you apparently in order to save their own job.

Edith:     Yeah. So he's like, "I can't have somebody working for me who doesn't know what we're doing." It's like, "Well, that's ..."

Paul :     I'm going to take this on a slight tangent here and say that it's neither of their faults and that one of the major problems I see in organizations is that they look for faults rather than looking for, "How can this be better in the future?"

Edith:     Oh, of course.

Peter:    Oh yeah.

Edith:     Of course I agree with you, Paul.

Peter:    I'm going to put a plug in. My favorite book of all time I think is [The Field Guide to Understanding Human Error](https://www.amazon.com/Field-Guide-Understanding-Human-Error-ebook/dp/B00BL0OZ0E/ref=mt_kindle?_encoding=UTF8&me=). This is a fantastic read. If you like planes crashing and people dying on the operating table, this is the book for you.

Edith:     Hey, I was looking for a Christmas present for somebody.

Peter:    That's perfect. Basically what this book is about is trying to understand why perfectly good pilots drive airplanes into mountains.

Edith:     Oh, there's a name for that, controlled flight into terrain.

Peter:    Right. Uncontrolled? Oh, controlled flight, yeah, because they've got their hands on the control.

Edith:     Yeah. They used to think ... No, it's like literally they will steer directly into a mountain.

Peter:    And it's fascinating for our industry because, obviously, medicine and flight have significantly more investment into understanding those fields than software. Clearly no pilot wants to fly into a mountain.

Edith:     Well, the consequences are pretty binary.

Peter:    Yes, but yet it happens all the time. People classify this as pilot error in the formal right-ups. Over the years, that doctrine of kind of blaming the pilot began to break down as people began to understand, for example, user experience. A great story from that book is there used to be this real problem where they would drop planes on the runway. You'd be going, you'd be in a plane, you're getting ready to take off, and suddenly the plane just falls on the runway. What happens is the pilot has lifted up the landing gear.

They would blame the pilot for this and say, "Oh, it's pilot error." Actually what happened was finally somebody went and looked in a cockpit and there are two levers, one that would control I think the flaps and one that would control the landing gear. They were the same size and shape and they were right beside each other. If you weren't looking at the handle, it was easy to grab the wrong one. Oh, and to make matters better on some models of plane they were the other way around.

Edith:     Oh no.

Peter:    This is unbelievable. It's a pilot error; the pilot grabbed the wrong handle, but it wasn't a systemic approach to understanding the problem. The bad news is, if you read this book, and you really should, they get into a number of different models for kind of trying to understand why failures happen.

You can kind of look for the break-the-chain model where, "Oh, if the pilot had grabbed the right handle, then if you only make the handle right, then the pilot will always grab the right handle," but there's all kinds of different models. There's like an epidemiological one where there's latent risks in the systems so you try and identify them before they happen rather than after. Basically all of these models have different kinds of defects.

One is people go around chasing things that will never happen. Another one is, "Well, you break the chain so this particular problem won't happen, but there's actually 50 more ways this problem could be triggered and you just end up complicating the operation environment." The bad news is that the author concludes that personal responsibility is an important part of safety, which is sort of an unsatisfying conclusion if you're a software person and you need to automate things. But these are hard.

Paul :     As you're saying each of these, I could think of a bug analogy for them.

Peter:    Oh, absolutely.

Paul :     You could be running your fuzzers to find all the bugs that could ever happen, and maybe you want to fix them or maybe you don't. Where is the ROI?

Peter:    Yeah. It's a hard thing to know. Anyway, it's an excellent read and it's certainly very inspiring for me. In our game, automation is the only way to scale. The author concludes that actually not automating and trusting pilots is the right way to scale, but we need to find our own solutions here in our industry.

Paul :     The solution that we tend to have is we look at what unicorns did and we try to emulate that.

Peter:    As I've been fond of saying, cargo culting off unicorns is not the path to success for anyone.

Paul :     I've a similar idea.

Peter:    Basically you kind of have to understand your own business. Those Unicorns didn't get where they were by cargo culting off something else either.

Paul :     Right, right, right.

Peter:    Right? If you want to succeed, you have to look at the fundamentals, you have to think about what's important, and then you think about how you're going to get them things. That's not really rocket science but it is very difficult.

Paul :     My version of that saying is that advice is not for you. It's basically ... When you look at basically anything that goes on the [First Round Capital blog](http://firstround.com/review/) about how some unicorn did some thing, how Slack grew overnight or how Stripe does whatever, it's like, "Well, that was Slack, that was Stripe, from our example earlier: that's how GitHub makes software, maybe it worked for them, maybe it didn't. We have no way of knowing because they're a unicorn and the rules that apply to them don't apply to you."

Edith:     Not even that, a lot of advice is temporal.

Paul :     Yeah.

Edith:     Like something that was very appropriate for that moment in time could be completely different.

Paul :     That moment, that place, that specific set of circumstances.

Edith:     Like six months later the world has moved on.

Peter:    More than that, I think there's also attribution error going on. Sometimes things are happening for reasons nobody understands, companies become insanely huge not out of any particular merit. Actually here's a great bit of science. I love studying this stuff.

Edith:     We all do. That's why we're here.

Peter:    A research project basically got a bunch of people to listen to music through their service. What they did is they had several different universes where you could see what other people were listening to, but they segmented all the users. You could be in universe one through six, but you'd see what other people were hearing.

Then there was a final universe where you couldn't see what anyone else was hearing. Basically it sort of simulated the radio environment where you could hear what was popular. What they found was that in each of these different sort of groups, different bands rose to the top of popularity. What determined popularity was popularity.

Edith:     Yeah, that's so true.

Peter:    The control group, obviously, didn't have this problem. What they found was, basically, a band had to be good to be eligible to become really a breakout, but which bands broke out totally depended on which ones got some early momentum. Maybe Slack is popular ...

They've done an amazing job of being worthy of and deserving of their success and I think they're a fantastic company and I have lots of friends there so I'm a little biased in their favor, but let's not forget that just because something worked for them doesn't mean they know why it worked or how it worked or that anyone else could do it.

There's also a big element of dumb luck and being in the right place at the right time. You have to figure out how to capitalize on that opportunity when it comes.

Paul :     So if I'm analyzing Slack, I can probably say that it's the polish, the design.

Peter:    It's the folksy tone of the error messages.

Paul :     Right, right, right.

Peter:    It could be all of those things or none of them.

Paul :     It could be all of them or it could be none of them. It could just be that people were sick of HipChat and this was the next thing that came along and it was good enough.

Peter:    I mean I'm plenty sick of HipChat, I'll tell you that right up. It's kind of a mean thing to say. I'm sorry.

Paul :     I really loved HipChat.

Peter:    I really loved Campfire once too.

Paul :     Yeah. Yeah.

Edith:     That goes back that Slack is the hottest right now and soon something else might be really cool. That's what we just talked about, is everything goes through its kind of fad.

Peter:    If you're so lucky as to get that period. Certainly I think Heroku I hope is a little less boring than it used to be. There was a time when people loved Heroku strictly because people loved Heroku and not of any merit of our own.

Edith:     We were talking about this about languages.

Peter:    Oh, program and languages, yeah. What's the next new thing? Elixr? Crystal?

Paul :     Elm.

Peter:    Elm. Oh geez.

Edith:     That used to be an email client.

Paul :     It was, yeah.

Peter:    It still is.

Paul :     Elm is the new shiny thing, well, one of the many new shiny things.

Peter:    What is so new and shiny about Elm for the listeners?

Paul :     It's Haskell for JavaScript.

Peter:    I'm sorry. You lost me at Haskell.

Edith:     That's like somebody pitched me an idea of Uber for pedestrians. I'm like, "I don't even know what that means."

Peter:    Haskell for JavaScript. Wow. That is either the best or worst idea I've ever heard. I'm pretty sure it's going to be the latter.

Paul :     I think it's closer to the best.

Peter:    Okay. Make the pitch. Why should we try Elm?

Paul :     I haven't tried Elm, so I'm just literally ...

Peter:    The hype is strong with this one.

Paul :     The hype is very strong.

Edith:     I hear Paul has a couple other business ideas too.

Paul :     I think static typing solves many of the problems that people have with writing JavaScript. That's it. That's all I got.

Peter:    Sounds good.

Paul :     So it sounds worthy of a try.

Peter:    I think the real problem with JavaScript, having written a tremendously large amount of JavaScript is not knowing how you got to where you are in the call stack because everything is asynchronous. How did I get ...

Paul :     Almost a synonymous problem.

Peter:    How did I get here and why is this argument undefined?

Edith:     That's like the meaning of life.

Paul :     This is what static typing solves.

Peter:    Kind of.

Paul :     Yeah.

Peter:    You can still pass around null values.

Paul :     Right, right. Maybes.

Peter:    Maybes. Right.

Paul :     This is exactly the kind of problem that [inaudible] solves.

Peter:    Now you know why you're screwed, but that doesn't necessarily help.

Paul :     Exactly. Yeah. The first step to solving the problem. It's no longer in the 37th stack frame. It's in your checker before it wounds out to your customers.

Peter:    So one would hope. I'm sure that Haskell and Elm and every other language will give you plenty of room to hang yourself still.

Paul :     I'm sure.

Edith:     Yeah. So Peter, speaking of rope, what are some of the pitfalls or drawbacks of continuous delivery? Are there any gouges or things that you'd warn people about?

Peter:    I think success from continuous delivery comes from, one, having good data to act on. If you're not following the important things and then following up, then it doesn't matter how often you deliver you're not going to see much benefit. You're just essentially random-walking your way around the market.

Two, you have to be actually prompt with your continuous delivery. If you have things hanging around in branches indefinitely, your cost of delivery just goes up and up; you pay the integration costs, you just pay them continuously. Short-lived branches I think ... Some people say, "Oh, you have to develop on master."

I think short-lived branches are fine. Everybody is used to pull requests these days so that's not a big deal. I think those are probably the two biggest things. I think a good culture of code review: prompt, thorough, thoughtful, friendly, "You're not being review; your code is," that's sort of the third piece.

Paul :     I'm not convinced about the code review part of it.

Peter:    Go on.

Paul :     I guess I'm just not sure what the problem is that is being solved by code review.

Peter:    I think that traditional software models have a much larger quality assurance phase and tend to have more formal organization around software releases, the "What are you doing?" the "How is it being structured?" There's a great book ... Actually it's not a great book.

There's a great chapter in a mediocre book called The Architecture of Opensource where the Berkeley DB authors write about creating Berkeley DB and the lessons learned along the way. I hope I get the quote right. It was "Patches and bug fixes erode software architecture." When you think of what that means for continuous delivery, what you have is many, many small things happening all the time.

Paul :     Right. A continual erosion of the architecture.

Peter:    Right. The idea behind good code review is it sort of gives you an opportunity to reflect on that and comment on it and have other people understand what's going on. It's certainly not essential in the small, but if you're talking about success over the long term or over the…

Paul :     I don't want you to think I'm against code review. I think every single pull request in the last like three and a half years, maybe, at Circle has been code reviewed before it got merged, but I find myself sometimes just wondering, "What exactly are we doing with this code review?"

Peter:    Yeah.

Paul :     Is this a syntax thing? Very often it ends up being product reviews are being conducted at the end of like five days of coding. Before we had a real product process at Circle, this was a real problem, that someone would build a thing and that's when it would first come out for product review.

Edith:     So you had a process and it was you built it and then reviewed it.

Paul :     Yes. Right. The product review happened very, very late in the product cycle and it resulted in people being very unhappy when ... If some of the ...

Peter:    Because they had spent a huge amount of time and …

Paul :     Right. Some of the early product decisions or some of the early product decisions that they made, there was disagreements as to whether that was the right product decision, then that led to problems. If you're of the GitHub/opensource view of ... Sorry. It's unfair to give it to GitHub. I think this might be a Linus Torvalds thing of code talks, something like that.

Peter:    Bullshit walks, I think is the expression.

Paul :     Yeah, yeah, yeah.

Peter:    Yeah. I think the PR model ... Historically in the opensource world, it's very common for weeks on end on a patch, drop it on a mailing list, and then be told to go stick your head in a pig because no one cares. Obviously in a work environment where, one, you're paying someone for that time and, two, they will quit and then you'll have to find someone else if that happens too many times, that's undesirable.

Paul :     Or you just don't hit your own goals as a manager or product owner or whatever.

Peter:    Yeah. Or as an engineer. The opensource model is you tend to have one or a small number of, basically, dictators who decide at their whim.

Paul :     Hopefully benevolent ones.

Peter:    Well, dictators ...

Paul :     ... or occasionally.

Peter:    ... rarely remain benevolent.

Edith:     I think to Paul's point, it's really just about being lean with, even, development.

Peter:    Yeah.

Edith:     I'd say when you build something you have domino effect, like you spent five days on it and you don't want to throw it away even if you're wrong.

Peter:    I have kind of a mental checklist on projects about whether or not something is ready. You kind of run it more or less formally depending on what the project is and how big and how many things it touches. Is the product good? Does it solve a real problem people have? Does it do it correctly? Is the engineering good? Is the code well written? Is it well architected? Does it fit into the architecture? If it introduces new abstractions, are they the right ones?

If it introduces no new abstractions, should it? That kind of thing. SRE, is it going to break? Is it going to perform? Does it have security holes? Is it good? Is it hardened? Will it go bump in the night when too many users try to hit it at once? If you've got those sort of things, like "Will it work? Is it built right?" and "Does it solve a customer problem?" then you're probably ready to go.

Paul :     That introduces a lot of friction into the small, one-line book fix that you're about to release.

Peter:    I would run that sort of checklist personally if I spent more than a week on something.

Paul :     Sure. No, I'm being devil's advocate here.

Peter:    For a one-line bug fix, sure.

Paul :     Suggesting largely that very frequently code review concerns often form roadblocks.

Peter:    What percentage of downtime, Edith, do you think is caused by single-line bug fixes?

Edith:     If I had to guess, I'd say the less damage you think it's going to make the less time you spend reviewing it and therefore the more likely it is to break something. I say this on my own of like ... This is my own experience of like ... You know the famous phrase of, "What could possibly go wrong?" If you're doing a complex data migration, you spend a ton of time on it.

Peter:    Yep. And you get good reviews because it's sort of the opposite of the bike shed problem, which is like a complicated patch people will be thorough with, but like "Ah, a couple of lines, it's a doc string," no one notices you forgot the comma on the end of the line, you push the code.

Hopefully you're running continuous integration so it goes red at least, but the more subtle errors can slip past you because you put a seven instead of an eight and now you've provisioned the wrong things relative to what the pricing page said and "I didn't realize because it was just a one-line change."

Paul :     Or the example from earlier, like "Are we good to delete this index?" It's like, "Yeah, we're not using."

Peter:    Sure. No one is using it.

Paul :     Yeah.

Peter:    Yeah. I guess at least code review means there's a second pair of eyes, someone is taking a second that didn't write it to think "Does this make sense?" Of course I learned back when I used to get a lot of code reviews ... I'm more of a product manager these days.

Edith:     Everybody is a product manager.

Peter:    Everybody is a product manger now, but no one is a product manager, there's too many of them. Back when I used to get a lot of reviews, I just knew who to ask for what kind of review I wanted. If I was worried about the architecture, there was someone I would ask and they would give me a really ... They would always really critique the style and thoroughness of the patch.

If I wanted someone to check it for obvious bugs, I knew someone I could ask and they'd do a technical edit on it basically and read each statement backwards individually to make sure it still made sense. If I just wanted to ship the damn thing and I was hoping for the best, then I knew who to ask for that view too.

Edith:     That's actually really good advice, Peter. That's something that we talk about a lot, is the trade off between time/quality features. You're also trading that off even in your code reviews.

Peter:    Yeah. It's sort of subconscious, but when you ask someone for a review, if you've worked with them for a while, you know what they're going to review and what they won't.

Edith:     Yeah. I love quality, but sometimes you've just got to ship stuff.

Peter:    Yep. Sometimes you've just got to ship it.

Edith:     Because the biggest risk is always just that there's no business value.

Peter:    Yeah. Sometimes you can put things out there and then see if there value, and if there isn't, you'll take them away again.

Edith:     Well, Peter, we really enjoyed having you here today. Do you have any parting thoughts around continuous delivery or why people pun?

Peter:    I don't know that we talked about puns on the podcast. I think that was before the recording.

Paul :     I think that was an aside.

Edith:     I was hoping you would talk about them now.

Peter:    Do I have any thoughts about continuous delivery or why people pun? I think punning is one of the great joys of life.

Edith:     I totally agree.

Peter:    It's that little bit of wordplay. Actually I was thinking about this on the way over. It's not really a pun, but I was trying to figure out what the emoji representation of a podcast is. Like microphone, cellphone, broadcast tower? How would you represent a podcast as an emoji?

Edith:     Emojis are ...

Paul :     I think it's the little pile of poo.

Peter:    No, that's already taken by everything else.

Edith:


<blockquote>Emojis are basically a reduction back to hieroglyphics.</blockquote>


Peter:    Yeah. I love it.

Edith:     We came up with all of these letters so that we could have complex thoughts and now we're going back to hieroglyphics.

Paul :     How did the ancient Egyptians represent podcasts?

Peter:    I think it was Eye of Horus, ankh, and then a foot. Yeah. I guess we'll close on that then.

Edith:     Thanks so much for coming by.

Peter:    All right. Thanks, everybody.

Paul :     Thanks for this episode of To Be Continuous brought to you by Heavybit and hosted by me, Paul Biggar of Circle CI and Edith Harbaugh of Launch Darkly.

Edith:     To learn more about Heavybit, visit heavybit.com. While you're there, check out their library home to great educational talks from other developer company founders and industry-
