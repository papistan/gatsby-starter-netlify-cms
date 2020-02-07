---
author: andreaech
comments: false
date: 2016-11-03 18:31:05+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-organizational-scaling/
slug: to-be-continuous-organizational-scaling
title: 'To Be Continuous: Organizational Scaling'
wordpress_id: 1286
categories:
- To Be Continuous
tags:
- Amazon EC2
- AWS
- BitBucket
- github
- Google Cloud
- HackerNews
- Moz
- OKRs
- organizational scaling
- Peter Thiel
- product manger
- Rand Fishkin
- Silicon
---

In this episode, Edith and Paul discuss the steps that a startup can take for successful organizational scaling. They bring up important questions including: What roles should your team members play as your company grows? How do you prioritize resources? Is Paul a good coder?_  _This is episode #26 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.




TRANSCRIPT__







**Paul Biggar:** This week we’re talking about scaling.

**Edith Harbaugh:** We started to talk about this last week. We talked about specialization versus scaling.

**Paul:** Versus generalization?

**Edith:** Yeah.

**Paul:** Specifically, the scaling that we’re talking about is organizational scaling, rather than our team scaling prep, not infrastructure scaling.

**Edith:** Correct. Though, I think they go along.


<blockquote>I think there’s two big sins, which are premature scaling and waiting too late to scale. And they kind of go hand in hand.</blockquote>


**Paul:** Right. Yeah, you can say the same for organizations as well.

**Edith:** I think I’ve seen the mistake of startups that have raised a lot of money and have acted like they already made it.

**Paul:** Was it you that wrote a scathing blog post about Lasers? No, Famo.us!

**Edith:** Famo.us.

**Paul:** Famo.us, yeah.

**Edith:** It wasn’t scathing. It was meant to be kind. But basically, you can have hubris when you raise $20-30 million and think that you have already made it.

**Paul:**I remember meeting their head-of-something at a Heavybit function, and they hadn’t released their product yet. They had a Head of Marketing or something, and I was like, “You did not make the product before you built the team that does the marketing for the product.”

**Edith:** I’d say, actually, I think you should build your marketing and product together, because they go hand in hand.

**Paul:**It was like a VP-level sort of thing. So I would say don’t hire VP levels for your seed-stage stuff.

**Edith:** I’d say hire a VP-level person if they can also do individual-level work.

**Paul:**We should step back a little bit.The thing I think that we’re talking about is, when you’re starting a new team or a new company, you’re in the range of two-to-five people. And the steps, the things and the activities, and all the stuff that you do at two-to-five people, should be suitable for, I’m going to say, getting product-market fit on that.

**Edith:** When you’re two-to-five people, you’re constantly iterating on, “What is our product? What is our market?” And that’s why I say it’s good to have a marketing person.

**Paul:** Because we talk about this all the time. And so what we’re going to talk about this week is the next level. So you’re taking it from the five people to 21-to-20 people, at the next level of scale, and what’s involved in that.

**Edith:** Well, I’ll be honest, that my company has eight people.So I don’t know how qualified I am to participate in this podcast.

**Paul:** You’ve done this before in various organizations, I think, or been part of various organization that go in that.

**Edith:** Yeah, of course.

**Paul:** I’ve only been part of very large organizations and one organization that scaled. And then I have the collective wisdom of many, many startup-founder commiserations, “Here’s how we fucked up,” and “Oh my god, you should see the problems that we went through when we were scaling.”

**Edith:** What are some of the common mistakes that you’ve seen?

**Paul:** Well, not scaling early enough. In particular, organizations outside of engineering. It’s very common to have engineer founders hire more engineers. And in particular, to not build the product org. That, I feel, is a mistake people keep making.

**Edith:** Why do you think that is?

**Paul:** I think engineers have a world view that is influenced by open source. Very, very strongly influenced by open source. Open source, for the most part, is engineers building and engineers PM-ing a sort of unified function. I would say that the PM function is also very restricted in open source.

The things that you build are the things that scratch your itch, and any pull requests that come your way. It’s a real lead-with-code sort of thing, and I actually think that that’s completely unsuitable for open-source products, but it’s particularly unsuitable for startups or any products.

**Edith:** I think the critique is that it’s reactive, and some might say, Linus Torvalds, that the reason why some people think that he’s a jerk is that he’s like, “I don’t want to take every pull request. I have a vision and I’m trying to make sure that the only thing I accept is the things that fit the vision.” But what ends up happening then is you end up rejecting people extremely late in the process.

**Paul:** Exactly. This is the problem with open source.I made a contribution to something the other day, and before I made a contribution I made an issue saying, “If I made this, would you accept it?” Crickets.

And so then I built it and made a pull request, and there’s still crickets.It’s been like four days, which, I don’t know, maybe that’s a bit quick, but you kind of expect an answer in four days.

**Edith:** I think it goes along with the value of product management, in some ways, validating that there’s a need or a market for something before you do the work to build in it.


<blockquote>Whereas open source has it backwards, where people go off and build their code and then get their noses, rightfully, a little bit out of joint.</blockquote>


**Paul:** Absolutely.

**Edith:** But, it’s like, “I did all this work!”

**Paul:** This is a problem that I had at Circle, that I wasn’t very good at articulating what our direction was and what the product vision was. And so people would routinely build stuff, where I stuck my nose in like literally at the last minute and said, “We can’t ship this, because it doesn’t fit within the product vision.”

**Edith:** And that’s heartbreaking for everybody.

**Paul:** Oh god, yeah. That was the worst thing. If I would run a company again? Advice for people managing this transition of the new startup: the most important thing is to set out your company mission, your company vision, your culture and your product vision.


<blockquote>You want to really establish who you are, what you want to be, where you want to go, what you want to do as a collective unit, so that everyone is on the same page about that.</blockquote>


That solves all sorts of problem. When you’re hiring someone, it’s like, “Does this person agree with the vision? Are they part of the mission? Is that a mission that they agree with?” And the same thing at the company level, and also the product level.

If someone joins your company and wants to take the product in a radically different direction, then either they need to change their mind, or you need to change your mind. Otherwise you’re just going to be pulling opposite directions from each other.

**Edith:** Two examples. You put your finger on why I became a product manager. I was an engineer and I was tired of building stuff that the product managers would just reject after it’s built. It was extremely painful, from us who’d built it. And I was like, “We need to stop doing this. This is not what I want to do anymore. If I’m a product manager, this won’t happen.”

And of course it still happens, but you understand why, and you have more empathy, and you try to fix it. You inadvertently build an organization that reflects your own mission, or lack of mission.

**Paul:** You want to say more about that?

**Edith:** I’ve heard that GitHub has gone through a lot of strife right now because they had built a company that was very much out of bottom-up: “We sell to individual developers.” And now they’re trying to get more enterprise-y for very obvious reasons. That’s why there’s a lot more money. And a lot of people are just like, “We can’t work here anymore.”

**Paul:** A specific about GitHub, I heard that they’ve gone through many different transitions of that size. But I guess every company goes through major transitions.In particular, there’s a saying in the Valley that, I forgot what exactly it is, but the people who are your heroes up front are not going to be the people who are there in your organization later.

**Edith:** Well, since it’s a classic, have you read “[The Innovator’s Dilemma](https://www.amazon.com/Innovators-Dilemma-Revolutionary-Change-Business/dp/0062060244)”?

**Paul:** I wish I had.

**Edith:** It’s a really good book. This is not new; this is a book from 20 years ago. But it’s talking about how the innovators are the prototypers, the people who are willing to wear a lot of different hats, who are willing to be wronged very quickly. And then you have a transition point to more lieutenants.

**Paul:** Right. That goes right into our last week’s discussion of generalization versus specialization.

**Edith:** Yeah, it’s not anything unique to software. It’s unique to any new thing.

**Paul:** The problem, then, with product managers when you bring them in, is often engineers feel that there’s a lack of autonomy that they’re getting out of it. They used to be the ones who were the decision makers about what to build, and all that sort of thing. And then there’s a feeling that the product managers are going to tell them what to build, and often that feeling is based on reality.

**Edith:** Like I said, I’ve been on both sides of this. I don’t have a clean answer. It really depends on your engineers. I have an engineer friend who says, “I have a lot of personal stuff going on right now, and I just want to be told what to do.”

**Paul:** Right.

**Edith:** He wants to be an engineer. Other people are like, “I think of myself as a product manager/engineer/marketing,” and you’re like, “Woah, okay. You’re none of these things very well right now.”

**Paul:** Right. People think that product managers are managers. Engineers, I think, often feel the product manager’s a manager so they’re people who tell them what to do.

**Edith:** Oh no.


<blockquote>Product managers are persuaders.</blockquote>


**Paul:** Exactly right. A good product manager is a persuader, exactly.

**Edith:** Well, a persuader or a facilitator, a consultant.

**Paul:** A researcher.

**Edith:** I think the greatest strength of a product manager is to knit together a group of people all with different ideas and make them collaborate on a common goal.

**Paul:** If your organization is entirely engineers at the start, I think the first thing you’re going to need when you’re scaling is to get the start of a product organization together. Someone who has the skillset and who has the experience to be a product manager, or who has been a product manager before and understands what a successful product organization looks like, is going to be a really good thing to get in, especially if they can work together with the engineers and not against them.

**Edith:** Yeah, I think that’s key.


<blockquote>If they think of themselves at odds, it will not succeed.</blockquote>


**Paul:** There’s a saying that the project manager’s like the CEO of their organization or of their sub product. I kind of feel that. I don’t think that that’s a very apt definition of what a good product manager does, but there’s a lot of people who feel that way.

**Edith:** It’s funny because, like I said, I was a product manager, and now I’m a CEO.

**Paul:** Right. But you wouldn’t have a product manager and give them CEO level. Well, I guess it depends on what you see as a CEO’s role. But a lot of the CEOs, and I include myself in this, work towards building by consensus and trying to get the direction the same. I don’t actually tell people what to do. But I think the traditional view of a CEO is someone who tells people what to do, and then is responsible when it all fails.

**Edith:** Yeah, I think I was fortunate that I was basically given a managerial role at my past companies, where I had responsibility for revenue. Not just for product, but revenue, how many sales were made, marketing. And it was very good for me to think that way, that you can tell people what to do, but if you talk to them and listen and come up with a sure path forward, things go better.

**Paul:** Right. Speaking of talking and listening, I think management is a good thing to talk about in the context of the scaling that we’re talking about. You should have managers. That’s a controversial thing.

**Edith:** It’s funny. I love talking to you, Paul, because I think I’ve talked to post-transition Paul.

**Paul:** I think you have. Yeah, pre-transition Paul had a different point of view.

**Edith:** I’ve heard rumors that, before, you were very much like, “We never need PMs. Everybody can self-manage.”

**Paul:** Right. Well, a little bit. But I think the position that I used to have is that everyone should be ICs of various kinds. In particular, I think it’s interesting, related to management, in that a traditional view of a manager, someone who is the manager of an engineering team, let’s say, often someone who is making technical decisions, who’s making architectural decisions, who’s hiring and firing and all that sort of thing, doing HR stuff, and also is responsible for the people stuff, the career development, the “How are you feeling today? Let me get you a glass of orange juice so that you can crank this code out.” And sometimes, on top of that, they also write code.

It occurred to me, I think it’s very obvious, in fact, that the idea that the best person on your team, who’s usually the person who gets promoted to engineer manager, do they also happen to have all these skills? They’re your best coder. Do they also have people skills and that sort of thing? So, instead, you need to break it out into different roles.

I think the people manager role is necessarily one that the organization needs. And then the product manager role is necessarily one that the team needs. And then, possibly, there’s some sort of architecture or technical decision-making sort of role. I think this is actually what modern companies look like.

The thing I found interesting before, pre-transition Paul would have said that you can have all this without hierarchy. And I think post-transition Paul is like, “Yeah, I suppose you could. But I haven’t seen it work.”

**Edith:** It’s interesting because Google did a big [longitudinal study](https://hbr.org/2013/12/how-google-sold-its-engineers-on-management). They had a theory that the best engineering manager is the best technical person, because people need to respect their acumen. And then they did a lot of studies, and it turns out, of their own managers, that no, the people who had the best technical skills were sometimes the worst managers.

**Paul:** Right, I wouldn’t be surprised.

**Edith:** Well, you’re not surprised. Butit was a surprise for them.

**Paul:** I had a surprise around product management. I’ll relate this back. My surprise was that not all engineers can do product management. And when I say product management, let’s say, can have good product vision and insights. And I was surprised because I thought, inherently, that’s a part of building a product. Or at least, inherently, what was part of being an engineer.

And then I thought back. I was like, “Well actually, we’ve never been trained in building products. We’ve never been trained in product vision.” What we’ve been taught to do, at least if you go to computer science courses or whatever, is you’re taught to write code and sometimes think about formal methods. But, generally, you’re there to write code.

People who are engineers have 10 years of experience of writing code, and not necessarily, although sometimes, there are very talented product-vision people in there as well. And they go nicely hand in hand, but very often are missing.

The assumption that I had had was, “Everyone’s going to be good at product vision.” And that assumption was flawed, and I think it’s the same thing that, maybe, Google had made that. Maybe Larry and Sergey were particularly good at this, or some of the early people that they hired or the first people who got promoted into management or excellent technical people who thought, “Oh, excellent technical people are also obviously going to have excellent communication skills.” And I think you could make some sort of intransitive argument there that wouldn’t necessarily hold up too well.

**Edith:** You think everybody is like yourself.

**Paul:** You think everybody is like yourself or the examples that you can see in front of you.

**Edith:** I know that you’re an excellent coder, and you have an excellent product vision.

**Paul:** Actually, you have no idea that I’m an excellent coder at all. You’re assuming I’m an excellent coder, but there’s no evidence of this whatsoever.

**Edith:** People have told me this.

**Paul:** Who has told you this? I can’t think of anyone who would say I’m an excellent coder, who has knowledge that I’m an excellent coder.

**Edith:** There is no one that would vouch for you?

**Paul:** I mean, when I’m looking closely at who has worked for me or worked with me, or who I’ve worked for, the amount of people who would have closely looked at my code or the speed at which I put out code or how my code holds up in production, that sort of thing, there might be two or three people, in total, who could say I’m an excellent coder. I don’t think I’m an excellent coder.

**Edith:** But you do look excellent in a LaunchDarkly T-shirt.

**Paul:** Thank you. It’s a constant reminder that I don’t have all the good ideas.

**Edith:** I don’t understand.

**Paul:** I mean that LaunchDarkly is a good idea.

**Edith:** Oh, thanks Paul.

**Paul:** And I didn’t think of it. In fact, when I first heard of it, I thought, “This is stupid.”

**Edith:** Wait, did you really ?

**Paul:** Yeah. And I was like, Feature Flags as a Service? That doesn’t make sense.

**Edith:** Why did you think it was stupid?

**Paul:** Because it’s a small library, right? I mean, it’s not.

**Edith:** This is fascinating. Why did you think I was stupid?

**Paul:** I didn’t say you’re stupid.

**Edith:** Oh, no.

**Paul:** I thought, there’s no way you can possibly use that. We build that in 50 lines. I don’t understand how there’s a whole company behind this.

**Edith:** That’s a common evolution. We’re creating a category, and the first part of it is, “Why would you need that?”

**Paul:** Yeah.

**Edith:** “Okay, maybe I might need that. But if so, I would build it myself.”

**Paul:** Right.

**Edith:** “Okay, wait a second. Maybe I’ll buy this.” It’s funny because I’ve seen so many people go through that evolution in the past two years.

**Paul:** By the time that we built our fourth feature flag-ish thing in the code base, that was different to all the others for some specific reason.We’re like, “Maybe we should stop building these things ourselves.”

**Edith:** Yeah, that’s level four. Level zero is, “Why the hell would anybody ever need this?”

**Paul:** And so level five is where you buy LaunchDarkly?

**Edith:** Yeah

**Paul:** That’s where we are happy customers.

**Edith:** It’s really funny, though, because people go through these stages.

**Paul:** Oh yeah, I totally see it. It’s the same with CI, right? People are like, “Oh well, at first I can just run tests on my own machine.” And then some problems with that. “Oh I can setup Jenkins now.” Three days into setting up Jenkins, “All right, maybe I will, try this CircleCI thing.

**Edith:** I love it when people acknowledge that we exist. I think I told you, I went to this conference in Sydney, I cited feature flags. I was going to say a comma, say who it was, and they all just started talking about feature flags, why they were or weren’t a good idea. I loved it. Nobody knew who I was.

**Paul:** Perfect.

**Edith:** I feature flagged myself.

P- Right.

**Edith:** This is a long detour.

**Paul:** We were at managers?

**Edith:** We were at whether or not Paul is a good coder.

**Paul:** Oh, okay. Let’s just go with “maybe.”

**Edith:** All right, so the original point was that people assume that everybody is like them. So as a founder of a company, of course you have to have some sort of vision. And you have to have some sort of way to build what you’re building. And then you think, “Everybody I hire will be just like me. It’s just another tittle, a product manager, and they’ll perform like a product manager.”

**Paul:** Yeah, exactly.

**Edith:** I get very annoyed at companies that require all product managers to have a CS degree. I think that’s extremely foolhardy and short-sided.

**Paul:** Someone explained to me the Google- versus the Facebook-school of product managers. And apparently at Google, and I haven’t worked at Google or Facebook, so correct me if I’m wrong…

**Edith:** And you’re a terrible coder.

**Paul:** Yeah, I probably wouldn’t even get in. The Google product managers have a CS background, and the Facebook product managers have a design background.

**Edith:** Okay, that explains a lot.

**Paul:** That’s actually all I have on this topic.

**Edith:** No, I think it explains a lot. I think you sell for what you know, and Google’s kind of legendary for its non-existent support, its complicated systems, and that’s why they’re really floundering with Google Cloud Engine.

**Paul:** I tried to build something on Google Cloud, it was an on app engine, and I thought it would be super simple to throw up a single-page app on it. No!

**Edith:** No.

**Paul:** So much.

**Edith:** Was it just over-engineered?

**Paul:** There were just so so many steps involved. And I was thinking, “Maybe I can avoid AWS, because AWS is so many steps involved. My idea of it is that Google Cloud platform is sort of like a second generation of AWS.

**Edith:** No, it’s not a second generation. It’s its own genetic offshoot. I read a lot of evolutionary psychology when I was on the plane.

**Paul:** Oh nice. Did you read, “[Why Beautiful People Have More Daughters](https://www.amazon.com/Beautiful-People-Have-More-Daughters/dp/0399534539)”?

**Edith:** I have that book, but it’s been a long time since I read it.

**Paul:** I love that book. As I understand it, the entire field of evolutionary psychology is questionable. But it’s one of those books where it’s kind of like “Freakonomics,” that maybe each individual chapter is questionable in some way, but the overall idea in Freakonomics’ case, the idea of incentives, and in evolutionary psychology the idea that maybe we do things because 10,000 years ago we did things. I think they’re great.

**Edith:**I think there’s this idea that everything as a straight forward evolution it’s better than the thing before it. Sometimes they’re not, sometimes they’re just sideshoots.

**Paul:** So, you think Google Cloud platform is a sideshoot of AWS?

**Edith:** It could still evolve to be better, but everything I’ve heard right now is that everybody’s consolidating on AWS.

**Paul:** Funny thing about AWS services…

**Edith:** That everybody loves to hate on them?

**Paul:** Yeah so, my sense is that there’s two classes of AWS services. There’s the things that they built themselves, which are usually great. And there’s the things where they copied other people, which are usually crap.


<blockquote>I think that when you see AWS copying your startup, generally that’s very little to worry about.</blockquote>


**Edith:** Well, except they have the might of AWS.

**Paul:** Sure, they’ll make more money from the AWS version of it than you’ll ever make. Because they have that. But you’ll still have a better product that you’re able to carve out a very successful, large business out of. But I think if you’re building something that AWS built themselves, you don’t really see people…

**Edith:** I see your point.

**Paul:** AWS built EC2. They’re excellent at building EC2. But then they built code pipelines, and… not so much.

**Paul:** [Martin](https://twitter.com/martin_casado) came and made [a podcast](https://blog.launchdarkly.com/to-be-continuous-the-process-of-category-creation/) with us a couple weeks ago, and this kind of goes contrary to dogfooding. What you’re basically saying is Amazon is really good at building stuff of something they built from themselves. But they’re bad at being product managers for stuff that they’re not building in-house.

**Paul:** Yeah, roughly. So the dogfooding, I get it. And what? You take someone else’s dog food?

**Edith:** Well, basically acting like a product manager for external customers.

**Paul:** Yes, that seems very right to me.

**Edith:** Yeah, where as, I think Facebook has been so good because they focus on a single product.

**Paul:** It’s really easy to do if you’re Facebook. Also, Facebook has thousands of products. It’s just depending where you draw your lines.

**Edith:** Yeah. I’ve talked to a pretty sizeable company that are 40 people. They don’t have a product manager. I was kind of amazed.

**Paul:** It’s not that it’s impossible to build a successful company without any of these things, it’s just that you’re making it much much harder on yourself.

**Edith:** What my question then is, you have people acting as product managers. Probably your SCs, your CTOs, or somebody’s acting as a product manager. And it’s sucking up a lot of their time. It’s just you’re not giving them their title, and it’s not getting first-level support.

**Paul:** Yeah, and they’re probably not particularly good at it.

**Edith:** When I talked to them, it turned out that one of their SCs was basically acting as a product manager but with a very limited view of the world.

**Paul:**


<blockquote>The thing that the product manager does, or one of the things that you start to need to do at the second stage of scaling, is you start to need to prioritize.</blockquote>


**Edith:** Yeah, before I was a product manager I thought my biggest issue would be coming up with the things to do. I really thought this. So I was like “How am I going to still get ideas?” Once you’re product manager, there is no shortage of ideas. Everybody has ideas.

**Paul:** I guess it’s a saying that’s organic at five people, what it is you’re going to build. Because someone has a really strong vision, and it doesn’t really need to be that informed by customers, perhaps. Or there doesn’t necessarily need the feedback, the emails coming in from existing customers, or there’s conversations as you’re on your way to product-market fit.

It’s kind of obvious what prioritization is. I think Paul Graham said you don’t need a bug tracker, because the things that are most obvious are the things that you need to fix. And you don’t need to write anything, then. And that holds to three, four people.

**Edith:** It should be very obvious. Let me give a slight shade.


<blockquote>The micro things are very obvious to people. The macro things sometimes can be much harder.</blockquote>


**Paul:** I look at it a slightly different way. I look at it like: the things that you do yourself, the things that you’re dogfooding are obvious, and the other use cases, other parts of the products, things that you know yourself, your support forums might get neglected.

Stuff that you don’t need yourself need explicit support at the second level of staging. And in particular, if there’s a thing that you’re slightly talented at, where you’re doing well with it, that a thing that you especially need to get head from under you.

For example, let’s say that you’re particularly good at writing blog posts that drive traffic. When you start to scale your company, you need to hire someone whose explicit job that is. Because you will stop doing it and you won’t really get a focus on it.Because you’re kind of good enough at it, and you think it kind of comes naturally.

You can say the same thing with support, you can say the same thing with really any part of marketing. You can say the same thing with product design, you can say the same thing with product vision. If you’re vaguely kind of good at it, then that needs to become its own area of responsibility with someone responsible for it as soon as possible, or else you’ll flounder at the next stage.

**Edith:** Yeah, definitely. We went through those transitions. I think the thing that struck home close to me is that there’s only so much time. But community is something interesting. You had some opinions about community and the culture at a company, how the culture of one company might mot work for another culture.

**Paul:** What I was saying before, about, “You have to set your mission and your vision” and that sort of thing. Really, what those are are elements of company culture. You have to know what it is that you’re building as a company. And you want all the people who are on board for that ride to be compatible with that culture.

There’s a great chart that [Rand Fishkin](https://moz.com/about/team/randfish) made, that’s the CEO of Moz.com, or former founder of Moz. And what he said is it’s, “Who do you fire?” You’ve got someone who’s maybe not so great at their job, or someone that’s maybe not so great at their culture. Or, on the other axis, they’re good at it. So you got four stages, good at their job, good at their culture. And he said that people who aren’t necessarily doing great at their job, but they’re great in the culture, you keep them. And people who are doing badly in their culture, but doing great at their job, you let them go.

**Edith:** I agree, except for I think that’s where a lot of concerns about Silicon Valley and diversity come from. Because culture can be such a catch-all for, “Do you like to go play basketball at lunch?” And I’d say some people are just not suited for that.

**Paul:** We were talking a little bit about how you have to have product managers or you have to have prioritization, and that you have to have explicit human interaction and that sort of thing.

**Edith:** I think you need to have ruthless prioritization. And I think you have to have prioritization not just in what you’re going to do but in how well you’re going to do anything.

**Paul:** What do you mean by that?

**Edith:** You could spend a long time on one feature.

**Paul:** Oh yeah.

**Edith:** And it’s really painful, particularly at your, at any, size.

**Paul:** It depends on how important that feature is.

**Edith:** It’s really hard. People hate hearing that this is a check-box feature, but sometimes they are. Sometimes we’re just doing this for competitive pressure.

**Paul:** I think the one that every SaaS company learns is they need invoice emails and they need to have a PDF attached. No one cares about this feature except the accountants of the people who pay you. And we got this feature request so many times before we built it, and it’s just so unimportant as far as the product goes, but its essential in terms of what our customers need.

**Edith:** We built it just because every month, people would email us, “Where is our invoice?” and we would handmake them. It was mainly that we got to the point were it’s costing us a couple hours a month to handmake invoices.

**Paul:** And the irony is that, I think, Stripe has it built in there.

**Edith:** Yeah. Actually, CircleCI was one of the people who wanted invoices, I recall.

**Paul:** Oh really?

**Edith:** Yeah

**Paul:** Oh man, it’s good to come in full circle. That’s because we’ve scaled to the 50-people size now, and we need things that we didn’t need when we were five.

**Edith:** Full circle… Did you do want to go around the topic?

**Paul:** Oh my god.

**Edith:** Are we spiraling into…?

**Paul:** The direction that I was trying to go was talking about goal setting. There’s prioritization, but really you need a high-level thing that’s like, “What are the goals that we as a company are tying to achieve?” And then at a lower level, “What are good habits and processes that allow individuals and teams to get the most out of their time at work?”

**Edith:** Yeah, that’s a lovely way to put it.

**Paul:** You were saying earlier about how you think Paul’s a great coder or whatever.

**Edith:** I’m surprised, I feel like you’re fishing at this point.

**Paul:** I remember reading about the habits of Richard Stallman and also John Carmack. Richard Stallman famously sat down in a room for 30 days and produced GCC, all right. And I feel I don’t have the process or the habits to sit down in a room and produce a compiler in 30 days.

**Edith:** Do you think that’s because of what a compiler is?

**Paul:** No. I think it’s all to do with my habits and, for example, I’ve been coding some stuff recently, by myself. And I think I’m terrible when I don’t have, let’s call it an accountability buddy. But some people can sit in a room for 30 days and produce a compiler. I’d sit in a room for 30 days and I’d read a lot of Hacker News.

**Edith:** Do you think that’s why Hacker News exists?

**Paul:** Because people were procrastinating?

**Edith:** Yeah.

**Paul:** Oh man, I read this amazing interview.

**Edith:** Do people procrastinate because of Hacker News? Or does Hacker News exist because of procrastinators?

**Paul:** I’m sure PG was procrastinating too.So, there’s this panel where George R. R. Martin and Stephen King were both talking.

**Edith:** Oh, those are the two opposites of the spectrum. Stephen King has so many books, that he made a pseudonym because he didn’t want to put out five Stephen King books a year. Literally, he’s like, “I have too much product.”

**Paul:** They were talking and Stephen King said something like, “Oh, you know, 30 days, I can produce a new book,” or whatever. And George R. R. Martin was like, “But what happens when you get stuck, and like then you go check your email?” I was like, George R. R. Martin has a classic procrastinator problem, and that’s why he’s going to die without finishing that series.

**Edith:** Yeah I know. The TV show’s going to wrap up

**Paul:** We’ll know the ending before even “Winds of Winter” comes out. That’s the second-last book, not even the last one.

**Edith:** I have a soft spot for Stephen King. I know he’s considered kind of low-brow, but his books are good.

**Paul:** I really enjoyed one Stephen King book, which I think wasn’t labeled Stephen King.

**Edith:** The Richard Bachman ones?

**Paul:** I don’t think it was. Did he have another pseudonym?

**Edith:** He might have had another, but he wrote “The Running Man” and “The Long Walk.”

**Paul:** Yeah, no. It wasn’t one of them.

**Edith:** The long walk is basically a race where you had to walk, I think it was a mile every 20 minutes. So 300 people did it, started. If you didn’t do a mile every 20 minutes, they shot you.

**Paul:** Oh, it’s like Takeshi’s Castle.

**Edith:** So it was basically like an ultramarathon but with the ultimate price.

**Paul:** Wow.

**Edith:** I think Stephen King is the living proof that you can write high-quality books in high quantity, and that’s what drives other writers nuts.

**Paul:** Taking that analogy back to software, the difference between a high-performing team and a not-high-performing team, is often not the skill of the people, of let’s say the coders on the team, but largely down to process. And that’s individual process and team process.

If you put hurdles in the way of people, and we find that we’re back in continuous delivery, then stuff is going to get delivered a lot slower. And if you try to remove all sorts of hurdles and nuts, things like product direction, if everyone agrees on the direction of the product, then 90% of you’ll maybe double your productivity.

If you have agreed goals and whether you’re using a framework like OKRs or list out, “Here is what we want to do this month,” you’ll get there a lot lot faster. And this is why people like agile, they like scrum, because they are processes that work.

I think a lot of the people who criticise that agile or criticise scrum, maybe they don’t feel the same problem that a lot of people have. Maybe they have really good processes themselves, or they are able to ship things without necessarily having a unifying team process.

**Edith:** I think people who, we’ve had this fight before because I defended waterfall. I think sometimes people think of agile as giving up too much control. They like to have everything documented and cross their T’s before people march off to go write them

**Paul:** Documenting them and crossing off the T’s is a perfect example of something that sits in the way of producing.

**Edith:** I learned this very early, because that was my first job. One of my first jobs was writing docs. I was writing specifications, and I’m like, “You don’t ship a specification.” It could be the most beautiful specification in the world, but it doesn’t matter.

**Paul:** I once went for a government contract where the thing was to produce a specification. But the specification was in such depth, that someone that’d actually written this software and then turned it into a specification, and then they were also bidding for it. So they were just going to produce the software that they had already written.

**Edith:** That’s so meta.

**Paul:** Oh yeah, it’s mental. I went to that meeting. I was like, “Nope, never, never doing any government procuring ever again.”

**Edith:** Was this in Ireland?

**Paul:** Yeah, it seems like it’s gone the same everywhere.

**Edith:** I do think documentation at the rate level is good, so you don’t have the same arguments or discussions over and over again like, “Why did we build it this way?”

**Paul:** There’s a technique that I came up with with Alan, my co-founder, for how to solve these discussions. I tend to find that most of those arguments are implementation-level details. So you argue, “I want to write it this way, or it needs to be written this way because of this code.”

We came up with a solution for this, and it’s basically that. I’m sure many people have come up with this solution. I’m not saying I invented this, but here’s one that we did. Basically, all discussions have three levels. There’s implementation level, there’s the solution level, and then there’s the top level which you could call the problem or the goal level. Whenever you’re arguing at the lower level, go back up to the problem level and make sure that you’re solving the same problem.


<blockquote>When you agree on the problem, it’s typically very easy to agree on a solution. And when you agree on the solution, it’s typically very easy to agree on implementation.</blockquote>


**Edith:** Yeah, I wholeheartedly agree. I think a good product manager, and it goes back to why I don’t think they need a CS degree, a good product manager is very good at that top level.

**Paul:** Exactly, and in fact, when discussing that “a product manager is going to take away my autonomy,” really what the product manager should be doing is agreeing with everyone, customers, engineers, on what the top-level stuff is. Maybe agreeing with the engineers on what the solution is and bringing that back to customers to check. And then leaving the implementation stuff entirely to the engineers.

**Edith:** Where I’ve seen product managers get into trouble is where they start to make, for example, an API design, a database design. I was just like, “Why, what?”

**Paul:** Not sure I agree on API design. An API design is an externally consumable.

**Edith:** No, for internal APIs.

**Paul:** Oh, like, “This is how the code should be organized.”

**Edith:** Yes

**Paul:** Oh yeah.

**Edith:** They were designing architecture, and I was just like, “What?”

**Paul:** I’ve ended up in this trap several times, where I consider a ton of problems, and then it naturally forms the solution in my head. All the way to enter the code.And then I’m trying to describe, “Oh, we should do this implementation stuff,” and people are like, “We’re not even on the same page!”

**Edith:** We’re not even in the same book! And we’re not even in the same shelf, and we’re not even in the same library.

**Paul:** This would argue that engineers might be worse product managers than non-engineers because they have the ability to know how they would implement it themselves. And whereas, if someone doesn’t actually know how to write code and is a product manager, then they’re like, “Well, here’s kind of what we need to have done.”

**Edith:** This is a perennial debate I’ve had many times. I’m on this side. You are the opposite, is that, “Oh, the product manager should understand the codes so they know what is and isn’t possible.” And I say the reverse.

**Paul:** Oh really?

**Edith:** If you know what the code can and can’t do, you’ll start to have Stockholm syndrome.

**Paul:** True.

**Edith:** And you don’t even put forward what customers really want, because you’re like “Oh, the code can’t do that, so I’m not even going to make that.”

**Paul:** There’s also the, “You know, it would be really cheap to do it like this.” Often the prioritization that a product manager does is effort versus reward, if they have a good feeling about what effort is. And sometimes you can know what effort is.

**Edith:** I’d say that biggest lesson I’ve learned is: don’t assume and go ask an engineer inexplicably. Sometimes stuff I think is very expensive is cheap, and sometimes stuff I think is cheap is expensive.

**Paul:** But when you know the actual code base you have some idea of, “Actually, we can do this super cheap.” Usually, if you discuss that with an engineer, they’ll come back to you with, “Oh yeah, we can do it this way.” I guess what I’m saying is dialog with engineers, rather then telling people what to do.

**Edith:** You’re the voice of the customer.

**Paul:** There’s an idea that everyone can be the voice of the customer. And in the similar idea, everyone should be marketing. Everyone should be whatever the thing is, and whenever that happens, no one’s doing it.

**Edith:** Everyone should be sales.

**Paul:** Well, when that happens no one is.

**Edith:** Tell me more, because I agree with you violently.

**Paul:** We did a thing where everyone does support. All right, so every week, a different person did support. And this is was when we were up to about nine people, I think we did this. It was really a terrible idea.

I mean, it was a wonderful idea in many ways, but it was also a really bad idea. Because no one was specializing on it. We kind of took the knowledge that we built up and discarded it, almost. So whatever you learned in that week, at the end of the week you were burnt out and not ready to solve it.

The idea was that you got to empathize with the customer. You really hear about something that’s important, and then you get to prioritize it.And so what we had essentially was people filtered through, talking to customers on support, and everyone made their own prioritization function. And sometimes people fix things. But usually they were so burnt out by support that they were dying to get back into whatever they had been working on before.

**Edith:** Are you saying that they would do nothing but support for that week ?

**Paul:** Nothing but support for that week. If they had time, they would try to do more than support. If they had time, they would try to also knock out a feature that solves some of the support.

If I had to do that again, I’d say that you should have two people, one actually on support. We also tried that, but I think if we had had a dedicated support function early, that being sort of a voice to filter in, to educate the rest of the team as to what problems people were facing and how to prioritize them to lower support, and that sort of thing.

Once we actually switched to that model, which is much closer to what we do now, things got a lot easier. Our support descended dramatically because there was actually someone whose job it is now to write docs to answer the most important customer support thing and so on.

**Edith:** I think this goes back to something we talked about before, about specialization.

**Paul:** Yeah, I mean last week’s conversation is very relevant to this week’s one.

**Edith:** At TripIt we had a monthly meeting where our support manager collated the top 10 sources of tickets, and some were just stuff that we weren’t going to ever change. For example, we were never going to add a Blackberry app. But we knew what the other tickets were and we could start knocking stuff out.

Whereas, I think, if you didn’t have somebody that had a consolidated product view, that would’ve said “Hey everybody’s complaining we have this very vocal minority that wants Blackberry. Let’s march off and do it.”Not seeing the bigger market picture that Blackberry is and was kind of dwindling, and that wasn’t a good use of time.

We just launched a Bitbucket support at CircleCI, which has been, since the dawn of time, the number-one requested feature in our support, specifically by non-customers. Because, by definition, if you use Bitbucket, you tend to use Bitbucket or Github, as opposed to both. And we were Github only.

I argue that we chose the right time, or at least close to the right time, to offer Bitbucket support. Maybe we’re a year off in either direction, but if we had launched at the start, with both Bitbucket and Github, I think it would’ve been very hard to specialize. We’d be doing twice the amount of work.


<blockquote>It’s hard to go broad early, and limiting your platforms, in particular, is a very useful way of keeping your velocity up.</blockquote>


**Edith:** I think that’s what a good product manager does. I think that goes back to priority. I think the other sin you can do, if you’re too driven by you own product and your current customers, is you don’t see the bigger world around you.

**Paul:** Right, another problem with dogfooding.

**Edith:** Yeah, I think that’s this thing I did when I went from being an engineer to product. I thought it would be extremely easy. I would just do all this stuff I already saw that was a problem with our system. Once I became a product manager, I realized that there was this vast universe out there of things that I had just not encountered before. Competitor pressure, deals we weren’t closing.

**Paul:** Related to that, I think is technical debt. It’s very easy to become myopically focused on. Reducing technical debt, or something like that. But really the skill to a successful product or a successful organization or successful startup is the right amount of tolerance for fucking up all these things. So you have to put the right amount of focus into everything and not too much.

If you get your sales process perfectly, than maybe it’s time that you should’ve put into something else. Or if your support stuff is perfect or your docs are perfect, you’ll want to have the right amount of debt in all the things. I think being a successful team, organization, startup, product, whatever, is balancing those well.

**Edith:** The classic Reid Hoffman quote is, “If you’re not completely embarrassed by your first iteration, you waited too long to ship.”

**Paul:** Exactly, yeah. And if you watch “Silicon Valley,” they actually use that quote in a recent episode.

**Edith:** They do?

**Paul:** They do, yeah.

**Edith:** Wow.

**Paul:** I mean, yeah, it’s startup culture perfectly.

**Edith:** I wish I wasn’t so busy doing my own startup that I could watch TV again.

**Paul:** I’m sure you can find time. Get rid of one ultramarathon and watch the entire thing start to finish.

**Edith:** Just instead of running for 50 miles, watch a “Silicon Valley”?

**Paul:** Watch an entire season.

**Edith:** I’ve heard it’s really accurate, which I think is why I can’t watch it.

**Paul:** Oh, it’s scary. Like I know everyone involved. Or you know a person caricatured by a character.

**Edith:** Is there an Edith in it?

**Paul:** I’m almost sure there is. I can’t think of it off the top of my head.

**Edith:** That would be scary. Is there a Paul in it?

**Paul:** Richard Hendricks is the star. I think that him going into the Peter Thiel guy at the start, I was there. And when that happened, I was like, “Oh god.”

**Edith:** What happened?

**Paul:** Oh no, it was just that I have been in that situation, the extreme naivety trying to raise money with nothing and no knowledge of what you’re doing, and then having someone tell you, “What the fuck are you doing?”

**Edith:** Oh wow.

**Paul:** I feel like half the people in the San Francisco area have been in that chair.

**Edith:** I’m sure I’ve been in that chair.

**Paul:** Yeah.

**Edith:** I don’t know if I could watch it.

**Paul:** Parts of it are definitely awful.

**Edith:** Because it’s so true?

**Paul:** Yeah.

**Edith:** And then, I think, sometimes that half the stuff that really happens, people wouldn’t believe you.

**Paul:** I think they’ve had to cut stuff out of the show because it was too unrealistic. Or the stuff that actually happened out of the show, because it was too unrealistic.

**Edith:** Silicon Valley is a weird place.

**Paul:** It’s made up of unrealistic people doing unrealistic things

**Edith:** I think


<blockquote>you have to be a naive dreamer to think that you can create something new from nothing.</blockquote>


**Paul:** And then you need to be some sort of steady general to go from, “We’ve created something out of nothing” to scaling it to the next level.

**Edith:** That’s why I think ultramarathons are good training. You have to be a naive dreamer to think that a human can run 100 miles And then you have to be a steady plodder to put in all the work to make it happen

**Paul:** A very nice analogy. What happens when you get to the end of the 100 miles?

**Edith:** Get a nice steak dinner

**Paul:** Is that an IPO? Is that the exit?

**Edith:** No, a nice steak dinner. They give you a belt buckle.

**Paul:** Okay, and the steak?

**Edith:** And the steak and you take a couple months off and then you start thinking about your next ultramarathon.

**Paul:** Oh really? You can’t run again for several months?

**Edith:** It depends who you are. Some people run right away.

**Paul:** Jesus. Anything else in this scaling world? We didn’t talk about VPs. I want to talk a little bit about VPs. I didn’t really believe in VPs, then I met some VPs. I was like, “Oh, that’s what you guys do.”

**Edith:** Sometimes we should make a consolidated list of things Paul did not believe in.

**Paul:** Oh, so many things. I mean, I’m the kind of person who learns best from experience, and it kind of means that I have to fuck up things to get there.

**Edith:** Learn best from experience is kind of a nice way of saying…

**Paul:** I won’t listen to people until I actually fuck it up?

**Edith:** Yeah. People can give Paul advice. Will Paul take the advice?

**Paul:** And then when I fuck it up, I’m like “Oh, this is like that thing Oren was talking about.” I mention Oren because he’s specifically someone who’s given me tons of really valuable advice that I didn’t really get until after it was applicable.

**Edith:** I think that’s not admirable, but I think I know for a fact that Paul gives a lot back to the startup community and gives a ton of advice to many different people.

**Paul:** Did you say Paul?

**Edith:** Yeah.

**Paul:** Me?

**Edith:** Yeah, Paul.

**Paul:** Yeah, okay. I do?

**Edith:** Yes!

**Paul:** Okay, great, yeah.

**Edith:** You spend hours at conferences giving advice to people.

**Paul:** It’s the same advice that I give repeatedly.

**Edith:** But to different people.

**Paul:** A tape recording of Paul could say, “Validate.” If you replaced me with a tape recording saying “Validate,” just on a loop for 15 minutes, it might actually have the same effect.

**Edith:** Would this be PB as a Service?

**Paul:** Literally, between Collision and Web Summit, I think I might have talked to 30-35 different startups in 15-minute increments, and I’d say 90% of them I told, “Validate.”

**Edith:** I told people to focus

**Paul:** Oh really, okay.

**Edith:** You’re already “validate.”

**Paul:** Like, “What are you doing at a conference? You should be focusing on your project”?

**Edith:** It was a photo company, and they’re trying to start in 30 cities. I was like, “Take only one.”

**Paul:** Oh, I mean “validate” is the same thing.

**Edith:** You mean validate, focus by validating, or validate by focusing?

**Paul:**The only other thing I’ve said is, “Maybe don’t outsource,” or “You need a technical co-founder.”

**Edith:** The thing about outsource, I was thinking more about what you said. Because it’s funny, I had an entire job just being an Outsource.com person.

**Paul:** Did we talk about outsourcing on the podcast or before the podcast?

**Edith:** In the previous podcast we briefly said, “Don’t outsource your startup.”

**Paul:** Oh yeah, okay.

**Edith:** So, I was a dot com consultant. This is the punchline now. I really remember like there were these Stanford MBAs, and they had an idea. They hired the company I worked for to build it. That was my job.

**Paul:** Oh wow.

**Edith:** The whole idea of iteration or that there might need to be something after we built it? Nope.

**Paul:** Oh god, yeah. “Here’s an idea, let’s knock it out.”

**Edith:** It was like a two-month project to build the idea.

**Paul:** It hurts.

**Edith:** It hurts that people lived through all this pain?

**Paul:** I can’t imagine.I presume they failed.

**Edith:** Oh, everybody failed.

**Paul:** Right. I guess it’s kind of unfortunate that the lessons that they probably took from that was that like, “There were structural problems,” rather than their own unique, individual non-validation problems.

**Edith:** I think that was just the way everybody thought about the world back then.

**Paul:** Right. I mean, people still think about the world now like the phrase, “I have an idea for a startup.”

**Edith:** There’s so much execution that goes into every startup.

**Paul:** It almost doesn’t matter what idea you have.

**Edith:** I think it matters that you care deeply about your idea, because there’s so much pain and effort that, if you don’t care, you’ll give up.

**Paul:** I meet people who think, “I want to build a startup but I don’t have an idea, so I can’t.” And it’s like, just talk to people.You’ll get ideas. Sometimes I’ll take out my list of 50 ideas, and like I’ll go through them and see, “Any of these seem interesting”?

**Edith:** Have you had any takers yet?

**Paul:** One or two, but then they decided not to, for various reasons.

**Edith:** I started this by saying that you have given back so much to this startup community by helping people with your advice. So then you said people had given you advice that you had to learn the hard way.

**Paul:** I wonder, if the people I give advice to, whether they actually listen or not.

**Edith:** It’s hard because when you do a startup, you get so much advice. Everybody gives you advice. You have to listen and filter out what’s actually applicable.

**Paul:** Right.

**Edith:** What’s applicable for a consumer mobile app is utterly, sometimes, not applicable to a company like yours or mine.

**Paul:** Right. Though, the lessons are often very good. But you just have to pick the right lessons from them, and it’s just hard to know what they are. The lesson from the Facebook growth team, or Facebook’s growth, is the quantity of experiments that you do, or the frequency…

**Edith:** The velocity.

**Paul:** The velocity, yes, perfect, of experimentation is your growth rate. There’s a lot of different things that you could pick out of it. You could pick specific implementation or things that maybe only apply to 10 million people or only apply to consumer apps, or that sort of thing. But I think there’s good, concrete stuff in that.

**Edith:** I think sometimes people take the wrong lesson. Like, “Hey, you email all your friends to get them to join your site,” which is totally not appropriate for different companies.

**Paul:** Yeah, the blog post that I’ve intended to write many times is entitled “That Advice Is Not For You,” There’s a list of startup ideas and there’s a list of blog posts. Things I will never do but like to fantasize that I might do someday.

**Edith:** Sounds like a good list.

**Paul:** Yeah, but in the blog post, one of the blog post is titled “That Advice Is Not For You,” and it’s basically, if you look at let’s say the First Round Capital site, they have all this amazing advice from teams that are killing it like Stripe and Slack, and all that sort of thing. None of that advice applies to you.


<blockquote>It is impossible to separate the advice from the context in which it happened.</blockquote>


You can take Stripe’s advice on something, but Stripe was a runaway success. Slack was a runaway and overnight success. And not the kind of overnight success that took five years to get there. Actual overnight success. If you take the advice and you’re not an overnight success, it’s probably not going to apply.

If you’re an amazingly successful company, you can make all kinds of fuck-ups. You can reinvent multiple, different ways at doing things. And if you’re not, if you’re going to be a nice $10- or $100-million-dollar company and not like a decacorn, or whatever those things are, the advice probably doesn’t apply to you. And you probably shouldn’t take it.

**Edith:** I completely agree

**Paul:** Yay.Is this like 25 episodes where we’ve never disagreed on anything?

**Edith:** We’ve disagreed on many things.

**Paul:** Have we?

**Edith:** Oh, there was the time we talked about waterfall vs agile, and you made me edit it out later.

**Paul:** That might be the only thing we disagreed on in 25 episodes.

**Edith:** Let’s see, what else have we disagreed on?

**Paul:** This can be a challenge.

**Edith:** There’s other things, though. That was a particularly violent disagreement.

**Paul:** Yeah, the only definitely violent disagreement. I’m glad we agreed to take it out.

**Edith:** You never listened to that episode, huh?

**Paul:** No, did it go in? No, I don’t listen to the episodes. I can’t, it hurts. All right, the only remaining thing I want to say is…

**Edith:** We never actually talked about VPs.

**Paul:** Oh, we never did. Okay, VPs are great because they know what to do.

**Edith:** Okay.

**Paul:** Done.

**Edith:** Well, I would disagree.

**Paul:** Okay.

**Edith:** I think VPs can’t know the precisely right thing to do for a business that is not your own.

**Paul:** Okay, fair. They are the people who have read all the First Round Capital posts?

**Edith:** Or you might be very impressed by a VP and then realize later that their business they came over from was not your own.

**Paul:** Right.

**Edith:** Example: not a VP, but oh god, I worked at this company where we were an enterprise software company and we hired, as our new CEO, and I say we, the board, hired a guy who, honestly, he’d run a sporting goods company.

**Paul:** Not the same thing.

**Edith:** One of his first decisions was, he’s like, “Why do we have all this money for engineering? Let’s outsource everything to India.” Because that’s where you’re extremely successful if you’re making sporting goods, which is a very commoditized, goods thing. And I was like, “Yes, labor is much cheaper in India than here. Why not outsource making footballs there, or whatever?”

**Paul:** Right.

**Edith:** Basically killed our company.

**Paul:** So, software isn’t like footballs, is what you’re saying.

**Edith:** In terms of being able to turn around in six months and build software quickly, outsources, insource, I think there are some companies that are very successful at that.

**Paul:** Successful at outsourcing?

**Edith:** Yeah. But you have to be at a certain stage and have a certain discipline.

**Paul:** Right, and you probably don’t want to be creating a brand new thing. Creating the third of a thing might work, just copy the thing that’s there, and then you just need an army of engineers to do it.

**Edith:** I think you’re going to hire somebody who has a strategy that they’ve executed very well at other places, but the strategy might be completely wrong.

**Paul:** Right. Or there might be cultural reasons why that strategy worked, and your company is different.

**Edith:** You might be very good at direct marketing, and this might be more of a relationship sale or something. There’s many many reasons why they’re right or wrong, why a VP could be wrong.

**Paul:** I think


<blockquote>the problem that you get with VPs sometimes, it’s that they want to repeat the same playbook that they had before.</blockquote>


And maybe they aren’t experienced enough to see that their playbook doesn’t apply in that situation

**Edith:** There’s a company we both knew, where they just keep going through VPs.

**Paul:** VPs in sales?

**Edith:** VPs in marketing.

**Paul:** Oh, right.

**Edith:** And it’s like, “Okay, what’s going on over there?”

**Paul:** Interviewing VPs is particularly interesting. You look for people who kind of think the same way that you do but at the same time have the ability to tell you something new and bring in experience that you don’t know.

And necessarily, that those things that you don’t know, you can’t really evaluate whether they’re right or they’re wrong. You can only try it out, and you can take your best guess from the candidacy that you have in front of you and discover that you were totally, totally wrong.

**Edith:** It’s tough because you’re not hiring an individual contributor then

**Paul:** Right. You’re not well suited to evaluating their work This reminds me of, I think it was [Keith Rabois](https://twitter.com/rabois?lang=en). How do you say his name?

**Edith:** I think that’s close enough

**Paul:** It’s not the French way. I know it’s not like “Rebois” or which is what I thought.

**Edith:** I still remember the first time you tried to say my last name.

**Paul:** “Harbaugh.” So I hope it was him, after saying his name, that I was right. That a VP is another barrel in a gun. Individual contributors are bullets, and at certain point, more bullets is better. But at a certain point, you want to be able to fire with multiple barrels, and a VP is another barrel.

**Edith:** I think this goes back to something we’ve talked about before about why we need managers.

**Paul:** The final thing I want to say about scaling from the first level to the second level of your company is look at OKRs. If you haven’t looked at OKRs, and goal setting is massively valuable and I talked a little bit about that, but OKRs are awesome.


<blockquote>If you don’t use OKRs directly, look into what OKRs accomplish for you and find something that accomplishes the same thing.</blockquote>


**Edith:** That’s a good advice.

**Paul:** I guess that’s where we trail off anticlimactically

**Edith:** Yeah. Thanks for… I haven’t … I don’t know.


