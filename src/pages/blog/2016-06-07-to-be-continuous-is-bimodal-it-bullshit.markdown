---
author: andreaech
comments: false
date: 2016-06-07 23:31:51+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-is-bimodal-it-bullshit/
slug: to-be-continuous-is-bimodal-it-bullshit
title: 'To Be Continuous: Is Bimodal IT BullshIT?'
wordpress_id: 901
categories:
- Continuous Delivery
- To Be Continuous
tags:
- /steve Jobs
- Agile
- Amazon
- Bimodal IT
- Gartner
- Jeff Bezos
- Jez Humble
- Kleiner Perkins
---

In this episode, Edith and Paul discuss Gartner’s Bimodal IT model, they battle over Waterfall vs. Agile, and they talk about how Continuous Delivery will deliver you from your technical debt nightmares. This is episode #20 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.



**TRANSCRIPT **

**Paul:** This episode, I think, is going to be a very hateful episode, very ranty.

**Edith:** This is the Hateful 8, the Quentin Tarantino of episodes.

**Paul:** Definitely going to be. I think this happens when you’re discussing something which comes from Gartner.

**Edith:** Gartner.

**Paul:** Gartner. I like Gartner. There’s just a lot of legacy in how Gartner talks about producing software that a lot of it I don’t agree with.

**Edith:** Yeah. Recently, they came out with this report. They’re pushing a theory called … Well, they came out with it in 2015. It’s called [Bimodal IT](http://www.gartner.com/it-glossary/bimodal).

**Paul:** Well,


<blockquote>as soon as you use the word IT, I’m switching off almost immediately.</blockquote>


**Edith:** Why do you switch off?

**Paul:** It’s sort of like community signaling. It’s like if you talk about tech or software, or engineering, or something like that, you’ve got an understanding of like … It implies to me that you know how to build software. If you talk about IT, then I hear someone holding the purse strings as a top down CIO, ancient corporate thing, which of course is the world that Gartner lives in. No wonder they’re using the word IT all over the place. I don’t think I know any engineers who would describe what they do as IT.

**Edith:** Well, I do think you have a kind of self-selecting sample, because you live in San Francisco.

**Paul:** Deliberately so.

**Edith:** All right. Basically, Gartner’s approach, which I disagree with, but I’ll describe it, they basically try to break up software development into 2 Modes. They call the one Mode of IT more the systems of record, the big banks, the slow, the very … I’ll just read off how they described it. It’s all about reliability. It’s all about plan-driven. It’s about things that are far from a customer. Basically like back end systems.

**Paul:** This is Mode 1?

**Edith:** Yeah, this is Mode 1. They say think marathon runner, like kind of slow, steady, reliable. The path 2, they describe as the agile sprinter. It’s just more about continuous for new projects, for things that are very customer facing.

**Paul:** Yeah. I’m looking at the graph here, or the chart. It really seems like Mode 1 is Waterfall, and Mode 2 is Agile, or at best, or at a very best approximation.

**Edith:** I think it’s Gartner basically trying to break up the vendor landscape, because that’s what they do. They try to …

**Paul:** Okay. You can take vendor and put into Mode 1 and Mode 2.

**Edith:** Yeah. They’re saying, “Based on your project, here’s …”

**Paul:** Got you. I’m going to say without any shame or fear of being wrong, but that if your CIO buys from a Mode 1 vendor, quit now.

**Edith:** Quit now.

**Paul:** Quit now. That’s it. I’m walking out the door.

**Edith:** Jez Humble wrote a brilliant comeback, which I’ll acknowledge right away, because I’m a huge admirer of Jez Humble, where he’s basically like, “This is bullshit.”

**Paul:** Okay. I read his comeback. I agree that it is bullshit. I think it’s bullshit for different reasons than he thinks it’s bullshit.

**Edith:** All right. Let me summarize his just for those who’re following at home. He basically said that this is bullshit because these 2 systems interact together. The argument that we have our back end slow systems, and our front end fast systems, and they could go at different paces is ridiculous, because they need to talk to each other. Like if you’re a bank, and you’re rolling out a new website, you need to talk to a back end system. You can’t really iterate.

**Paul:** Is this not micro-services, though, that we’re talking about? You have two different services that operate at different paces, is that not possible?

**Edith:** He also said that the best companies like Toyota iterate on both axes as the same time.

**Paul:** Right. I noticed he mentioned Google and Amazon a whole lot.

**Edith:** Yeah. You can’t say, okay, these systems are really slow and reliable, and these are fast and agile, that somehow we’ll come up with a winning combination from this.

**Paul:** Right. Slow cannot be reliable in like …

**Edith:** Yeah.

**Paul:** I’ll come to that. What else did Jez say?

**Edith:** Well, that’s a summary. I encourage everybody to go read his whole article, because it’s good.

**Paul:** It was quite good. My 12 seconds skim of it, I was impressed. My sense on this is that they’ve packaged up Waterfall into a best practice.

**Edith:** Yeah. I think Waterfall is very comforting to some people, because they think of Waterfall as a way in which they have more control.

**Paul:** Right. There’s a lot of upfront planning. That’s what … I think people are more comfortable. There’s something very seductive about the idea of we will spec it then it will be right. Then, we will deliver that. I just don’t think that it’s good, realistic, I mean, any sort of way to deliver software.

**Edith:** I agree. I think this is what Gartner’s trying to say is that like,”Hey, Agile seems very frightening.” When you said, “This is repackaged Waterfall,” you say that like it’s a bad thing.

**Paul:** No, I do, because they’re saying that it’s valid to like … Essentially, what they’re doing is they’re allowing people who are stuck in the Waterfall world to be like, “Waterfall is perfectly valid. We’ll have 2 projects that do Agile, and keep the majority of the company on …”

**Edith:** Yeah.

**Paul:** Right. Perhaps a migration where eventually the people who think that die or retire, then maybe. If they’re actually presenting this, or if they actually believe the thing that they’re saying where this is a valid way of producing software, I think they’re batshit.

**Edith:** Yeah. I agree. The example they gave is Waterfall is more like a marathon runner, and Agile’s a sprinter. I think, as a marathon runner, or as an ultra marathon runner, you have to be extremely agile when you’re running. Like, you’re constantly changing your plan.

**Paul:** Right.

**Edith:** You’re constantly, like …

**Paul:** That’s when you know where the finish line is. I mean, the whole point with software, and the whole problem with software, and the reason it’s different to building a bridge or something like that, is you rarely know where the finish line is.

**Edith:** That’s such a good metaphor.

**Paul:** You don’t even know what it means to have …

**Edith:** To be done. Yeah. When you run a race, you at least know here’s the end point, how much food do I need.

**Paul:** You know the path, as well, right? You’ve possibly run this race before.

**Edith:**


<blockquote>I think with software, it’s more like you don’t know where the finish point is. There is no finish point in fact, because if you’re successful, you’ll be continuing to evolve.</blockquote>


**Paul:** Right.

**Edith:** Like Amazon started off as a book seller. Now, they sell cloud services. If they say, “Hey, we’re going to take this Bimodal approach for … We have our steady book system. We’re just going to iterate on the front end, they will never come up with AWS, which is where they actually make all their money.

**Paul:** There’s an interesting thing in this chart of like the culture is IT-centric removed from the customer, versus in Mode 2, it’s business-centric where it’s close to the customer.

**Edith:** Yeah, which I think is ridiculous.

**Paul:** What crack are they smoking? It’s like they’re saying that it’s okay to have a mode in which you’re removed from the customer.

**Edith:** Well, it’s basically kind of a SOP to the old world. Hey, we release every 3 years, and nothing changes. I heard a really interesting story from … Do you know James Smith of Bug Snag?

**Paul:** Yes. I know him.

**Edith:** He used to work at Bloomberg. He said there’s some pieces of Fortran that were mission critical, but yet nobody understood.

**Paul:** Of course not.

**Edith:** They literally could not …

**Paul:** As soon as you say it’s mission critical, then no one’s allowed to touch it. No one will touch it. No one will understand.

**Edith:** Yeah.

**Paul:** Disaster.

**Edith:** Now, they’re in this bad state because it’s mission critical, but they can’t improve it, because it’s like well nobody understands it. They took this Mode 1 approach of like, “Hey. This part is done.” Now, they’re in this hole, because it’s written in Fortran.

**Paul:** Right.

**Edith:** Versus if you go more than Mode 2, of let’s always be improving, they would have iterated into a better language or better way.

**Paul:** You do end up in this situation sometimes. I think that you do need a tactic to get out of it. I think it’s not a particularly hard thing to do. You put in API in front of it. You try to build something else that matches the API. Then, you feature flag your way into it. I certainly … Or I think, anything where you’re looking at long cycle times, where you’re looking at the fear of touching a component, anything where you’re not constantly delivering the customer value and getting feedback from that value is just a disaster.

**Edith:** What do you think are the pitfalls of that model?

**Paul:** It’s one of those things where when you’re doing a Continuous Delivery podcast, and you have a continuous delivery company, and you live in this continuous delivery mindset that it’s been quite a few years since I’ve had to …

**Edith:** Then wear your continuous delivery T-shirt.

**Paul:** Right. I mean, the major pitfall is risk.

**Edith:** Yeah.

**Paul:** This is why we love continuous delivery. I’m sure we’ve talked about risk in every episode so far. If you have had a long cycle time, and you’re going in the wrong direction, to go back to the race analogy, it’ll be a long, long time before you discover that you’re going in the wrong direction. You may be unable to find your way back.

**Edith:** You could have just driven yourself off a cliff to go on the race. You could be like …

**Paul:** Essentially, what you’re saying in this is we’re going to close our eyes and drive according to the plan. If the plan is wrong, or we don’t actually know how to follow the plan …

**Edith:** Or there’s not a car that we’re in.

**Paul:** Exactly, yeah. There’s an interesting thing here that they talk about approval-based. This is how I think about this world. It’s like … Do you have the phrase “Jobsworth”? No. It’s a phrase you have, we probably have in England, as well, but the idea is that you only do exactly what’s in your job description.

**Edith:** Yeah. Like work to the hour.

**Paul:** Yeah. Work to rule, all this sort of thing. It’s like no one got fired for buying IBM. You do something within your job to stay employed, but you actually don’t give a shit about a project being delivered. You don’t care about the company.

**Edith:** Garbage in, garbage out. I built what you told me to build.

**Paul:** Exactly. When it says plan-driven approvals-based, it’s like, all right, no one’s getting fired for implementing this plan that has been approved, but everyone should be fired for agreeing to go along with this.

**Edith:** It goes back to something we talked about a long time ago. How much leeway does an individual have to say like this entire thing is kind of broken? Like if you’re at this big organization where it’s like, “Okay. You do what the Spec says to do. You do what the Spec says.” I think people are scared of Mode 2.

**Paul:** Anything new is scary. The way that people deal with fear a lot of the time is they clamp down on it. They put approvals in front of it. They’re like, “I want to see everything that comes out.” When you move to agile, and I’m going to use the agile with the small a, process of like constantly changing what it is you’re doing. You’re constantly changing the direction you’re in. You’re path finding very effectively, but you’re acknowledging that you don’t actually know where you’re going. Yeah. It’s scary times.

**Edith:** Yeah.

**Paul:** Scary times until you’ve done it a few times. Once you’ve done a couple of cycles like this, nothing looks scary at all. It’s scary to think that you could plan your future.

**Edith:** Yeah. Well, it goes back to the whole thing about should I start up? Do a 5-year plan.

**Paul:** Right.

**Edith:** I don’t think they should do longer than a 3-month plan, to be honest. You should have a 5-year vision.

**Paul:** Yes. A vision, definitely. You could argue, and I think that this is actually quite a thing to do, is that you have, let’s say, a 3-year plan, or 2-year plan, let’s say, and you redo it every month.

**Edith:** It seems like a lot of overhead.

**Paul:** Maybe every month is a bit often. You redo it as soon as you get feedback. When I’m looking at what I want to do for my personal productivity, I have a month plan, a week plan, and a daily plan.

**Edith:** On Tuesdays we do the podcast, right?

**Paul:** Yes, exactly. I put in what I’m going to do this month, or what I plan to have accomplished. Frequently, halfway through the month, I’ll realize that the things that I wrote at the start of the month will have been wrong, so then I redo the monthly plan.

**Edith:** I do think there’s a big benefit of writing it down.

**Paul:** Yeah. Plans are worthless. Planning is essential.

**Edith:** For a startup, like every month, we’ve talked about our big picture goals. Then, for every week, we break it down like this day next week. We’re not blind.

**Paul:** All this is a very Mode 2 thing in Gartner’s thing. I don’t think anyone would say, “First, we would build the software. Then, we will QA the software. Then we will deliver the software. Then, we will hire the sales people. Then, we will sell the software.” I guess the engineers are twiddling their thumbs at this point.

**Edith:** I do think there is something to … You staff to demand. You build an MVP and see if you can attract people to it. You do some marketing, see if your marketing is successful.

**Paul:** You iterate. You use the feedback that you have to get somewhere. All fundamentally agile stuff. I would be shocked if anyone in the left side of this, left side of the chart in the Mode 1 thing, has any sense of using feedback in there to guide … I mean, you can’t if by definition, your cycle time is long.

**Edith:** Well, I think a classic example of this is healthcare.gov.

**Paul:** Right. The first version, not the second version?

**Edith:** The first version which was very much like, “Hey, let’s build a system. Then, we’ll try to manage it all in a very large scale.” Instead of saying, “Hey, let’s try to break this down to the smallest chunks as possible to deliver.”

**Paul:** I think that the jobsworth thing that I was talking about becomes inevitably part of one of these large government IT contracts where you have someone, thousands of people executing the plan, and getting paid, and no one can see the wood for the trees, possibly willfully.

**Edith:** Sometimes willfully. Sometimes even if they say it, they’re branded as a trouble maker.

**Paul:** Yeah. Whistle-blower.

**Edith:** Yeah. Shut up code. The classic is the poor engineers of the NASA Challenger.

**Paul:** Mm-hmm

**Edith:** Do you know Challenger?

**Paul:** Yeah. That was the shuttle accident. People died.

**Edith:** Feynman was one of the heroes. He wrote a book. He was part of the investigation. Basically, the engineers at the contractor were like, “We can’t do this launch. It is colder than we’ve ever done a launch.”

**Paul:** Interesting. Something shattered because of the cold, is that right?

**Edith:** They had an O-ring, which is basically an expansion joint. It’s basically a piece of rubber that expands and contracts when the rocket is taking off. What happened because it was so cold is rubber is brittle. It couldn’t contract properly. The engineers the night before were like, it was in Florida “It’s colder than we’ve ever done a launch. We cannot do this.” They were just basically saying no. Then, their superiors were like, “This is a long tangent.”

**Paul:** I saw a very good split between Mode 1 and Mode 2 recently. This was in Jeff Bezos’, I think, annual shareholder talk about how we do things at Amazon. It’s not the same Mode 1, Mode 2 as Gartner, but it’s a very, very similar thing. He split things into Mode 2 where we expect to fail a lot, and Mode 1 where failure is really not an option. Something where like we give all the Kindles away to make it up on books. That’s in Mode 1. You sit down. You do the plans. You do the financial models. You really work this out. Mode 2 is like we launch a fire. We don’t get anywhere in the market place? Fine. We do, amazing. A lot of the successful things like Amazon Web Services like Alexa were all like Mode 2 projects that they threw 10 things against the wall, and one of them stuck. Then, they quietly … Not too quietly, because they’re at Amazon scale, people complain how these things go away. They killed 9 of them.

**Edith:** Yeah, I think Jez Humble’s point, I think what you made before is that even in Mode 1, you have to realize that failure’s not an option, but failure can happen. How do we build a process against that?

**Paul:** I guess I’m misquoting and poorly paraphrasing Bezos to say failure’s not an option. It’s much more, there are some things that you need to do methodically and be very careful about. These are very, very few, and far between. The vast majority of organizations proceed as if everything is a type 1 decision, when in fact the vast, vast majority are type 2.

**Edith:** Well, I think that’s because a lot of organizations don’t have a culture where failure is cool.

**Paul:** Right, exactly. I mean, there’s inherently a tie between this we can fail and we’re shipping with short cycle times, because really, you can’t fail when you have long cycle times.

**Edith:** No. If every moon shot takes 3 years, you can’t fool around.

**Paul:** Right. It becomes inevitable that when you start to have these really short cycle times, you see that the cost of failure is really low, and the benefit of trying things that might not be successful is really high. I guess that’s where I’m drawing the analogy between Gartner’s type 1 and type 2, or Mode 1 and Mode 2, and Bezos’ type 1 and type 2. They’re fundamentally concerned with the same thing. One of them is just this throwback, awful thing. I think Bezos really nails how to think back those different projects.

**Edith:** I love your example of running, because I like running. I think Mode 1 is more like everybody is Steve Jobs. They know the exact right direction to go in. Versus, hey, none of us are Steve Jobs. Let’s wiggle our way in the right path and figure out if we’re going the right path.

**Paul:** Right.

**Edith:** By the way, even Steve Jobs was not Steve Jobs.

**Paul:** Right.

**Edith:** He had very expensive mistakes.

**Paul:** I think one of the most damaging things, as well, in the industry is people who think they’re Steve Jobs. Damaging to themselves.

**Edith:** Do people still think that?

**Paul:** It was a thing 3 or 4 years ago where everyone you talk to, who is in, at least in the start up-y part of the world, would think they were Steve Jobs.

**Edith:** I’ve never thought I was Steve Jobs. When I was fund raising, I think I was dinged a little bit, because sometimes I would say stuff like, “We have some marketing ideas. We don’t know which one is right.”

**Paul:** They expect some sort of certainty. People find confidence to be very attractive, is a good word. The sort of thing you want your CEO to have is confidence. You feel a lot of confidence investing in someone who is confident, even if it’s ludicrous.

**Edith:** That’s what I figured out, and then I can put my statements stronger. We think content marketing is going to work out. It was the exact same thesis.

**Paul:** I had exactly the same thing when I was going down to Sand Hill Road a lot. I’m very much of the, “I don’t know what’s going to work. I don’t know the right way. I’m sure we’ll figure it out. We’ll try things. We’ll get there. We’ll work through our mistakes to get there.”

**Edith:** Investors do not want to hear that.

**Paul:** Right.

**Edith:** Investors do not want to hear that. They want to hear like, “Hey, we’re going to do content marketing. Here’s our plan.”

**Paul:** What I did, and I remember this vividly, I remember sitting in the parking lot in Kleiner Perkins at 8 in the morning. I’m the only car in the car park. I’m blasting Lose Yourself by Eminem as loud as I possibly can. I was just sitting there and shouting. The way to instill the confidence that they expect you to have.

**Edith:** It’s funny, because I got the exact same feedback. I think because we’re very similar. I was like sit up straighter, be more authoritative.

**Paul:** Right.

**Edith:** In my head, I thought I was being very analytical. Like, we have some strategies. We don’t know which one is right. We’ll work through this. They’re like, “No. Say you have strategies, and that you’re Eminem …”

**Paul:** This is quite the tangent. There is a strong correlation between someone who can lead and someone who’s confident in their decisions. The pattern that I, giving VC’s the benefit of the doubt here, is that they’re looking for someone who can take a ragtag group of misfits and lead them into battle and come out successful the other side. Many start ups, that analogy applies.

**Edith:** Well, it’s very true. You’re basically a squad leader.

**Paul:** Right. You want to see that confidence from your squad leader.

**Edith:** I mean, I grew up in DC. I grew up going to DC, and seeing a lot of World War 2 movies.

**Paul:** Mm-hmm.

**Edith:** There’s this classic plot line of the left over squad, who’s actually have all this A-team. You assemble them to something that’s stronger than all the parts and you lead them to victory.

**Paul:** The leader starts out a little tough. No one really likes him. Then, he manages to pull a vision together when they get trapped behind enemy lines.

**Edith:** It’s basically also the plot of Star Wars, by the way.

**Paul:** Who’s the leader?

**Edith:** I would say it’s Princess Leia.

**Paul:** I think that’s probably right. Star Wars good, Gartner bad, is that our conclusion?

**Edith:** I think Gartner is good in that …

**Paul:** I actually think it is, as well. I’m being a little bit facetious here. Want to walk back on that last thing.

**Edith:** I think there’s still a fair amount of fear around what Agile really means in terms of control. I think Gartner’s …

**Paul:** It’s only been around like 10 or 13 years at this point. I expect that the people would still fear it.

**Edith:** I don’t know if you’re being facetious or not.

**Paul:** That’s facetious.

**Edith:** Gartner’s message right here is find your young, risky projects and go off and do this fresh new thing, Agile.

**Paul:** No matter what, I think, don’t listen to Gartner on this. Every project is a type 2 project. The risk is lower. Long cycle times kill you.


<blockquote>Even if you’re on the piece of Fortran that no one can touch, like you can continuously deliver your way out of that far better than you can do a Mode 1 project out of it.</blockquote>
