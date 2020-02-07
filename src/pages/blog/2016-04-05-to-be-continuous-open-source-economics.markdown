---
author: andreaech
comments: false
date: 2016-04-05 23:43:59+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-open-source-economics/
slug: to-be-continuous-open-source-economics
title: 'To Be Continuous: Open Source Economics'
wordpress_id: 891
categories:
- To Be Continuous
tags:
- Confluence
- Databricks
- Heroku
- javascript
- Kafka
- LinkedIn
- Linux
- Mikeal Rogers
- Nadia Eghbal
- NodeJS Foundation
- open source
- open source software
- OpenSSL
- Python
- RedHat
- ruby
- Sean Byrnes
- Steve Henson
- Steve Marquess
---

In this episode of To Be Continuous, Edith and Paul are joined by [Sean Byrnes](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=0ahUKEwjm3ZrNl7nVAhWFQiYKHel_DIYQ6F4ILzAB&url=https%3A%2F%2Ftwitter.com%2Fsbyrnes%3Fref_src%3Dtwsrc%255Egoogle%257Ctwcamp%255Eserp%257Ctwgr%255Eauthor&usg=AFQjCNEHo6WTsCbNjwv7a828hxo1IsWt0w), CEO of [Outlier.ai](http://outlier.ai/), and [Nadia Eghbal](https://twitter.com/nayafia). The group discusses open source economics, and examines several potential evolutions of adding money to the open source equation. This is episode #17 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.



**TRANSCRIPT**

**Edith:** Nadia what do you like best about Open-source?

**Nadia:** I like that Open-source is where I feel I spend time with a lot of creative people, it’s sort of like creative talent at its best, then it feeds directly back into the rest of start-ups and technology and everything else that I love. It seems like everything starts with Open-source which makes everything magical.

**Edith:** Sean what do you like best about Open-source?

**Sean:** It’s the community I enjoy learning from other people, I enjoy being able to find people I wouldn’t be able to connect with that I have interests in common with, and the community that helps because I consider Open-source to extend beyond just ready lines of code to sharing ideas and sharing concepts and sharing solutions to problems. While I might not always use those same solutions I’m always inspired for new ways to solve other problems.

**Paul:** That’s super interesting because nobody said that they like how it supports their Silicon Valley start up through share cropping, or nobody said I like how I get paid to work.

**Edith:** Paul that comes later in the episode but this would be a great time for our guests to introduce themselves.

**Nadia:** I’m Nadia Eghbal, I’ve been writing recently and thinking a lot about how to support Open-source infrastructure. Originally I had a background in non-profits and impact investing and working with foundations, but most recently I was founder of a start-up and then I went into venture capital, and have sort of seen the system from all different sides. Would love to marry together all those different interests and topics, which seems to happen in Open-source.

**Sean:** I’m Sean Byrnes I’ve been writing software most of my life, I’ve also been a founder of companies and an investor. I would not consider myself an expert in Open-source and I don’t want to claim that pedestal but I have … I am the maintainer of some Open-source libraries which seem to be pretty popular, and I have contributed to others. I think that I’ve been lucky enough to know a lot of Open-source developers in my life which is by no means a majority of them but enough that I feel part of the community at least.

**Paul:** One of the topics that we were discussing just before the show started is this idea of how Open-source developers get paid, or if Open-source developers should get paid. Nadia it sounds like you’ve been talking about this for a while or thinking about this for a while, can you kick us off.

**Nadia:** Yeah, I actually have a new thought on this topic from [Mikeal Rogers](https://twitter.com/mikeal?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) who runs the NodeJS Foundation. He said recently I think on the last post I had written that everybody gets paid for Open-source, and I think that’s a really great way to start thinking about it versus saying that nobody gets paid. In the end we’re contributing time to Open-source, and in the end somebody is paying you to have the time to work on Open-source. Whether it’s your employer and then you can work on Open-source full time at your job, or you’re full-time employed and that gives you the bandwidth to be able to work on Open-source on the weekends or whatever.

When you think about paying people to work on Open-source I think people bristle at the idea because they think that money is not involved in Open-source at all. What I really liked about Mikeal’s point is that


<blockquote>in the end money is actually really closely tied to Open-source, and we’re just not talking about it.</blockquote>


**Sean:** It’s interesting because my point of view is that it’s actually more nuanced, I agree with you 100%, but I think that it’s very nuanced in that a lot of people do get paid for Open-source. It’s not even that we aspire to wanting them to get paid because there’s lots of kinds of Open-source. It’s funny because on Medium Nadia and I had an exchange and I kind of quantified it into the 4 categories of Open-source the way I see them which is by no means the universal standard, but at least how I see the role there.

There are places where Open-source is part of your … A corporate product is part of the whole, like LaunchDarkly has Open-source SDKs. It’s not because they are doing anything, granted it reduces their sales friction if their customers can see the code before they integrate it into their app, that’s one kind of Open-source.

Second is what I call corporate Open-source, where there’s an Open-source project but there’s a company that sells services and products and stuff around it. Confluence does that for Kafka and Databricks does that for Spark. I think of the first companies to really make a good model out of it RedHat you can argue had mixed success but that’s another kind, where if there was a company whose corporate goal and sales is towards this project.

There’s the third kind which I call kind of like corporate marketing which is you take a project out of a company and you roll it out like LinkedIn did with Kafka.

Where actually the company’s maintaining it they just make it available, so Google with Angular and Facebook with React. Again there I think … You can argue why companies do this some of them do it for recruiting, some do it for marketing, and some of them do it because they’re very nice people. I think that the 4th category is where it’s a little bit weirder, where it’s what I call like the community where somebody started a project. Maybe it’s an individual maybe a few people to solve a problem. A lot of the most important Open-source projects today started that way, even Linux started that way, and it grew and it got bigger.

Then it became unclear because other people were using that project to build other companies and build other products and make more money. I think in that 4th category is where I think it’s less, because in the first 3 categories is usually pretty clear who’s getting paid to do what and where the money’s coming from. In the 4th category it gets very muddied very quickly because if I start something, and the metaphor I like to use is the Open-source library that I wrote was something called likelyJS which is a recommender system for node.js, where you can implement something like Amazon product recommendations.

I know that there are people in the world that are using that as part of companies and those companies are obviously making money because they’re using it to recommend products. The question is, in that world do they owe me anything for creating that which is underlying their products? Then in turn what do I owe the projects that I built likely on top of? Where does the flow of economics in that world go?

**Paul:** I have an interesting view on that, years ago I got involved in this project called PHC which was a compiler for PHP and there’s a couple of guys who had started this and I joined a year later, and when they started it they made it GPL. When I joined I argued we should change it from being GPL to BST, because if someone comes along and uses that technology to build something that’s cool, I would rather that happen that that not happen, and it might be that if it was GPL that it wouldn’t happen.

That essentially in sort of the … Related to likelyJS you decided by the license whether or not you were going to make it publicly available, or if you didn’t want people to build business on it you could have made it GPL or AGPL or something along those lines and you could have restricted it in any way that you wanted and you chose not to. There’s something implicit in that that communicates to people who are building their companies on it etcetera as to what your intent was.

**Sean:** That’s true although there’s a nuance in there which is that even the GPL suffers from this. Richard Stallman still complains about this today which is you could still use likely.js on a server to produce a service.

**Paul:** AGPL would work around that …

**Sean:** Sure and here’s other licenses that I could choose, but the majority of licenses out there today. Even then let me argue the counter-side not because I agree with it just because “Hey let’s argue because it’s more interesting, what’s up?” As an individual developer I don’t have the time or resources to go pursue … I’m not going to go sue somebody, really no come on, it’s not going to happen. I think you were right only in the act of releasing it as Open-source on GitHub.

I was making a decision that it’s possible for people to use this in ways that either I don’t intent; they could have used it on Silk Road to recommend drugs for all I know seriously. Or to make money on it in ways that I am not going to benefit from, and I made that decision knowing full well the impact of that. I would actually argue most developers do that. The question is whether or not there’s like remorse later on when it turns out, “Wait I really wish I hadn’t made that decision, I could go back in time.”

**Paul:** I think this is a common thing that people create a thing and then they say, if this is popular I could sort of keep it or I could … There’s value here that I could keep to myself or I could keep the value to myself or try to profit from it in some way, but they make what is essentially a marketing decision. I’m just going to release this, I’m going to see what happens to it, I’m going to see if it spreads and then if it spreads, I can then make a decision as to how possibly I can make money out of this, or I can get value out of this. At that point obviously the cat is out of the bag in terms of people actually using the software.

**Nadia:** I think it’s actually you should start from the principle like you said of … It’s really great when you give something away and then people can use it for whatever they want. Whether it’s for a hobby project, whether it’s for illegal drugs or whatever businesses whatever that’s kind of one of the coolest things about Open-source is that you can use it for whatever you want, and that’s what you signed up for. If you don’t want to do that then don’t license it that way.

At least the problems that I’m seeing or that I’m interested in are not really about sellers remorse I guess of I made this thing and now it’s really popular and how can I make money off of it, but I think it’s more really about investing back into the infrastructure that we’re all using and that requires some sort of maintenance and upkeep.

That’s why I like the term infrastructure and I’m trying to use it in that sense of things that don’t have a business model or a business attached to it. Like you literally could not charge for Python, it’s not going to happen, or the packaging associated with it or whatever. Still millions of people are using it to touch billions of people and you literally have one person working on a library or project. It seems like it’s in everyone’s best interest to make sure that it works properly.

**Edith:** I think Nadia made a really good point that


<blockquote>A lot of the fun of creation is the creation and the hard work is all the maintenance and the support and the documentation after.</blockquote>


So like Sean you basically got the fun.

**Sean:** Totally.

**Edith:** Then you’re just going to be like …

**Sean:** If you think even back to the original like [Cathedral and Bazaar](http://www.catb.org/esr/writings/cathedral-bazaar/) essay from years ago, that was one of the fundamental topics of … Eric was inheriting, I think was called POPMail from somebody else. He had gotten tired of maintaining it and so he wanted somebody to take it over and he found Eric and Eric took it over. We as engineers we like creating and we like creating things in our free time and we don’t like maintaining them as much, and maintenance feels more like work. I agree with Nadia’s point that if everybody is driving economic value from it somebody has to be willing to step forward to support it.

I think the problem is that I also … It’s funny that you have a background in non-profit because I also have worked with non-profits, and I see the similar lament in non-profit companies which is that … Not non-profit companies, non-profit organizations where the person who starts it usually really wants to solve this problem, they’re usually very good at that. They’re not good at the fundraising and when in this case the non-profits it’s like raising grant money or getting donations.

They have a good mission and they have a good organization to go do it, and they had this lament which is why can’t they get more support to solve the problem they see in the way that they want to solve it. I see the same around maintainers of Open-source projects, and I think the challenge is going to be that I wonder if it is even possible for the general economy to support them to do what they want to do the way they want to do it, or if they are going to have start doing it the way the …

**Paul:** They have other options, they can start a consulting company, I think you’d call it a category 2 company or something like that to build around it and support themselves that way. Then their job isn’t what they wanted their job to be which is making cool software, their job is doing maintenance contracts for a big soulless enterprise.

**Edith:** You say that like it’s I mean, Soulless Enterprises is I mean …

**Paul:** I’m a big fan of Soulless Enterprises, but I’m just looking to sort of put the …

**Sean:** They have a lot of money, but you have to sell them.

**Paul:** If any Soulless Enterprise would like to buy CircleCI they should contact me for enterprise pricing.

**Sean:** Just mention the code OSS for 10% more.

**Edith:** By the way thank you wearing your LaunchDarkly t-shirt today Paul.

**Paul:** Always. Nadia and Sean had this conversation on Twitter a week ago which led to them being on the show. One of the tweets that got involved was from a [@jacobian](https://twitter.com/jacobian?lang=en) who’s one of the senior Python kind of people. What he said is, “OSS developers deserve to be paid, SV, Silicon Valley has made massive profits by exploiting free labor, this needs to end.” I think that there is this feeling in Open-source at least by a lot of people who end up on the maintenance side of things that there is a sort of a share cropping going on here, and that something needs to happen about that.

**Edith:** I think Nadia actually put this extremely well in the essay like I wish I had written that essay, it was brilliant, but what really fed this is the explosion of GitHub and that it’s really easy now to start an Open-source project.

**Nadia:** I feel like right now is just a time when we’re so used to thinking of Open-source in a certain way and things have kind of gone along as they have for so long, that we haven’t necessarily noticed or taken a step back that like the past 5 years look completely different from the past 30 years. Stuff is just not the same anymore, and in part it’s really … I think GitHub is a really a good thing because it means that Open-source kind of won in a way. Companies want things to be Open-source, they want to learn how to Open-source their own projects. They want to understand the whole thing.

Everybody’s defaulting to Open-source and that’s a really positive thing and the question is more of not like, “Oh we’re exploiting people and that really sucks,” but how can we help support that underlying layer that has helped make everything so great. They obviously need some sort of reinvestment back into it.

**Edith:** Yeah, one of the most fascinating things about the Cathedral and the Bazaar which was written 30 years ago is that they referred to Linus Torvalds as this charming guy. This charming personable guy who persuaded people through sheer force of will to work on his project. To go back to Sean’s like example about a nonprofit, and everybody in the studio right now is, “Wow that’s not …” by anybody’s perception now and I don’t know whether that’s just the grind down of having to keep maintaining a project or …

**Sean:** First I’d like to thank … I don’t know if his name is actually @jacobian but whatever it is thank him for his service and work on Python. I think no matter what we agree on here we can only agree that the people doing this are doing a service for the general community.


<blockquote>The problem I have with calling it free labor is that I find it … I think it’s misleading, and secondly I find it a little bit condescending that the intelligence of software developers that they’re just being taken advantage.</blockquote>


They’re somehow they have no choice. There actually is legitimate free labor being abused in the world, people who have no choice they have economic limitations, they have no options. The reality in software development is that no matter where you work in the world software developers are a highly paid profession, people who can make many doing this, maybe more in Silicon Valley than elsewhere but people can make money doing it.

It is a challenging profession and these people are smart and they understand the impacts of what they do. I think the question largely is I really do think it comes down to the fact that there are people who have done work that is now being used in other ways, and what is the rationale and the economic equality that they deserve for that. There’s equivalencies previously in history, it’s not like this is the first time in history that technology’s been used in different ways, you looked at the ways the telephone changed the economy and electricity changed things, these things fundamentally alter the way we function and they can be used in ways we didn’t intend.

You think to the original … All the original programming languages all came out of academic research. Then it was always going to be, university research has always been available to the public so as always as Nadia said back then it was obvious. Now we have companies, like GO is developed by Google, so what does that mean? Does that mean that the world changed? Like Java was developed by Sun Micro systems that worked out really well, but Java’s never really been Open-source.

**Paul:** To take his point a little more, I don’t necessarily agree with @jacobian's point here, but I think the feeling that he’s trying to say is that there’s tons of these start-ups who are making millions and millions of dollars, and they’re building it on the "free" and I’m making a quotation marks which you can’t see.

**Sean:** They were great actually good flourish a nice wrist snap.

**Paul:** Companies are making millions of dollars on putting together, wrapping together Open-source libraries and Open-source technologies that are produced by people to whom they gave no money, and to whom they are sending bug reports and who are then shouldering the maintenance burden all for free relative to the companies that are using them.

**Edith:** I think a lot of Open-source was based on we call it take a penny leave a penny model where “I’ll use this project but I’m contributing back to …”

**Paul:** I think it was actually the take a penny, take a penny.

**Edith:** It was originally I’d say this very idealistic thing where it was coming out of universities. It was like you’re working on this part of the stack or work with proto-stack and we’re all getting paid by research grant so it doesn’t really matter. What’s changed now is that it used to be that using Open-source was very subversive thing, like it was stick it to The Man.

**Paul:** Now The Man is exploiting Open-source.

**Edith:** Yeah, Open-source has won the battle where you no longer have … I remember when I started out you had to fight to use Open-source.

**Sean:** I have a funny story about that which I forgot to tell at the beginning.

**Edith:** Now it’s a reverse now all of a sudden it’s like the big companies in Paul’s words the soulless corporations, who are filing the snotty bug reports. It’s like it’s bad enough to get a snotty bug report from a customer that’s paying you, but when it's from somebody who doesn’t even give you anything? There are some legendary GitHub threads where basically somebody is like, “You don’t understand who’s the customer here.”

**Nadia:** Yeah exactly.

**Sean:** I’m not going to tell my finish story now because I would lose the moment, but I would say that again it comes back to me a feeling that there is this problem that exists where the mindset is I want to get paid for doing things the way that I want to do them. I think that that’s the challenge that I run into with this, which is they could ignore those bug reports. You could say listen I don’t care what you think. Literally a lot of these projects most Open-source I don’t have statistics, most Open-source projects have a single maintainer. It almost always is a single contributor if you’re very lucky you get a full from … There’s almost always one person’s that’s doing it. That person has the ability to do whatever they want even the most popular ones even though they probably wouldn’t do this they could in theory do whatever they wanted.

**Edith:** That’s the whole idea of the benevolent dictator.

**Sean:** The benevolent dictator for life, exactly, so my point is they want to get paid for operating this in the way that they want to operate this, and doing this in a way. Maybe that’s not the right model, maybe there’s a point where these things turn over. What happens today often I see, not for Python that’s obviously not going to go away, but for libraries and somebody will build one, and they’ll maintain it for a while and they get sick of it and a few will pop up.

Likely, when I wrote it was a very first and only recommendation engine for Node, now there are a dozen. I haven’t maintained it in a few years because frankly there’s better options available. That becomes a circle of life where the community is maybe not contributing to the original project, but creating new ones that pop up around it to replace and augment it and it becomes this kind of free flowing free form entity and community.

**Paul:** I find it very similar to the things that journalists are lamenting about, journalists are talking about the …

**Edith:** We used to get paid.

**Paul:** We used to get paid, we used to get paid a lot we were the arbiters of what content was and then all these people came along, and they started making content for free and that content isn’t the right content, or whatever complaint it is. A new technology the internet allowed anyone to write and lots of people wrote for free, and it devalued what they were doing and then the people who wrote from free found business models, whether it was like being able to get a job from writing or YouTube royalties or whatever the thing is.

There’s this really strong parallel that the people who are maintaining the big project are like, “We want to get paid for this how come no one’s paying us?’ The people who are maintain the small projects and who are building it for free, and are getting jobs out of it or are getting consulting out of it or whatever are like, “Fuck it I’m making billions of these, I do it because I like to write and I don’t care about your problems of maintaining Python.”

**Edith:** It was why I Tweeted this and I’d like to expand on which was I think a lot of these free projects crowd out paid products, like I mean that in a very economic sense. If there’s 4 free libraries sitting around for recommendations, it’s really hard to get paid for one. I think that makes perfect sense for projects on the level of the one that you’re talking about Sean, and especially for Javascript libraries and there’s a lot of overlap.

**Sean:** No shade being thrown at JavaScript...

**Nadia:** Anti-shade, but I’m just saying that like there are plenty of and I think that’s sort of where all the fun and the creativity is happening is like, “I made this project and I'm going to put it out there,” and someone else might made another one and that’s cool and you can choose whatever you want. That really mirrors sort of like the information revolution in a lot of ways with content and journalism and other things where like music even where you can just like give it away, and now paid products can’t compete.

I think that’s actually okay in a pretty natural and expected development and we shouldn’t fight what’s happening. Then there’s still plenty of examples of projects like Python and its packaging or Ruby and its packaging or whatever that aren’t being supported at all, it seems like you can’t use a small project to explain why we shouldn’t support a big project because these big projects …

**Paul:** I think OpenSSL has a really good example. OpenSSL had one maintainer and it had some security issues with it that were basically … and everyone in the world was relying on it and then everyone got screwed.

**Nadia:** Yeah totally.

**Sean:** I don’t agree, if you think about how many languages exist today how many options you have to choose between … It is true that Python … You’re not going to have like 3 versions of python that people are maintaining, but there are so many languages if the python maintainers are like, “Listen we don’t want to do this anymore,” and they walked away from it. It’s not like the world would end, the existing Python may not get better.

**Paul:** We’ll disagree on this. If you look at all the companies and all the projects and everything that are being built on Python, the world would end. If Python went away someone would come in and have to support it.

**Sean:** Exactly, but that’s my point.

**Nadia:** Why don’t we just do it? Why do we wait for a disaster to happen? Even with OpenSSL for example, they were asking for years for donations openly soliciting trying to get people to pay towards, and it was only when there was this huge bug that suddenly everyone was like “Oh my Gosh.”

**Paul:** I have a strong opinion about this? Basically they’re asking the wrong questions, if you’re going around saying we want donations or whatever …

**Nadia:** Like they think we’re trying to kick start.

**Paul:** Right companies actually really can’t give donations, donations are really fucking hard to give. What they should be looking at is companies and their risk profiles. You have a company that is built on top of Python and they have no support contract and the whole thing could fall under them at any minute, they’re definitely going to want to donate or give or buy or something that reduces their liability in some way, reduces their risk factor. The idea of going around and saying, “We need money please give us money,” I think is ludicrous.

The idea that I’ve drawn up for this is basically someone should go out with literally a sales team, go to every Silicon Valley start-up, every venture capitalist start-up, every venture capitalist, everyone who makes revenue in the software business and say, “Give us .1% of your revenue or 1% of your revenue somewhere in that range and we’ll make sure that it goes to the libraries that you rely on to de-risk those things going away, the bugs not being done, or that sort of thing,” and the idea that people would just like throw their hands in the air and say, “Why wouldn’t anyone donate to us?” it should be a very proactive approach of going out to each of these companies saying give us money, here’s an LOI, here’s my check, bring out the checkbook we’ll make sure the money gets there.”

**Nadia:** Actually with OpenSSL, there’s actually a very interesting set up I talked to [Steve Marquess](http://openssl.com/docs/marquess_cv.pdf) who is at OpenSSL just to understand that structure, and it was actually … They realized exactly what you realized which was … Even though people keep saying OpenSSL never got more than like 2,000 donations a year. That wasn’t actually how they were paying their bills, they were doing consulting contracts. They brought in no more than I think a million a year but it was more than $2,000. There’s Steve Henson who is contributing to … Or he was the one paid maintainer for a while at OpenSSL and now they have a bunch of other people.

Then Steve Marquess came in for this reason to say, “Hey I’ll write a little bit of code here and there but really what I think you need is a little bit of a business mindset,” and so he managed and continues to manage all of the contracts, all the business services. None of the developers want to talk to clients but he will be like kind of that interface ... Even like email he says “Don’t ever email Steve Henson just email me I’ll forward it to him if he needs it.” I think that actually speaks to what is … What Open-source needs more of is …

**Edith:** A business.

**Nadia:** A business mindset.

**Paul:** I’m proposing something that’s ever so slightly different to that that rather than a single company like … Rather than each company in like OpenSSL having a business person who goes around and who tries and raise money, or who sells the developers time for things. You have a single company …

**Edith:** You have the united way of Open-source?

**Paul:** You have the united way of Open-source.

**Nadia:** Then Paul then you still have the issue like how does this united way decide where the money goes?

**Paul:** You can look at people’s Gemfiles to determine where the money goes.

**Nadia:** I'm totally onboard with this, this is kind of what I’m slowly trying to move towards.

**Sean:** I think companies are more likely when they get scared like that to hire a shadow maintainer than they are to donate to the Open-source project. You see this all the time companies that rely on big projects like HBase and Cassandra they actively go out there and try to have … They basically have shadow maintainers on their team whose job it is to be the expert on the source code, they update it...

**Paul:** Companies typically use more than just HBase, they’re using hundreds and possibly thousands of …

**Sean:** We’re talking about a class of projects which are the huge projects, like the programming languages, the big projects because the small ones we’ve already talked about those, we can go back and talk about them again, but those are a different story.

**Paul:** Do we think that the small projects don’t deserve funding?

**Sean:** I think that it’s much harder to make a case for them because they live and die so quickly, I think it’s really hard.

**Nadia:** I would liken them to art which is how a lot of people think about code and when it’s sort of on that level I think of it as art and creative expression. When I think about like the big projects I think about them like highways or roads or infrastructure.

**Edith:** Or cathedrals.

**Nadia:** Or cathedrals.

**Paul:** This is interesting no one thinks the small things deserve some sort of support?

**Sean:** I think if you were willing to maintain one long term maybe, the problem is they’re just less complicated. Then you run into the barrier like if it was really easy to recreate Python maybe we would. JavaScript libraries are one thing, I like to think about stuff, ideas that are more complicated than that, but still that’s my personal opinion. There’s definitely a gradient of the complexity or something.

For example in most places there is N number of implementations of a bit vector, I guess it’s really not hard to write a bit vector like if you really didn’t like the ones out there you could write it yourself. A programming language is on the other side of the spectrum which is really complicated it. If you’ve ever done one it’s like crazy hard to do.

On the spectrum there, if the smaller ones probably deserve but the replacement cost is so low that you can just churn them through and on the higher end where replacement cost is higher. This is where I think that if a company really was scared about their reliance on it, they’re less likely to support the Open-source project where they have no control over what the money goes towards. Like if I give to OpenSSL I personally believe they would do something positive with it, but a corporation cannot make that bet, so I want somebody on my team who knows OpenSSL code that can improve it or change it in ways that I need= and I see that as my investment in my production.

**Paul:** I’m going to suggest that we’re thinking about this a little bit wrongly because the way that we’re talking about big projects, big projects are infrastructure small projects are art or whatever.

**Sean:** I disagree with that too.

**Paul:** It applies kind of a morality to the value of particular Open-source projects and the value of what they do. Really the value applies to individual companies, a company derives a certain value from a certain library and it doesn’t matter whether it’s a big library or a small library or a big project. That company should be putting money into it’s risks and if it’s risks include a very small library that has one maintainer but that is a key part of their drug recommendation engine, it’s going to be up to that company to make sure that the money goes to the right places.

The way of determining who gets money that I’ve been thinking of is literally looking at Gemfiles or looking at POM files or whatever it is in your particular language. You can follow that dependency tree to see who actually is involved, what projects are involved in making your library, how much they are being used and determined that way. Who should get support, even whether there is someone down that path who is willing to support what you have.

**Nadia:** I actually totally agree I think … When I think of big versus small projects, maybe that’s not the right term but just the idea of something that has critical dependencies or someone or something that really, really needs this to work for their own purposes then somebody should be supporting it. Also just as a simple heuristic like if maintainers asking for more support, they might need more support. Support doesn’t always look like money, but maybe it’s like I don’t have the time to work on this, I’m really stressed out, whatever it requires some sort of closer attention. If a maintainer’s really happy, Sean you’re happy with your projects and you’re not asking for any support then you don’t need to support it.

**Paul:** The thing that this inevitably gets to is what happens when money gets introduced to Open-source, I wouldn’t at all argue that Open-source doesn’t deserve money and needs to keep doing it as art but definitely …

**Sean:** Let’s all agree the 4 of us deserve a lot of money.

**Paul:** I think there’s definitely an argument to be made and I think that you’ve both made this, that people will get involved in Open-source for intrinsic value. It’s not for the money largely, and so when you start to introduce money to it and you start to prioritize and maybe people want project management and that sort of thing, and road maps and deadlines and that sort of things, is money going to damage what we believe as Open-source and how can we avoid that?

**Sean:** Or is the answer that really you have to help projects transition between … I laid out my 4 categories whether or not you agree with them but maybe if a project becomes really critical and has an individual maintainer, there has to be an infrastructural support then transitioning to a different model. We don’t sit around worrying about what’s going to happen to Spark because Databricks is there, we don’t worry about what’s going to happen to Kafka because Confluence is there.

**Paul:** They have the product managers and that sort of thing who talk to the customers who determine the order of things and the priorities and the road maps and …

**Sean:** Maybe the answer is that you have to help these projects transition. I worry that even if you’d follow back the gem paths or the packages, it’s still not clear to me if you know exactly who to support and how. Yes they want support and that makes total sense, but again I worry about going back to the thing I mentioned a few times, do they want support to do their project the way they want to do it? Or do they want to do support to do the projects in the way that the companies want to use it and the way that they want to go? It’s not like they get money to just keep doing it, the money comes with expectations that you’ll do what I want.

**Paul:** The money is for de-risking largely, and so there has to be some sort of maintenance guarantee or turnaround time or understanding that bugs are going to get fixed in order for that to happen.

**Nadia:** One point I quickly want to make in regard to what happens when we introduce money into Open-source. What I had said in the beginning of this is everybody gets paid for Open-source already and I think that’s a nice framework to have because …

**Edith:** You can’t take that to the grocery store on Fridays.

**Nadia:** What I’m trying to say is for example like Heroku’s employing the core Ruby maintainers right now. They have a full time job and they’re allowed to work on Ruby and that works right now because Heroku’s supporting them. Who knows if Heroku will support them later, Ruby is older than Heroku. In the end there’s some sort of arrangement working there, we’re not thinking about what’s going on with Ruby, is it okay for that language because Heroku’s paying somebody to work on it. Money is already there and already being used we just aren’t quite thinking of it as directly I guess.

**Edith:** It goes back to a lot of these Open-sources coming out of the government, who was really paying for this? Tax dollars.

**Nadia:** The internet started because the government was funding it.

**Edith:** Yeah so all those people who were getting a PhD were in effect funding this infrastructure.

**Nadia:** Money is already there.

**Edith:** You could say it was on the back of somebody getting paid 20k a year as a grad student. I’m serious that’s what a UC Berkley student gets paid which is pathetically low.

**Paul:** Money that’s in Open-source now is not being directed towards a particular goal or a particular agenda. It’s being worked on, on the side or something along those lines. Although I agree everyone is getting paid, but they’re not getting paid to do a thing largely. When companies start to support that then people change from doing a thing because they like it or because they’re using it for work, and they feel other people could use it to actually needing to support this for some other companies agenda, and that’s a different goal it’s a different feeling, it’s different from what I want to do on Open-source.

**Edith:** Nadia you’ve talked to the most I know you’ve done so many interviews, is there any common thread about people wanting to get paid or not wanting to get paid what are you hearing the most?

**Nadia:** I think it’s part of actually what Sean was saying around do they want to get paid to do the same thing they’ve always been doing. Like life obviously just doesn’t work that way as nice as it would be. I think community and funding are actually really closely tied and they’ve tried to be careful to call it sustaining Open-source infrastructure more than just funding, even though it kind of gets simplified to funding sometimes. It’s not really about money it’s sort of just about money enabling people to do what they already want to do. When I think about introducing more money let’s say to Open-source, it’s really around like how do you help enable a healthy thriving community to exist? How do you help maintainers manage their time better?

It’s like a very delicate question and it has to be implemented by somebody who I guess understands … We’re not trying to change Open-source, it shouldn’t be a centralized thing. You can’t have say like an institution that is producing all the Open-source infrastructure and it comes from this one place, that would be awful. You have to work with each of these ecosystems that’s completely different, each of them takes pride in being very different from the other ones and so figuring out how to coordinate all that is actually probably the hardest part.

**Sean:** Let’s agree if there was an institute for Open-source you’d have to fill out forms in triplicate at the front desk in order to get in to either review the source in the … Is the tension here because originally I feel like a lot of this arose out of … It was very organic. A lot of products being created and it was almost Darwinian in that something survived and it died and suddenly replace it. Now we’re kind of not willing to let it be that simple anymore like we’re not willing to let the Python maintainers walk away, because the Python’s too important we’re not willing to let it be Darwinistic any more, we have to find some way …

**Paul:** I don’t think that’s it, I think we are willing to let anyone walk away who wants to walk away. I think that people are looking at money that is arriving in other parts of the ecosystem and saying, “It isn’t fair that that is going there.” It is where is mine but I feel where is mine is a very kind of pejorative angle on it.

**Edith:** I don’t mean it in all that way just meant it more like I worked so hard on these with this idealistic view that I was giving back to the community, like what Sean said, and then I see all these people who are taking the code not contributing back and by the way being real jerks when they have a support request.

**Sean:** Who decides what’s fair then? I agree with you, I remember when RedHat went public and all of a sudden the founders of Red Hat were filthy rich. I remember being like, “What the hell happened to Linus?” Then I read an article where they did give him a bunch of shares of RedHat. I still was like wait a second, he got a fancy car and they got … That’s not fair.

**Edith:** It’s like the whole kick starter thing with Oculus VR.

**Nadia:** A lot of people had kick started Oculus VR and they felt like they were part owners and then they sold to Facebook for what was it like 600?

**Sean:** 3 billion I think.

**Nadia:** Because it wasn’t equity based yeah.

**Edith:** I feel like we’ve been kind of stuttering our way towards Open-source perhaps needing money that there’s an issue of what projects survive versus wither, and capitalism actually has a pretty defined model for this. Like if a company can’t find sufficient customers to pay them for their goods, they go out of business. I think what I want to hear what Sean and Nadia and Paul are saying about who decides how much funding to give to somebody, we talk about a centralized institute of Open-source and like wait a second, I’m curious to hear other people’s thoughts around this.

**Paul:** I think there’s a bit of a patronage, I don’t know how you pronounce that in America, model around it at the moment that you could imagine that Python or something like the Sistine Chapel. There’s a Medici somewhere who’s funding it’s development for basically altruistic or perhaps personal status reasons or something along those lines. In fact those people who’ve been doing things with GitTip and Patreon and that sort of thing who are looking at that as a kind of a patronage model, which I think is a terrible way of funding these things relative to the more capitalist alternative personally.

**Edith:** It’s interesting because they’re doing it after … There’s 2 models, there’s the after the fact which we already talked about, after the fact where you kind of go around saying, “Hey we built this,” the second is I’m fascinated that now people are trying to kick start software.

**Nadia:** Yeah it’s actually a bunch of … Django, RVM there’ve been a bunch of crowd funding campaigns around funding development, but it’s hard because developers already don’t want to spend time marketing themselves. Everyone agrees even outside of coding, Kickstarter campaigns are a lot of work. You can only really do it like once or maybe twice until people are kind of tired of you. I don’t think I’ve seen one that’s gone much more than 50k or so.

**Paul:** I received a cold email a while back from Ruby maintainers and I’m not sure who exactly was involved in it, but they were looking to get funding to sponsor the kind of Ruby ecosystem RVM, and the servers that go behind our RubyGems and that sort of thing.

**Nadia:** They did it.

**Paul:** They made it?

**Nadia:** Yeah, it’s called a Ruby Together if we’re referring to the same thing. I think it’s actually a really great model as we talk about sort of how do you direct more money without it turning into this weird capitalist business. I think it’s actually really important to decouple infrastructure from business models for that reason because you're not selling things and you want it sort of like ... It’s more of saying like, “We need this to be good so that all the other business stuff on top of it is good.

Yeah, Andre created this thing called [Ruby Together](https://rubytogether.org/); I think it’s structured as a 501c6, so a trade organization. He got a bunch of recurring donations from companies and from individual developers to sponsor work on what he calls Ruby Infrastructure. I think they mostly do bundler, RubyGems and RubyGems.org. Part of it was because of this like some of these things that we’ve talked about were ... Like for example there are a couple of companies that were funding or basically employing maintainers of different core Ruby projects. Once they lost that support because it just didn’t contribute to the company’s bottom line or whatever, no one was maintaining these projects for a really long time.

I think RubyGems went a year without anybody committing to it, which is crazy. They had issues like where somebody hacked into RubyGems, I think it was a couple of years ago.

**Paul:** I remember that.

**Nadia:** Yeah and so nobody could take care of it because it’s a volunteer system and nobody is responsible and everybody has full-time jobs. Some people ...

**Paul:** I remember in that particular case, someone was away or there was like 12 or 24 hours before anyone actually looked at it.

**Nadia:** Yeah, people had to take vacation days from their jobs to work on it which is incredibly nice of them to do for everybody else. It’s stuff like that that I think they want to help prevent.

**Paul:** How much did they raise? Who did they raise from?

**Nadia:** They're very transparent on their website about all this. I think I haven’t checked recently, I want to say they have maybe like $16,000 a month recurring and they were trying to grow that. I think they just ...

**Paul:** That is ludicrously small.

**Edith:** Yeah.

**Nadia:** It’s really, really small which is kind of crazy, right?

**Paul:** The important thing here is that it’s recurring.

**Nadia:** It’s recurring, that very important.

**Edith:** Still that's barely one full-time person at San Francisco rates.

**Nadia:** It’s a shame, and more people should be donating to it.

**Paul:** How is it so low like?

**Edith:** I think the whole donation thing is fundamentally broken.

**Sean:** Altruism unfortunately if you've been working in non-profits. Altruism is this great thing that is a very short well, like people ...

**Paul:** This isn’t altruism by any means, this is companies who like possibly went down when RubyGems went down and saying like, “Fuck it, we can’t do that anymore. We lost X amount of money and I'm willing to donate $5,000 or whatever.” Because I think if it was clear if I donated my $5,000 that wouldn’t happen again, it would be different. I don't know, I have trouble believing corporations see the math being that simple.

**Nadia:** They should, because yeah if someone were dedicated full-time to RubyGems for example, if something went down, they would get it back up. That didn't happen because nobody was working full-time on it.

**Sean:** If you're a corporation, do you try to support the RubyGems project or do you find ways to isolate your service and your product away?

**Paul:** You do both. Fundamentally if you're based on RubyGems or on the Ruby ecosystem and you're making a million dollars a year, is it something that you're not going to donate $5,000 a year to? Of course you can donate $5,000 a year to, because just fundamentally someone wants to de-risk your site going down or your deployment process going down.

If you're unable to deploy for 2 days because RubyGems is down, you're in a really shit position. There’s CEOs who are coming into the VP of engineering or developers or whatever size you are and yelling, “Why the fuck is the site down? Why haven’t we been able to get this promotion out? Why haven’t we been able to get this bug fixed? Whatever that is.” $5,000 is a trivial amount to make that happen.

Or I'm making this on a $1 million a year revenue thing. If you're Salesforce and you're making a billion a year or 10 billion a year or whatever Salesforce makes. Donating a million a year, 2 million a year, 10 million a year? It's small fry.

**Edith:** To follow the money, Salesforce is actually Heroku.

**Sean:** No, no but that's exactly the point, I feel like a lot of these larger companies feel like they do that. You think about Google’s and Facebook’s, they do invest a lot in Open-source and in employing these people.

**Paul:** They're doing it for different reasons than that.

**Sean:** Cloudera, at one point I feel employed, this is me exaggerating, the maintainers of most of the Apache project at one point. These companies feel like they are I think it’s going to be hard set for them to be like, “I'm going to support your project versus I'm going to write my own language Go, and I'm going to start writing everything in Go.”

**Paul:** I don't believe that it's supporting your project, I think the tie that you need to make is de-risk. I am being helped de-risk my business by putting money into making sure that these things don't happen.

**Sean:** If you were paying for a service contract, I would believe the corporations would see it that way but they're not ... That's not what these ...

**Paul:** There isn’t a service contract available.

**Sean:** I know, but that's my point. I think that that's why I don't see the line being that straight. I don't think, seriously.

**Edith:** I'm pro-donation, I'm just saying it doesn’t map as you said before doesn't map into value delivered for the corporation.

**Paul:** There can be a more direct map than is being drawn now I agree it’s not a service level agreement.

**Paul:** A question for all of you, there's a new license that just came out recently called the fair source license, have you seen this? It’s interesting because basically I try ... It’s not an Open-source license but it’s not a closed source license. Essentially it says that, “Here, you can look at my source code, you can use it but there's a limited amount of users you can have before you start paying me.” It’s not like you just take it and do whatever you want with it. Most Open-source licenses are like, “Go do with it what you will" but Open-source is like you essentially can try it out until a certain point which is where you start paying me.

**Edith:** This is more like a Shareware.

**Sean:** It’s like Shareware, it’s a little bit unclear about how you enforce the limits. There's lots of questions but I'm curious - is the solution in the licensing? Is the problem that the licenses now are too open. If Ruby came with a license that listen by the time you're making $10 million a year on a ruby program you have to give us $5,000, would that solve the problem?

**Paul:** There's a question of what is a Ruby program? So for example if you're a ... Let’s say you're a big bank and you make more than $10 million a year. Everything's in java and there's a team that goes out and says, “Well, we’re going to be doing some Ruby stuff now.” Maybe you think that in the future everything will be Ruby but right now it’s one small thing. Is the bank going to say, “Oh this is great, let’s give our money to Ruby?” Or is the bank going to say, “Ruby is banned and you're not allowed to make anything Ruby”

**Sean:** Maybe, I don’t know.

**Nadia:** I really like the fair source license, I like the people behind it, the lawyer who drafted it, Heather Meeker, she's worked on Mozilla and a bunch of other things. She has a good mind for all that stuff. I think it will be great for maybe some of those projects we’re talking about where let’s call them smaller projects with air-quotes, because of yeah you have something that you're working on and you want to charge fairly for it. I think it will be a lot harder for stuff like Python for example to use.

**Sean:** Why? Why would the same rules not apply? Why?

**Edith:** Sean gives us the 5 why's of the Kanban.

**Sean:** That was all 5 why's, right there.

**Nadia:** I think there are a lot of answers to that. My answer to it is just looking at the history of Open-source in the first place. We worked for 20, 30 years to get all this stuff open for a reason and it had these ... I think when it started maybe it was more just like political or counter culture thing of like we shouldn’t charge for something that should be free or whatever. Code should be free, everyone should be able to use it, no one owns this, whatever. Then you saw this incredible explosion of start ups in large part due to Open-source which is something no one could have predicted.

It’s like when you create a platform and you give people access to that platform, they start making things that you could never have even dreamed of. It’s so great and like we should default to having those tools for anybody to pick up and do something incredible with. I want to protect that.

**Paul:** With those things it’s obvious in retrospect, not ahead of time.

**Nadia:** Exactly.

**Edith:** I think GitHub's relationship with Open-source is fascinating. You put it in your article that they fueled the explosion, but they're closed source. I’d say now ...

**Sean:** They spend all day rolling around in money.

**Edith:** Now there's a big petition from a bunch of Open-source people like why aren't you giving us all these tools? The capitalist part of GitHub is like "well, we don't make any money off of these open source projects."

**Nadia:** Yeah, it’s really hard because they ended up ... They make money off of enterprise.

**Paul:** They make money off those Open-source projects.

**Edith:** How?

**Paul:** It’s a freemium model. They got huge because they ... Because of all the Open-source. GitHub is the default, no one wants to use Gitlab or whatever because of the network effects of Open-source. To suggest that there's no value there and that I'm sure that someone with a better analytical sense than me could actually put a dollar value on it.

**Sean:** It’s like SourceForge before them, I mean SourceForge made money before GitHub even existed, there was Open-source.

**Sean:** All of GitHub’s value is derived from the fact that Open-source is always there.

**Edith:** Here's the question then for you. You're the product manager for GitHub, you get a long list of requests for features from Open-source which doesn't pay you anything. On the other hand you have a list of requests from enterprise customers and you're trying to put together your road map.

**Paul:** I agree that there's certainly a temptation to say, “Fuck it, these guys are paying us money,” I think this is one of the very difficult lines to straddle. When you have that group of customers you have to be very careful to keep them happy and to keep them there. You can’t please everybody and you can’t do everything and you can’t acquiesce to demands and that sort of thing. If Open-source was to leave GitHub, there's an existential crisis for GitHub.

**Nadia:** Yes, I think it’s just a balance that they're to find right now because ... This has been written about publicly too in articles and stuff just about like internally right now in GitHub there's this tension between do we double down on enterprise? But if we do too much of that we’ll forget our ... Yeah, there's just a little bit of turmoil, executives changing positions and stuff. I think they're just going to have to try to figure it out because they realize that, yeah we might not directly make money and this is kind of true of like Open-source businesses too are like we might not directly make money off of that community but without that community the rest of it is meaningless.”

**Sean:** That was the one benefit of GitHub and I think the genius of GitHub actually is that they've actually turned like corporate software to look more like the Open-source projects. You go back before GitHub like most closed source projects are managed much differently than Open-source. Today everyone is on GitHub we’re all doing pull requests, we’re basically using Open-source stuff and methodologies for closed source. Actually it’s in the favor of Open-source because it makes it seem less different, it doesn’t seem strange, another different way of thinking.

**Paul:** It’s actually interesting that there's a lot of the closed source methodology that people want GitHub to allow that GitHub refuses to allow. For tighter integration with Jira or replacing the issues or replacing pull requests with something that involves more code review or that sort of thing. GitHub is saying, “No, this is the way to do it,” and so people as you say, they end up much closer to Open-source than they would end up otherwise.

**Edith:** I would say that pull requests have helped fuel continuous delivery.

**Sean:** I would also argue Open-source has fueled continuous delivery.

**Edith:** All right, let's hear this.

**Sean:** Yes, I've got nothing to back that up, I would say that … I didn’t say I will argue that, I said I would say this.

**Paul:** I think it’s interesting because people use continuous delivery when you want to deliver continuously and Open-source fundamentally doesn't do that. For the most part people have released with almost byzantine release models of like, “We’ll release something with a version number in like every quarter or whatever that thing is.” If you're using small projects the small projects will tend to like, you make a pull request there's a new feature goes in or whatever and then you're like, “Oh, I’d like to release a new one.” So you make a pull request with a new number or that sort of thing.

That is almost close to continuous delivery except that it’s not actually continuous, there's no actual infrastructure, there's no automation. Yeah, I think Open-source isn’t contributed to frequently enough to have continuous delivery and are generally not continuously delivered.

**Sean:** Although it’s really hard... this is a topic from the other side, it’s hard to have continuously delivered downloadable software because inside downloaded …

**Paul:** No, not at all, you just every single version the software gets tagged with a branch name or a SHA or whatever.

**Sean:** There’s nightly builds and stable bills in most of these projects.

**Paul:** Yeah, nightly and stable is continuous delivery. I would argue that they don't exist for most of these projects, I would argue they occasionally exist on the larger projects.

**Sean:** When they start making money maybe they will!

**Edith:** Wait, I thought you had an anecdote you wanted to share?

**Sean:** It’s a completely off topic but a long time ago when I used to work at Verizon, this would have been 15, I don't know - long time ago.

**Nadia:** Didn't they have a hotline commercial?

**Sean:** Yes, so anyway back when I was working for Verizon, this is a phone company. I was a big proponent of Open-source at Verizon and this is back when Linux was like, “Oh scary stuff what is that?” The big tagline was Linux is not ready for prime time, this was the big thing. We can't use it in production because Linux is not ready for prime time. Here's Sean saying, “Linux is ready for prime time.” I managed to succeed in creating this little bubble inside Verizon, let’s use Open-source, let’s get it through. I actually was invited to speak at a Linux conference here, the first time I've ever been to San Francisco. I lived in the north east, I had never been to California, I flew all the way to San Francisco to speak at a Linux conference and they weren’t even that big, this was maybe 4 rooms in one of the hotels around here.

I got here and my talk was starting in an hour and I get a phone call from my boss saying that the lawyers at Verizon were afraid that they were going to get sued because this is back when people were suing if you use Linux because it was infringing on the patents of the other companies. I got prohibited from going on stage, I flew all the way here, and an hour before my talk they're like "you can't go on stage because if you go on stage people will sue us because they'll hear you talk about the fact that we use Linux."

**Paul:** That is a phone call that you don’t answer. An hour before any talk you do not answer the phone from your boss.

**Nadia:** This is where like when Paul and I go to speeches, I try to get a hold of him and he's like.

**Sean:** I thought they were calling to wish me luck, I didn’t think they were going to be like, “Nope sorry nope you can’t go on.” Let’s all admit we've come further than that which is great.

**Nadia:** Absolutely yeah.

**Sean:** Funny, a similar thing happened to me. One of my first internships was I was working at Sony in London, Sony Computer Entertainment Europe and my job was to port the EyeToy driver to PS2 Linux, which was the Open-source hobbyist version of Linux. I made the transition, I ported it or whatever and we went to release it. We did release it and then the Monday after I got an email from my boss saying, “Sorry we had to pull it. The lawyers didn’t particularly like this.” It was an actual IP issue, it wasn't like we’re afraid of Open-source issues. Someone else owned the library that had been ported.

There were some magic numbers in there and so we were going to do something where there were two kernel modules and, it never got done. Yeah, lawyers.

**Paul:** Yeah, there we go. If we agree we're going to get rid of all the lawyers and we're going to pay all the Open-source people. We've gotten a lot done in this podcast!

**Edith:** So you have moved to San Francisco.

**Paul:** We’re going to use the money that we used to pay the lawyers to pay the Open-source people.

**Sean:** What will we do with all that? There’s too much money we wouldn’t even know.

**Edith:** We haven’t really touched on something that I actually was very curious about. You said in your article that you though VCs were not willing to fund Open-source?

**Edith:** I call it not venture back-able, specifically the infrastructure stuff I'm talking about and I guess languages are part of this problem. VCs back plenty of Open-source businesses and plenty of infrastructure, especially stuff around DevOps and data infrastructure, obviously you guys are both ventured backed and so you guys can’t see where my hands are going. Yeah, absolutely there's a place for venture in Open-source.

**Paul:** They backed NPM.

**Edith:** That's right, yeah they did. I think it was ...

**Paul:** Is that not infrastructure?

**Nadia:** It is absolutely infrastructure.

**Paul:** Okay.

**Nadia:** I think that it’s in our best interest especially looking at history, the history of Open-source to keep it a public good for better or worse terminology in the sense that like we’re all benefiting and we’re all using it and so it should be something that is a tool that anybody can pick up and use.

**Paul:** This sounds like communism.

**Nadia:** Yeah. I got distracted by the door and public good, I should have never said it, I take it back.

**Sean:** It was like a range, I agree venture back-able is the right way to think about it because the reality is most of these valuable ... I wouldn’t call them infrastructure, I want to call them really valuable Open-source projects, are not going to grow fast enough to have venture backed returns. Venture backed returns are very specific kind of business returns.

**Nadia:** Some of them don't even have business models. Period.

**Sean:** Even if they did, they just wouldn’t go fast... like Python has been slow burning forever, this is not a fast growth business, Ruby si the the same thing. These are the things that are just so fundamental now that we use that just aren’t fast growth that are going to produce venture backed returns even they had a business model associated with them. Ruby toiled in security for years until rails came out. Let’s be honest, these things are non-linear.

**Paul:** This is funny you talked in your Tweets about people investing in programming languages or "has anyone ever made money from programming languages?" My PhD was in compliers and I remember being at a conference where I talked to one of the guys who made this ... I wouldn’t say important compiler, but it was a company that people had heard of, people in the compiler community had heard of. It said that 85% of compiler companies have one customer and the one customer was like basically providing the services or they had a service contract with them. They were building it for that one customer who used it in one particular case.

**Edith:** That's not venture-backable.

**Paul:** Not only is it not venture back able but like with compilers and again programming languages is the same thing. You’re competing with free or you're competing with some other company who's providing it for some internal benefit that they have. The Google’s of the world are contributing to GCC Apple us contributing to LLVM . If you contribute with another C compiler no one is really going to ... No one is going to make money off it … so CircleCI is where I ended up as like the closest possible thing that could make money to being a complier.

**Nadia:** That’s awesome.

**Sean:** That's great, I never heard the origin story before, that's awesome.

**Edith:** I'd like to say in full disclosure. Sean is actually an advisor and an investor in LaunchDarkly, so he obviously believes that we have …

**Sean:** That's why she always says nice things about me.

**Edith:** He obviously believes that we'll have exponential growth that will pay for his kids' college education.

**Sean:** That’d be nice because it could be expensive by then.

**Paul:** Education will be done by then, there won’t be any universities.

**Sean:** That's true.

**Paul:** They will all have risen up to...

**Nadia:** That sounds like communism.

**Edith:** Paul is from Europe.

**Paul:** Education is free.

**Edith:** I will say, I think there's a good distinction between a lifestyle and VC backed business. VCs want to get exponential returns because they're betting that the 10 companies they invest in 9 will probably fail and one will have to make up for all that return. They're actually not looking for steady 5 or 10% return.

**Sean:** There's this interesting pathological case of Open-source, I don't think it happens very frequently but let’s take the example of NPM for a second. Node comes out as a language and it’s really interesting and has a lot of interesting things.

**Paul:** It’s growing much faster than most of the languages.

**Sean:** Growing really fast and then you have NPM which is a package manager for Node. Which actually in some ways is more interesting and has more economic value than the language itself. So NPM can raise venture money, they can build a business around it and like this is an interesting ... I don't think this happens very frequently, this is an obvious case of economic disequilibrium where NPM wouldnn't have existed without Node. Now actually NPM today actually does exist a little bit without Node, you can use it to manage packages that aren't Node packages.

This company if it’s sold for a billion dollars, what does it owe back to the Node community?

**Edith:** This just goes back to your RedHat comment.

**Sean:** Is it going to be like I'm going to give you a bunch of shares that maybe you could buy a house or maybe a nice car, while I go off and buy an island? How do you ...

**Paul:** It’s particularly funny since Node was built by Joyent or with Joyent as their corporate sponsor, at least before it was cast out or whatever happened there. Who enjoys the economic goodness that came out from it, is it the people who started it or is it Node or is it Joyent?

**Edith:** This actually has its roots in the 1600s where

**Nadia:** Going way back!

**Edith:** It was scientific...

**Sean:** First code back then was made on the frontier.

**Edith:** They had to use calf skin... No, the whole thing about the scientific community went through the same spasms of who really gets credit for a new discovery? What you said about NPM and Node it’s like, one wasn't possible but the other amplified its effect. The same with discovery of calculus, the famous quote was, “I could do this because I stood on the shoulder of giants.” We have the ability to build all these infrastructure companies now because we do have the foundation of languages, because we do have the foundation of competitors.

**Paul:** It’s giants on top of giants, on top of giants at this point.

**Edith:** It’s all turtles dude.

**Sean:** Giants is about giants sometimes it's a little bitty turtle.

**Nadia:** It’s actually great ... If we’re going to go back to the 1600s...

**Paul:** It will turn out there was a Medici at the end of it.

**Nadia:** Yeah it’s right, you started this. Just comparing it to highways and cars in the United States, I actually wanted to write something about this as an allegory. We have an interstate highway system right now, you can go from one side of the country to the other and that happened in the ‘50s or ‘60s, it got started. They've been trying to do it for since like the ‘20s.

**Edith:** It was actually communism was the reason they did it.

**Paul:** I thought it was lobbying?

**Edith:** No, they were afraid the Russians would invade and they needed it to move tanks quickly.

**Sean:** I think it was aliens, end of story.

**Paul:** Not the other types of communists? Not America is being communist to provide all these things. It’s like fear of communism.

**Nadia:** That's part of it. There's also another part which was cars started in like the late 1800s or whatever and they weren’t really being ... They were slowly growing but they hadn’t hit a point of really being used by consumers everywhere. Suddenly after World War II we had mass production happening, everyone was like alright like we want to be able to drive anywhere and do anything with these roads but it’s a really shitty system. Eisenhower ended up championing it and during his presidency and the argument that he made for it an interstate highway system was really similar to the need for better infrastructure with Open-source too. Which was like if we can connect everything together so much more prosperity can happen on top of this highway system.

It’s not just consumers driving together or citizens driving around and seeing each other, but it’s also trucking companies can drive across and transport goods from one place to another. Ton s of people are going to make money off of having a more efficient system.

**Paul:** Perhaps to draw a failure in this analogy, there was a very convenient federal system that was already taxing all the people that could actually build this thing and I don't think that's... You're suggesting that this should exist in Open-source?

**Nadia:** It should, but just to clarify, not a ... I don't believe we should have the unified whatever centralized system.

**Paul:** Federal government of Open-source.

**Nadia:** I just want to clarify this point, I just mean that that was kind of the point right there was somebody to step in and help fund it but we all agree that this should exists. We talk about because ...

**Paul:** If you were to build this federal system I think VCs would fund that.

**Nadia:** Yeah, to be super clear I do not want a federal system of Open-source.

**Sean:** That's a really good allegory because it brings up the most important point. It took the only proven wealth redistribution mechanism we know which is government to do that, right? The reality is, we’re probably not going to have government stepping into Open-source but we’ve never seen a privatized wealth redistribution at that scale work.

**Paul:** We do have governments in Open-source. We have governing bodies, there's the Apache stuff...

**Edith:** They don't have taxation rights.

**Paul:** They could have ...

**Sean:** I wasn't referring to governance as governments, I was saying with wealth redistributions, the idea of taxation and...

**Paul:** Right, those foundations and communities are receiving money from the member organizations.

**Sean:** I'm talking about the scale of if Apache was all Open-source then that would be true. We’re talking about a larger undertaking here right?

**Paul:** There's a model here that that could grow into a United Way of Open-source eventually.

**Edith:** I’d say one more thing, I love Nadia's analogy. There's a huge issue right now that all these bridges were built in the 1950s and ‘60s and they're crumbling now, because it’s one of those things…

**Sean:** Because we were supposed to have flying cars let me just throw it out there.

**Edith:** Drones! Drones!

**Nadia:** We don’t need roads anymore.

**Edith:** No, it’s this issue; it’s very much like Open-source. It’s like this issue of deferred maintenance and then it’s somebody else’s problem. All of a sudden these bridges that were rated for 50 years, like the 50 years are here.

**Nadia:** The funny thing about physical infrastructure like bridges is, it’s one of the few issues that everybody on … No matter how you politically affiliate, everybody agrees that we should have a better infrastructure system. It’s like very non-threatening politically. It still doesn't get done because it’s not a sexy topic and no one wants fund maintenance. Even with Open-source infrastructure, like we don’t even all agree that this needs to happen. I think that’s kind of like the first step. Is that like, alright, we do need to figure how to support it, what that looks like is, you know, we can talk about that but …

**Paul:** If we can't agree why we need to support it, and I think that there is quite some disagreement over that, then we are never going to agree on how…

**Sean:** Is there the flip-side? Is it true that all Open-source products would welcome this kind of… I'm just taking the case of Hudson, right? Hudson was an Open-source continuous build server that was ostensibly run by the community that Oracle tried to…

**Paul:** It’s one of these old ones that doesn’t work very well and…

**Sean:** You just get CircleCI, go to circleci.com to sign up, if you use the code Sean Burns you actually have to pay 10% more so don’t use that one. The idea was Oracle was like the parent company and they were like, “Forget you, we're renaming it Jenkins and we're creating a new one, right?” and so they actually resisted having … I don't know what you would call it like…

**Paul:** Corporate overlord.

**Sean:** Corporate overlord. I wonder if, even if that did exist. If it is a universal case that all projects would… the important ones, would accept this kind of help like on terms that were not theirs. It’s like would they … if we could even do it? We could snap our fingers.

**Nadia:** Yeah, we absolutely should not do it on terms that are not theirs. I think the question is not "do all projects need it", but "do enough important ones need it that this is worth looking at."

**Paul:** What are the terms that people want?

**Sean:** Let me be more specific. I just … Would they accept them on similar enough terms that you could have a generalizable solution, is more of what I mean. I agree with you that we shouldn't dictate to them, but the problem is that they all want it slightly differently; there is no general solution then.

**Nadia:** Yeah, I think that's actually one of the hardest parts is that every ecosystem is different or everyone has different needs and different histories and so you can't just say, “Here's a million dollars, like it’s fixed now, right?” and so it really looks … I think that's kind of the fun part is… I think of it as sort of like Open-source infrastructure needs a developer evangelism team, or it needs like a community manager or something, right?

**Paul:** Or a sales team.

**Nadia:** Or a sales team.

**Edith:** Sounding more and more like a corporation.

**Sean:** It needs HR and Finance.

**Nadia:** I think of it more as like stewards and that, and coming from a non-profit background I can think of it as like stewards and advocacy, not like sales and product and like…

**Paul:** Oh it needs sales and product. Open-source needs sales and product more than it needs anything else.

**Sean:** It’s funny because we always project what we… it’s like I actually can see it from Nadia's perspective in non-profits and I can see it from your perspective working in for-profit. I think there's often a tendency that’s super imposed what's worked on Open-source, because clearly Open-source is not working. The problem is like; I don't even know if that's solution, right? We need something that's totally new, something that we have never seen before, like communism.

**Paul:** Let’s suppose a million dollars arrived tomorrow for Python. All right, let’s say a million dollars a year arrived tomorrow for the use of Python. How would that be used? How would it be distributed? What are the conditions by which people get paid by this, who gets paid by it, and how does that work?

**Edith:** Do we pay out everybody who once contributed?

**Nadia:** I think this has happened with grants in the past or even right now for Open-source projects. Where like, they'll give them a grant for like three years for example, but then it’s like what happens after these years? That's even a problem for non-profits and philanthropy, right? Like you don’t want to just sort of get somebody hooked to this like drip of capital and they just need the money over and over. There has to be some sort of like integration into sustainability and impact. I don’t have any magical answers, I think that the one commonality that I've seen across a lot of projects that need more support is that, there isn't any sort of like non-coding function that's really celebrated or encouraged

**Paul:** Right. Yeah, there's no love for product management and…

**Nadia:** Or even documentation to like help people get started, right? So it’s like, “Why aren’t people contributing? Well maybe because they can't figure how to get started, right? So, investing into those kinds of things, maybe it’s not always about like direct payment or whatever, but it’s like how can we help build the ecosystem around the code so that it’s then easier to kind of like pick up and contribute to it.

**Paul:** To ask it in a different way, if the people who are looking for the money had their way, how would it be spent?

**Nadia:** It really depends on the people, which I think is, yeah…

**Paul:** What have some people said? What's the biggest opinion or the top 2 or something?

**Nadia:** The maintainers themselves have, I think, a pretty like straightforward approach to it which is like we want a salary for this and it’s like, and I don’t think they've put as much thought maybe into like how that actually works, and that’s the part that I’m trying to sort out.

**Paul:** There is in the top five or 10 people get like a proper, like Silicon Valley wage out of it or?

**Nadia:** Yeah or just even be able to like pay rent and yeah, take care of their family’s, you know - basic stuff.

**Paul:** They want to be able to work on it full time, and so work for let’s say Python or something versus working for Heroku on Python.

**Nadia:** Right and so one think that I think might help in the short-term is matching up some of those maintainers with companies that are willing to hire them to work full time on their projects. Because that is happening right now already, and I think sometimes when I've talk to developers who've tried to negotiate that for themselves with companies it’s been ... It’s hard.

**Edith:** Well it’s really tough sell, it's like you are basically saying like hey, hire me to not work on anything that...

**Nadia:** Exactly, and it happens right now, it’s already a practice.

**Paul:** I think when that happens it happens because there is a company that already knows the value of doing this, and so they try to recruit that person. And often they'll negotiate like a fifty-fifty like with Guido and like Google, well now he's at Dropbox. But originally when he went to Google there was like a fifty-fifty time thing.

**Edith:** I actually had a follow up question for both of you one was for Paul and was… it’s interesting, you come from a developer background, why are you advocating for sales and marketing for Open-source.

**Paul:** Because people don’t donate, so you need a sales team to go and get those donations, so… and I think that there is no doubt that if you showed up at a bunch of unicorn’s doors and said here’s the risk factor that you face, here’s the economic down side of effect.

**Edith:** I’ve seen this in a movie and it was set with the mafia

**Sean:** I would rather go to the Fortune 500 because a unicorn is looking to the stock market being like shit, shit, shit, shit.

**Paul:** Maybe it's the Fortune 500, you turn up to people who have got money and risk on a certain problem.

**Edith:** Basically you’re saying…

**Sean:** You put a dollar value on that risk and you say here is what you should do to mediate that risk, and I mean no one is saying we’ll put a horse’s head in your bed. We are saying you can donate or you can not donate, and here is the risk, here's the Heartbleed thing that happened. Or here’s what happens if all the credit cards in your system which are being protected by this thing which is like one maintainer only on Tuesdays. Then you can say give us the money and then you can direct the money to good places, and there are questions as to how the good places need to go. But like getting the money in, I think is the first thing, and then you can have the conversation about how should we actually spend it.

**Edith:** I think this is fascinating, because always the sell for developer tools, as you know developers don’t want sales or marketing, they just want to use it.

**Paul:** You're right, developers don’t want sales and marketing, what you need sales for is to make an enterprise sale. You need to find the champions within the organization, and you need to find the people with the purse strings and you need to make an economic case to them as to why they should spend that money.

**Edith:** An offer they can’t refuse

**Paul:** Make an economic case as to why they should spend the money.

**Edith:** Yeah the infrastructure is looking pretty rickety.

**Sean:** That’s awesome.

**Paul:** And then you have to keep the process going.

**Edith:** You're going to come around every week…

**Paul:** Make sure that they are happy okay right that’s what I was saying is exactly.

**Sean:** I'm pretty sure a horse head with HTTP code 702 or something...

**Paul:** But that’s fundamentally a sales process and it’s not like a developer process, you can’t just say, oh this should happen and expect the company, do not expect a developer within an organization to try and make that happen. There is a specific skill set to managing this process, to getting that money out of people and to signing all the things, and that’s called sales, that's what sales people do.

**Nadia:** That I’m totally on board with.

**Sean:** Why is it… this one last question which is that there is so much economic disequilibrium that exists, so much friction exists between these projects that people are working on, open-source that are relying on such and such company. Why is it that capitalism doesn’t kick in and companies do erupt even if it’s not the maintainer, somebody else, like a side company erupts to mitigate the risk the large companies feel. That jump up to fill that gap. Because there is this potential if there is this money that the risk has an economic value. Capitalism would dictate the companies would erupt into this void even if it’s not the maintainers.

**Paul:** There are a couple ones that have. For example Ruby stopped maintaining version 2.3, or maybe it was rails that stopped maintaining version 2.3. This German company came in and said there are a bunch of companies who are stuck in rails 2.3 we are going to support rails 2.3. We are going to back port security fixes and all that sort of thing. They sold licenses for like I think it was $10,000 a year or something along those lines they got a ton of customers and they made a ton of money.

**Edith:** I think another thing is that the risk is so dispersed I mean so basically my mafia jokes aside, what you're selling is insurance but it’s not insurance on any one given point of it, it’s kind of back to United States of infrastructure. To have like...

**Paul:** Someone will fix your pothole.

**Edith:** Yeah, but to have 70 different people come up by your office to advocate for their little corners, not sustainable, there's not enough economy of scale.

**Sean:** If people did know, if they knew exactly how much money was out there. Would the void be filled by ... Is it merely a communication problem or companies just erupt around these problems?

**Edith:** To me it goes back to unit economic scale. If you're hiring a sales person to go and extract 20 bucks from like 3 million different companies, that's not enough to afford a sales person.

**Paul:** I think there's a related thing to this that developers don't want to make companies and they don't want to sell. They like to write code, they like to write software and they don't often don't know how to take the value that they bring and attach a price tag to it and find the people who will pay that price tag.

**Edith:** Sean actually you're developer, you started a company.

**Sean:** I will say I think that a lot of developers don't know how. I don't know if they don't do it because they don't want to, they just wouldn’t even know how important that position is.

**Nadia:** That's something I hear over and over and over again from developers is like I would really, really love if someone would pay me for this and however you want to pay them. I just don't even know where to start, I don't know where to go.

**Paul:** Even I think if they did know where to start, the work starts to look significantly different than the work that they actually want to do. As we’ve all started companies, we know what that's like, you don't write code when you're starting a company. You talk to customers, you work on product, you hire people, you raise money and very, very little of it actually looks like …

**Sean:** You go to the institute of Open-source, you fill our your triplicate forms. You wait a long time.

**Edith:** My last question for Nadia is tied in - you said something interesting about technical documentation.

**Nadia:** Yeah, I just thought of it as an example of people might disagree around sales or marketing or get kind of freaked out by these terms. Even documentation I think of it as something that's not literally writing code but it’s extremely important just to help people communicate with each other. It’s a technical and acknowledged function in Open-source but that doesn’t always get enough love.

**Edith:** I’ll say it upfront, technical documentation never gets much love.

**Nadia:** Never does, yeah and like how do you get started with a new project? You read right?

**Paul:** This is why people hire people to write documentation. Because developers like to write code, they don't like to write documentation and they don't have particularly good skillsets at it. You need people who have that skill set.

**Sean:** Next week we talk about continuous documentation.

**Edith:** I'd like to give a huge thank you to our 2 guests, this was the first time we had 2 guest. Any final words?

**Sean:** Go Open-source, support your favorite projects.

**Nadia:** Yeah, what he said.
