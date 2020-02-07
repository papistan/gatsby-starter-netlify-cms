---
author: andreaech
comments: false
date: 2017-02-01 08:24:24+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-whats-the-future-of-continuous-delivery/
slug: to-be-continuous-whats-the-future-of-continuous-delivery
title: 'To Be Continuous: What’s The Future of Continuous Delivery?'
wordpress_id: 1419
categories:
- To Be Continuous
tags:
- Agile
- Diane Green
- Docker
- enterprise software
- Hacker News
- Joel Spolsky
- Mozilla
- Sam Stokes
- Shaun Burns
- VMWare
---

In this episode, Edith and Paul are joined by Marianna Tessel, VP of Engineering at Docker to discuss the evolution of software delivery from the days of punch card systems. Marianna shares her thoughts on the future of continuous delivery, where she envisions software will be written in small chunks, instantly sucked into the system and ready to be used.

Marianna also shares lessons from her days at VMware on selling to enterprise clients and driving bottoms-up developer adoption.

Is ‘next shiny thing syndrome’ keeping you from being successful? Listen in to find out more.

This is episode #29 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.




TRANSCRIPT__







**Paul Biggar:** So, Marianna tell us what is your favorite thing about continuous delivery?

**Marianna Tessel:** So, I think my favorite thing about continuous delivery is to think about how software development has evolved to get to this point. And how it used to be where you develop big discrete chunks, and now it’s more of this continuing straight line.

And actually my favorite thing about that is to imagine what it will be, and think about how


<blockquote>One day you’re going to write out little chunks of software and it’ll get sucked into the system and work right away. Imagining that we’re still on this journey that’s not complete is fascinating.</blockquote>


**Edith Harbaugh:** One of my favorite people is here today and I’d love for her to introduce herself.

**Marianna:** Oh, thank you. So, I’m Marianna Tessel, I work at Docker, I’m one of the executives there. I build and run the engineering team and I’m actually helping with strategic partnership, and we announced a couple and we’re working on a few more, so I’m doing a little bit more strategy and business these days. But before that, I should talk about my past.

So before that I was at VMware for several years and before that I was at Ariba for several years. So, kind of doing enterprise and infrastructure for a while. And before that I was at a company called General Magic, which actually has an interesting piece of the Valley history. They were trying to do iPhones long time ago, that is, personal devices and it had a very interesting set of people.

A lot of ex-Apple and a lot of people that went off to do a lot of interesting things afterward. It was kind of an interesting upbringing in the Valley. And before that I was in Israel, and my first engineering job was in the Israeli military.

**Edith:** Wow. So that’s a really interesting evolution because you’ve seen the evolution from these huge multi-year releases to continuous delivery and even beyond. What are the biggest changes and what do you think is driving this?

**Marianna:** I think there are probably multiple changes but obviously tooling and what’s available is a huge one. If you take it all the way back, I don’t know, even before I was in the industry. People did punch cards, like you had to really think about what you do, and you’re going to have to go somewhere where the card can be punched and it had to be loaded to the computer.

Well, you can imagine that wasn’t very prime for continuous delivery. You know, you had overtime and the computers weren’t connected, and things like that. But over time, the tools are there to really make delivery of software continuous. And more important, the way we think about software delivery has changed from these big chunks and lots of discrete planning to kind of more of an ongoing evolution.

So, we’ve had cultural and concept changes, as well as the available tools to do that.

**Paul:** So you mentioned software being like sucked into the system as soon as you write it or something like that. I think that’s a really like fascinating way of looking at the world that reminds me of the early days of Circle. When we would actually like rappel into production servers and run code from our editors. But I’d love to hear more about like how you think that’s going to go.

**Marianna:** Well, if I had the exact solution, I might have been sitting here with HeavyBit. So I don’t know exactly how it’s going to happen. But I’m just kind of thinking that both in terms of the readiness of the servers as well as the tools where as you edit, the thing already becomes something that is runnable.

So what you write, maybe it’s like a different language. But everything you write is already runnable. And you know, it quickly propagates itself into the system. You can imagine your editors are already connected to everything else.

I don’t know, maybe there’s not going to be even an editor, right? You kind of express something and immediately it gets kind of propagated into some sort of a machine code or something that then runs into, that gets sucked into the system itself.

**Paul:** It’s funny, this gels a lot with the concept I’ve been thinking about a lot, and I think we, when [Sam Stokes was on](https://blog.launchdarkly.com/to-be-continuous-empathy-in-software-development/), we talked about this a little bit. And the phrase I use is sculpting applications. And the idea is basically that you’re kind of editing a live system at a much, much higher level than it is today.


<blockquote>You’re not building containers and deploying them and orchestrating them. You’re writing something that has almost no accidental complexity, no difference between the problem that you’re expressing and the distributed system that sits under is sort of hidden in some way.</blockquote>


**Marianna:** Right, exactly, so you kind of express yourself at a much higher level than is available today.

**Paul:** It’s funny, I’ve been writing a lot of Haskell code recently. And I’m shocked to discover that actually the difference between the ideas that I’m trying to express and the ideas that I have to express are vastly different, there’s a lot of accidental complexity in a way that I thought they weren’t supposed to have. Sorry, irritating.

**Marianna:** Yeah, and so, there’s definitely ways to go and I’m sure we’ll look back at this conversation and say, “Well, it kind of evolved in a different way.” But I think the concept of software development is going to continue to change actually quite a bit.

**Edith:** Yeah, I mean the way I think of it is just, stuff is moving further and further up the stack. I think like VMware was the first pass of we don’t really have to care about the machines, we just care about virtualization and Docker’s the next evolution.

**Marianna:** Right.

**Edith:** What made you move from VMware to Docker? What was the impetus to do this?

**Marianna:** Oh, that’s a good question. You know, there’s a personal reason firstly. So a kind of software reason was that I thought that the container seems to be like the next thing that’s going to be relevant in software development.

**Paul:** Yeah, I hear it’s the future.

**Marianna:** Yeah, I heard it’s the future too. I’m pretty sure, you know, it’s the future.

**Edith:** I thought it was so 2015 at this point.

**Marianna:** So yeah, I was actually noticing that it came up more and more with users. So you know, I took notice of that and love to work on the bleeding edge. And on a personal level, I spend a lot of time at VMware already and was ready for a change and really wanted to work on a smaller company, so it was a combination of that.

**Edith:** And it’s funny, we ran into a friend of yours from VMware, Adam. And I’ve noted that I know a lot of people who worked at VMware and I admire them all very much. So, what do you think was it about that culture that has produced so many great people, you know, I put yourself, Martine, Joselyne, Peter at like, just great, great, great people.

**Marianna:** Oh, thank you for saying that. Here’s kind of my thoughts. So first of all, VMware was an amazing company and is an amazing company. And had amazing founders, an amazing idea. And it had an interesting run, so I think like with any company like this, it attracted good people to join. So, good people were interested in joining, so there was a collection of good people.

And I think culturally it was a very good company, it was very much engineering led but there’s something about being in successful companies that really helps you understand how it needs to be done when it’s done right.

And I think many of us that had the fortune to be part of the VMware run, had kind of learned, “Okay, well here is how it looks when it looks right. And here is what it means to win.” And that kind of I think helped many of us as we went on.

**Paul:** It’s funny, I hear the same thing about early stage startups, that like a useful thing for a founder is to have been at a series B stage company. And it sounds like you’re saying the same thing, that for executives who are leading the 50 person company to be the 1,000 person company, having been at VMware and seen that working is a very useful thing to have had.

**Marianna:** Yeah, absolutely, it definitely gives you a real context and example of how it should be done or can be done successfully and that is a reference point that you have.

**Edith:** Yeah, it’s interesting, I look up to Diane Green so much, in my fantasies I’m the next Diane Green and, because she did so much at VMware. What do you think were the most important cultural lessons there in terms of a successful team?

**Marianna:** I mean she’s obviously amazing, I have to confess that while I was interviewing while she was there, I took this long break before I started, so I actually never worked when she was there but kind of her legacy was everywhere, right? And, first of all, you know, like I said, it was very technical company that really appreciated good thinking and good engineering.

And that’s always been the case and still is the case. I mean I even watch her now and she focuses on partnerships and kind of win-win seems to be part of what she was doing and I think that has helped the company a lot. And I’m not the right person probably to talk about that but like I said, culturally the company has always been amazing and definitely I think the founders set the stage for that.

**Paul:** And then, how much of that are you able to bring over to Docker? How much of Docker’s culture is already set by the culture that’s there before you arrived?

**Marianna:** Yeah, it’s kind of one of those things that there is a culture that is there and also a culture that’s kind of set by the founders and set by the team that’s already there and set by the people that do keep bringing. So, every time, even though you bring concept from the culture you’re familiar with, it’s always some sort of this combination of things.You really take up the culture and just copy it.

It’s almost like impossible to do, every company has its own setup, so it means that it ends up with a different culture. But obviously understanding what it means to work in enterprise, understanding how, what it means to work with enterprise customers is like, you know, we’ve got a tonne of that in the VMware university.

**Edith:** So, you’re talking about the lessons learned of selling to enterprises, I think everybody would love those lessons, if you could condense them down.

**Marianna:** Yeah, okay, this is kind of my view of it. So first of all, obviously you need to understand what they need and partner really, really, really well with your customers, especially with the first early few. Work with them very closely and keep defining your product as you go with them. And then, you know, enterprise they often want a lot of these what we call enterprise features.

Like they have specific needs for security, for compliance, and just something that you must understand and even though it’s, maybe you don’t feel it like as a core compatibility of your invention, that it just has to be there so they can accept it in their org. The fact that they have a lot of systems already existing or vendors they already work with.

And making sure you can integrate with that and appreciate that is quite important. Understand the pace in which they can take software and will take software. I’m assuming here you know, on this end there’s differences obviously from on-prem and in the Cloud.

And if you’re really trying to create a company, maybe I’m a bit jaded because I, at VMware I’ve done a lot with partners, I really believe that it’s like a village and you have to really understand how to work with others because it’s very rare that you’re the only software that they’ll use. So, understanding how to partner, both on the business side and on the technology side.

**Paul:** So there’s an interesting sort of question that I have there around developing software and developing out the feature set around, I guess kind of the tightrope that Docker has to walk around partners, and around the space, and around open source, and around high valuations, and that sort of thing. It must be quite a challenge to build software under those circumstances.

**Marianna:** Yeah, absolutely. To say the least, yeah. I mean obviously, it is very challenging but I have to say, I wish the world could see how true we are to the community and how much the team works with the community, with the open source community. The incoming grade of PRs is just like mind-blowing and the team is so dedicated in understanding what is needed, what the actual users want, and incorporating that, and really listening to it.


<blockquote>I mean sometimes the internal teams, they are also part of the community.</blockquote>


I mean last year I gave a talk on Docker community and how we deal with it and one of the points there was that actually our internal team is a part of the community as well. They also have to kind of go through the process and I just wish it’s something that was maybe more known.

And the other thing I would say, the community also is built of different parts. I mean there are users that actually consumer your software. There may be developers that build on top of it. And there are also vendors that have all sorts of needs from your software that are legit as well. So it’s not kind of a one thing, it’s like you’re talking to one person in a community.

It’s a very complex collection of people, and companies, and different goals.

**Paul:** Right, the one that I find fascinating is where they’re trying to use Docker as a format but obviously Docker wants to be much more than that, and possibly wants to have the role of Swarm. And so there’s the need to simultaneously be, I don’t want to necessarily say good partners but like partners with that, along the same time as trying to build a competing product in the same space.

**Marianna:** I mean we definitely are thinking of ourselves as beyond just the container format. And we provide the platform, and are listening to what users want. But I will also tell you that we very much have the philosophy of batteries but removable. So, many of these components that we know, like networking storage orchestration, and we are going to even include the others.

We know that other people want to innovate, we totally allow that and we actually build the system in a way that encourages that. And we are going to continue improve that, so there is recognition that there might be users, and customers, and vendors that are interested in a different solution.

**Edith:** We were saying before that we think you have one of the hardest jobs in the Valley.

**Marianna:** Oh. I think I have one of the more fun jobs.

**Edith:** Well, it’s just, it’s not an easy job to balance the needs of all those constituents.

**Marianna:** That’s for sure and like you said, it’s very much under the microscope.

**Paul:** Right, right.

**Marianna:** Often people have opinions, looking and writing, so everything is sometimes magnified.

**Paul:** I had this experience a little bit at Mozilla. So, I really liked where you’re saying that other teams are just community members. Because at Mozilla, it really did feel like there was a difference between the people who were employees of Mozilla, that they had a lot more privilege than external community members.

But it was interesting that at Mozilla, you would frequently get someone saying something on a mailing list or something like that, it was a very open company. And it being taken as gossip by some member of the press, and the modern equivalent of Hacker News.

And I can imagine, you know, someone at Docker saying, making a comment on a PR that gets completely blown out of proportion or that people read their own nuance or read between the lines in just the wrong way.

**Marianna:** Yeah, absolutely, just recently I’ve heard of this PR that was rejected because of some security issue but it was again, blown out of proportion, it was discussions like, “Oh, it’s rejected because of something else.” But you know, you’re right, sometimes things are misread or misunderstood.

**Paul:**


<blockquote>Our industry is one that has a lot of negativity and perhaps a lack of empathy. There’s always a willingness to look for the worst case in what people do and especially in Hacker News and that kind of thing. So the idea of making something as contentious as a big open source project is frankly terrifying.</blockquote>


**Edith:** But you find it fun.

**Marianna:** Well, not everything is fun. You know what kind of the big titles are, what sells and my people like a bit of controversy. Or people always are drawn to more dramatic titles, so I think that’s kind of why they’re being pursued and being commented on.

**Edith:** Yeah, so which ties me back to, what do you think is the biggest change besides more scrutiny and Hacker News between making a software project back at General Magic or Ariba and now?

**Marianna:** Oh wow, you know, so much has changed that it’s not even funny. But first of all, what’s available in terms of tooling is unbelievable. And even a simple thing, like my first job at General Magic was to write a web browser for the device. I mean cause the internet was kind of happening, and they were like, “Oh, we really need a web browser for this device.”

So, and it was like, “Oh, can you go do it?” Like HTML3 I think was coming out then. I went to the library to borrow a book about HTML. So I can you know, write a web browser to parse it. Can you imagine?

**Edith:** That’s amazing.

**Paul:** So let’s just like go into the library.

**Marianna:** So you know, today it’s Stackoverflow.

**Marianna:** Yeah, it just available, so the information that’s available to you, the tools that are available to you. Starting a company before was like a big deal but today like you have the Cloud and you can really quickly just get like computer resources and storage resources. Like again, all of these things were a big deal, so it was really harder.

And this is kind of coming back to continuous delivery. Tools are available now to really develop in smaller chunks with higher speed and more precision. And you know, it’s just great. I remember at Ariba, when I was at Ariba, when the Agile methodology came out and everybody were like, “Whoa, what is that thing.”

And we actually went to get training and our trainer was one of the people that actually wrote the Agile Manifesto.

**Paul:** Which one was he?

**Marianna:** I don’t want to misspell the name, so how about I’ll check later. But you know, very much hardcore and kind of believing in this methodology and we’re all like, “What are you talking about?” And today it’s so clear for people to work in small teams and all these things that people do today. But it was very waterfall those days.

**Paul:** I think a lot of the Agile stuff has been watered down isn’t exactly the word that I’m looking for. But like back in the day they talked a lot about extreme programming and there was a lot of zealotry. And I feel that Agile has gotten to the entire industry now. But the vast, vast majority doesn’t approach it with the same zealotry as it was originally.

**Marianna:** Yeah. Well, I think the thing I would say though is that a lot of people think that Agile is kind of a religion that you have to implement in a very particular way. And I actually found that


<blockquote>An implementation of Agile is highly modified and that you find the Agile version that is suitable for your product, for your team, for your culture, for you know, all of these things.</blockquote>


So, I kind of more subscribe to the thinking that these are all ideas and methodologies and you take from it what you want and you adopt it in a way you want.

**Edith:** What were the biggest gains you saw after adopting it?

**Marianna:** Probably like so many things but you know, probably one of the biggest was how much closer we got to the customer. I remember we started having shorter milestones and connecting to customers really often, and really kind of thinking about developing the software in like smaller chunks, in smaller teams, and have a team that has QA inside and again today it kind of sounds obvious but it wasn’t obvious for us then.

And I remember there was one time when we were working on a feature, I think it was purge and archive, and we had this brilliant idea. But first we’re going to implement purge and then we’re going to do archive, and we’re talking to this customer and he was like, “What are you talking about purge? “You know, we have to save all this data.”

We need it for compliance reasons or whatever and, but you know in the engineering mind it sounded brilliant because first you figure out how to get rid of all this data, then you figure out how to store it, and it seemed like a perfect solution. But the early conversation with a customer, we realized we were completely on the wrong track.

You asked me about the enterprise, what does it mean to be in enterprise? I guess one thing that I wanted to add that I kind of forgot is that you need a lot of patience in the enterprise because there is the enterprise adoption cycle. And it is what it is, both in terms of selling but also in adopting software. So, if you’re on a enterprise journey, just take pills, or whatever you can find in the pharmacy.

**Paul:** It’s funny, on the one hand you’ve got like this furious rate of PRs coming in. And on the other hand, you’ve got the enterprise lifecycle, which is much, much slower and there’s the need to do both I guess.

**Marianna:** Yeah, you still have to kind of go through the enterprise adoption cycle, especially for things that go for production, especially for like bigger corporations and you are kind of subject to all of that.

**Edith:** Yeah, it’s funny. So, we sell to enterprises and we’ll have our champions and they’re like, “Okay, how do I get procurement to sign all this?”. “How do I get legal to sign off of this.” Like they want to buy but they have to work with their system,

**Edith:** Yeah, exactly that, they’re like, “I need to work this, I need to let the system digest this project.”

**Marianna:** Right, and go through all the approvers, and all the reviews, and all the internal compliances.

**Paul:** There was one point where we started selling to enterprise and one of the steps that you needed to buy it was that your purchaser had to have a GitHub account. And it’s like, “Well, how do we sign up?” Well, you go into the thing and you fill in the credit card, and it’s very straight forward. And he’s like, “Well, how do we get in?” Like they need a GitHub account, we’re like, “Oh.”

**Edith:** And the thing is that your purchaser might be anyone.

**Paul:** Exactly, it was someone, and very often the accountants are the people involved and the accounting department, do not have a GitHub account. But that’s what you need if you want to see billing.

**Edith:** Yeah, I mean I was talking to a procurement person who I’m actually friendly with. And I was like, how’s your day? And she’s like, “Oh, you know, I’m working on this, I’m working this other project, I’m also buying advertising from the New York Times.” So, I mean she’s procuring everything up to and including LaunchDarkly in newspaper advertising.

**Marianna:** And companies can also do all sorts of things and still want to use your technology, so they don’t necessarily as you know, advance with everything as we sometimes feel in the Valley.

So you can go in a company that maybe manufactures equipment or does some construction and they want to use like new technology but it’s like you’re talking to a whole different world and you need to have a bit of language translation there to understand how to go about it.

**Paul:**


<blockquote>I think that’s one of the things that’s super powerful about this, the bottom-up developer adoption. Like there’s going to be someone installing Docker on their own machine for their little project. And somewhere, you know, three steps up and two steps across the hierarchy, there’s someone that they have to convince to buy that eventually.</blockquote>


But they’re able to get it going, get it working without having to get that conversation going.

**Marianna:** Yeah, absolutely, that’s kind of the beauty of developers bringing in software and the ease of adoption, and they’re open source, and all these different things. And by the way, SaaS has the same attribute because it’s so easy to open an account and just to get going. And AWS has all the same attributes.

It’s so easy to get going. I mean I remember a few companies ago, when we started using Salesforce and nobody really decided to start using Salesforce but somehow we discovered there’s like a bunch of people with Salesforce accounts. And it was like, “Oh, there’s this tool.” And then we’re like, “Oh my god, we have to move our software to SaaS.” And it was actually at Ariba because it just seems such a brilliant way for everybody consuming software.

**Edith:** Yeah. I mean I remember the cost of sales used to be so much higher because you had to have a lot of people, you had solution engineers who would just go and do the POC.

**Marianna:** Yeah.

**Edith:** So we had an entire staff of people to do POCs because that was the only proof of concepts because that was the only way that a customer could see the software.

**Paul:** And would people pay for the proof of concept?

**Edith:** No, but it did inflate the final purchase price.

**Paul:** Right, because you have to pay for all the previous proof of concept that didn’t work out.

**Edith:** Yes, so you would have to do these two to three month proof of concepts. And it was probably the same at Ariba.

**Marianna:** Yeah, like when you see a company kind of at this upswing, that normally means that they had a lot of these like long cycles. Then went with companies, then all matured at once, and it’s true that once something becomes very, very prevalent and it’s kind of just easier, and I’ve definitely seen it in a couple of companies I’ve been at.

It’s just easier to close an account, and sell, and get adoption, et cetera, et cetera. But going back to kind of talking about open source and SaaS, I think it’s just so important when you write software to understand if you write software to enterprise, what’s your in? And how would you find like an easy way in?

**Edith:** Yeah, totally. So you two have more in common than I thought, you both have written web browsers.

**Paul:** I don’t know if I’d say I’ve written web browsers. I’ve taken part in the late stage work on a JavaScript engine, so Mozilla’s JavaScript engine.

**Edith:** And you thought about working at Docker.

**Paul:** So, in 2011, I was leaving Mozilla.

**Edith:** Oh, wow.

**Paul:** And I sent an email to the YC list saying I need a job and like 100 people replied. And I think one of the more interesting ones was Solomon, who’s the founder of Docker. And at the time, the company was DotCloud, so this was long, long before Docker. Like DotCloud was a Heroku competitor. And so, I went in and I talked to Solomon, and I interviewed with a couple of engineers.

And they had me do the take-home project, to build a distributed web crawler on DotCloud. And I had never really built web stuff before and I had definitely not built distributed system stuff. And so, DotCloud was my first real experience with that and it was amazing. I loved DotCloud so much, it was such an amazing product. And then they’re like, “Yeah, you don’t have enough “distributed systems experience, sorry.”

**Marianna:** Funny.

**Edith:** Do you regret it? Or were they right?

**Paul:** Well, I mean if I had taken, if I had taken that job I wouldn’t have built Circle.

It’s funny, I look at like all the jobs that I was applying for, I was applying for Dropbox and then there were other companies that have gone nowhere that I was convinced were going to be amazing. But like if I had, had one that I was super excited about, that took me, I wouldn’t have built Circle, so it all works out in the end.

**Marianna:** Well, you say it all worked out, then obviously Solomon is brilliant, he went and did Docker, which is amazing. And you never you know where things are going, so it’s always kind of in retrospect when you go back and you’re like, “Oh, like that step led to that, and led to that.”

**Edith:** Well, so you’ve been at Docker not since the very beginning but since you said it was 50 employees?

**Marianna:** About, yeah, in between 50 and I don’t know, maybe about the time there was a bit more.

**Edith:** How many are you now?

**Marianna:** We are over 250, so quite a bit. In a couple of years, we multiplied ourself by, five times.

**Paul:** Still a small company at 250 people.

**Marianna:** By VMware standards, yes.

**Marianna:** By VMware standards, actually VMware also went through multiplying itself every single year, that’s been challenging. I remember when somebody pointed out at an all hands that”Do you realize that in this room there are more new people that just joined this year than all the people that joined the previous 10 years combined?”

I was like, oh my god, that is true. And it’s kind of, tells you how much you have to reinvent yourself when you go through this growth because there’s so many new people every year.

**Edith:** Any lessons learned or things you’d like to share about that experience?

**Marianna:** Obviously, a lot is learned, but you know, I would say that the biggest thing is to understand that at every phase, you’re like a little different company and you are going to have to reinvent yourself because what was true for 50, not true for 250, and when I left VMware, it was 18,000 people or something like that.

Definitely not true for 18,000 people. So, you kind of have to keep reinventing yourself at every single stage. But, and I think it’s so important also to have that, we talked about this winning gene or whatever, is understanding how, but have kind of this resolve of like this is hard but we can do it and we will do it and we will win. That’s like very good DNA to have.

**Edith:** Yeah, my advisor, Sean Byrnes, he gave me really good advice, he said


<blockquote>The things you do from 1 to 10 will not work when you go further. You’re going to need different things to go from 10 to 100.</blockquote>


And he wasn’t talking about employees, he was talking about revenue, scalability, anything, and then 100 to 1,000, like every unit of 10, you have to change your techniques.

**Marianna:** Yeah, it’s kind of this snake, right, that keeps on peeling skin and growing a new one.

**Edith:** So we started talking about, Paul were you talking about React?

**Paul:** We were talking about interviewing

**Marianna:** Hiring.

**Edith:** Yeah, so Marianna was saying, I don’t know, can we reveal your interview question?

**Marianna:** No.

**Paul:** Alright, so if you’re interviewing for Docker, you should know basic computer science concepts. Is it how many bits are in a byte?

**Marianna:** Pretty much.

**Paul:** Well actually, that kind of depends, never mind. So, the discussion that we were having is that I don’t really believe that it’s necessarily important to have basic computer science concepts to be an engineer.


<blockquote>And in particular, there’s a subset of engineers that I meet, who know almost nothing about CS. They’ve learned front-end concepts or they’re able to string things together very quickly and they have focus. And those two things allow them to build very large things, especially if they have product vision. But they wouldn’t be able to answer a Whiteboard coding question.</blockquote>


**Edith:** Yeah, actually how we started talking about it is because I didn’t know about the story Paul was saying, how he interviewed a bunch of companies and didn’t get accepted and I’m like, wow

**Paul:** Well, I mean I got some of them.

**Edith:** Some of them, but sorry, the ones that you didn’t and I said, wow, it’s such a mess because here’s like this amazing guy.

**Paul:** I was also rejected from Dropbox.

**Edith:** So, here’s this amazing guy, right, that went ahead and founded such a great company and clearly the interviewer has missed that.

**Paul:** I mean, no one in the industry knows what they’re doing around interviewing. Like, Google had this number that came out recently that 50% of the people they hire after this grueling and intense process turn out not to work out. It’s like 50%.

**Marianna:** And Google is famous for its interviews.

**Paul:** So, it’s not that they don’t work out but like the correlation, 50% of the people they hire are successful in the way that they were expecting them to be or something along those lines.

**Edith:** That’s crazy, it reminds me of the the SATs in the states. And everyone says the SATs are not a correlation with eventual success.


<blockquote>I think so much of being successful is ability to work well with other people.</blockquote>


**Marianna:** Yeah, and have persistence because you’ll have difficulties and you want to overcome them.

**Paul:** I think focus is a big one. It’s very, very easy to keep chasing the next shiny thing, and especially in companies. I think a lot of companies are like this today, where you’re kind of not quite encouraged but certainly not discouraged from having side projects and sort of, you come in with a PR that you weren’t told to work on and maybe it’s a good thing or maybe not.

And so there’s this sort of next shiny thing syndrome. And if you can avoid that and you can stay focused on your thing, you can deliver so much stuff. And if you keep going for the next shiny thing, often you’ll have like 10, 15, 80% finished projects that never actually cross the line, and as a result you’ve made nothing.

**Marianna:** You know, several years ago there was this blog that came out that talked about, I mean I’m forgetting the source of that. But talked about how when you hire, you need to hire smart people that know how to get things done.

**Paul:** Oh, that’s [Joel Spolsky](https://www.joelonsoftware.com/).

**Marianna:** Yeah, yeah, yeah. And I think it’s so right. But I would add to that, also like the soft skills but this kind of goes to your point, that if you wander around, you will never get anything done and maybe each one of the things we’re doing were brilliant but it doesn’t matter because nobody gets to enjoy it.

**Paul:** And 90% of a brilliant project is zero.

**Edith:** Yeah, I was talking with a friend who works at a big software company I won’t name. And he said he loved Agile because before they would have these year-long projects. And what would happen eight months in, was the business would change their mind.

So, they basically had gone.

**Marianna:** By the time they were listed, it was obsolete.

**Edith:** Well, they couldn’t even, it would work for eight months and the business would say, in defense because I’m business now, like the market changes. They said


<blockquote>Whatever you started working on for eight months, it’s not what we want anymore. So they had this continual string of non-delivery.</blockquote>


**Marianna:** The continuous non-delivery.

**Edith:** Yeah. Absolutely, so he loved Agile because he said, “You know, we break it into smaller chunks but it’s guaranteed to get done.”

**Paul:** I think a lot of engineers like not having structure. And one of the things that I think is best about Agile and the various tracks of Agile is that structure helps you get things out the door, helps you get them to customers. When you look at the product function, there’s the get things to five customers, let’s get things to 50 customers, let’s get things to all your customers.

Like, it’s not just writing code that’s involved in that, and you need that kind of structure.

**Marianna:** Yeah, I mean in the daily scrums and like definitely when you do like this burn down charts, like you get to a lot of details. But it doesn’t feel quite as suffocating, you know.

**Paul:** Well, I mean if you tell an engineer that like, “Oh, we’re going to have a daily scrum and you’re going to have to be in at a certain time to get to that. And then we’re going to have a burn down meeting and there’s going to be like two weeks of it. Keep going”. They’re like, “Oh my god, meetings. I just want to write code. Let me write code.”

**Marianna:** What if you tell them that you bring chocolate.

**Edith:** I was going to say something about chocolate and then I started thinking about like the culture of goodies.

**Paul:** Yeah, I mean I’m the worst at this, like I need external pressure to stay focused on a particular thing. I don’t know if it’s ADD but like it feels like really bad ADD.

And like, having customers as the external pressure is like really, really useful to getting things done in the early stage. And then when you’re at the stage where there’s less external pressure or different external pressure, I guess it’s not specific. I found it much, much more difficult to get things done.

**Edith:** I think the lack of customers can be very awful for projects ever getting delivered.

**Paul:** Right, right. As soon as you have customers, it’s like, oh, of course you’re going to get things done because there’s someone yelling for it.

**Edith:** Well, you were going to say something.

**Marianna:** No, I was saying that provides you the focus you need because we talked about being focused and suddenly there’s a deadline, there’s a need, there’s a person, you feel like, then you’re like, “Oh, I have to be focused on that.”

**Paul:** Yep, yep. Nothing like urgency to get something across a deadline.

**Edith:** I totally agree with you, we all need that.

**Paul:** Yeah. So, something I found interesting is, so Paul today was showing off his shiny new green card. Yay, can’t kick me out now.

**Edith:** Yeah, so what made you both decide to come to the states? I mean Ireland has a really booming software industry, as does Israel, what made you decide to come here?

**Marianna:** Yeah, so actually I told you that my first engineering job was in the military and in Israel it’s compulsory, so I went to this program where I went first to school and when I graduated I did my compulsory service, and I served for a while and then I did what many people do after they finish their military service, I went travelling.

And we went, with my husband, we went to India, and Nepal, and Thailand, and we spent several months backpacking. Then we had friends here in the Bay Area, we decided to stop by, even though it’s not really on the way. But when you kind of take a big plane ride, everything seems on the way. And we stopped here, she was doing like PG at Stanford and he was working here.

And we came here and it was like, wow, we love the place, we were both engineers and we’re looking at all the companies here and it just seemed like an unbelievable place, and it still is for people that do software. And we kind of stayed here and I still think it’s the most amazing place for software development .

**Paul:** It’s fascinating, I’ve exactly the same story. Yeah, so I mean, I wasn’t with my husband in Nepal.

**Edith:** How about India?

**Marianna:** Were you in the Irish military?

**Paul:** Yeah, yeah, they’re very famous. It’s a very stealthy military, people don’t really know that much about it.

**Edith:** I’m not going to make a joke here.

**Paul:** So, what happened was I got a paper accepted in a conference in Hawaii. And from Dublin, San Francisco is on the way. And so I was like, alright, I’m going to fly through San Francisco and I’m going to see if anyone will let me give a talk. And so I convinced a guy near Google to let me give a Google tech talk. And then I gave a talk at Facebook and I gave another one at Lawrence Livermore National Lab.

And so, when I came over, obviously, my grant is paying for all the flights and you could stay in a fancy hotel. But instead I saw this, on Hacker News I saw someone advertised their hacker house in Palo Alto, this was about 2009. And it was on this site called Air Bed and Breakfast.com.

And so I stayed like literally on an air bed in a hacker house in Palo Alto, and all the guys in the house were going through Y Combinator. And I was just like, oh my god, there’s just, there’s all these people who are just like building their ideas, and there was no money at the time, like it was 2009.

**Edith:** There was no money.

**Paul:** There was no money. The only ones from that batch who were really able to fundraise were Airbnb. But everyone was just like building their stuff and they were super excited. And in Dublin at the time, I mean you described that Dublin is this second city of tech in a certain way.

**Edith:** There’s Intercom.

**Edith:** CircleCI has an office there.

**Paul:** And every San Francisco company has their second office is in Dublin. Their European headquarters. But I mean at the time, it wasn’t quite like that, Google was there and Facebook maybe was kind of getting set up around then. But it wasn’t really the same.

And the things that mattered in Ireland when I was in my twenties were real estate, and construction, and finance, and software, so it was like no one gave a shit. And so, you get somewhere where like suddenly software is everything.

**Marianna:** And not only that but cool.

**Paul:** Yeah, exactly, and I realized I have to move here.

**Marianna:** Yeah, you can write software and be cool at the same time.

**Paul:** Right, right, it was shocking.

**Edith:** So, I was not in the military. I have been in Nepal but it’s funny because I moved to Texas as part of the Dotcom bust. So, my company got bought, I moved there.

**Paul:** You were here before the bust and then you had to move to Texas. Wow, that’s the worst.

**Edith:** Oh, I was in Austin, but I realize now that it was Austin that was still kind of working its way out of the Dotcom dregs itself. Like literally, Intel had started to build a huge headquarters downtown. And then, the recession hit, and there was this empty shell because they did not have the money to finish it and they didn’t think they would ever have the workers to be in it.

**Paul:** Wow.

**Edith:** So finally, they just dynamited the whole building because it was an eye sore. So this is the state of Austin and I came back to San Francisco because of the same thing, I was like, wow, people are building cool stuff here.

**Paul:** What year did you come back?

**Edith:** I came back in 2007. Just in time for the 2008 recession. But it was the same sort of feeling of Austin at the time was dead.

**Marianna:** Seems like we all came here for the love of software, and love of tech, and love of creating product. And honestly, there’s so many people like this here, that it’s just is amazing, like everyday and like the people you meet, the people you work with. I don’t think there’s a second place like that.

**Paul:** Well…

**Edith:** So, that would of been a perfect time to end, Paul. That would of been like a perfect way.

**Marianna:** We need controversy.

**Edith:** And then Paul jumps in with the, the well…

**Paul:** I kind of feel that the feeling that I had in 2009 of like people just into software and building things. I feel that it’s not what San Francisco is anymore. Like I feel that it’s kind of a gold rush now.

And it feels like what I imagine New York felt like during the finance rush of like 2006 – 2007. Where it just kind of like, busloads of graduates just like move here to chase their dreams and I don’t necessarily feel that that’s a bad thing, I mean I chased my dream here and it’s a great place for people to do it. It just, it doesn’t feel like it did in 2009 when I wanted to move here.

**Marianna:** But do you agree, they’re like both, like both people that, not just chasing but really want to do like great things?

**Paul:** Sure, yeah, absolutely. People are, I think people are sort of moving here for the same reason but it’s not the same people.

**Marianna:** Are you telling them to get off your lawn.

**Paul:** No, no, so I’m emphatically not trying to tell them to get off my lawn. I’m just saying that…

**Marianna:** But if you were to have a lawn

**Paul:** I’m just saying that the garden party isn’t the one that I used to enjoy going to.

**Edith:** I guess I haven’t been here as long as you, but I think there’s always this sense that the new people are not as cool as the people who’ve been here for a while.

**Marianna:** Yeah, the people that came here in the nineties, they’re like the coolest by the way.

**Paul:** Right. I think they don’t really talk to us, they own all the property.

**Edith:** She’s here doing a podcast with us.

**Paul:** Fair enough.

**Marianna:** Yeah, you’re like the cool people.

**Edith:** I do think, I completely agree with you that I feel like doing a startup now is like being in a band in Seattle in the nineties. Or being a screenwriter in LA or being an actor in New York. Like, what all these four things have in common is there’s basically zero qualifications to claim you’re doing any of these. You know you can just say I’m writing a screenplay if you’ve opened Microsoft Word once.

**Paul:** It’s kind of the beauty of it. Or at least, I feel it was the beauty of it when there was very few people writing screenplays. Or there were very few bands or whatever analogy we want to pick.

**Edith:** I think New York has always had actors though.

**Paul:** Has it? Okay. For people who just love software, I’m not sure San Francisco is the most amazing place anymore.

**Marianna:** Where is the most amazing place?

**Paul:** I don’t know, I don’t know if there is one.

**Edith:** This sounds like the beginning of a movie, where like Paul…

**Paul:** Yeah, yeah Paul gets in an RV and drives around America for a couple of months figuring out things, writing my novel. Or my great programming language.

**Marianna:** Finding the Xanado of development.

**Edith:** Well, we really enjoyed having you here, any final thoughts?

**Marianna:** I had a lot of fun. And for the record, I still think it’s in the Bay Area.

**Edith:** And she was in the military, so I’m going to agree with her.

**Marianna:** Yeah, like you have to agree with me.

**Paul:** I guess I should too. The veiled threat.

**Marianna:** It was a lot of fun.


