---
author: andreaech
comments: false
date: 2015-10-22 00:10:31+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-the-fear-of-shipping/
slug: to-be-continuous-the-fear-of-shipping
title: 'To Be Continuous: The Fear of Shipping'
wordpress_id: 681
categories:
- To Be Continuous
tags:
- A/B testing
- continuous delivery
- SaaS
---

In this segment of [To Be Continuous](https://twitter.com/continuouscast), Edith Harbaugh and Paul Biggar talk about the fear of shipping and if code is an asset. This is podcast #5 in the To Be Continuous podcast series all about continuous delivery and software development.

This episode of To Be Continuous, brought to you by Heavybit and hosted by Paul Biggar of CircleCI and Edith Harbaugh of LaunchDarkly. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.


Paul: Okay, so one of the things we wanted to talk about this week was the idea of shipping velocity and how it’s affected by team structure, sort of miscellaneous factors that aren’t part of continuous delivery.

Paul: So at the end of the last episode, Edith, you said, I think this was a quote from Yammer VP, “The organization you design is the software you built.”

Edith: Yeah, it was actually from the [CTO Adam Pisoni](https://twitter.com/adampisoni) and it really struck home from me because I see this at so many companies, they have a lot of engineers and they wonder why they have a lot of code but not a lot of product. And it ties back to what you just said of specializing the product management role.

Paul: Right. I think that this a name. I think it’s [Conway’s Law](https://en.wikipedia.org/wiki/Conway%27s_law) and the way that I saw that expressed is that if you have, if you’re building a compiler and you have four different teams that are building a compiler, you’ll end up with a four-pass compiler.

Edith: There’s no one vision.

Paul: Right. When looking at lots of different teams and team structures, the interesting one that I found was the Heroku one.

And they have a language team and they have an add-ons team and they have sort of sharp delineations in their software, or in their stack, that allows them to really focus on one particular area because they’re such sharp demarcations between the different areas of the product.

Edith: I think that’s good if you’re a fairly mature product. I think in the early days of Heroku that would not have worked at all.

Paul: I wouldn’t say it’s quite from the early days, but relative to now it was quite early, I think they had that in Cedar, which was around 2010.

Edith: I just more meant when you’re an early stage start-up, sometimes you change your entire product.

Paul: Well okay, yes, yes. I mean, absolutely. I think once you get into, once you get past the first stage of the product, and if you’re able to draw very good interfaces between how your customers understand what your product is.

Edith: I don’t know, I mean I’ve seen this go bad in so many organizations, where you have entrenched engineering organizations that care more about staying on their current project, then actually about where the market is going.

You know, like we’ve always worked on this, so we need to stay here because we don’t know anything else versus being able to evolve to where the market is going.

Paul: Right. This reminds me a little bit of something that I’m working on at the moment. We brought in some UX experts to look at our app and to help us sort of transform it into something that was a little more usable.

And they did a fantastic job and I spent this afternoon reading some of the reports. But what was difficult was understanding where the product needed to be. So for us in particular, there’s not enough focus on the deployment.

There’s a lot of focus on the build and there isn’t really sort of a broader look at what do engineers actually do when they’re trying to do continuous delivery. And so we ended up with what was in the product was redone in a really fantastic way, but there wasn’t much affordance made for here’s the thing that actually needs to be in the product.


<blockquote>And when you talk to customers, it’s hard for customers to tell you oh here’s the thing that you actually need to be or they look within the box you’ve drawn for them.</blockquote>


Edith: Yeah. I say this ’cause I had a similar evolution to you, I actually started off in engineering. And when I was in engineering it was very obvious what we should build next, extremely obvious. And so I always thought that our product manager was an idiot for not seeing as clearly as me. When I became a product manager, I realized how myopic I had been as an engineer.

Paul: Can you give an example of what was the next thing to build that in retrospect was wrong?

Edith: I would see all the little bug fixes that we should be doing instead of the next big features. Or not even the next big features, but the next big product.

Paul: I think big or small, or big picture versus small picture, is a good way to distinguish these two. I think that it’s very easy when you’re talking about product management to get the idea that a product manager knows everything and the engineer is just an implementer.

And I think this is where a lot of the resistance to product managers comes from with an engineering organization’s the idea that they’re going to be relegated to mirror kind of peasants in the…

Edith: Code monkeys.

Paul: Code monkeys, there we go.

Edith: You know, nobody wants to be a code monkey. That doesn’t sound very fun.

Paul: Right, right. I would disagree with that, but I think that’s–

Edith: Wait a second, we never disagree.

Paul: It is very frustrating trying to understand everything. And on the other hand, it’s very satisfying to ship things and to get your stuff in front to customers. So very often, the ability to just be a code monkey for a certain period of time is this sort of soothing feeling of just shipping software that fixes a lot of small problems.

I remember reading one of the famous GitHub guys, I don’t remember which one it was, but let’s assume it was [Kyle Neath](https://twitter.com/kneath?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor), that spends a lot of time on big projects. And in between the big projects, he needs to find what is the next big project to work on.

And it’s often very frustrating, or very you go down certain rabbit holes and whatever, and you end up kind of not shipping things, or you end up getting frustrated or whatever. And what he likes to do then, is just reach to the back log and just take a bunch of small fixes. And he spent like two weeks of just like implementing very small things.

You don’t need to think about it, and it’s cathartic and it lets you ship and so a couple of weeks as a code monkey I think is a very useful thing to sort of refresh the head and that sort of thing.

Edith: I agree, but I think nobody wants to do that full-time and I’ll also challenge something else you said, which is everybody wants to ship.

I think there are a lot of people who find shipping terrifying. and they’d rather keep holding stuff on until it’s perfect... Like, I’ve certainly been with in situations like this where it’s like–

Paul: Right, where we can’t ship because it’s not perfect yet or it’s not complete.

Edith: Yeah, and as an engineer you have this real battle of well what if people want this, or what if they want this or this might be not quite right.

Paul: Yeah. The personal strategy that I use to manage that is to try to write the blog post that you’re going to launch this with and to, cause very often you’ll be like, “oh I can’t launch this cause it hasn’t got this feature, it hasn’t got this feature.”

And in the blog post, assuming that you’re going to tell people how to use it, or you’re writing the doc maybe, if not the blog post. You get that sort of feedback as you’re trying to explain to your user how to do this you’re going to say, all you need to do is this, and you’ll realize that this is seven steps long instead of one step long.

Edith: Yeah, the Amazon model. So at Amazon, they actually start with writing the press release first.

Paul: Okay, right.

Edith: And everything and that’s a really good guide back.

Because too often, people do the other end of they’ve built this gargantuan thing and they’re trying to write a press release or blog post and they’re like, whoa, we’ve built all this stuff but there’s nothing actually to talk about.

Paul: Right. And part of that, and something which I think engineers have a difficult time thinking about is how to get this widely in use. So you can build the feature, but its no use having built it if no one uses it. So you need to build the breadcrumbs, you need to figure out the ways that are subtly hinted that this is the feature that you want when it’s the feature that you want and to draw people’s attention to it.

And sometimes that’s putting it in docs and sometimes that’s doing a big announcement, but more often it’s trying to get the product in a place where the UX naturally implies the right path or the right direction for users to discover parts of the product.

Edith: Yeah, I mean the whole idea of responsive design, and I think even more, and this goes back to why I started LaunchDarkly, is you might have built it, but nobody might want to use it.

Like, you could have put all this effort into building it and done all these breadcrumbs that nobody follows. So that’s the idea of you actually start doing the bread crumbs first and see if people start following that path.

Paul: So with LaunchDarkly, I’m guessing that the way that you see whether someone is using it is whether it’s enabled for them. Is that right?

Edith: Well no, so what we do is we allow people to turn on features for certain users.


<blockquote>Just turning on a feature for a certain user doesn’t necessarily mean that they start using it.</blockquote>


Paul: Right, exactly. So do you tie this to mixed panel usage? Or some sort of analytic stuff?

Edith: We could tie it to different back ends, like we tie it to New Relic, we tie it to actually optimize so you can see if people are even, and we have our own internal analytics.

Paul: Gotcha, okay. So this is the thing for me, that I started a project recently, and the first thing I did is built the dashboards for adoption. And we’re still at the stage in the project where there’s no adoption, or there’s tiny amount of adoption amongst early users.

A trickle. A trickle that you can’t even see on the graphs.

Edith: So it’s more like a fine mist.

Paul: A fine mist. But what you need to get is you need to get to the place where everyone is using this. ‘Cause if you just build it, they’re not going to come.


<blockquote>They need to be told about it, they need to understand how to use it, and getting those first customers to using it and where it’s deployed amongst them is it gives you incredible feedback about how one actually ships that software to the larger customer base.</blockquote>


Edith: Totally agree. I mean, this is classic Lean principles of just making sure some people can use it well before rolling it out further.

Paul: We discovered a part of the product that exactly three customers were using.

Edith: How did that make you feel?

Paul: Well, we didn’t actually know it was a feature. This was the idea that you could do deployments in parallel. So at CircleCI we paralyze your build and so the idea is that basically we take your test suite and split it across 20 or 50 or whatever machines.

But it turns out that that applied to deployment as well. And there were exactly three customers using that. And one of them had a valid use case for it. Out of thousands of customers, exactly one valid use case was there.

Edith: So what did you do with the feature?

Paul: We killed it.

Edith: Did you tell him?

Paul: I hope so. Yeah, I know. I think we reached out to that guy. There was another way for them to do it.

Edith:


<blockquote>The painful part of project management is also when you have a feature that you like to kill but that a subset of power users loves.</blockquote>


So like at TripIt, we’re a mobile travel itinerary but we let people do a printout. And one time we’re like, oh nobody prints anymore, let’s just kill it. Turns out that people print and they really really like printouts.

Paul: Right, right. I understand that, yeah.

Edith: Like particularly if you’re traveling to a foreign country.

Paul: Yeah, you’re not going to have internet or your phone’s going to be dead.

Edith: Or you want to show something to a passport guard.

Paul: Yeah, or a local. Without handing over your phone, like here’s what I’m doing.

Edith: Yeah, so they were furious with us.

Paul: Right. So, had you killed it at that stage?

Edith: Oh we killed it. Like we were just like oh, we didn’t have good analytics on people printing, so we just said oh nobody’s printing, let’s kill it.

Paul: Oh, wow wow.

Edith: So our analytics later was that people complained. Quite loudly.

Paul: And so had you properly killed it at that point, or had you merely disabled it to see if it went away?

Edith: Let’s see. We disabled it. I think we could get it back but people were really really upset.

Paul:


<blockquote>I like the thing of shipping something turned off, rather than actually deleting the code. Even though it’s incredibly cathartic to delete the code and to hide and it and remove it. But the turning something off with a feature flag is just a lot better way to sunset something.</blockquote>


Edith: Why do you think it’s cathartic?

Paul: Oh deleting code is amazing. It’s like my favorite thing to do.

Edith: It’s funny. My cofounder [John](https://twitter.com/launchdarkly), he was from Ex Atlassian, and he said the winner of their hack competition was always the person who deleted the most code.

Paul: Right, right. That makes perfect sense.

Edith: Cause that’s what they wanted a reward is tidiness.

Paul: Yep, yep. It’s very much related to the idea of product management and validating things and making sure that you don’t build too much of the product. Code is not an asset.


<blockquote>Code is an asset in the financial sense of it in that you think you want it but you actually don’t. You actually want the best performance with the least amount of code slash asset available.</blockquote>


Edith: Yeah it’s like, so a friend asked me once, should I pay my developer’s more if they write more lines of code? I was like, no. It was like no, that’s a really easy metric to gain.

Paul: Right. So we were talking about deleting features by feature flagging them. I think that this is an awesome way to delete a feature because it’s very, very easy to get back. It’s much easier to get back than a rollback.

Rollbacks are this thing that nobody wants to do because they’re very, very painful. Especially if a ton of code has come in between. So if you ship something, or if you delete something by literally putting a feature flag in around it, and then you ship the code and then it’s still on, and you turned it off for a certain amount of people, see if anyone complains, see that it still works and that you know, show it to ten people, and then you delete it for everyone just by flicking the flag.

And then if you get someone saying, you know, we really, really, really need print it, You can turn it back on for them while you have a think about how you really want to solve this problem.

Edith: Yeah, I think feature flags is a really misleading term.


<blockquote>So feature flags implies that it’s always on or off, when really it’s more of a feature control.</blockquote>


It’s a way to encapsulate a portion of functionality such that you have total control over it, from the sunrise of it, you know, from launching it to certain people, seeing their reaction, getting analytics, and then all the way to the end, as you said, every feature eventually you want to kill.

Paul :     There's an interesting parallel here between feature flags and the configuration variables. By configuration variables, what I mean is, in a rails app, you often have a set of four different environments. You have dev, test, staging and production. You often get in trouble in that you fill your code base full of, "If dev, this," or, "If n is production, then do this." What you really want, is you want to be able to say, "If we have enabled the x feature, if we're using SSL," is one example of a thing that might be on in some configurations, but wouldn't be on in other ones. In the closure ecosystem, there's this idea of a component. Where, you build your application as a set of components and all of the variables through our components are passed into it. The variables are essentially feature flags. Are things disabled? Are they enabled? What is the setting that is built on it? It makes it very easy to compartmentalize functionality and to only expose a simple interface that allows you to control how the functionality works, without necessarily having to dive into the functionality all the time.

Edith:     That's exactly my vision for LaunchDarkly. That everything should be controlled.

Paul :     Right. You should like into the closure idea of components. It's a very sort of ... The closure people speak in very theoretical abstractions and that sort of thing. They use weird words like complecting. It's a weird thing, but they actually really know what they're talking about, which is even more annoying.

Edith:     That's always the worst, right?

Paul :     Yeah, so someone invents their own vocabulary and then they're right, so you actually have to discover what they mean by this vocabulary. Then no one else understands the vocabulary. So complecting is an interesting word, in this case. It means unnecessarily tied together, or it means that it's not complex, but it's two things that are like ... It's the opposite of simple, basically.

Edith:     That was the ...

Paul :     The idea that you have two components and they're two widely connected, or complected.

Edith:     Yeah. What do you think is a better word than feature flag, when really it's more about feature controlling or feature wrapping?

Paul :     I used to feel that there were different concepts for feature flags versus AB testing. That they were actually different concepts. I'm now convinced that they are the same concept.

Edith:     This is interesting, because I think AB testing is just something that is enabled be having an unwrapped feature.

Paul :     Something that is ... Say that to me again.

Edith:     If you've wrapped all your features, as I talked before, you can launch them, you can monitor them, you could sunset them, and you could also compare them.

Paul :     Right, right, right. Yes, so an AB test is really a feature flag which is enabled randomly for a certain subset of customers and you're looking at the analytics.

Edith:     Yeah, so it's just an extension of ... If everything is an object, and nicely, as you said, a wrapped object, it's then you could say, "Oh, is this object doing better than this other object?"

Paul :     Right. Okay. The thing that I found really weird in looking at how people talked about AB tests versus feature flags, weird because those are the same concepts, but AB tests are a marketing thing, or growth thing. You tie them to business goals or to KPIs, or to funnels, or something along those lines. Features, and especially the kind of operational side of features, you tie to database latency and basically operational metrics. There's not difference between business and operational metrics. Every AB test should be tied to operational metrics because it's no good knowing, "Oh, no one buys on this thing." If the reason no one buys on it is because the exceptions are through the roof.

Edith:     Yeah, you ...

Paul :     Similarly, there's no concept of, "This feature works really well if the database load is really low." Oh, the database load is really low because no one is clicking down that path. Your business metrics are through the floor.

Edith:     You're absolutely right. I think one of the goals of LaunchDarkly is to provide analytics on everything. I do think what I found when I was talking to customers is there's a lot of fear around AB testing. Just the word, I think, has been overloaded that people ... Give Max from Heroku, who sits down the stairs from us, they love feature flagging. They feature flag everything. He doesn't think of it as AB testing. He's like, "If you said do I AB test?" He would say, because that implies that you're really doing more of a test of an old versus a new and picking which on is better. Really, it's more he has a new feature and he wants to make sure the metrics are correct.

Paul :     Right. When I would advocate for AB test in the past, it was mostly to say, "Does this perform not worse than what was there before?" Someone to have a new design of something and they think it's great. We'd all agree that it looked a lot better, but does it convert better? In fact, not even does it convert better, because if it looks better and it converts the same, we should definitely go with it. Does it convert not worse?

Edith:     Yeah, the issue is most people don't have the traffic for AB testing.

Paul :     You can make AB tests work at a small scale.

Edith:     If you're a SaaS company with maybe 300 customers, you don't have enough volume to do AB testing.

Paul :     You don't have ... No.

Edith:     You could be quite profitable and very happy with those 300 customers that are each, like, 100K a year.

Paul :     AB testing is a test of statistical significance, right? On a small scale, you need a lot of people. To be able to tell small significance, or small differences, in the result. You know, 5% versus 6%. You need a large number to people to have any confidence in the statistical significance.

Edith:     Yeah, so if you have a feature ...

Paul :     You can tell the difference between 80% of people get through your funnel and 20% of people get through your funnel, with 50 customers.

Edith:     If you say ... So that stuff you have a feature that you use at the very top of the funnel. What I was trying to say is if you have something that people might not see very often, it's very hard to AB test it. If you look at a funnel ...

Paul :     It's also very hard to get ...

Edith:     You have your marketing site, which gets the most. You have your signup, which gets the most. Then the further down you get into product, the harder and harder it is to do AB tests.

Paul :     Especially if it's something where you don't have the funnel, necessarily, or where you have a funnel, but you haven't constructed a funnel. One of the ways I think about software is that everything is a funnel.

Edith:     Yeah, life is a funnel.

Paul :     Life is a funnel. Hiring is a funnel. Your jobs page is part of a funnel, but you don't actually have a mix panel thing built on your jobs page. Making any change to your jobs page, means that you don't actually know if it's had a positive effect, or a negative effect. You can't really tell anything about it.

Edith:     That's very true. On the other hand, if you're getting only like one person applying a month anyway, it doesn't really matter. That's still in the realm of statistical insignificance.

Paul :     Right, so you have no controls over something goes out, you just have opinions. Whereas on the home page you can have data and then on your jobs page, you can argue that this word that we use here is really off-putting to female developers, or something along those lines. If someone disagrees with you, you've got nothing to back up your arguments either way.

Edith:     Well actually, a company, Textio, now is doing a lot of statistical analysis of job postings to see if they have ... If the words in them are gender neutral, or not.

Paul :     That's based across a massive corpus of job pages, versus ... It's not maundering your actual through put, or something like that?

Edith:     No, it's just based on ... She's a machine learning PhD.

Paul :     Right. That works for something like gender, or things that are ... Diversity and the general case. It's not going to work on, "Are all the closure developers ... Are they aware that this is a closure shop?" As an example.

Edith:     Yeah and that's why you can't AB test life.

Paul :     If only.

Edith:     No, I mean, that would be horrible. You'd have to do everything a thousand times.

Paul :     Right, right, right.

Edith:     What if some of those thousands were just terrible?

Paul :     Right. You can AB test web pages.

Edith:     No. Not if they don't get enough traffic.

Paul :     Not if they don't get enough ... Yeah. Yeah.

Edith:     It goes back to what you said. You can have through putter latency.

Paul :     Right.

Edith:     You could test every page if you have a thousand years. If you have a low traffic page ... Sometimes, to go to what you said before, you just have to go with, "I feel this color's better. I feel this color pops."

Paul :     This is one of the most frustrating things about developing software. Everyone knows that you should have data and analytics and it's just very difficult to really have any idea of whether you should have analytics for a particular thing. You know you should have it on your funnel. You know you should be measuring what customer they're using. In almost every instance, you can make a justification for just doing it this way.

Edith:     You have to at a certain point.

Paul :     That's what's frustrating. If you could uniquely say, "In every situation, we're going to use data. We're going to use the funnel. We're going to use these analytics." Then you'd be in a great place. Where there are 90% of your webpage or your product, actually don't get enough use to get any statistical significance, and then you end up with only having a funnel on your signup page. Then you don't really have a very data driven company, as a result of that.

Edith:     That's the hard truth. There's still a lot of art in the science. At some point you have to make a decision, like I like ...

Paul :     Unless you're at Google.

Edith:     I'm sorry?

Paul :     Unless you're at Google.

Edith:     Yeah, unless you literally have the world's population using you, you do have to make a decision like, "I think our jobs page should look like this."

Paul :     Right.

Edith:     "I think that our onboarding should look like this."

Paul :     Right. Why? Don't know.

Edith:     Other people do it that way.

Paul :     I just kind of feel it. I think this pops more.

Edith:     Was that an American accent?

Paul :     No.

Edith:     I thought you slipped it on in.

Paul :     No. I think this color pops a little bit more. That's what most arguments about UX end up with, if you don't have high level principles and goals and personas that you're building the product around.

Edith:     That's fair. I think it goes back to what you said before. There's always this tension of data versus gut. What we talked about engineers about making it perfect versus ship it now. I think they go together. The more data you watch, the more you can be convinced that now is the time to ship versus the person who's like, "Okay, it's just time."

Paul :     Right, right, right. When I'm trying to ship something, I try to make sure that my fears are addressed, more than I try to make sure that the thing is feature perfect.

Edith:     That's a really good way to look at it.

Paul :     We shipped this feature that I've been working on and it was just supposed to go to the first 5 customers. What I want to do is make sure that the back end was shipped and then I could test it on our own project and validate, "Does it actually work at all? What does it look like when someone actually uses this in production?" The first thing that I really needed to validate is, "Can I turn it on without causing any problems to everyone?" Or to me and that meant that I have to make sure that there's no problem to anyone. Basically, what I had to do with the feature was insulate it from if it went wrong, in the thousand ways that I couldn't expect it to go wrong, that I knew for sure that it wouldn't affect the rest of the customers.

Edith:     Did you use a feature flag?

Paul :     A feature flag, but also ... The problem in a lot of languages is it's not just a feature flag. You have to wrap the exceptions and make sure that the exceptions get caught and just like end nicely versus going forward. It was something that was on the critical path where everyone's build. If the code went wrong, everyone's build could be affected. I just needed to make sure, no matter what goes wrong in this code base, let the builds continue.

Edith:     The builds must flow.

Paul :     The builds must flow. What I was addressing wasn't, "How do we feature flag this off?" It was just like, "Can I ship this without being fearful of something going wrong?"

Edith:     I think you sum it up very well. Fearful.

Paul :     Right. Continuous delivery is mostly about fear more than anything, I think.

Edith:     I think it's about mitigating fear because it's very freeing that if you could turn something off at any time, you could move forward.



Paul :     Right and if you ship something and you know that it's not going to break things ...

Edith:     You could ship it.

Paul :     Right. Exactly.

Edith:     I think it's when you have these big bang releases where it's everything all together in one kluge, that you have a lot of fear.

Paul :     Yup.

Edith:     I had a customer who said they stopped doing continuous integration, sorry, because it was faster to not. They were just ...

Paul :     Let me just predict how this ended up.

Edith:     Have you seen this movie already?

Paul :     I've seen this movie so many times.

Edith:     You saw...

Paul :     Every iteration of this movie.

Edith:     Every thousand?

Paul :     Yup.

Edith:     How does the story end?

Paul :     The story ends with software not being able to be delivered. Engineers quitting, is a common ending, or at least last chapter surprise. That like, "Oh, we're shipping so fast." No, we can't ship anything because it's so frustrating to ship things because we just don't know if it's going to work.

Edith:     How do you ... That's the end of the story. What's the next chapter?

Paul :     After the end of the ... What's the sequel?

Edith:     What's the sequel?

Paul :     The sequel is they bring in a new VP of Engineering. The VP of Engineering says, "What the hell? There's no testing." The VP of Engineering sets up testing. Everyone complains about testing and that everything was much faster before testing, but they have to do what the VP of Engineering says. In about a month, they realize their velocity is about 10 times faster than it used to be and everyone who complained about testing is actually happy.

Edith:     Yeah. That's what happened at our customer. They said they stopped doing testing because it seemed to take too much time. They got to the point where they couldn't ship. They were like, "Actually this is the same as like basic housekeeping." You can't just not do your dishes everyday for 2 months and expect ...

Paul :     Was there anyone fired on this journey?

Edith:     No, they came to a pretty quick realization.

Paul :     I think they probably got lucky there. People have been fired for less.

Edith:     Oh, really?

Paul :     If you're in charge of a software team and you bring out something that brings the team to a halt, maybe a little encouragement to your boss that you actually did know what you were talking about in the first place.

Edith:     I heard this legendary story that Salesforce, they got to such a state that it took them two years to ship anything.

Paul :     Wow.

Edith:     They fixed it. They fixed it because they realized this is a problem. It takes us two years to ship anything.

Paul :     Right.

Edith:     Well Paul, it was fun catching up with you about product management and how to AB test, or not.

Paul :     Whether AB testing is the same as feature flags. It is.

Edith:     Oh, Paul, we always agree, but not on this one. I would say, all right ... I would say that you can AB test if you have feature flags, but I don't say you have to AB test if you have feature flags.

Paul :     I think this is just language. AB testing is ... The way that I look at feature flags ... We have feature flags that sit in a bunch of different places. We have feature flags of, "Do I enable this on this machine?" We have feature flags for, "Do I enable it for this customer?" Then we have feature flags for, "Do we randomly enable this across the customer base and what proportion do we use?" They're all some form of AB testing. They're all some form of feature flag. I don't see a distinction between them at all.

Edith:     I think because in customers' minds they think of AB testing as some sort of statistical thing, where they'll get a deterministic result. Whereas, sometimes they're using a feature flag just to roll out a new feature and expose it to some users.

Paul :     Would you classify it as an AB test if it's statistical and not an AB test if it's not statistical?

Edith:     Paul, I actually agree with you. I was just saying, I've talked to a lot of customers and when you say, "AB testing," it puts a lot of fear into them that they have to ...

Paul :     Right, right. I agree that a lot of people see a distinction between AB tests and feature flags. I think my point is this. I've come to the conclusion that there is no distinction.

Edith:     I think we actually agree, after all.

Paul: Thanks for listening to this episode of "To Be Continuous," brought to you by Heavybit and hosted by me, Paul Biggar of CircleCI and Edith Harbaugh of LaunchDarkly.
