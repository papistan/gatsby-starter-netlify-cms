---
author: andreaech
comments: false
date: 2017-08-15 14:30:03+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-the-risks-of-selling-user-data/
slug: to-be-continuous-the-risks-of-selling-user-data
title: 'To Be Continuous: The Risks of Selling User Data'
wordpress_id: 2051
categories:
- To Be Continuous
---

In the latest episode of To Be Continuous, Edith and Paul examine the recent backlash that Unroll.me faced over selling user data to other companies. Edith shares her experience as Product Manager at Tripit and discusses the risks of developing a service that requires accessing customer emails.

They also examine how privacy sensitivity varies among users and has evolved over time.

This is episode #36 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->

This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.







TRANSCRIPT







**Paul Biggar: **Okay, so Unroll Me.

**Edith Harbaugh:** That seems awful abrupt.

**Paul: **So, I personally love talking about controversies. Everyone else seems to shy away from drama and avoid talking about it, but I think they're fascinating.

**Edith: **Paul Drama Lover Biggar.

**Paul: **Yeah, that's true.

**Edith: **I actually thought your middle name was an F, so Paul Fracas?

**Paul: **That's a good one.

**Edith: **Paul Fracas-monger.

**Paul: **I'm terrible at this game.

**Edith: **What's the game?

**Paul: **It's like your pun game, I just can't do anything with them.

**Edith: **Alright, I'll let you talk.

**Paul: **Okay, so Unroll Me happened.


<blockquote>There's a company called Unroll Me that's owned by a company called Slice,which sells to a company called Uber. And the thing that they sell is your personal data! </blockquote>


**Edith: **And the whole thing is fascinating to me because I have a firsthand experience with a lot of the same decisions. So I was product at TripIt.

**Paul: **Really? Long-time visitors of the show will find that incredibly new news that they've not heard before.

**Edith: **Now I think you're teasing me with just raw sarcasm. So at my first project when I joined TripIt, the way it worked was you would forward an email to TripIt and we would parse it and extract useful information so that you could get a nice itinerary. And this in and of itself is kind of fascinating because basically we're reverse-engineering a database. So there's been all this work to take information about your flight or your hotel, form it into a beautifully formatted or ugly marketing email that will get sent to you.

Which then we decompose back to the database field. And, a constant kind of thing we got was one, people who just did not like TripIt because they didn't like sharing private data. And then two, people who want us to actually look at their inbox and not have to forward emails.

**Paul: **So, even when people have to explicitly forward, they were already complaining about privacy.

**Edith: **The people who were really unhappy just wouldn't do it.

**Paul: **Right, okay. What was in the email? Is there credit card info, or their address, what's the private info?

**Edith: **Everything. Whatever email you forward us, we got. For example, I'm going to Collision, so I just got an email confirmation of my hotel and I forward that. And that would actually have a lot of personal information.

**Paul: **Gotcha. And after you'd processed it, did you delete the email, what happened? How did you take care of that privacy concern?

**Edith: **So, my understanding is the way it was five or six years ago.

**Paul: **Sure, sure, of course.

**Edith: **So I'll state up front that I don't have firsthand knowledge of how it's done now.

**Paul: **Yeah, of course.

**Edith: **I know that back then, we would keep the emails, I think for two weeks.

**Paul: **So, for book checking and that sort of thing?

**Edith: **Yeah, so it was a constant moving target, so the way it worked under the hood was that we basically had all these regexes. An email would come in and you would match it with a regex.


<blockquote>The regex is basically pattern matching this email versus a template. </blockquote>


**Paul: **Right.

**Edith: **It was a constant battle because what was happening on the other side is that the suppliers, the airlines, hotels, were also changing their email formats.

**Paul: **Not to combat you, just like, that was a normal thing, that you change your product sometimes.

**Edith: **Sometimes we weren't sure.

**Paul: **Oh really?

**Edith: **Yeah, sometimes we weren't sure but sometimes it was just like, Southwest decides to have a holiday message as a top banner and suddenly that throws everything off.

**Paul: **Right, okay. So someone forwards something and then, it fails to parse fully and then there's a human involved in reading it.

**Edith: **So we had different levels. We had what we call a partial parse, where we would get some of the information but not all of it. And then we would start to flag that, and then start to cycle through. We would do what we called a rerun or a reparse, where we're trying to pick up information. This is actually when I really got into continuous delivery and microservices, though we didn't call it that back then. Because basically what we had to do was we had to decouple releases.

**Paul: **Right, as soon as something came in. It's funny, we had a couple of things like this at CircleCI where due to the changing circumstances around us, we had to make a very, very quick change. And it couldn't even wait for a fully deployment in our case. So for example, if you're using NPM or one of those providers, and something changed in the world at large, which it sometimes does, we might have to make a change to the image on which your tests are run.

And rebuilding an image was a two- to three-day process, and shipping it out was like a 36-hour process so there was no way to make the change. So we had a thing that ran called pseudo-hacks. So, a short script that we could enter into a database and at the start of every build, that ran that short script if there was one. We would find clever ways to hack around the edge cases where they're pulling down .SRT's or just changing adding a file at a particular place until we could get right into the next image.

**Edith: **Yeah. Eventually, by necessity, you had to decompose a monolith, like you had that, we had our web UI and our mobile apps that went at a very different speed that we called Itinerator which was picking apart itineraries. It was a constant battle because, as you said, vendors would change their emails all the time.

And I remember I was in a meeting once with the engineering manager and she's like, can't we ask them to tell us? And I was like, no, if you're an American Airlines marketing manager in Dallas, it's not on your list to go tell TripIt. And in fact, we were always at semi-warfare with the airlines.

**Paul: **What year was this?

**Edith: **Oh gosh, 2011?

**Paul: **2011, okay. So a couple of years later, this is 2013, 2014, Google added that schema.org thing, so you could add metadata to your emails, mostly for Gmail so that you could add a button at the end of the thing to click download or add to calendar or whatever the thing is you're supposed to do. I wonder if today that would be a way to include the data for processes like yourselves.

**Edith: **Yeah, we were really the only big person doing it. We had a couple me-too competitors, but nobody else was investing as much time. So, one, this is really how I got into continuous delivery and really saw in action how important it was to deconstruct different services. Two, the funny thing was, everybody thought we sold the data and we didn't.

**Paul: **So why did they think you sold the data?

**Edith: **Because people are paranoid. So I was the product person on this and I would field all the questions. I would work with support, we would get angry things like, "you're selling our data." And we're like, "no, we're not."

**Paul: **So, what made them think you were selling the data?

**Edith: **Paranoia!

**Paul:** Right.

**Edith: **So we would reassure them over and over that we weren't, and again, maybe TripIt does now, I don't know.

**Paul: **Did your terms of service say that you could sell the data?

**Edith: **I don't recall. I know that we did not. And one of the reasons we did not is that nobody was interested back then.

**Paul: **Right, so TripIt was free, right?

**Edith: **TripIt was free, we had various premium services on top of it.

**Paul: **Gotcha. So you made the money via the premium services. So do you think that if there was money in it, that you back in the day would have sold it if someone was buying?

**Edith: **I think, sufficiently anonymized, we would have. I mean I know that it was something we talked about in terms of like, "hey, if American wants to know how much pickup United is getting from the airport." But, the airlines just weren't interested. Nobody was interested back then.

**Paul: **Gotcha, that's very interesting. So let's continue this story, because you obviously then went to parsing the full inbox, or something along those lines.

**Edith: **Yeah, so the step one was that you forward us an email, the step two, as some people said, "I'm too lazy or I'm too busy. Why don't I give you access to my email? And you can find any relevant emails." So this was a really fun project that I worked on, because maybe it was just the technology was different back then, is people were very concerned that we basically copy their entire email. And we didn't do that because back then, storage was still horrendously expensive.

**Paul: **Here's another question. If you could have, would you have?

**Edith: **I don't think so.

**Paul: **Okay.

**Edith: **So what we would do is we would scan headers. So you know the way an email has a header with a sender so we were looking for certain senders. Like reservations.southwest.com. That's a good header. And we viewed everything else as an undesirable byproduct.

**Paul: **Because you have to store it, yeah.

**Edith: **Yeah, we were like, we don't want all those emails.

**Paul: **The other obvious thing is that it puts a big target over your head.


<blockquote>Having email access puts a big target over your head because someone could hack in and then use that to access further customers. </blockquote>


But if you're also a store on all the data and you don't encrypt it appropriately or there's a bug somewhere in your process, there's a big giant target in possible data breach over your head that could possible be an existential risk to your company.

**Edith: **Yeah, so we were very careful about this. So we had an OAuth, we never stored passwords. And we never stored full emails. What we were very careful is we would scan headers. And if something was a relevant header, then we would parse that email.

**Paul: **Yeah, and you didn't store the email.

**Edith: **We did not.

**Paul: **Gotcha. So you talked about that two-week window where you stored things from missed parses. That was still in place?

**Edith: **So that was emails that people sent to us, and that was basically so if we fixed the regex, we could call it a reprocess.

**Paul: **Oh, okay. Now that it's still being stored on Gmail servers, you don't need to do that, you just say, we failed to parse this email, link to it, and then you can come back to that later without storing it. So it's actually better, ignoring that you now have OAuth access and that's the security thing. But certainly in terms of what you're storing on your servers, you have a better security story for your users.

**Edith: **Yeah, so basically what we store, and again, the huge caveat. This is the way it was five years ago, and they could have rebuilt it several times. We would store, what's the last email that we scanned. So that you have a number in your inbox that this is email, there's actually a hidden secret number of like, you scanned up to 17,792. Because we didn't want to have to rescan all the emails every time. So we would want to scan only the new emails from the last time we looked.

**Paul: **Okay, what's the thing about 17,000?

**Edith:**


<blockquote>In your email inbox, there's a hidden number which is the ordinal count of email. Every periodic number of hours, we would go in and scan and see if there was new emails that we should pick up. </blockquote>


So we needed to know the last place we checked. So we basically have a count of, this is the last email we saw, check for a new email since then. Because Gmail lets you have unlimited storage. So we didn't want to go back and scan eight years of email every time we looked at it.

**Paul: **So, I'm lost as to the 17,000, the significance of that number.

**Edith: **Just that every email inbox basically has a number of the last email that we had looked at.

**Paul: **Oh okay. You you looked in some chunk size or something. In some chunk size.

**Edith: **We looked from the last time we looked.

**Paul: **Yeah, okay.

**Edith: **Even then in 2011, people had had Gmail for a long time and it encourages not to delete. So we didn't want to have to rescan every email.

**Paul: **When someone signed up, did you look back in history? Did people want that?

**Edith: **So I was the PM on this, so that was actually a lot of questions we had at the beginning where this was something very new. There was one company that did something similar which was Pudz Company. Gosh, they had something to do with purchasing. So they'd do referred seats, but we were for travel, so we had a lot of questions, like "how far do people want to go back? Is it relevant? Do people want to populate, is this going to kill our system if we start scanning millions of email inboxes." This is also how I first started really using feature flags to plan out a project.

**Paul: **Oh, interesting.

**Edith: **So at the beginning we just had people who were heavy travelers, and we would turn it on in production for about a batch of 10, and get feedback from them. And we were gradually turned on for more and more people.

**Paul: **And so on the back filling, did people like that?

**Edith: **It depended. Some people really like having a complete history of all their trips. Some people saw it as clutter. And there's just some stuff we couldn't get around, like Southwest emails, you can't pick up a year from.

**Paul: **Oh, okay, but there's the year in the mail headers.

**Edith: **For whatever reason, it didn't work out that way.

**Paul: **Oh, okay.

**Edith: **So, the Southwest ones would always turn up as the most recent year, which would confuse the heck out of people.

**Paul: **I guess you probably didn't have parsers that could go back to the dawn of time. Presumably you've gotten rid of old parsers from your code base.

**Edith: **Yes, that was another issue. So it was an interesting project. Like a lot of little stuff, once you start to dig into it, about how exactly it works. And then I remember once, Turkish Airlines sent out something which was like, enjoy your trip to Istanbul, that somehow got parsed, which was an advertisement "enjoy your winter vacation to Istanbul!"

**Paul: **So everyone suddenly has as trip to Istanbul on there.

**Edith: **It had just enough that our parser picked it up as a trip to Turkey and people totally freaked out. Because they're like, I'm not going to Turkey, did my account get hacked?

**Paul: **There's been some kind of credit card fraud.

**Edith: **Yeah, so people were really unhappy about that.

**Paul: **So I'm very interested in the idea of these people who were against it even when it was forwarding email.

**Edith: **Some people just were very anti-TripIt.

**Paul: **Okay, but why are you even talking to the anti-TripIt people?

**Edith: **We weren't. But they would post blog posts or angry tweets about like, this is an invasion of privacy. And our basic answer was like, we're pretty transparent. I remember writing a blog post about how we handle emails and it basically came down to like, if you don't want us to scan in your inbox, don't. You can forward us emails and we will only see those.

**Paul: **Well it's interesting because there's been a radical shift in people's belief in how privacy should be since we were both around when the internet was kind of getting kicked off. We were teenagers or adults in that period. And seeing, let's say, the Slashdot crowd, and how they would talk about privacy in the early 2000's.

**Edith: **Oh, yeah.

**Paul:**


<blockquote>Cookies were extremely controversial in the past. And these days, people are giving access to their full inbox, to their full contacts list, to their Twitter and Facebook and to tons of different companies. </blockquote>


So the Unroll Me thing is something that would have been insane a decade ago.

**Edith: **Oh gosh, I mean, I'm actually pretty happy that there was not Facebook when I was in college.

**Paul: **Oh, yeah, completely agree. That would have been a disaster.

**Edith: **There was Facebook but it was an actual, physical book. Like I don't know, did they have that in Ireland?

**Paul: **No, we didn't, actually. I mean, I think that would have been a giant violation of privacy. I remember I was in middle school in the U.S., and they sent out books with people's names and addresses and phone numbers for everyone in the school.

**Edith: **You mean like a phone directory, Paul?

**Paul: **I guess, yeah.

**Edith: **Pretty standard.

**Paul: **Well that's really interesting.


<blockquote>When we were young, there were phone books with our addresses, now we don't want anyone to have our address. </blockquote>


**Edith: **Well, I mean, that's because you're a shadow figure of the night.

**Paul: **Well, not even that, and I'm not even in any sort of danger but when you look at internet stalking and that sort of thing, if there was an equivalent of The League or a Tinder or something in the old days, you get someone's name, you figure out who they are.

**Edith: **You drive slowly by their house.

**Paul: **Right, because there's an address!

**Edith: **Duck when they're looking.

**Paul: **Right because there's an address in a book that is delivered to everyone's doors. It's like prime stalk material and this was a totally normal thing for decades.

**Edith: **Oh, yeah! I mean how else would you know how to call people?

**Paul: **Right, but there were addresses as well.

**Edith: **This was pretty standard, Paul.

**Paul: **I know, I'm just sort of thinking back. In modern times, we have, I think, a fairly pragmatic view of privacy. It's like, TripIt, I don't believe, cares about me personally, so TripIt can read my email. But, there's a direct threat, and I don't personally feel this way. But I know lots of people for whom this is a real issue. There is a direct threat to knowing someone's address.

**Edith: **Yeah!

**Paul: **And that was a thing that was totally fine 10 years ago but we we were freaking out over the idea that a company might be able to read emails that we forwarded to them explicitly.

**Edith: **Yeah, it is kind of the death of the phone book. I remember when I went to college, they gave us a physical lookbook with everybody's picture who'd submitted in their phone numbers, so you could call people. This is back when people had a phone in their dorm room. But now it seems a little bit of an invasion of privacy.

**Paul: **Yeah. I mean, even someone's phone number without asking, I get spam calls basically every day from people who've bought my phone number from somewhere.

**Edith: **Yeah, it's bad. So my cofounder John, he answers the phone all the time because he has two small kids. So he's like, I have to answer it even if it's unknown because it could be the school nurse, or like a neighbor. And so I've been with him when he answers and it's a truth universally known that if you're a startup, somebody wants to sell you recruiting services or some random thing.

**Paul: **Usually a SaaS product from another startup.

**Edith: **Yeah, whereas I have the luxury of, if I don't recognize the number, I usually don't answer.

**Paul: **Yeah, but what if it's customers?

**Edith: **We now have a number that does not ring to my line.

**Paul: **Nice.

**Edith: **Side note, when we started off, it did ring directly to me and I would answer. And I didn't want to admit I was the CEO because it made us sound too small-potatoes.

**Paul: **Yeah. So you were the secretary when you answered and then you transferred it to the CEO?

**Edith: **No, they'd just say can I talk to the sales person, and I'm like sure, and I'd help them. And then somebody Googled me later and they wrote me an email like, I didn't realize I was talking to a CEO.

**Paul: **Nice! Okay, so bring it round to Unroll Me. So Unroll Me is a service that unrolls you from mailing lists and spam and all that sort of shit that you presumably signed up for.

**Edith: **Play on un-enroll.

**Paul: **Right. And they were a company that were ran for a couple years, they didn't really have a business model. And so they decided to sell personal data in some anonymized form. That was allowed by their terms and conditions, so they have terms and conditions that say that they can sell anonymized data. And they've since sold to someone else, to Slice, whoever they are.

**Edith: **I know Slice well because we were the biggest OAuth user of Gmail. And Slice was probably the second.

**Paul: **What does Slice do?

**Edith:**


<blockquote>So what TripIt did was scan and look for travel and make you a nice trip itinerary. And what Slice was trying to do was scan and look for receipts. </blockquote>


Like any receipt from anything and then the idea that they could, for example, tell you if a price had dropped on something so you could get a refund.

**Paul: **Okay, so Slice is a company that reads your email and sells it as well.

**Edith: **They, I think, always thought of themselves as that way. Because I actually know some of the Slice people because we would chat. We saw ourselves as a travel productivity tool. So we always saw the trip users as our customers.

**Paul: **So when you're saying that they think of themselves that way, as in they know what their business model is? Or, they're very transparent to customers about the fact that they make money from selling their data.

**Edith: **I think they always were more transparent. So they would say, "hey, we're going to tell you when stuff is about to go out of warranty or tell you when you can't return it anymore or tell you when there's a price drop. And I think Slice was pretty transparent about the fact that thet are going to sell data.

**Paul: **One of the interesting things is that the blame is landed on Unroll Me and has not been landed on the parent company, which is the ones who were actually selling the Unroll Me data. I don't know if it's even a parent company. There was an acquisition, they own the product.

**Edith: **We were tweeting about this. I think it's because there's such a clash between what the Unroll Me users thought they were getting. So they were attracting a persona of, privacy-sensitive, I don't want unsolicited emails. Which is a certain class of people.

**Paul: **That's interesting, right. It's the more privacy-conscious people. But I feel like if you were really privacy-conscious, there's no way you'd hand over the contents of your email, essentially.

**Edith: **Yeah, and this is where I get into it. Let me go back. I was a really early Gmail user. Actually I got one of the first alpha invites.

**Paul: **Nice, nice.

**Edith: **Were you that early?

**Paul: **I was not that early, I was a couple of months after the launch.

**Edith: **I knew somebody who knew somebody so I got an alpha invite back when they were going for like $1,000.

**Paul: **Oh, wow!

**Edith: **Yeah.

**Paul: **This is before the April 1st launch date?

**Edith: **Oh, yeah.

**Paul: **No way.

**Edith: **It pays to be in Silicon Valley. But they give it to anybody now. And even then, I remember there was a bit of a kerfuffle that they could give you ads. And I remember my friend trying to spoof me. He would send me mud wrestling or something so I'd get mud wrestling ads. He was basically mail bombing me with salacious words so they would start to show up.

**Paul: **Well, harking back to earlier in our conversation when we were talking about difference in expectations of privacy and that sort of thing. People were really up in arms that Google would have algorithms read your email.

**Edith: **Oh yeah, sure.

**Paul: **And show you ads. It was crazy!

**Edith: **That's what I mean, people were really upset, like my friend would spoof me.

**Paul: **Spoofing sounds like not that upset. That's like taking it in fun. But people for years refused to use Gmail.

**Edith: **Yeah. And then eventually I think, there are still people who don't, but most people are indifferent.

**Paul: **Well, I think the expectations of privacy on the internet have changed.

**Edith: **That's interesting.

**Paul: **Completely, so Gmail's been out 13 years. To my mind, privacy has always been about whether or not a human can get access to some information on you. Or the information can be used against you.

**Edith: **Yeah and I think this goes back to, I'm still not a fan of they just passed that rule in the states where your internet traffic can now be sold.

**Paul: **I'm fairly lefty and most of the people I talk to are fairly lefty, and so people were up in arms about this. And I looked into what was happening and it was weird. Correct me if I'm wrong here but as I understand it, there wasn't someone who's passing a law. It wasn't like these evil republicans are passing a law that allows you to change it. As I understand it the law was that they were changing who was responsible, like the FCC was responsible or is now going to be responsible or something like that for the ISPs' rules.

So it was like a relatively new rule was now going back because they weren't in charge anymore or something like that. I forget the actual thing but for something like 11 years of Gmail's existence, that rule had not existed. It had existed for two years, something like that. So the ISP's have always sold your data. And now they can again, and it feels like the amount of spin that was put on it was fairly disingenuous.

**Edith: **Yeah, it's funny because I remember maybe 10 years ago, basically your company, if you're employed, has the right to read all of your company email.

**Paul: **Yeah. I remember reading one of these early startups, I don't remember which it was. But they talked about "what do we do about if employees are doing personal internet at work?" Because this used to be a thing.

People used to be like, "oh, you can do work internet at work, but you can't do personal internet at work." So they'd track everything. Same thing with schools. So now that the internet is pervasive and a key part of our lives, that has changed. So this company said, we keep all internet logs public. So it's like, you can do whatever you'd like at work but everyone will see it. That's so much worse than the other side of it.

**Edith: **That's originally how Hotmail came about.

**Paul: **How so?

**Edith: **So Hotmail, they were two engineers that wanted to start a company. And they couldn't find a way to talk about it except for at night. Because at work they didn't want to use their professional email, and back then, imagine a world with no Hotmail. Like imagine you either had your professional email, or you had to go home and use a hard line to use AOL. So that's how they came up with Hotmail was literally like, hot mail that you could access from a web browser instead of having to telnet or dial in. This seems like ancient history now.

**Paul: **Absolutely.

**Edith: **But yeah, I always had this view that my email was so boring that if my employer wanted to read it, good luck. There would be long discussions of running.

**Paul: **Well so then Gmail put chat into your email. And so the precursor to Hangouts was Gchat.

**Edith: **Well, there was YTalk.

**Paul: **Sure, but now, it was like searchable and recorded for all time in your inbox.

**Edith: **But before that, there was Yahoo! IM and chat was not a new thing.

**Paul:**


<blockquote>But chat was not recorded up until Gchat. </blockquote>


**Edith: **I thought it was.

**Paul: **So now it was recorded and searchable. I mean you recorded it if you were using Adium, or one of these things, they kept logs.

**Edith: **I'm pretty sure Yahoo! IM was recorded.

**Paul: **By Yahoo!?

**Edith: **I think so.

**Paul: **It's been such a long time.

**Edith: **It's been decades. Yeah, it is funny to have a permanent record. I have an old friend in Seattle who I was writing about something and he has a pretty unique username for Gmail. I was going to comment on it and then I looked and I had given him his first Gmail account, and he had talked to me about the username.

**Paul: **Yeah, okay, so you'd commented on it.

**Edith: **14 years ago when he initially set it up. Because it's like, "oh, why is toxic in your name?"

**Paul: **Okay, so coming back a little bit here. Unroll Me and Slice and so on have been selling this to Uber. There was a couple of interesting articles about this. So one was by the cofounder of Unroll Me.

**Edith: **Oh, that was an email that should not have been sent.

**Paul: **I'm very sympathetic to what she said in it. So what do you think is bad?

**Edith: **I think it was the kind of email that you write when you're upset. And you look at it the next day, and you're like, "okay, here's how I need to fix it".

**Paul: **Right. And it wasn't just an email, this was a Medium post.

**Edith: **Yeah, but I mean like, I've actually done this when I'm upset.

**Paul: **Yeah, you write it, and then you don't send it, and then you look in the morning and you reread it and then you delete it.

**Edith: **Yeah, or you say, "okay, here's the message I wanted to convey that got lost in the anger. Here's the two points that nobody actually read. Which everybody has done.

**Paul: **So in the case of Unroll Me, they didn't break the law.

**Edith: **I think they broke people's trust.

**Paul: **I mean, clearly they broke people's trust because people are pissed.

**Edith: **Like, did you see John Sheehan's tweets?

**Paul: **What did John say?

**Edith: **Many things about how he was upset.

**Paul: **I'm going to say, I'm not actually in favor of Unroll Me, and I'm vaguely being in the devil's advocate position here, and vaguely slightly sympathetic to the things that's going on. Because I don't think it's quite as serious as people are making it out. So, terms of service. It was in the terms of service. It's like, "we sell aggregate data, was basically written in their terms of service." It wasn't hidden anywhere.

**Edith: **Yeah and it's funny because we get pushback on our terms of service. Our only intent is that we want to be able to use a tool like Intercom. Or Full Story or Mix Panel. And people get very paranoid.

**Paul: **There's been a lot of problems that people describe in their terms of service, we have a license to your data basically to fulfill what our service does. We store your data because we have a database, or we process your data because we have computers. And people read that as like, "oh my god, what are they doing with your data?" And I think this is true of almost any service when the pitchforks come out.

**Edith: **Yeah, and I know it's so we need to know how many servers are connected to us, what SDK's are in use, pretty basic stuff. But people sometimes get the wrong idea.

**Paul:**


<blockquote>There's definitely people who are going to get the wrong idea from fairly normal terms of services, and then there's the people that we discussed that are much more paranoid. </blockquote>


It's interesting to compare Slice versus Unroll Me because you said, and I don't know how true this is, but Slice was much more up front about, we sell your data. And I guess that's why people haven't really been attacking Slice.

**Edith: **I think that's why they thought Unroll Me was trying to appeal to one set of people who would actually be very much against this.

**Paul: **Right. But Slice owns Unroll Me, and operates Unroll Me. I doubt it's a separate company, I'm sure it's an acquired product and is run by the same people who run Slice. So even though they knew about the transparency, they were keeping Slice transparent. With the Slice products, they were transparent about what they were doing with the data. And so they clearly knew that that was a good idea or whatever, and then didn't apply it to Unroll Me.

**Edith: **Yeah.

**Paul: **And Slice is probably the people who sold to Uber. Unroll Me, when it sold, was probably a very, very small company.

**Edith: **Yeah.

**Paul: **It sounds like it was kind of the two people or something. And so it was Slice that sold the data to Uber and certainly is the company that continues to sell the data to Uber. I wonder why we're attacking the two founders, who are no longer involved, rather than attacking Slice, who were also named in the same article.

**Edith: **I think it was because of people's perception of Unroll Me and what Unroll Me stood for. They had this perception that Unroll Me was privacy-conscious and actually turned out was appealing to people who they weren't a good fit for.

**Paul: **Yeah.

**Edith: **I think also that it was because the use case for which they had pitched themselves for was so different than what they were actually doing.

**Paul: **So the thing that they were doing is not an invasion of privacy.

**Edith: **I think people's expectation was similar to TripIt's that, I'm going to sign up for this and I will unsubscribe. It was not, you will have access to everything.

**Paul: **Right. But, the thing that they did, so they parsed your Lyft and Uber emails.

**Edith: **Probably using Slice's algorithm.

**Paul: **Right.

**Edith: **So if I picture the flow, and I don't have any inside knowledge of this, they probably took everybody who had OAuthed in and used the Slice technology to parse.

**Paul: **Right. That is what I'd expect. They're probably doing a per-customer consultation. So it's like, Uber says we want Lyft's data, so they go in and they figure out how to do Lyft's data. It's not like they're already selling Lyft data. They're selling Lyft data because Uber is paying them.

**Edith: **Now I'm getting more and more into the hypothetical.

**Paul: **I'm totally in the hypothetical as well.

**Edith: **I don't have any insider knowledge of their business practices.

**Paul: **Sure. But thinking through how this business probably works. What probably happens is they try to sell to someone, and that someone says we're interested in this data.

**Edith: **We want to know how Lyft is doing in output.

**Paul: **We want to know how Lyft is doing. It's like, well, we have emails.

**Edith: **In specific geo's.

**Paul: **Yeah. And then they make a parser for Lyft emails, then. Maybe they're selling Lyft emails to everyone, but I imagine that they're doing it on a, this is a lot of consulting. These are very high-ticket items. They have account managers, et cetera.

**Edith: **I keep coming back to, "wow, there's finally somebody who there's actually a market for this that might have just been Uber."

**Paul: **Yeah.

**Edith: **So the other interesting thing is that the article that we get into is, who else is Slice selling data to?

**Paul: **Oh, everyone. Everyone who's got competitive needs. Oh actually, didn't it say that Lyft also does competitive analysis?

**Edith: **Yeah.

**Paul: **So I imagine that they're selling to people who want to know about markets in general. So they're probably selling to investors, private equity firms, people like Goldman. People like management consultants.

**Edith: **That was originally the entire idea of Mattermark, that they would do basically competitive intelligence and what startups were hot.

**Paul: **Is that only on public data?

**Edith: **Ah, who knows, I know that that was originally a lot of their things that will tell you what startups are about to blow up.

**Paul: **Right. Okay, so the data that's being sold. It's your Lyft tickets, your Lyft receipts, fairly anonymized.

**Edith: **I want to go skiing now.

**Paul: **Your Lyft receipts, anonymized. Is that a big deal?

**Edith: **So, I don't want a bunch of people with pitchforks to come after me.

**Paul: **Yeah. I feel like I'm setting myself up to be the pitchforks person here.

**Edith: **But nobody knows where you live, so it's fine.

**Paul: **Yeah. Well I'd just like to say that I think I signed up for Unroll Me and then I was like, eh, this is too much access and took it away fairly immediately.

**Edith: **Yeah, I think that ruined OAuth for all of us.

**Paul: **Yeah, I think years ago was the right time to unroll from Unroll Me.

**Edith: **Yeah and it's funny because


<blockquote>There was this whole trend for a while where you would authorize all these Facebook apps. And then people realized that this was kind of a dumb idea because somebody would always take advantage of it. </blockquote>


**Paul: **Yeah. It's interesting how Facebook figured out the one fear that everyone had is that it would post to your account. Everything now says this could not post to your account. And that's in the Facebook UX.

**Edith: **Yeah, it's funny. This is the final one, so another project I worked on at TripIt was the ability to auto-post.

**Paul: **To auto-post to?

**Edith: **Different social networks.

**Paul: **Oh, interesting.

**Edith: **So like, say you have an upcoming trip to New York. We could auto-post to your Facebook feed, your LinkedIn feed, your Twitter feed, or your Yammer feed that, "hey, Paul Biggar. Paul Fracas Biggar is going to New York." And a lot of people hated this, a few people liked it.


<blockquote>The few people who liked it were the social super-connectors who wanted everybody to know where they were. </blockquote>


**Paul**: Yeah, was that a useful thing for growth?

**Edith: **It got us some good PR. And actually it was funny because, Yammer was doing this big launch around their feats, and we were one of the partners and all of the articles ended up being about TripIt instead of Yammer.

**Paul: **Oh, nice!

**Edith: **I was the product person on it and they were like, because the headline was supposed to be Yammer, not TripIt. Because they did all the work to line up with PR and I kind of stole it. But we were very careful about, only people who wanted stuff posted. We never auto-posted because that would have just ticked people off.

**Paul: **And so I guess that's the crux of it. People are fine if it's the things that they're supposed to be parsing and supposed to be using it in the way they sort of advertise, and the terms of services does not protect anyone.

**Edith: **Yeah, well I think


<blockquote> There's a difference between legal, and what pleases your users. </blockquote>


And I'll go back to classic Blender, which is Facebook Beacon.

**Paul: **Remind me of that.

**Edith: **So it was a very early ad product that Facebook had where basically it would say, "so-and-so just purchased this." And people were up in arms about this. Because the idea was that it was all about social buy-in. You buy many things on the internet that you do not want your friends to know you buy.

**Paul: **Give us some suggestions of things that you buy on the internet that you would like your friends not to know that you buy.

**Edith: **Well, Paul, what have you bought in the last week and do you just want to name them all?

**Paul: **That's true actually, I don't think there's anything. It's like, Paul just bought corn flakes. That sounds kind of sad when you say it like that.

**Edith: **Did you buy some milk, or you just eating the flakes straight out of the box?

**Paul: **You monster, eating dry corn flakes!

**Edith: **That sounds so sad. No, it kind of goes back to the email log. There are people who like everybody knowing everything about them, and people who are horrified. For example, so the Facebook Beacon is like if you're buying a book like, "How to Leave Your Abusive Spouse." Or like, "How to Interview for a New Job."

**Paul: **Or an Ayn Rand book.

**Edith: **Why is that so bad?

**Paul: **Post on your wall in San Francisco that you're buying an Ayn Rand book.

**Edith: **I already have them.

**Paul: **Oh, good.

**Edith: **Everybody should have some historical fiction. So I think we've come to the conclusion that there's many things that yes, you can disclose in your terms of service, yes might be legal, but might be a completely bad idea.

**Paul: **Yeah, I think you could argue one way or the other about whether it was morally in the right. Clearly it's definitely legally fine. But I think, generally, if your product is doing something that your users are not going to be a fan of, you're generally not making a good business in my mind.

**Edith: **And let me give a big comma that you can never make everybody happy all of the time.

**Paul: **Sure.

**Edith: **And I think this is where businesses ultimately go out of business if they're unable to monetize in a way that makes enough of their users happy.

**Paul: **I think the distinction that I would draw there is, you're not able to make people happy all the time. But, you have to make the users of your product happy. The people that you make unhappy, you should be able to say "you go over there, you don't use our product". That's great. But when the actual users of a product are going to be unhappy with the things that you're doing, that's generally a bad sign.

**Edith: **Yeah, I mean Facebook has had at least, I don't know, I've lost count of how many exoduses where Facebook people say, I don't want to give up anymore private life. I'm going to go use this other service over here.

**Paul: **It's different when you have a monopoly though. One of the things that you can do when you have a monopoly is ignore your users. I'm not saying it's a good idea, but it's what Facebook's doing. It's what Google's doing, et cetera.

**Edith: **Well, I think they're just saying, "hey, we're this environment for this sort of people." And that's why now you have spinoffs like Snapchat. Did you ever have in Ireland, the concept of a permanent record?

**Paul: **I've heard this idea, yeah.

**Edith: **Well there was this famous song, I hope you know that this will go down on your permanent record.

**Paul: **Right, there was never a permanent record, was there? It was just a lie that all the teachers used.

**Edith: **Well it was this lie that somewhere there's this file with every bad thing you'd ever done up to like.

**Paul: **Santa's going to bring you coal at the end of the year as a result.

**Edith: **Yeah, multiple lumps, enough for a barbecue. So now there is a permanent record but it's a permanent record that you yourself left.





