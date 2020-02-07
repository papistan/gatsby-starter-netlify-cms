---
author: Kimh
comments: false
date: 2018-12-19 22:31:45+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-marketing-an-open-source-project/
slug: to-be-continuous-marketing-an-open-source-project
title: 'To Be Continuous: Marketing an Open Source Project'
wordpress_id: 193641
categories:
- To Be Continuous
tags:
- Docker
- Golang
- HashiCorp
- Kubernetes
- Mozilla
- opensource
- RedHat
- VMWare
---

In episode 50 of To Be Continuous, Edith and Paul look at how marketing plays a role in open source and how creators can turn a vision into a successful developer community.

This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.

https://soundcloud.com/heavybit/to-be-continuous-ep-50-marketing-an-open-source-project?in=heavybit/sets/to-be-continuous
















TRANSCRIPT





**Paul Biggar: **We're talking open source again. Specifically what we're looking at is when you've got some open source project, and you tend to think that it's just coders that you need. You just need people contributing code back and building the product. But you actually need a lot more. You had a specific story about this, Edith.

**Edith Harbaugh: **I have a couple. [We had Armon on](https://www.heavybit.com/library/podcasts/to-be-continuous/ep-44-open-source-for-enterprise-with-hashicorp/) a few episodes ago who was the co-founder of [HashiCorp](https://www.hashicorp.com/), brilliant guy. He was talking about how much marketing had gone into getting their first open source projects off the ground.

**Paul: **Yeah, of course.

**Edith: **Everybody should go listen to that episode because Armon is brilliant. But he was talking about how they initially got 100 downloads, not per day or per month. Per year. And there is much work of them going around meet ups and talking about the project and basically being marketing. Then also pretty recently I was at an event and I was talking to a guy who was on an open source committee.

His open source committee was community. And I said, "What does that do?" And he's like, "If people are disagreeing, we're the arbitrators." So I'm like, "You've recreated HR."


<blockquote>There needs to be a source of truth or a source of reconciliation if people are not getting along. Which is sometimes not technical, but sometimes just personality. </blockquote>


**Paul: **Certainly in the marketing one, one of the things that you see is a lot of open source projects take off because their creators are excellent marketers. Sometimes you see the same thing with a startup, you've got someone who is a great writer who has 20,000 Twitter followers, who's got a popular blog or something along those lines. And then they build something. And because they have this built-in distribution channel, that something goes somewhere.

**Edith: **Yeah, and they don't really realize what they're doing is marketing.



[tweet_box design="default" float="none"]**Paul: **As we know engineers hate marketing and they hate being marketed to.

**Edith: **Yes, but they love to tweet.

[/tweet_box]

**Paul: **Engineers love being marketed to. They just don't know it.

**Edith: **When you were at Mozilla, how did you see them breaking up their open source project?

**Paul: **Mozilla had such a large distribution channel because it had been going for so long, and it was one of the original things. I don't think Mozilla really lacked for marketing. In fact a lot of the things they did, just by posting on their blog they would automatically get to the top of Hacker News and would get people discussing them. They did PR quite well. I don't think Mozilla lacks for marketing at all.

**Edith: **And then people don't realize how much marketing they had, and they think that they could just start an open source project and PR happens.

**Paul: **I had an open source project back in the day, it was a PHP compiler. We did extremely limited marketing. But the very, very small amount of marketing that we did, had a tangible effect.

This was pre-Twitter, and it was just a little too late on the open source side of things. We'd post it on SourceForge and Freshmeat. This is 2005, and we were just over the hill, but still all the same on those. They got tons of people just checking it out, downloading it, installing it, etc. And just that was an act of marketing and finding users.

**Edith: **How did that make you feel?

**Paul: **I don't think I identified it as marketing at the time.

**Edith: **But were you happy that people were using--?

**Paul: **Oh yeah. I remember an argument with the other people on the project that I eventually convinced them where we were arguing about licensing. And it was originally a GPL project and I convinced them to switch it to BSD.

The reason being that we wanted people to use it. I felt that the GPL restricted people from being able to use it, and the argument was, "What if Apple came along?" In compiler word Apple was the big baddie that GCC was trying to stop from appropriating their software.


<blockquote>"What if Apple came along and built a closedsource product around it?" And I was like, "That sounds great. I'd love so many people using our software." Thatconvinced them. </blockquote>


So apart from marketing, and you mentioned community management, I think community management is one of those things that people these days are often doing really well. There's a lot more people doing a really good job of this.

**Edith: **Who do you think does a good job of that?

**Paul: **The Rust community. They were one of the first projects to adopt a code of conduct. I remember reading some posts by Graydon on their mailing list. That's [Graydon Hoare](https://twitter.com/graydon_pub), who was the original Rust designer.

Someone would post something and they were just being a dick about it, and Graydon would answer their question but he would immediately start by saying, "We don't discuss in this way," and correct their behavior and then continued the conversation in a way that wasn't excessively confrontational at all. But it made clear what was acceptable and what wasn't unacceptable in the community.

**Edith: **Yeah. That's a smart way to do it.

**Paul: **I joined a Slack recently.

**Edith: **People still do that?

**Paul: **People do. There are still Slackers. I don't like them, but I joined one.

**Edith: **I thought peak Slack was 2016.

**Paul: **I thought it was peaking last year. But yeah, I'm certainly getting the impression that for open source projects, having a Slack where you can't search what people have said before. If Slack fixed that I think that Slack would continue to be used for open source communities.

**Edith: **But you can search.

**Paul: **There's a 10,000 user limit if you don't pay.

**Edith: **If you don't pay.

**Paul: **Or, a 10,000 message limit if you don't pay.

**Edith: **You can search, it's just you have to pay.

**Paul: **Yeah, but typically if you're going into certainly an open source project Slack to find out the answer to your question. So you want to search for the answer to your question, and this is why I was reading today some community that's moving to Discourse. I've used a bunch of Discourses that typically discussed something. The OCamel one, the Elm one. They're really, really good.

**Edith: **Slack also makes threading very hard.

**Paul: **It does.

**Edith: **They tried to put it in, but it's just hard.

**Paul: **You need to bake that in from the start.

**Edith: **Yeah.

**Paul: **OK, we've got marketing, we've got community management. The thing that's mostly missing from open source is product management. We talked about this in the episode where [we had Adam Gross on](https://www.heavybit.com/library/podcasts/to-be-continuous/ep-47-product-management-with-adam-gross/).


<blockquote>It's just that people don't design what they want their software to do. People have change logs but no roadmaps. </blockquote>


**Edith: **GitLab has published a roadmap.

**Paul: **Sure. GitLab is a company though. Companies that are built around open source are excellent at this, because they have a company to build. They have a place that they're going.

**Edith: **Ah. So you're making a distinction between open source communities, and open source companies.

**Paul: **I'm really thinking of, if you start a new open source project today, are you just a public repo on GitHub? You want people to use it, you want it to turn into something. Maybe it's unspoken. But you're not really doing any of the activities that would make that work.

And then if you do start to take off, that you're still not doing any of the activities, unless there's some immense commercial stuff around it. Rails for example, while 37 Signals wasn't excessively making money directly off Rails, but they were still making a lot of money in various ways off the fact that they were the creators of it.

**Edith: **And then there is just the pure stuff. The ones that are most relevant to us right now are Go from Google. We were actually built on Go. We don't use it, but it's interesting to us because it's adjacent to [Istio](https://istio.io/).

**Paul: **Which one is that?

**Edith: **Istio? I don't know if you're following it at all.

**Paul: **No, I don't know about them.

**Edith: **It's kind of two rival standards, depending on who you talk to, rival or complementary. Istio and Envoy, which was the idea of a service mesh.

**Paul: **Are they not appropriately putting out roadmaps? What's the connection there.

**Edith: **They're just not trying to charge money. They're just big companies trying to push these open source projects.

**Paul: **OK. Sort of like Kubernetes.

**Edith: **Yep.

**Paul: **Kubernetes has a roadmap.

**Edith: **Yep.

[tweet_box design="default" float="none"]**Paul: **Anything that really has a large company behind it, large companies know how the sausage is made[/tweet_box].

**Edith: **Perhaps too vividly.

**Paul: **Yeah. There's a lot of open source things that are about engineers only, who only value engineers.


<blockquote>They don't value designers, they don't value technical writers, they don't value marketers or community managers. All the things that make a project into something really successful and useful to lots of people. </blockquote>


**Edith: **To loop back to a prior episode, they could be what turns that project into a product.

**Paul: **Sure, whether you think a product is commercial or not. It's the non-commercial open source, but a product.

**Edith: **Yeah. Whether or not you should be able to understand it just by spending enough time with it, versus value and technical writing onboarding. People will want some degree of hand-holding to start to use it. And I don't mean hand-holding at all in the negative way.

**Paul: **Sure. It's the way a good sales engineer might help their customer onboard.

**Edith: **Yeah. There's this myth that if you're smart enough you can just start doing anything immediately without any help.

**Paul: **Similar, the myth that the project founders or the engineer who wrote it can do all these things. Then you often see people who are burning out because they were doing all these things, when they're when their passion was really coding.

**Edith: **Yeah. Or just try to have a lot of empathy. Everybody can be very smart, but in different ways. And you need to give them a lot of hand-holding in a very positive way the first time they try anything. I'm going to go on metaphor but then I'll come back. The first time I tried to use clip on bike shoes. Have you ever biked with those?

**Paul: **This is quite some metaphor. No, I've not used them. They scare me.

**Edith: **They scare me too, and then I was biking cross-country and I really needed to start using them. And I'm a smart person. But I started biking and it was really hard to get used to them. It was just something that I needed practice and hand-holding on.

And there is a lot of things where it's like, "OK. You can have a very capable person, but their first encounter with something, maybe they need technical documentation. Maybe they need a wizard." God forbid a wizard, but maybe they need a quick start or a tutorial.

**Paul: **It's interesting. One of the large projects that I've a lot of experience with is the PHP project. I haven't written too much PHP, but for several years I was involved in the project in various ways.

One of the things that really allowed people to get involved in PHP, and I think they really pioneered this, is that all of their documentation had a comment section at the bottom. And this was before there was a Stack Overflow.

But you just had hundreds of comments with people being like, "Here's a way to do this. Here's the way I use this function to do this." It was really the Stack Overflow of its day.

**Edith: **But politer.

**Paul: **I'm sorry?

**Edith: **I hope politer.

**Paul: **No, no. It wasn't great.

**Edith: **OK.

**Paul: **It was the Wild West of commenting, and I'm sure there were people calling each other idiots and that sort of thing. This was like the late '90s, early 2000s.

**Edith: **Side note. Ev Williams just gave a talk, and he was trying to defend Twitter, and he's like, "This whole un-civility thing is this very recent thing." And I'm just like, "What?! Have you been on Usenet?"


<blockquote>You don't need gifs to have a flame war. You just need ASCII.</blockquote>


**Paul: **Yeah. The September that never ended.

**Edith: **Yeah. I thought it was a very inaccurate thing for him to say. His literal quote was, "Only the cool people used to be on the internet."

**Paul: **For fuck's sake.

**Edith: **"So we were all very polite." And I was just like, "No!"

**Paul: **No, no, no. "Only the cool people." I feel like the internet was initially populated by people who were absolutely uncool in almost every way.

**Edith: **That's what I mean. He was like, "It was only the geeks and the nerds, and I say this as a geek and a nerd myself. We were all polite." And I was like, "No, no, no." You had this veil of, you could type stuff, and people would flame.

**Paul: **Yeah. A large open source project that has this exact problem is the Linux project.

**Edith: **Well, it starts from the top.

**Paul: **In that case it definitely starts from the top. Every other project, thinking about Rust where the opposite comes from the top, the invaders come in and they act like they have learned from other projects and like they've learned from Linus. They have to be individually repelled.

**Edith: **It's funny. The closest I've come is I moderated a mailing list for a while.

**Paul: **Woof.

**Edith: **And this was in 2007, 2008. People forget that there are humans on the other side.

**Paul: **It's very easy to forget when it's just a text box. One of the best things, when I started using Intercom. The best thing about it was that you saw the human.

**Edith: **Or their avatar.

**Paul: **Yeah, the avatar of the human.

**Edith: **It's usually not that person, I hate to prick your bubble.

**Paul: **I understand that. But they saw my picture, and they're like, "This is another human." You got the same thing with Reportive. When you're writing to someone and you see their picture alongside, it's like, "This is a human who has a company that they work at and Facebook profile," and whatever else is in the information. But there's a photo and you see who they are, and that they are in fact a person.

**Edith: **This is a person who has feelings, motives, their own stuff going on in their life. It's not just some punching bag.

**Paul: **One of the best things about GitHub is emoji. Because it's one of these things that you didn't have in the old text days, you didn't have when you were sending patches to a mailing list. There was no way to humanize your message.

**Edith: **Emojis can be so open to interpretation. I do agree that they are a step up, but they can be open to massive interpretation.

**Paul: **If you stick to the smiley faces I do.

**Edith: **Your repertoire has not widened since--

**Paul: **It's really not very wide at all. People are sending me Bitmoji, and I don't understand.

**Edith: **Do you ever go for the winky one, or a thumbs up?

**Paul: **Sure, maybe a winky emoji. A winky face, a thumbs up, maybe a heart. Only the red one, obviously. Those other color ones, there's a heart with sparkles on it--

**Edith: **That's not you.

**Paul: **No, not at all.

**Edith: **So, I'm assuming you have your own Slack for your company.

**Paul: **Yes.

**Edith: **Have you started developing your own emojis yet?

**Paul: **No. And the Slack for our company is very underused. We followed your suggestion, our general room is now called the Dark room and the random is called the Light room.

**Edith: **Oh, I thought I recommended the reverse. But OK.

**Paul: **OK. Well, Dark is a good thing for our company.

**Edith: **And thank you for wearing your--

**Paul: **My LaunchDarkly t-shirt?

**Edith: **I appreciate it. So, your Slack isn't very used at your company?

**Paul: **There's five of us, and then we're all in the same room. And deliberately so. After the last company being very remote, we focused very hard on in-person interactions. Because we're inventing a new language, we're inventing a new technology. It's hard to do that without high bandwidth communication.

**Edith: **It's funny because my co-founder John and our first two engineers came out of Atlassian, which has HipChat.

**Paul: **Yeah, of course.

**Edith: **So we used HipChat and they would converse exclusively over HipChat.

**Paul: **And they're sitting next to each other?

**Edith: **Yeah. To the point where whenever we hired somebody they would be a little freaked out. They'd be like, "Y'all never talk," and I'd be like, "No. We're talking constantly."

**Paul: **There's so much value to synchronous communication. I have notifications turned off of my machine, that allows me to focus on actually coding stuff, which is my job at the moment. I guess when my job changes to much more management and leadership and all that sort of thing that you're supposed to do, I'll probably have to turn the notifications back on.

**Edith: **To bring it back to open source though, we are very reliant on chat. But there will come a point when I'm like, "Let's get on the phone," if we're not in the same place.

**Paul: **In an open source project?

**Edith: **No, at our own company. I'm just like, "We're losing too much. We're getting into some sort of disagreement. I think if we just stood up and talked--"

**Paul: **Yeah. I did this when I was at Mozilla. I was involved in trying to increase contributor engagement. One of Mozilla's great weaknesses is that it never focused enough on contributor engagements and sort of cannibalized its contributor community.

But there was a point at which we were working on initiatives for first people to commit, for new users trying to solve a bug to get involved in it in some way. One person was like, "We could do this," and someone else is like, "We could do this instead," and someone else was like, "We could do this."

And just the scope of what we were doing ratcheted up massively, and then all the people who were talking about it started going off and implementing their own ideas and going in their different directions. You had 5-6 people doing individual, their own things, instead of one unified effort. So I had to get on the phone with people. I had to be like, "Listen. We could do that, we could do this, we could do this. They're all great ideas. But we have to prioritize."

**Edith: **It's interesting. There's value in different types of communication that people don't always understand.

**Paul: **Voice is such a powerful communication method.

**Edith: **But I try to reserve it for times that need voice.

**Paul: **There's very few situations where you wouldn't gain benefit from voice.

**Edith: **OK, so here's a real one. We're hiring and we have a recruiter. There's two people that always want to talk. Recruiters and real estate brokers.

**Paul: **OK. Sales people.

**Edith: **And they're like, "I just want to check in." And I'm like, "Why don't you just send me an e-mail?"

**Paul: **Oh yeah, for sure.

**Edith: **They're literally like, "I just want check in on how you're feeling about this." I'm like, "Has anything changed since we talked three days ago?" And they're like, "No. I just want to check in."

**Paul: **Are we talking about your real estate broker, here?

**Edith: **Yes.

**Paul: **One of the great skills of sales, of which recruiting and real estate brokering are both that skill, is understanding what medium your user would enjoy better, and is more beneficial for your user.

**Edith: **But there is a great deal that is undervalued on talking to somebody on the phone.

**Paul: **For sure. And I've overvalued it a little bit. I said voice is always good, but with text you do get a record of it. You do get people seeing what has happened. I know during incidents, like SRE incidents and outages and that sort of thing.


<blockquote>Having everyone type everything, every thought into a chat room, makes it much easier to do retrospectives and to do the blog post that you have to do afterwards, etc. </blockquote>


**Edith: **The key though, is to force people to admit when they don't understand something.

**Paul: **OK. Tell me more about that.

**Edith: **So if somebody writes a line, I'm trying to think of a hypothetical incident. "We don't think many people will be affected by this."

**Paul: **OK. All right.

**Edith: **And then you need to call them out. "What does not many mean?" Because everybody's idea--

**Paul: **They're like, "I don't know, 50,000 or something like that." And you're like, "What?!"

**Edith: **Or they could be like, "It could be as many as five or as few as two."

**Paul: **Great.

**Edith: **Yeah. It is a very good medium where you have this record of everybody's definition of "not many," or "few," or "small."

**Paul: **The challenge that you have with this communication in open source is that you have so many people who have no shared language, I guess. And very little sense of--

**Edith: **The cultural norms.

**Paul: **Cultural norms of how to have a discussion together. One thing that I'll often do when someone asks me a question, my first thing in the vast majority of cases is, "What are your goals? What are you trying to do?"

I'm not sure I've ever seen anyone on the internet say, "What are your goals?" Think of a Hacker News conversation. The first thing they'll be like, "You're doing it wrong! Here is how you're supposed to do it!" And I'm like, "What are your goals? What are you even trying to do here?"


<blockquote>Once we understand, once we have a shared understanding of goals, then wecan actually discuss the implementation, the solution or whatever it is that you're proposing. </blockquote>


**Edith: **I was going to talk about one area of the internet where people are sometimes explicit about their goals, which was online dating.

**Paul: **Oh yeah, for sure.

**Edith: **People can be very explicit.

**Paul: **Yeah, and that's a great one. You want people to be explicit about their goals. Nothing like seeing something very exciting and then getting to the date or whatever, and then you're like, "Oh we're looking for completely different things and I've wasted 2-3 hours of my time figuring this out, that could've been done much earlier."

**Edith: **Yeah. "I want to have somebody who will go play pinball at this bar, and who--"

**Paul: **Yeah.

**Edith: **That's a case where people can be very specific.

**Paul: **You're an online dater, Edith?

**Edith: **No.

**Paul: **No?

**Edith: **No.

**Paul: **Hypothetically, what is your favorite online dating app?

**Edith: **It's gone.

**Paul: **It's gone? Did they just shut it down? It was Grindr, I heard they sold it.

**Edith: **No, they shut down Craigslist. Did they really shut down Grindr?

**Paul: **No, they sold it. But then there was a huge data leak a couple of days ago.

**Edith: **That was not good.

**Paul: **All right, where were we? Open source projects.

**Edith: **I think people underestimate the value of being very specific sometimes.

**Paul: **Yes. So you have some sort of goal and you have a pull request, and someone comes up and they say on the pull request, "I think you should do X instead," or, "You should do Y instead."

And occasionally you'll get people being like, "I think your approach doesn't solve this, or has this side effect," or whatever. But it's so rare to have people stepping back and being like, "Here are the goals of what I was trying to achieve."

**Edith: **I'm not on open source, per se. But I try to do that a lot when I'm trying to resolve a conflict in the company or the team. I'm like, "Step up. Let's back up the situation. What's happening? Why are we having this conflict.?"


<blockquote>Usually there's always two answers to everything, but it's like, "OK. Why arewe disagreeing? Is it because we actually have different goals?" </blockquote>


**Paul: **This is one of the reasons why compilers are very easy tools to have communities around.

**Edith: **Because it's very clear.

**Paul: **It's just everyone knows it's not supposed to crash. It's supposed to be extremely performance, it's supposed to generate fast code. And so any conversation starts with those shared norms. Then after that, this disagreement about no indentation and that sort of thing, all that is trivial to do.

**Edith: **I forget who we talked to, but they said, "The lower in the stack something gets, the more easy it is to open source."

**Paul: **That's interesting. So if you're trying to open source a product--

**Edith: **Linux. Like, OS. It's pretty clear what Linux needs to do.

**Paul: **The driver has to communicate with things.

**Edith: **Yeah. But as you move higher and higher up, it gets harder to open source it. If you try to open source, I'll even say like, a car. There's still a lot of disagreement about, "What does a car look like?"

**Paul: **Even trivial-seeming products, let me pick Intercom as an example. Intercom isn't trivial-seeming, but in the early days it would have been fairly straightforward what it did.

**Edith: **It's just a chat.

**Paul: **Right, it's just a chat plus some sort of messaging and maybe some triggers. But trying to do that, trying to steer a group of people who have no shared ideals about what the product is going to be into what Intercom is today. It's not possible whatsoever.

**Edith: **Yeah. The more novel or new or up for variation something is, the harder it is to open source.

**Paul: **You need a shared direction.

**Edith: **Yes.

**Paul: **And you need ownership of the components that lead to that direction.


<blockquote>By ownership I don't necessarily mean in the owners file, or something like that. But accountability. Someone has to be accountable for getting their part of the project in that direction. </blockquote>


**Edith: **Not to go all meme-y, but have you seen the internet meme, "You had one job?"

**Paul: **Yeah, yeah. Exactly.

**Edith: **Sometimes you just got to do one thing.

**Paul: **If you pick some random open source project, Docker is a wonderful example here because there's so many competing interests in the Docker ecosystem.

**Edith: **So many.

**Paul: **When you started with this, it's a continuization form up with file system hackery that makes it really fast, and this nice Docker file. But then you've got--

**Edith: **Red Hat, you got VMware.

**Paul: **They all have their own things they're trying to do, or they're trying to make it important in their ecosystem. They're trying to make their ecosystem important to it. And then you've got all these companies who are trying to own a little part of the Docker space. and that's exactly what Kubernetes is trying to do. Kubernetes was trying to own the orchestration side of things with Google's goal of competing with AWS and all that sort of thing.

Meanwhile Docker is trying to own their own share of it. They're trying to introduce Swarm, and they've got Compose to try and wrest control and try to own the entire ecosystem. They're trying to do everything in every single direction. So every time a company starts up that's doing something useful, Docker doesn't want to let that get away from them in case that becomes the useful thing.

**Edith: **Like CoreOS.

**Paul: **Yeah, exactly.


<blockquote>You just end up with this huge fragmentation in the system, and this huge amount of wasted work because everyone is trying to drag it kicking and screaming in the direction that suits them best. </blockquote>


**Edith: **We started off by saying an open source community was just people benevolently contributing code. And now we've morphed to corporations.

**Paul: **Yes. Corporations fighting over who can be the most benevolent.

**Edith: **Benevolent?

**Paul: **Who can seem the most benevolent as they, what are the words? Embrace, extend, extinguish? There was a time when open source was not corporations.

**Edith: **Yeah.

**Paul: **If you're taking a Richard Stallman view of the world, we should never have gotten into this open source thing. Free software was the only right way of doing it.

**Edith: **I just think that's funny, because now we say, "Open source has basically become corporations trying to seize a standard."

**Paul: **It always was. Not necessarily trying to seize a standard, but no one's really doing this for the good of their health. We could argue that we like to build companies because we just like to build things, but there's many other goals that go along with that. Regardless of how benevolent one might be.

**Edith: **I do think there are individual maintainers who are really just doing it because they care about it.

**Paul: **They're the ones who are getting burnt out first.

**Edith: **Yes. Because they're not getting paid and they're getting basically screamed at by everybody.

**Paul: **This reminds me. Do you remember when we had--?

**Edith: **Nadia.

**Paul: **Nadia, and was it Sean Byrnes on that episode? [Nadia Iqbal](https://www.heavybit.com/library/podcasts/to-be-continuous/ep-17-open-source-economics/). And the idea that they've been many iterations of this and probably Patreon is the only one that's working, is that open source people should get paid for their contributions. Oh, you look unhappy with this idea.

**Edith: **I think they should, but I think then that there is this myth that I should just get paid to do whatever I want.

**Paul: **Yes. That is a problem with the idea. And the other problem with the idea is that there will always be people who want to do open source for whatever reason that they want to do it. They'll always be competition coming from people who are doing it for free.

**Edith: **Yeah. That was a good summary of open source morphing more into corporations, but there are still people who honestly believe in it.

**Paul: **Who believe in open source?

**Edith: **Yeah.

**Paul: **For sure. But what is the goal? When you say you believe in open source, what do you believe that open source is? What is it for?

**Edith: **No, I said there are still people who believe in open source.

**Paul: **Oh, you don't believe?

**Edith: **I feel like you're trying to force me into an answer.

**Paul: **I'm thinking of a conversation I had. I got to meet Gerald Sussman, who is one of the guys who popularized Scheme, and he's an MIT professor--

**Edith: **I actually learned Scheme when I was a kid.

**Paul: **Then you might have used his book.

**Edith: **Yeah, because I learned Scheme when I was 10-11, it was the most useless language ever. It's basically a teaching language. It's good for learning but you can't do anything.

**Paul: **As well as being this fabled MIT professor, he's also on the board of the free software foundation. We spent an incredibly arduous hour arguing with each other. This was a complete waste of time for both of us.

**Edith: **More argue-ous than our podcast?

**Paul: **No, it was just this thing that started out as being discussing free software vs. open source, and so on. He's really into the Richard Stallman school of things. And my position was that perhaps free software would have done better if it didn't have Richard Stallman as its figurehead.

He vehemently disagreed and we were just starting at different places, and his goal is free software. And my goal is, "There should be software. People should build things, and--"

**Edith: **But they should get paid for it.

**Paul: **I don't even think that. I don't think that they shouldn't get paid for it, but when I produce open source software I'm not there for the goal of getting paid for it.

**Edith: **But I do mean if you have a corporation you have an obligation to the people who are working for you to pay them.

**Paul: **Oh yes. That is important. People should have roofs over their head and be able to feed their family, this sort of thing. We weren't disagreed on that.

**Edith: **I know our team believes in our mission, but they also show up every day because they get it.

**Paul: **They get paid.

**Edith: **Yeah.

**Paul: **You're saying you do pay your team?

**Edith: **Yeah.

**Paul: **OK that's good.

**Edith: **There was a scandal about that company Plynk.

**Paul: **Which one?

**Edith: **In Ireland.

**Paul: **Oh.

**Edith: **It was held up as this huge success because they raised $25 million Series A.

**Paul: **What's it called?

**Edith: **Plynk.

**Paul: **Never heard of it. In Ireland?

**Edith: **In Ireland.

**Paul: **They weren't paying people?

**Edith: **It turned out that they announced this huge round of $25 million, they were hiring people, and then they weren't paying them.

**Paul: **How did they convince them to come into the office?

**Edith: **I don't know.

**Paul: **There's this whole thing about the unpaid interns and the people who can only afford to be unpaid interns because their family is already rich, and this sort of thing.

**Edith: **We pay our interns.

**Paul: **Yeah. Software is one of the only industries, or at least it was one of the only industries that paid its interns. But it won't pay its open source contributors.

**Edith: **I remember I was looking for a summer job when I was in college. It was interesting because if you were in the humanities you would go and you would not get paid, but I was in engineering.

**Paul: **Yeah, you got paid a lot.

**Edith: **I got paid a fortune for me at the time, which was guess how much?

**Paul: **When you were in college, so that was the '40s.

**Edith: **We were using punch cards...

**Paul: **I don't know. The translation to modern amounts would kill me.

**Edith: **$12 an hour.

**Paul: **$12 an hour? After you I had a job at €7.50 an hour as a software engineer.

**Edith: **This was a huge step up, because for work study at the time I was getting minimum wage which was like $4.50 or something.

**Paul: **Back to open source. This idea of paying contributors, it's an excellent idea but there is a lack of an organization around that happening.


<blockquote>I had this idea awhile back that someone should make a company, maybe it's a nonprofit or whatever, around getting every company that uses open source to contribute. </blockquote>


And my idea was that every company would contribute 1% to revenue, 1% of VC dollars, and every person employed in software to contribute 1% to their annual salary. And that it would somehow be redistributed amongst the people who actually built. This was around the time that Open SSL was a disaster, and everyone was building these empires on these crumbling foundations.

**Edith: **The trick is, how do you redistribute it? To loopback for a second.

**Paul: **That would be the challenge.

**Edith: **Back when I was moderating the mailing list I was part of the Lean Startup group. Because this was the early days, it was 2008. And this other guy had this idea that he could get paid to volunteer. And I said, "Look. You cannot afford me. And the amount you want to pay me is so insulting--"

**Paul: **Yeah. I wouldn't do it for cheap. I would do it for free, but not for cheap.

**Edith: **Yeah. "I'm volunteering because I believed in the Lean Startup cause and I wanted to give back. But if you pay me $15 or $20 an hour to moderate this list, the insult is just not worth it. I'm not doing this for the money."

**Paul: **I had a similar thing. This company wanted to partner with Circle CI. And it was like, "We'll pay you $100 per lead that we get." And I'm like, "What the fuck are you talking about? No amount of money could be worth what we're going to give you. From 500 leads we make $50,000? That's two weeks salary," or something at the time.

**Edith: **Was this LaunchDarkly?

**Paul: **It was not.

**Edith: **OK. Good.

**Paul: **Did you guys propose that? Because that's ludicrous.

**Edith: **No, we would not have. No. The issue is what you just said. The issue of how to divide it up becomes very problematic.

**Paul: **Whereas doing it free, it's like, "You scratch our back we'll scratch your back." Or there's something else in it or something intrinsic in it, or there's a whole lot of promotion, etc.

**Edith: **For me, for volunteering it was like, "This is my time when I give back."

**Paul: **But you get something out of it.

**Edith: **Yeah. I volunteer right now for my accelerator. I give fundraising advice to a lot of people, including people you know. And I don't charge for that.

**Paul: **Exactly, yeah. No one charged me for it back in the day.

**Edith: **It would be weird if somebody said, "Thank you."

**Paul: **I don't know if you got this in the early days, but there are people around who are like, "Yeah. I will advise your company."

**Edith: **Stay away from them.

**Paul: **There's a category of people that do it well. These are people who do it who are experienced and who do it professionally, and who commit to a certain number of hours.

**Edith: **Yeah.

**Paul: **Like coaches. Not quite coaches, but something along those lines. That's good. But there's a lot of shysters in the ecosystem.

**Edith: **What I was trying to say is LaunchDarkly has advisors and there are people who were spending enough time with us that we said, "We should really be giving you some shares."

**Paul: **For sure. There was a point at which I needed more focused advice and I was talking to a business coach for lack of a better term, and there was an agreement and there was cash and there was shares and all this sort of thing. It didn't end up happening for a bunch of reasons. But there was a fair and equitable contract being reached.

**Edith: **Yeah. This is advice I give startups. There's people who I advise for free. I just like giving back.


<blockquote>If you're starting to ask a lot of somebody's time, you should be comping them in some way. </blockquote>


**Paul: **Open source needs a bunch of things to make your project successful. So that we're marketing, community--

**Edith: **Product management and vision.

**Paul: **Vision. That was probably the biggest one.

**Edith: **Yeah, "What are your goals?"

**Paul: **A roadmap, a direction. And maybe some technical writers.

**Edith: **Yeah.



























































