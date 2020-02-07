---
author: andreaech
comments: false
date: 2016-04-26 23:40:07+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-devops-2-0/
slug: to-be-continuous-devops-2-0
title: 'To Be Continuous: DevOps 2.0'
wordpress_id: 894
categories:
- DevOps
- To Be Continuous
tags:
- AB tests
- continuous delivery
- Dev Ops
- devops 2.0
- Facebook
- feature flag
- Google
- Michael Dearing
- Optimizely
- startups
---

In this episode, Edith and Paul discuss the emergence of the term DevOps 2.0 and try to decide what it means, they talk about the incredible early validation powers continuous delivery gives your team, and they denounce the unnecessary risks of April Fools jokes not backed by continuous delivery. This is episode #18 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.





**TRANSCRIPT**

**Edith:** Hey Paul, so I've been talking to different people lately about DevOps 2.0.

**Paul:** Okay, what's DevOps 2.0 exactly?

**Edith:** Well I have to preface, when I said DevOps 2.0, Jesse Robbins wrote me and he said, "I hate that term," so I knew I was onto something good already.

**Paul:** Right, right. If Jesse hates it, you might have something.

**Edith:** I like Jesse. He's Heavybit too, but you know. I think a lot of DevOps 1.0 was about making the pipe go smoother, and by the pipe I mean the release pipeline of getting bits from a developer's box out to production.

**Paul:** So smoother means less latency, or more predictable latency?

**Edith:** Less steps, more predictability, easier to do a build. I was talking to...

**Paul:** Developers less annoyed.

**Edith:** Yeah, I was talking to the Microsoft folks because we just did a big partnership with them, and they said in the old days of Microsoft Windows it would take 24 hours to do a build. 24 hours, just...

**Paul:** Yeah, I worked at Mozilla - we had a similar lag. Same order of magnitude.

**Edith:** 24 hours?

**Paul:** I had a 15 hour one once. Oh and it broke in the middle. It broke at 3:00 am when I'd gone to bed.

**Edith:** Oh no.

**Paul:** And then when I woke up people'd been yelling at me because the build had been broken for 12 hours. It was a Saturday at 3:00 am.

**Edith:** It's a good thing you were asleep, so you couldn't hear them.

**Paul:** Builds that go that long, or at least pipelines that go that long are inherently frustrating.

**Edith:** Yeah, they're very frustrating, and what happens then is you build up a culture around, "Hey a build is going to take 24 hours, so let's only build when we're very sure of things. We can't take any risks because if something happens halfway through..."

**Paul:** It's very defensive. You end up optimizing around your own processes rather than removing all the accidental complexity of shipping software.

**Edith:** So I think the first wave of DevOps has been making that process a lot smoother, so tools like Chef, Jesse's company, tools like CircleCI, and Ansible have made it shorter and quicker to do builds. So now when people throw around 24 hours, people laugh at you. What I think has happened at a lot of organizations, though, is they still have all this institutional scar tissue from when a build did take a long time, and they haven't really changed a lot of their processes to take advantage of builds being cheap and easy.

**Paul:** Is this kind of like when people talk about doing agile, but really they're doing some sort of waterfall model with stand up meetings?

**Edith:** Yeah, well there they do a stand up meeting where everybody sits down, which I've seen. They have their hour of stand up every day where they'll get into a room and sit down and talk.

**Paul:** I saw some company that changed its meeting to plank meetings, so whenever you're talking you have to be in a plank.

**Edith:** Was this part of the interview process, or like...

**Paul:** I think the idea is to shorten meetings, because you can't really hold a plank for that long.

**Edith:** Yeah, I think my max... I don't even...

**Paul:** I think your max would probably outdo most people's max in the industry. It's generally a not very healthy industry. And you're an ultramarathon... What exactly do you do?

**Edith:** I run 100 miles.

**Paul:** There we go.

**Edith:** But that's good for leg strength, not for arms.

**Paul:** All right, well your meetings will be short as well then.

**Edith:** Well thank you for the compliment, and by the way the LaunchDarkly shirt looks very attractive on you today.

**Paul:** Thank you, thank you. So DevOps 1.0 is a smoothening of the pipe, so DevOps 2.0?

**Edith:** Is the realization that if we have a world where we could do a release in 5 minutes, or 10 minutes, how does that change how we approach how often we release? How does that change how departments within an organization work together?

**Paul:** Gotcha, gotcha. It's probably no coincidence that my mind is screaming feature flags at this point.

**Edith:** Oh really?

**Paul:** When you think about releasing software every 5 minutes, the thing that comes to mind is validation, that you're now able to validate things incredibly quickly. I've been talking to a bunch of people about how they do their CD processes, and sometimes people are like, "Well it's great, we'd love to be using CircleCI, but it takes us 3 months to release software and I would love to change that, but..."

I've gotten to the point where I just don't understand how to release software with 3 month cycles anymore. It's like


<blockquote>whenever I talk to young companies, the only thing I say to them is, "You need to validate. You need to validate your business model, you need to validate that your products get to product market fit, or minimal viable product, and iterate your way there."</blockquote>


And so the idea that it might take you 3 months to get some software out, I just don't know how anyone can ever achieve validation. You would have to be lucky.

**Edith:** That's the whole idea of a lean startup, is that you're taking more at bats.

**Paul:** Right, so I agree with it completely, and I guess what I'm saying is, I don't understand anymore how it could be done the other way.

**Edith:** These 3 month companies, are they young startups or are they more midlevel mainline companies?

**Paul:** There's a bit of both. A lot of the people I hear from are those larger companies where it's like, "We're trying to change things around, we're trying to grow agile, or there's a [ScrumMaster](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=0ahUKEwiK-YLnlbnVAhVJOCYKHZdwChkQFggyMAE&url=http%3A%2F%2Fwhatis.techtarget.com%2Fdefinition%2Fscrum-master&usg=AFQjCNGLP9vznISJROAqL_9rPZsc_IshCw) coming on board," so they're trying to turn themselves around, but don't really know what it means, and are cargo culting it a little bit. And then the other ones are startups that say, "In 6 months we're going to have a release, and it'll do this," and I'm like, "What the fuck are you thinking?"

**Edith:** In 6 months you're going to be... Yeah, you're either going to be out of business or your competitors will have swum past you...

**Paul:** It's the same sort of people who are like, "We're just going to outsource this. We just need like $30,000, we'll pay this outsourcing company, and they'll deliver us the product." It just blows my mind every single time. I don't even know the starting point to go back and explain to them how wrong they are.

**Edith:** All right, so let's separate out the use cases. I think there's (1) startups, and then there's (2) mainlines.

**Paul:** To me, it's all validation. It doesn't matter whether it's startup validation, or it's our next feature or what our customer need validation. It's just all...


<blockquote>The software that you're developing is a hypothesis that it will deliver value for the user</blockquote>


and sometimes you have a lot of confidence in your hypothesis, and a lot of times there you still end up being wrong, and a lot of times you think it's a good idea, but really you have no idea how much it's going to get used.

**Edith:** I think there is a twist, that I think startups worry that nobody will use them. If you're an established company who already has customers, you worry that you'll break something existing, and that's where a lot of the fear comes from. I'll give you...

**Paul:** Right, here's why I get back to feature flags, because it lowers that risk. You can say, "I have this hypothesis that no one uses this feature." I talked about this at the web summit - I don't think I mentioned it on the podcast - about how I broke Gmail in Firefox. Did I mention this on the podcast?

**Edith:** Did it involve [a minion gif](https://techcrunch.com/2016/04/01/google-reverses-gmail-april-1-prank-after-users-mistakently-put-gifs-into-important-emails/)?

**Paul:** Oh my God, that's the greatest example of why you need continuous delivery. They didn't validate that, right? They didn't do any bug validation. They just launched it on hundreds of... I guess a billion users now, without any validation, and there was 2 bugs that caused people to have that minion gif sent to their funeral homes and their bosses, and people who they're applying for jobs for, and very serious topics.

And maybe it's because it was that April fools thing that there wasn't an opportunity to continuously deliver it, or... They could probably have done something, or slow-rolled it around the world, or something... But it is a key example to me of why continuous delivery lowers risk, and how not doing continuous delivery like Google did in that particular case is super, super risky.

**Edith:** Well hold on, because they did do continuous delivery. They just didn't use a feature flag.

**Paul:** They may have done a feature flag, but they didn't slow roll it.

**Edith:** Yeah, so I think everybody agrees that Google uses continuous delivery.

**Paul:** Yeah - yeah, yeah, yeah. And I'm sure that was behind a feature flag.

**Edith:** You think it was?

**Paul:** Right, because they needed to... They were going to delete it the next day.

**Edith:** Yeah, I don't know. I think it was just poorly executed. I think it's interesting that they thought they were funny and they weren't, and then they had no way to recover from it very quickly, because Google has such a big customer base. But I think that's separate than...

**Paul:** They could have found out that they weren't funny at a much smaller scale.

**Edith:** Much like me and my jokes?

**Paul:** The fact that they didn't discover that they weren't funny within an hour or 2 of it launching, that it even hit the US market, or that it hit the billions of people... April 1st hits...

**Edith:** April 1st, every year.

**Paul:** Right, but it hits 8 hours... 16 hours? 8 hours... Minus 9...

**Edith:** Minus 9.

**Paul:** Minus 9 is where it starts? That's where the first civilization is?

**Edith:** Well that's England. That's the Greenwich mean time.

**Paul:** So Greenwich mean time is at 0. We're minus 8 from Greenwich mean time, so there's another 4 hours west of us, right?

**Edith:** Depends on daylight savings time.

**Paul:** So there's at least 3 hours west of us, and presumably they could have discovered... I know not very many people live in the area that's 3 miles west of us, but they could probably have discovered before it hit California, before it hit the US.

**Edith:** Australia.

**Paul:** Yes! Yes, there we go. Australia is in...

**Edith:** Australia's actually a day ahead of us.

**Paul:** Where am I... Oh I'm doing this wrong! It goes the other direction. They hit April...

**Edith:** Far be it for me to correct world expert Dr. Biggar...

**Paul:** No you're right, it goes the other direction. So there was actually... Before it hit the US, there was 16... It's minus 5, so there's 17 hours that they could have reverted this before it got to the US.

**Edith:** Yeah, Australia. They didn't.

**Paul:** Right, they weren't reacting fast enough, they didn't have their metrics in place, they didn't have... I don't know what they didn't have, I wasn't there, but that should never have hit...

**Edith:** The states.

**Paul:** It should never have gotten as far as the states. It probably shouldn't have reached Europe. I think it's a little unreasonable to expect 3 hour turnaround time, but like 5... 5 hours to realize this isn't going too well, maybe we should roll it down to like 10 percent; maybe we should only show this to 1 percent of people while we figure out if they actually like it.

**Edith:** Or maybe we should just drop the mic entirely and leave the stage.

**Paul:** Right. Let's just delete this, drop the mic on ourselves.

**Edith:** That's really a classic thing. I'm surprised they didn't do it, because it's very classic for companies to test new products in Australia, and the interesting thing is, I went to Australia for work. Australian companies test new products in New Zealand, because New Zealand is smaller than Australia, but it's culturally...

**Paul:** Right, culturally similar.

**Edith:** Yeah, the same climate.

**Paul:** Interesting.

**Edith:** So this was all basically slow roll stuff out to New Zealand and see how it performs, then take it back to Australia. New Zealand is actually pretty tiny.

**Paul:** So this is quite the diversion. Where did we start?

**Edith:** I think you get these cultural practices around thinking that builds are expensive. I've worked at some pretty mainline companies, and I worked for Vignette, which was a content management system, and the worst thing that we could do was to destroy a customer's data. Anything else was like, "Okay this is bad," but if we destroyed their data it was really bad, because this is like a newspaper, and we're killing all their data. Cardinal sin.

So one time we did an upgrade - we released the new version of our software, and during the upgrade routines, it deleted people's content. Worst thing in the world to do. So what had happened is, we'd shipped this out, and by shipping it out, meant it was available for people to download and start installing. We realized pretty quickly there was this critical bug because we had customers screaming at us. So I was in this engineering meeting where the engineering director, instead of admitting fault and saying, "Hey I'm really sorry that we did this," he started yelling at the operations director, saying, "Why does it take us so long to take a build down?"

I thought this was a total dick thing for the engineering director to do. At the time I thought it was, because he'd just totally screwed up. He'd built this bad thing, and he was yelling at the operations director, "Why is it so hard to replace it with a new one?" And at the time, even though I was in engineering, I thought the engineering guy was in the wrong. Now with hindsight...

**Paul:** I'm not so sure about that one.

**Edith:** Now in hindsight I'm like, "You know what? It should be really easy to replace that."

**Paul:** So it should. I guess to play devil's advocate here: He... What's the engineers name?

**Edith:** Let's call him Thomas.

**Paul:** Thomas. So Thomas knew the bounds that he was working in, so he should have known it was a risky thing - he should have known that he couldn't roll it back, so that sort of bug would have been a disaster. On the other hand, he's totally right, and if he had some sort of organizational mandate to push it forward, which I guess you almost de facto do, to move your release processes forward, which I guess is de facto part of your job as engineering manager... Then that's quite defensible.

**Edith:** Yeah, and


<blockquote>I think this is where the original divide between dev and ops came from, is the developers would say, "We just built it; it's your job to deliver it,"</blockquote>


and there was a lot of mistrust and anger between them for precisely that reason.

**Paul:** That divide between dev and ops, and you see it now that that's... I think the expectation was, when DevOps was starting, that there was dev and ops, and they were merging. And what I'm seeing instead is that they're not merging so much as ops is becoming DevOps.

**Edith:** Yep.

**Paul:** And then there's this separate dev thing, which builds new features, and DevOps is keeping everything up, but in a more Devy way than they used to. I think there was an expectation that the developers would be their own ops people, which definitely some organizations have done, but is (I'm going to say) not as prevalent as people expected it to be.

**Edith:** I think it all depends also - and I keep coming back to the stage in an organization - I talked to a friend at a small startup, and when you're 3 engineers, everybody's DevOps.

**Paul:** Right right right.

**Edith:** And then it's interesting, but then one of them is a little bit more opsy.

**Paul:** Right. Usually what you see is someone who sys-admined in the late 90s. Sys-admin stuff on the side while they're becoming a developer, and then became the merge of the two, and had a job title that included SRE.

**Edith:** So I think DevOps is overall a good thing. I don't think anybody disagrees, that there's been a change where instead of it being a throw it over the wall to the next person and a lot of finger pointing, now there's a much smoother pipe, with tools like CircleCI which make it easy to turn around and build very quickly.

**Paul:** That's interesting, because that never felt to me like it was a DevOps tool.

**Edith:** Interesting.

**Paul:** Chef felt like a DevOps tool, or at least that it was designed for ops people to maintain machines, whereas CircleCI felt like, this is how software gets into production, and in the small companies that used it, it was devs doing the whole thing, and there were some ops thing as part of their job, but as we started addressing much larger companies, there started being a lot more ops involvement. But still the developers were kind of the end user. Does that make sense?

**Edith:** Yeah, I think it's just...


<blockquote>When I think of DevOps, I think of the overall process of getting code from a box to production.</blockquote>


**Paul:** I think the distinction that I'm drawing is a lot less on what the actual parts of the job are, and a lot more on people's identities and what communities they feel that they're part of.

**Edith:** Their tribe?

**Paul:** Right, exactly, their tribe. There's developers, and even they tribalize quite a lot into Rubyists and Pythonistas, and "I'm a front end dev," "I'm a back end dev," whatever. But the people who identified as ops in the past still regard themselves as a different tribe than the DevOps. The people who were writing Perl scripts before are now people who are writing scripts to manage lots of Amazon instances... I'm sure it's not Perl anymore, it's probably Python. But there's a tribal identity of being former sys-admins, which I don't think is the same tribal identity as people who, let's say, did a computer science degree and became software developers... Ignore the computer science degree, but became software developers and worked on products, and then those products became cloud enabled... You know what I mean?

**Edith:** Yeah, those ivory tower computer scientists.

**Paul:** Yeah, that's exactly what I'm discussing.

**Edith:** Yeah, Dr. Biggar, you wouldn't be familiar with that, would you?

**Paul:** No no no, not at all.

**Edith:** So when I think of it, I totally agree with you that there's different tribes. I was trying to describe the overall business transformation that happens at a higher level than within developers and operations, but I think is starting to spread to other parts of the organization like product and marketing, because they've been trained for... If you know you can only do a release every 3 months, that's a very different line of thought, as a marketing person or as a product person.

**Paul:** One of the interesting things about the success of Optimizely... Optimizely is an AB testing tool, but it's an AB testing tool that developers don't have to use. Developers install it once and then marketing can do instant upgrades, and one of the things that it seemed why this was so valuable and why it took off so much is that it was targeted at marketing, who needed to make immediate changes, and who recognized the need for immediate changes even though that all the customers that they were targeting didn't have the ability to do immediate changes, because they had longer release cycles. So if you have a 3 month release cycle, or even if you have a week long release cycle, it takes you a week to get an AB test out. Everyone says you should be doing 20 growth experiments a day or something, right?

**Edith:** 20 before breakfast.

**Paul:** Right, right. Maybe that's a bit aggressive, but certainly there's many order of magnitudes difference between 1 a day and a week.

**Edith:** I think also having been... So I was a really early beta tester of Optimizely at TripIt - it was that you got out of the hair of your engineering team, because it used to be when I...

**Paul:** So I totally agree with that. The distinction that I'm trying to draw is, when you had these older companies that had longer release cycles, I think Optimizely is evidence of how important that fast release cycle was for (let's say) the marketing department.

**Edith:** Absolutely.

**Paul:** Or the product management team.

**Edith:** Yeah. But Optimizely has traditionally been used on front end, static websites and not back end.

**Paul:** Right. AB testing is clearly a subset of feature flags. I didn't think that when they originally came out. I thought they had different purposes, but I've come to the conclusion over the last few years that it's just a pure subset, and that you can definitely use... It really is just a feature flag that's connected to a funnel, but every feature flag should be connected to a funnel.

**Edith:** It's interesting, so one of the things I've found is, I originally had this very engineering-centric world, that everything should be measured, everything should be AB tested, and I found with LaunchDarkly when I talked to more customers that, (1) most people don't have the volume to do AB tests. If you're at Facebook scale, yes, you can do 20 experiments before breakfast. If you're not, you can't. And second, this is really interesting that a lot of times people just want to get qualitative feedback. If you're a SaaS company and one of your biggest customers, say, is GE or AutoDesk, you don't really want to AB test on those users.

**Paul:** I think you might be using a different definition of AB testing, because I certainly would be happy to turn on a feature flag for a customer like GE and say, "We have this cool new feature that you're happy to use."

**Edith:** That's exactly how people are using it, but they're not using it in the old blind way of...

**Paul:** Right, so the point of AB testing, or one of the points of AB testing - obviously there's the growth angle. But there's also the no regression angle, right?

**Edith:** Yeah, absolutely.

**Paul:** So we're making a change to this, and we think this change is going to be neutral at best, but we're doing it because (I don't know) better positioning, better support, something in the market that we're not measuring in our funnel; we're doing it differently. And we expect that it's completely neutral, it won't tank our metrics. But that knowledge that you're not going to tank the metrics, that's super super important, to go right there. So you slow roll it, and you see that even... They don't have to be particularly statistically significant...

**Edith:** That's exactly it.

**Paul:** If it's just we get 10 users a day signing up, and 10 users a day continue to sign up, great. I don't need 1000 people to do this. So the reason that I tied feature flags and AB tests together is, to me AB tests... It used to be that I thought that AB tests were hooked up to business metrics and feature flags that were largely turned on to operational metrics, but really they should be both.

**Edith:** I keep coming back to DevOps 2.0. I think that's the change that we could start to make, is that suddenly you could tell your marketing person, "Hey, we could just launch this feature in New Zealand, very easily. Very cheaply."

**Paul:** I loved the example that Facebook talked about once where it's like, "We can launch this feature to 1 percent of women who are 25 to 35 in the Bay Area who have expressed an interest in..." I think this was some sort of wedding-related thing that they were talking about. And it's like, wow, that is a very very niche thing that you can target and experiment on.

**Edith:** Yeah, the way I frame it is that you can map your releases to crossing the chasm.

**Paul:** Oh, that's a really nice way of thinking about it. So you release first to the innovators, then early adopters, and then... So are you dividing your user base into laggards and early majority and that sort of thing?

**Edith:** Yeah, a lot of the friction that used to happen as a product manager in engineering was this pressure of, something has to be right, because it's going to go to everybody. And then there's always this old line customer like Merck, or Morgan Stanley. It's like it's got to be bulletproof, because it's going to Morgan Stanley. And then at the other end you have your nimbler people who are like, "I just want this released now. I'm fine with it being buggy," and in fact that's great, because your innovators want to get involved.

**Paul:** It really bugs me when I talk to startups who have the idea that they need to get it perfect for the launch.

**Edith:** Yeah.

**Paul:** It's like, "How will you know if it's perfect if no one has seen it?" It will never hit 20 thousand to 20 million or whatever people off the launch if it hasn't first seen 200 people who say they love it.

**Edith:** There's this paralyzing fear. Actually, Michael Dearing gave me really good advice. I felt like in the early cycles of LaunchDarkly that we weren't doing a very good job at onboarding, and he's like, "That's fine. More people will come." Because he's like, "Work on your onboarding, see the next people go through, collect the metrics." It was a very reassuring pat, because...

**Paul:** In fact the same people will come again.

**Edith:** Yeah. [Michael Dearing](https://twitter.com/mcgd?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) is a super smart guy. So the way I look at feature flags is not so much as AB testing, but more... It's very freeing for an organization to decouple the marketing launch, to decouple perfection, and start to segment their users and say, "Early adopters get this now." Iterate. Innovators get it. And then when it's all bulletproof, which depending on the feature might be 2 hours later, might be 2 months...

**Paul:** Someone was talking to me about how some of the teams at Heroku did releases, and what they said is that they have a 1 week long sprint where they design the feature on Monday, and they get the first version out on Wednesday morning, and they get a lot of feedback from internal users, and then they get the second version out Wednesday evening or Wednesday afternoon or whatever, and then there's a final launch on Friday. That was there entire development process, and so they get an entire feature out in 5 days, but also that there's 2 to 3 rounds of iteration within that process of launching that feature.

**Edith:** So at LaunchDarkly itself, we use LaunchDarkly on LaunchDarkly.

**Paul:** I would expect so.

**Edith:** So depending on the feature we can have much longer with it just within our early beta users. If it's something... We just did Custom Roles, which was a high end feature for enterprise customers where you can get really granular control over who can control a feature flag. And in the turtles world, we control it with a feature flag.

**Paul:** Of course. I'm vaguely getting it, but that's a little complicated.

**Edith:** Even today when I was on a sales call, we had an early customer who's like, "Can I get access to this? It's okay if it's not fully documented or a little rough," and I was like, "Great."

**Paul:** Yeah, as long as people understand that they're getting something half baked. In fact, you always want to have someone who understands that they're getting something half baked, because you never know how to bake it. You never know quite what temperature it needs to be cooked at.

**Edith:** Hopefully you even have a mixing bowl and an oven.

**Paul:** Right.

**Edith:** I keep coming back to the curve, and what's interesting also is that the curve for a feature is different. Different features -


<blockquote>somebody might be an innovator on one feature and a laggard on another, so it's not a set thing that one group always wants all our early features.</blockquote>


Sometimes there could be some features that some people want that other don't.

**Paul:** I think the important thing is to make sure that people always get the feature in the end. You don't want too many people who have the feature turned off a long time... I'm sure you have customers who are suffering from feature flag debt?

**Paul:** Same thing as technical debt. There's code paths that you can't release because there are still customers using both sides of the feature flag.

**Edith:** No we haven't had that, but we're pretty vigilant.

**Paul:** I'm sure your customers will have it, if not your own feature flags, but your customers' feature flags. Facebook had... I think at one point they did an audit: They had 4000 feature flags that still existed. Many were years old and someone hadn't seen it to the end.

**Edith:** Yeah, so the worst example I heard... Well there's probably worse. We went to Microsoft Build, and I presented, and then a ton of people came to our booth to tell us their feature flag stories, which was awesome, because a lot of people had built their own home brew, and they're like, "Here's what we've faced."

This is hilarious: They were using feature flags, and they had an ambiguously named feature flag that 2 separate teams started using for completely separate things. They didn't have a nice system, they just had it in a config file somewhere, so what would happen is one team would start amping it up and the other team would be using it for something else, and it was the classic thing where it's like, "It's not working right! Let's turn the knob up further," and it just was completely messing up all their software. It's basically when you think that your yaw is your pitch or vice versa when you're flying a drone.

**Paul:** So what's our takeaway from all this?

**Edith:** My biggest takeaway is I think DevOps has made it easier to do builds, and I think people are still catching up with what that means for an organization.

**Paul:** Yeah, there'll be a lot more things in the future that are based on that idea, that deploys are cheap, yeah.

**Edith:** That deploys are cheap, that you don't have to push everything to everybody at the same time, and then that frees up a lot what you can be doing with your software.
