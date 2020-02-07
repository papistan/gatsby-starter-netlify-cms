---
author: andreaech
comments: false
date: 2016-03-21 23:48:33+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-its-the-future/
slug: to-be-continuous-its-the-future
title: 'To Be Continuous: It’s The Future'
wordpress_id: 888
categories:
- To Be Continuous
tags:
- '"It''s the Future"'
- A/B testing
- CoreOS
- Docker
- Heroku
- Paul Graham
---

In this episode, Edith and Paul discuss Paul’s blog post titled ‘[It’s The Future](https://circleci.com/blog/its-the-future)‘. This is episode #16 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.





**TRANSCRIPT**

**Edith:** Paul, so you had an article that literally - when you published it I looked up and Oren, who sits next to me at Heavybit, and Max, who sits next to me were literally laughing out loud and quoting different lines. This was an article called, "The Future" and I have to say it was extremely funny. It was one of the reasons why we started doing the podcast, because I was like, "This guy is really funny. We should start having a conversation." So I'd love to hear more about why you wrote that article and the reaction to it.

**Paul:** Yeah, cool. I feel we should do many more episodes that involve a lot of compliments and flattery at the start of the episode. It's a pretty good way to start an episode.

**Edith:** Well anytime you wear the Launch Darkly T-shirt, you just always look.

**Paul:** The article was called, "[It's the Future](https://medium.com/circleci/its-the-future-90d0e5361b44)" and it was basically a send-up of the Docker ecosystem at the time. It doesn't age that well because Docker moves so quickly.

**Edith:** Like a ship.

**Paul:** The premise of it was, there's a lot of complexity in the Docker ecosystem. It was a screenplay between two characters, one of whom was asking, "I'm trying to launch an app, how do I do this?" And the other, who was a complete Docker and container and "it's the future" fan boy. It went back and forth, and each time they would ask something, there would be a new rabbit hole to go down. The image that went with it was a rabbit looking down a rabbit hole. It was very well-received. When I first wrote it, and I showed it to a couple of people at Circle, they didn't know that I had written it. They thought it was just a thing I was sending around.

**Edith:** Clever. So you were A/B testing it?

**Paul:** No, not deliberately. I had just been ambiguous with how I was phrasing it.

**Edith:** So did you deliberately leave your name off so that they weren't tainted, or was it accidental?

**Paul:** No, they just didn't look closely enough. I posted it in a Slack, Pastebin sort of thing. My name wasn't on it. They thought it was just a Pastebin meme that was going around or something like that. But I had showed it to our PR people, and the PR people said, "Under no circumstances can you publish this."

**Edith:** Because?

**Paul:** Because there's others in the ecosystem that were mentioned, potential partners and actual partners, and that sort of thing. They said, "You can't publish this," when everyone in the office in the office was saying, "Oh my God, you have to publish this." So I sat down again with PR and negotiated its release.

**Edith:** Was this an external firm, or your internal PR?

**Paul:** This was internal PR. There's our regular PR person, and there's someone who is providing external PR services at the time, and then our social media person. It was the three of them sitting on one side of the table while I'm trying to negotiate the terms of release.

**Edith:** They must have felt strongly, because they'll say that people usually don't want to disagree with the CEO or founder.

**Paul:** Yes, definitely in the first draft.

**Edith:** Is there a legendary first draft?

**Paul:** I have a first draft somewhere. Basically, some names were changed to protect-

**Edith:** The guilty?

**Paul:** To protect people who were our partners or who we wanted to be our partners.

**Edith:** Which in Silicon Valley is basically everybody.

**Paul:** Right, exactly. So you can't really tell from the situation, but there's a lot of "someone is dead" in the article. Something is dead, you need to use Docker now, or you need to use CoreOS, or you need to use one of the new shiny things. Virtualization was one of the things that was dead. Maybe owning bare metal was dead, or something like that. Companies that were involved in that were first named, and then we had to pick other companies who were not going to be our partners, but who were vaguely in that space. It's funny because one of the founders of another Docker company had emailed me afterwards.

So I wrote that post, called, "It's the Future" and then I wrote a follow-up post called, "[It Really is the Future](https://medium.com/circleci/it-really-is-the-future-fbe18bbc20aa)" where I said, "The last post is just a joke, we actually think this is how technology is going." I mentioned 12 companies that were in the Docker space whereas before I had only mentioned 6 of them. Someone wrote to me and said, "Thanks for mentioning me. We felt kind of left out in your previous article, that you didn't make fun of us."

**Edith:** Yeah. The biggest insult of all is not to be insulted, it's to be ignored.

**Paul:** Right. So we ignored some companies deliberately who actually wouldn't care - big companies, or at least much bigger than us, being ignored would not be a massive insult to them - and replaced it with, I think Vagrant was one of the victims. Heroku was one of the major ones that was like ... Heroku's dead, you need to do something else. Of course the punchline is, well if you haven't read the article, read the article. At the end it's going back to, Heroku is the simple way to deploy all this instead of having basically a distributed systems degree to launch a web app.

**Edith:** Oren and Max who sit next to me had both come out of Heroku. They thought it was absolutely hilarious.

**Paul:** I sent the article to some people I know at Heroku and a couple minutes later the Heroku Twitter camp re-tweeted this.

**Edith:** Was that your intended distribution strategy?

**Paul:** Yeah. The way I distributed the article was, I emailed everyone I knew in the industry and said, "You might enjoy this."

**Edith:** So basically you're saying you're a social media master.

**Paul:** Social media master, and then there was the Hacker News. Released it at the right time. I think you're supposed to release it at 10AM on a Thursday or something like that. It was 20 minutes after I published it on Hacker News where it'd had one or two up-votes, and then all of a sudden, I guess after people had read the thing, because it was a long thing. All of a sudden it went quite viral.

**Edith:** Super nova. So how did you come up with the idea to write it?

**Paul:** It's hard to know how something spun into your head, but there's how I thought I wrote it, and then based on the feedback that I got I realized there was another vector. It just popped into my head one day. I said, in my head, something stupid about how Docker is annoying or something like that. Then it just evolved into a sort of he-said, she-said situation. I read, afterwards, someone tweeted at me to say, "Oh that reads a lot like something I wrote on the joelonsoftware forums 10 years ago." I went back and read it. I had read this 5 times before.

This will probably ring a lot of bells about the hammer factory abstract protocol method, or whatever. A guy goes into a hardware store to buy a hammer, and the shopkeeper says, "Oh we don't sell hammers anymore, we only sell hammer factories." So he's like, "All right well I'll have one of those." And it's like, "Well actually we don't sell hammer factories, now we only sell hammer factory factories." And it's like, "Okay well get me one of those." "Well actually people wanted more than hammers, so we have a tool factory factory." And it goes on.

**Edith:** It's kind of like the Austin Powers joke where he says he has a factory that makes tiny factories.

**Paul:** Exactly. It was factories of factories of factories. It went on for a long time and it was very deep. It's not the same joke, but it's the same layout and it's the same setup. I think that was probably a large influence. I didn't realize it until he mentioned it to me.

**Edith:** It's a funny pattern which I think people have been doing. There's always a straight man. The question I've been trying to figure out for a while is am I the straight man or are you?

**Paul:** Right. I don't know if you've seen "Who's on First?"

**Edith:** Yeah.

**Paul:** Someone else said, "This is basically 'Who's on First?'" I went to look at "Who's on First?" I had never seen it before.

**Edith:** You'd never seen it?

**Paul:** I didn't grow up in America.

**Edith:** Oh I thought you grew up in New York.

**Paul:** I lived there for a couple years as a teenager, but not really. I watched "Who's on First?" and it was one of the funniest things I had ever seen. It's amazing.

**Edith:** People only know the first part, but it just gets funnier the deeper you go into it.

**Paul:** Yeah, it's like 7 minutes long.

**Edith:** The jokes just pile up on each other. I think that's what I liked about the article, you name-checked so many things. They were right there.

**Paul:** Right. I was talking to some large company which shall remain nameless, who wanted to be our partner afterwards. They wanted to be our partner entirely because of the article. The article had been sent around in an internal list and people thought it was hilarious. But when we went to talk to them, and I was chatting to one of the senior guys there, and he was saying that there was so much technical detail in it, that it actually looked like we knew what we were talking about. And it wasn't just a joke. That was kind of the point. There is a lot of technical detail in there, and I think, certainly at the time it was very accurate for what the ecosystem was like.

**Edith:** Part of why it was funny is that it wasn't just a word salad of plain, like anybody can look at CrunchBase and be like, "Here are seventeen names and combine them."

**Paul:** Yeah. So a number of people sent me their versions of that. They wrote a version for something else. One guy wrote it for front-end technologies. It was super clear that he knew what he was talking about, and the joke really held up and it worked well.

**Edith:** We have a similar, it's a cartoon, but ... There's somebody who is trying to ask something to somebody else about how it worked and they're like, "Well, you know, we have a Firebase back-end that then ..." And then the punchline is, "So you just tell me to fuck myself?"

**Paul:** Right, I know the one.

**Edith:** Once our designer was asking how we collected emails on our website, and we're like, "Well!"

**Paul:** Someone else sent me an article that was ... It wasn't as bad as a collection of random words, but it didn't make as much sense for the joke. That one didn't get published.

**Edith:** Did you set out for it to be a widely circulated piece that would get you partnerships, or was it just scratching an itch, or a combination?

**Paul:** It was very intentionally a content marketing piece. It wasn't like I sat down to write content marketing, but it was a, "This is funny, we should publish this on our blog." And obviously the point of the blog is that people come to the site, and they get re-targeted and all this sort of thing, and that they eventually buy our product. Even through direct mechanisms of clicking over to the site. I think at the bottom of the piece we had a call-to-action, "Do you want to use Docker and continuously deliver that shit?" Which is one of the quotes from the piece.

It was published because it was content marketing. And that's why we argued with the PR folks, that we should publish this.

**Edith:** So how many drafts did you go through? Some of the jokes are really funny. Did you have people-

**Paul:** By the time I published it, nothing was funny. I can read it now, I can't see a single joke in there.

**Edith:** There's the one about BSD and you're like, "It's San Francisco."

**Paul:** BDSM, right. I recognize that they are funny in a purely academic sense. But I can't laugh at anything. I've read that thing like 100 times, and nothing is funny after you've read it 100 times. The first time and the second time and the third time I read it, I could see that it was funny. It went through maybe 10 or 12 drafts. A couple of drafts at the start, and then there was the draft to remove the partners names and be rewritten with other people's names in its place. Then there was a couple more drafts. There was a draft to make it ambiguous to the gender of both participants.

**Edith:** Oh that's very clever. I didn't realized that until now.

**Paul:** There is one place where the, what's the opposite of the straight man?

**Edith:** The comedian? The yuckster?

**Paul:** The straw man or whatever.

**Edith:** Oh the straw man.

**Paul:** That's probably not the name, but the person who the joke is on.

**Edith:** That's the straight man.

**Paul:** Oh okay, right.

**Edith:** The straight man is the one who says, "Oh, who's on first?"

**Paul:** Okay, okay, I can see that. That person said, "I'm more of distributed system guy now." That was the only kind of gender reference in the whole thing, and obviously there's a big thing at the moment of trying to make sure that everything is not just put out from the male perspective. The assumption that everyone in the tech industry is male. We deliberately removed all kind of gender reference and rewrote some of the jokes to make it ambiguous as to who was what, or whether there was even any genders involved at all.

**Edith:** That's fascinating. The reason why I asked was because I saw the producers of Airplane speak, and they say that they had tested every single gag in that movie on studio audiences. I pictured you putting out draft after draft and sharpening each line.

**Paul:** There was a little bit of sharpening, but for the most part it went out as it was.

**Edith:** So it was more like dulling as you're taking out the pointed-

**Paul:** No, actually, when we changed the companies involved it got funnier. We had the opportunity to refine the joke and make it a bit more appropriate for the companies that got mentioned. Some of them had a been a little bit of a reach before because, in my head I was thinking of the people who were our partners at the time, and it had been a bit of a stretch to make the specific joke I did. Then when I had to remove them, I could search around a little bit and find the ideal company that could be poked in just the right way.

**Edith:** The article was a lot of planning, it was a content marketing piece-

**Paul:** I mean, it was a thing I wrote in about an hour, that we then planned, "How do we market this to get the most effective outreach," and that kind of thing.

**Edith:** So what was the reaction? What was the thing that surprised you most?

**Paul:** I guess the thing that surprised me most was that a lot of people's reactions were, "Oh yeah, fuck that Docker shit." Most people who read it perceived that we meant it, and that Docker was complete crap.

**Edith:** Interesting, because I think it was clear that it was very tongue-in-cheek.

**Paul:** In fact, when we launched it, we had a tongue-in-cheek disclaimer at the top, which we've since removed because it wasn't really necessary. But there was a lot of people complaining when we wrote the, "It Really is the Future." Nobody hated, "It's the Future." A lot of people hated, "It Really is the Future."

**Edith:** Interesting.

**Paul:** So the idea that you're going out and taking the piss out of this new technology, people love that. But you go back and say, "Actually, we really do think it's good." People hate that.

**Edith:** Oh no.

**Paul:** Yeah, so the haters really hated on the second one.

**Edith:** But the second one I thought was really innocuous. The second one was just kind of a "Ra, Ra, Docker is good" piece. It wasn't a dialog, it wasn't funny.

**Paul:** It wasn't that funny, no. But there was a discussion of, "Why do people hate new stuff?"

**Edith:** Oh I like that line.

**Paul:** The kind of people who would look at the Sistine Chapel and say-

**Edith:** "Why do we need to paint the ceiling?"

**Paul:** "I have a fresco in my house already." Something along those lines. Obviously no one likes being dismissed as mere curmudgeons.

**Edith:** I wrote a kind of controversial article called, "[Kill the Staging Server](http://readwrite.com/2016/01/22/staging-servers/)" And I actually have a follow-up planned called, "[The Staging Server is Dead](https://blog.launchdarkly.com/staging-servers-are-dead-long-live-a-staging-server/)"

**Paul:** Long live the staging server?

**Edith:** Yeah. I got a lot of really good feedback, but the one tweet that made me a little bit sad was this one person who had a link that's like, "Call me when you start doing serious software development." And I'm like, "Okay, you don't have any rebuttal or rebuke or feedback, you're just like ..." By the way, shouldn't software development be fun?

**Paul:** Right. [Paul Graham](https://twitter.com/paulg?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) has this article that he wrote years ago, "[The Six Levels of How to Disagree with Somebody](http://www.paulgraham.com/disagree.html)" and the main one is "refute the main point of the argument," and the simplest and least effective or least convincing one is "dismiss it out of hand" or "insult the person who says it for who they are" or something along those lines. It's very easy to ignore those. I don't even notice that hate any more.

The feedback that I found really interesting was the people who were mentioned in the articles who were kind of making jokes at each other about the article. There's a couple things I got wrong, but people perceived them as part of the joke. One of the things I talked about is this guy Diego, who in the article he worked for CoreOS and he wrote etcd.

In fact, he did neither of those things. I had met him when he was interning at CoreOS or something like that, but he didn't actually take a job there. Alex Polvi tweeted at him, "Oh I hear you work for us now. I expect you to be here on Monday morning." The thing is, I didn't know that. People thought it was all part of the joke. People corrected every single minor detail that they thought was part of the joke. They were like, "Oh I love how you made this joke here about how Diego works at CoreOS." There's various things like that, but


<blockquote>not a single person pointed out that Katy Perry did not write the song, "Call Me Maybe"</blockquote>


**Edith:** Oh wow.

**Paul:** That was an intentional-

**Edith:** That's Carly.

**Paul:** Exactly.

**Edith:** Yeah, I'll own that one.

**Paul:** I think I got that wrong in the first draft, but after that I left it in deliberately because-

**Edith:** Do you think nobody wanted to admit that they know female pop stars?

**Paul:** I don't think anyone knew. I think that people were like, "Call Me Maybe, Katy Perry, that sounds right."

**Edith:** No, no, no.

**Paul:** 100,000 views and no one pointed that out.

**Edith:** Maybe they either didn't know or were embarrassed to admit they knew.

**Paul:** Maybe, but every little tiny bit of something else that was ever-so-slightly off, I was-

**Edith:** Like what else?

**Paul:** There was another one, but I don't remember what it was. It was kind of along those lines as well. I didn't know that he didn't work there and I didn't know that he didn't write etcd. I think he did design raft. I'm pretty sure that he designed raft, which is the protocol in etcd. I don't remember the other thing.

**Edith:** You said you already felt that the article was a little dated, so how do you feel like things have moved on since then?

**Paul:** So the whole Docker thing moves really really fast, so there's probably a couple of companies or technologies that were mentioned in there that have been acquired or gone out of business or something along those lines. I remember when I wrote it there was a bit of a war going on between CoreOS and Docker. They've since buried the hatchet and become friends, but there's probably a couple of technologies there that have changed. CoreOS released the Tectonic stack sometime after that, I'm pretty sure. That would probably get name-dropped a little differently or something like that. I imagine that Docker has had several releases of Swarm at this point. That might have gotten a bigger thing. The things that were big at the time were the things I mentioned, and those are not necessarily the things that are big now, just because of how early Docker is and how quickly technology is moving.

**Edith:** This is a friendly podcast, but what do you think of Docker now?

**Paul:** I think Docker is awesome. It solves a real problem that people needed solved, and the complexity that results from that is real. It's getting managed, and it's getting managed better over time, but it's real because you're writing distributed systems. Distributed systems are hard. No silver bullet technology is going to make distributed systems easy, it can just make them more manageable. And Docker, certainly very useful as part of making distributed systems more manageable, but they're still a distributed system. Obstructions leak, and obstructions will continue to leak. And you still need to understand a whole set of new technologies.

**Edith:** So are you going to write a new, "The Future," in a year or so-

**Paul:** I tweeted about this recently. I think that's the best thing I've ever written, and I think I probably can't do it justice again. I remember looking at the Google analytics for this article. The follow-up article was bigger than the biggest thing I'd written before, and then the first article was 5 times bigger than that or 10 times bigger than that.

**Edith:** Wow.

**Paul:** First day, 100,000 views. So you can't really follow that up. I spent a couple days thinking about it like, "What am I going to write next? What am I going to follow this wave with?" I quickly realized you can't be chasing that dragon. The likes and social media and content marketing dragon is kind of like the problem that people have with Facebook or maybe with Instagram. When you're constantly looking for people to like your thing and you're looking for affirmation from social mechanisms instead of just what you're working on, everything's negative from that point.

**Edith:** That's interesting, because you're not that active on Twitter.

**Paul:** Exactly, and part of that is just accepting that I'm not really that good at Twitter. I occasionally say some stuff that's interesting or funny, but I'm very happy to not be chasing likes or affirmations or re-tweets or whatever the thing is.

**Edith:** Yeah, they're very seductive. I do content marketing, too. I write articles. I wrote my first one about fundraising. I compared fundraising to enterprise sale. You have your champion and you have a process. It got a decent amount of traffic. I though it would get a lot more. But then I wrote something which I considered kind of geeky and technical, which was why people were doing continuous delivery. Much more popular than the fundraising article. Then my last one which was on staging servers, which I thought was intensely narrow of an audience, got the most traffic of any of them. And it actually got comments. It got shares. It got comments. I was like, "Wow." I think it's proof that something I though only really I cared about actually had this core.

**Paul:** It tends to always be that way. Something that you don't expect to be as big as it is. I remember someone telling me that, what is the name of that company, there was a Google Docs competitor that got acquired by Yahoo at some point.

**Edith:** Tumblr?

**Paul:** No, a Google Docs competitor. Anyway, the biggest piece of content that they ever wrote was something about AJAX. It was written in the early days of AJAX and all the JavaScript-y stuff. It wasn't a company that made JavaScript tools, or it wasn't a developer tools company, but that was the biggest thing that they had ever written and the thing that led to the most inbound traffic. If you're judging things by the business metrics that you're trying to generate, you have to be looking at leads or sign-ups or money in the bank at the end of the day rather than whether someone re-tweets your stuff or whether there's a like there. You have to be looking at the business metrics, not the social metrics. Not the things that make you feel good.

**Edith:** Well, they go hand-in-hand.

**Paul:** Often they go hand-in-hand, and I think often they don't.

**Edith:** Didn't think this was going to go all philosophical, but-

**Paul:** For example, a lot of the things that had the biggest re-tweets and that sort of thing were fundraising enhancements, but people don't follow fundraising enhancements to buy your product. As content marketing goes, a fundraising enhancement isn't all that good. A viral blog post, much better.

**Edith:** I'm happy that we got to talk about this. Is there anything bad that came out of this article?

**Paul:** I don't think so, really. I don't think that there was any negativity from any of the people involved. There was a couple of haters on Twitter, but there's always haters on Twitter. There was a couple haters on Hacker News, but that's what Hacker News is now, unfortunately. But definitely, I'm glad I wrote it and I'm glad I followed it through and I think that it would be hard to ever top that one.
