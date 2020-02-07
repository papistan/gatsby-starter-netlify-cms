---
author: andreaech
comments: false
date: 2016-03-19 23:44:26+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-all-software-is-saas/
slug: to-be-continuous-all-software-is-saas
title: 'To Be Continuous: All Software Is SaaS'
wordpress_id: 814
categories:
- To Be Continuous
tags:
- Atlassian
- Coverity
- Dropbox
- feature flags
- JasonLemkin
- Java
- on-prem
- on-premise
- Pipedrive
- Quip
- SaaS
- Saastr
- Salesforce
- SDKs
- Software as a Service
- stripe
---

In this episode, Edith and Paul talk about the history and shifting definition of SaaS, some of the last Continuous Delivery holdouts in tech, and the need for early customers to know there’s a person behind your software. This is episode #15 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.



**TRANSCRIPT**

Paul:      Hi. I’m Paul Biggar, Founder of CircleCI.

Edith:     Edith Harbaugh. CEO and co-founder at LaunchDarkly.

Paul:      You’re listening to “To be Continuous.” A podcast about continuous delivery and software development.

Edith:     You can get in touch with us anytime at our Twitter handle [@continuouscast](https://twitter.com/ContinuousCast).

Paul:      The show is brought to you by Heavybit. To learn more, visit heavybit.com. While you’re there, check out their library. Home to great educational talks from other developer company founders and industry leaders. We’re going to talk today about SAAS, software-as-a-service and about how that relates to continuous delivery.

Edith:     Jason Lemkin runs a huge conference called SaaStr. It was just called one of the top conferences that an entrepreneur can go to. When I looked at who was attending, it’s basically everybody who’s making software.

Paul:      Right.

Edith:     You know? Its original premise was that you needed a conference just for Software as a Services and this was that conference. Now it just I look at it and like, “Well, this is just software.”

Paul:      What you’re saying is that all software has become SaaS?

Edith:     Yeah. Even beyond that, SaaS in itself has then turned around and gone back to on-prem -

Paul:      Right.

Edith:     - which on-prem is on-premise where a customer takes a version and they install it on their own hardware which is at that point, is it still even SaaS?

Paul:      Right. I guess a good point is or a good place to start is to say, “We think of SaaS as being Software as a Service. Like it’s software that you run in the cloud or something like that. Is that really what SaaS is? Is that a modern definition?

Edith:     Well, the original definition was a movement away from how software was sold when I started off which was people bought a 3-year license and they got a version of it. Then they would pay 18% or 20% depending on what they negotiated for updates.

Paul:      Okay.

Edith:     What would happen then is that people would get cheap or they would forget and they would stop paying their support. Then they would just have this old perpetually good and I’ll put an asterisk back to that perpetually good version they could run for forever.

Paul:      Got you.

Edith:     There are still a lot of customers out there who are running even yet V6, which was the original product that came out over a decade ago.

Paul:      That kind of gels with my understanding of what people are talking about when they talk about SaaS. It seems to be a lot more of a business model than is necessarily about how software is delivered. The idea of recurring revenue based around having to pay every year all the time. How the software is actually delivered whether it’s sold on-prem, whether it’s sold on the cloud, whether it’s a Percy license or whatever, seems to be rather separate from how people think about SaaS.

Edith:     I think they have gotten mingled in people’s minds now because you have the whole second wave of people saying, “Hey. I love the SaaS service but I want an on-premise version.”

Paul:      Right. I remember talking to [Coverity](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=0ahUKEwiYvLSQo7nVAhUERSYKHThAAsgQFggzMAA&url=http%3A%2F%2Fwww.coverity.com%2F&usg=AFQjCNE80aT1SnkES_I86KSp1bRBA57d2Q) when they were transitioning from their on-prem licenses. I think they were selling it for something like 8 cents a line of code or something like that. They were transitioning to a SaaS model. The reason that they were transitioning to a SaaS model was they were going public soon. The economics of a SaaS model are well understood by Wall Street and are well understood by public companies and our much better economics and much more predictable and just much more profitable all around than the old model of selling the enterprise software and the maintenance fees.

Edith:     Also Paul this is hilarious for 2 reasons. One is I remember when SaaS was something that Wall Street didn’t understand.

Paul:      Right.

Edith:     Like when sales force was the new kid and they had their actual logo was software with a slash through it.

Paul:      Right. It was 15 years ago. You see that bankers and investors can learn something over 15 years.

Edith:     Well, because the very nice thing about the other model, of the on-prem model, is you get all the money upfront.

Paul:      Right. Yeah. It’s definitely a ... There’s a different accounting model and a lot of people have spent a lot of time talking about the accounting model and when you can recognize revenue and ...

Edith:     Yes. It’s a headache. I don’t want to talk about it.

Paul:      Well, you’re going public and you’ll have to deal with that shit.

Edith:     I had to do it a TripIt because TripIt was a division of Concur. Part of what I did was a lot of revenue reconciliation and it makes your head spin.

Paul:      Right.

Edith:     The second funny part is one our advisers is Andy Chou, who was the co-founder of Coverity.

Paul:      Right. I know Andy.

Edith:     I think what surprised me is originally I thought there’s no reason why anybody should want on-prem but actually we’re having customers who were requesting it for various reasons.

Paul:      Right. I mean the main reason I’m guessing is security policy.

Edith:     Yes.

Paul:      They get to not necessarily that it’s more secure but that they get to deal with how secure it is or they get to ... I mean one of the main reasons that people want other people’s software is that it’s more secure than writing it themselves. A reason to buy software versus building it yourself is that you can trust that these people have a dedicate security team and spend a lot of time thinking about the edge cases and that kind of thing. One of the nice things about SaaS originally is that you didn’t have to install it on your machine and worry about updates and worry about security and worry about firewalls and that sort of thing. As you say, some people, especially large enterprises, are very into worrying about that sort of thing. They have 400-item checklist that you need to fill out before you sell software to them and it’s all about security. It’s not ... I’m actually going to say it. It’s not really about security but it’s about the security process which is I think for many large companies more important than the actual security of the situation.

Edith:     You’re basically calling security theater?

Paul:      Not exactly. When you get to a certain size, you can’t actually guarantee security and so what you do instead is you establish processes and then there’s someone to ... There’s a scapegoat somewhere. You have plausible deniability because you spent the time when you did the ISO process or the hyper whatever it is.

Edith:     I actually have a tangent. I read an article on staging service, which was deliberately provocative. My mom writes ISO standards.

Paul:      Oh really?

Edith:     Yeah. I always kind of make fun of her because I’m like, “Oh mom. Nobody actually follows those in the real world” which is kind of a jerk thing to say.

Paul:      Right.

Edith:     What she said back to me is that the standards always lag but 10 to 15 years reality of the world.

Paul:      Right. Of course they would.

Edith:     That was a polite way for her to put it. Back to you point ...

Paul:      What I’m saying is that it’s funny that people look at going on-prem with a SaaS product to deal with security when 1 of the initial great parts about SaaS is that you don’t have to do that. Someone else is running the software.

Edith:     I didn’t think that was the reason why people bought ... I actually have 2 more interesting data points. From my perspective, it wasn’t security that people bought SaaS, it was that they didn’t want to take on the cost of hardware.

Paul:      Okay. As in a Capex sort of arrangement?

Edith:     Both the Capex and the people. Like I remember when you used to like ... I was an engineering program manager and product manager of an installed product. When I went to customers, they had to maintain a staff of people who did the care and feeding on an entire stack. They had people who would database, web server.

Paul:      That’s the thing now when as a small company when you buy SaaS, you’re not just getting the software but you’re getting a team of 5 people who keep it operational and people who are building the new stuff and all that sort of thing and you’re paying like %$50 or $500 or $5,000 a month for this is which is infinitely cheaper than you can do otherwise.

Edith:     Yeah. You’re basically buying the economy of scale that you don’t have to spin up your own app server to run every piece of software that you bought.

Paul:      Right. When we talk about what SaaS is, a lot of us think of SaaS, a lot of engineers especially think of SaaS as being in the cloud. SaaS is a thing that is run by the vendor on the public cloud. It’s a multi-tenant thing. It’s the thing that updates all the time. There’s maybe a lot of quite synonymous with continuous delivery or something along those lines and it has APIs and their restful and all that sort of thing. The modern SaaS tool that us developers are used to. When you look at installing that on-premise, you actually get the vast majority of the benefits of it. You just don’t get all of them. I mean you get the modern tool, you get the rest APIs, you get the cloud but I mean it runs very often when people are talking about installing on-prem. What they’re talking about in installing it on AWS virtual private servers or talking about VPC, virtual private cloud, or you’re running it on VMware. You’re not actually being given something, which can install on 16 different flavors of Unix like it was 10 years ago when people were selling software.

You’re getting VM that’s probably or you’re getting container images and that’s a very different world than it used to be. You’re getting still a lot demands. If you buy circle on-prem, it’s a part of your cloud and it scales off and it scales down and like managing a particular set of servers in the way that you are. In fact, a lot of the server managements or a lot of the scaling is built into the product itself. You’re dealing with a control panel, which is probably a fairly part-time job for 1 developer rather than an entire team who’s managing the database and managing the stack and all that sort of thing.

Edith:     Yeah. Exactly what you said was one of the big original draws of sales force.

Paul:      Okay. Go on.

Edith:     One of the original draws when their literal logo was no softwares, it felt like, “Hey. You don’t have to buy this entire stack of people -

Paul:      Got you.

Edith:     - to run.” If you’re a sales organization which Salesforce originally was, it was like you want to get it feasible into your pipeline. You don’t want to have to employ an entire IT staff to get that because that’s was the way -

Paul:      That’s what we did with Siebel or something, right?

Edith:     - Yeah. I mean that was SAP’s whole business model is that you bought this incredibly complex packages to run your business processes. Then you own them top to bottom vertical implementations.

Paul:      Right. It’s funny that Salesforce is the original SaaS because I don’t think any of us who look at modern SaaS would look at Salesforce as a pinnacle of it.

Edith:     No.

Paul:      They do quarterly releases and they’re not continuously delivering ...

Edith:     I think it’s they got pulled very much by their enterprise customers. They did this before they had an effective feature flagging management system.

Paul:      Right. Yeah.

Edith:     By the way, thanks for wearing your LaunchDarkly shirt today. Salesforce got pulled so far with all these one-offs for different customers that I heard that at 1 point, it took them 2 years to make any release.

Paul:      Wow. The fact that they got it to quarterly cycles is probably a very positive thing for them.

Edith:     Yeah. What happened is they got to this point where it was a 2-year cycle then they’re like, “We can’t do this anymore.” Then the 2-year cycle just like changed anything.

Paul:      Yeah.

Edith:     That’s when they hired a lot of agile consultants who say we need to release quarterly ... We need to be faster.

Paul:      Right.

Edith:     Which is a sea change.

Paul:      Quarterly is not fast enough for those of us on the kind of the small side of things or also the big side of things. Facebook would have revolution if they said, “Quarterly is how often we’ll release.”

Edith:     Salesforce is interesting- they are very much the incumbent. They’re not really selling on innovation.

Paul:      Right. It’s funny because the amount of Salesforce replacements that are out there, I read somewhere that there were 1,600 sales and marketing automation companies that were funded last year.

Edith:     Yes.

Paul:      Those are 1,600 Salesforce competitors.

Edith:     Well, I think it’s kind of Salesforce is the way IBM used to be.

Paul:      Right. It’s an ecosystem in consultants and partners and you’ll never get fired for buying Salesforce.

Edith:     Yeah. Exactly. If you’re going to run your sales pipeline, it’s like, “Do I want to go with this new risky tool or not?”

Paul:      Right.

Edith:     I said something to the team the other day which they didn’t say was much of a pep talk, but I said, “The only reason people bought LaunchDarkly is because they ere truly desperate.”

Paul:      Okay.

Edith:     “That there is really no alternative just in the market. If IBM was making this, if Salesforce was making it, if this was something that was not ...”

Paul:      Right. This is enterprise that are buying.

Edith:     Yeah. We have a lot of enterprise customers ...

Paul:      They’re buying from a small startup because they’re desperate. That’s the correct ...

Edith:     Yeah. They’re desperate in a good way. They’re like, “We really need this.” They trust us. That was the end of the pep talk.

Paul:      It sounds like IBM should buy you.

Edith:     I hear that LaunchDarkly is very popular these days.

Paul:      I see.

Edith:     We originally had this thesis that we would be a lot of small companies. Instead we have big enterprises. They're like "we need this."

Paul:      I mean it’s one of those things where small companies they think they can build it themselves. In fact, there are libraries out there to do feature flags and that kind of thing. You can do fairly effective feature flagging mechanism with 1 or 2 developers kind of just taking a library and off to the side or something like that. It’s really when you’ve done that for a couple of years that you start to see the error of your ways.

Edith:     I mean really what we’re selling is feature flag management.

Paul:      Right. Yeah.

Edith:     Somebody did a dis on Twitter which was, “I can implement a feature flag in 50 lines of code.” I’m like yeah, of course you can.

Paul:      Right.

Edith:     The first feature flag is easy. It’s when you start to have 50 and you want to control them and manage them and see who touched them last. That’s when it’s hard.

Paul:      Going back to SaaS and that sort of thing, you were talking about SaaStr originally and you were talking about Salesforce as kind of a model that ended up having lots of sales people and that sort of thing. One of the original things that I felt about SaaS and that people were talking about SaaS was that it kind of sold itself -

Edith:     Yeah.

Paul:      - and didn’t need sales people that much. You could buy SaaS with a credit card and people talked all about best company, the 37signal stuff or kind of early successes in the SaaS world. They were like, “There’s no sales people here. You just buy with a credit card.”

Edith:     Yeah. I think you’re right. There was a belief that a while that SaaS was synonymous with self-serve.

Paul:      Yup.

Edith:     That if you didn’t need to go get your IT department to go install this if it’s the old SAP model, if you didn’t need somebody to install that, if you didn’t need people to figure it, if you can just onboard yourself, why do you need a sales person?

Paul:      Right. Exactly. There was a low price point associated with that. People were typically selling very low price things. Certainly not things that cost thousands of dollars or tens of thousands of dollars.

Edith:     I think there’s 2 things that are happening there that are making sales people be part of the ecosystem. It’s more and more complicated things that are being served over SaaS.

Paul:      Mm-hmm (affirmative). Okay.

Edith:     Like again I remember when everybody’s like, “Oh, you can never for example have portal server or something that’s actually technical via service.” Now AWS is a service.

Paul:      Right. Yup.

Edith:     Now that there’s more and more technical things and I say not technical just in terms of Dev tools but more technical terms of marketing automation, sales automation. When you have a bigger purchase there is a need for a sales person.

Paul:      Right. Maybe more than a sales person. A sales person is definitely useful. When you have the product, you need an account manager. You need someone who you can email and say, “Something is wrong. Help us right now.” Related to that, when you’re getting installed, you need a sales engineer and you need someone to manage the process and make sure ... No one ever needs a sales person. You can always carry yourself through the process. If you want to buy software, right, and you were desperate to buy software, you could get yourself through it.

Edith:     It’s interesting. I mean I’m sorry about talking a lot about my company today. What we saw with LaunchDarkly is we originally thought we were getting directly to developers. What we saw is that we had a different buyer persona that a user persona.

Paul:      Right.

Edith:     I think that’s where you insert sales people into any SaaS process.

Paul:      What I’m saying is that you’re inserting it because it is a more efficient way for the company to ensure that sales happen not because it’s necessarily required.

Edith:     Here’s my own experience. We originally thought we were going to be very much like Atlassian -

Paul:      Okay.

Edith:     - which is deep at our DNA. My co-founder John is from Atlassian. Our first 2 engineers were Atlassian. It was me and 3 Atlassian people. Eventually I came to a realization that even though I would tell people like, “Hey. You could just go start using our product.” I was actually talking more to directors of engineering or CTO who just wanted more information from me before they decided to invest for their entire organization. PVH put it the best. He said "they want to hear that there’s a real person behind this."

Paul:      Looking back at Circle, the vast, vast majority of our customers bought without talking to an early human at all. Maybe they emailed support but it wasn’t the sales process. It was completely self-serve. This was true for the first 3, 3 and a half years. Occasionally people would request their CFO to have a conversation with someone on our side or ..

Edith:     The CFO?

Paul:      - Yeah. Just to allow them to gain confidence that there’s a real human there to sign off on the purchase. I think that 1 of our first thousand dollar customers, our thousand dollar a month customers. They were like, “You know our CFO wants to know that you’re a real company.” At the time we were 5 people. It scarcely a real company at all. We were able to ... We were selling $10,000 a month contracts without a sales person.

Edith:     You had a sales person -

Paul:      We had a sales person. Absolutely.

Edith:     - which was you.

Paul:      We had a part time sales person -

Edith:     No. You were the sales person.

Paul:      I was the sales person. Yes. That’s what I mean. It was part-time and I wasn’t exactly running the process. I didn’t have a big checklist of where everyone was in the pipeline and following them through. I was largely answering emails as they came in and the customer was driving the process because they desperately needed it. That’s a very different sales process than people buying in the on-prem. People who buy Circle on-prem are talking to a sales person. They want to talk to a sales person. They want someone who will manage the process for them and make sure that it doesn’t drop off the radar because they’ve got quarterly goal that’s associated with getting CI in place. They have 40 different steps that they need to go through to be able to buy software. They need someone on the other end who’s actually going to do that.

Edith:     Exactly.

Paul:      It’s not going to be a support team. It’s going to be a person whose job it is to make sure that happens.

Edith:     Yeah. A good sales person helps everybody look good.

Paul:      Right. We’ve gone from a place where people bought almost entirely self-serve to a place where people and I mean as an industry, as the SaaS industry, to a place where people use enterprises. You’re right. It’s a lot to do with the complexity. It’s a lot to do with like people selling larger price points and larger companies looking to buy SaaS. At the start, you can buy your Salesforce SaaS whatever and those guys had tons of sales people to deal with that. The vast majority of SaaS looks a lot more like Fog Creek and 37signals. There were no sales people on the other end. Now, people are selling much, much higher price points. I’m looking at a company like ... Do you know Hearsay Social?

Edith:     Yeah. It sounds familiar.

Paul:      They’re based in Mission Bay. They sell some sort of predictive model based on your social profiles to like insurance companies and that sort of thing. There’s something like ...

Edith:     Sounds very brave new world.

Paul:      There’s something like 200 potential customers for them in the entire world and their massive, massive contracts. They have a massive sales team. Right? Maybe not a massive sales team but it’s entirely sales driven. Because you can’t sell to one of those 200 giant companies without having a sales team that is managing every step of the way. That is an entirely SaaS product. There’s no on-prem. It’s all in the cloud and it’s all managed on the Hearsay’s servers. Because of the business model, they need a sales team and the price point.

Edith:     This is pretty disappointing but I agree with you. I think what’s really happening is that SaaS was originally scary and new so it was very much low market and it’s just moved up the food chain as a higher and higher price points like what you said. Like some Hearsay ... They’re not just going to tell 1 insurance agent, “Hey. Install this.” and start giving quotes. It’s something that has to come organization wide and at that point, you need a sales person.

Paul:      I remember the way that many of us in this industry learned about SaaS was reading the Joel on software discussions about how this sold Fog Creek and why they switched to a web-based thing. I’m not sure he used the right SaaS. Maybe it was cloud, maybe there was a -

Edith:     There’s maybe a pre-SaaS.

Paul:      - It wasn’t pre-Salesforce but I think it was pre ... The rest of the industry knowing about SaaS. Part of the benefits there was the vendor controls updates.

Edith:     Yes .

Paul:      The vendor decides exactly when the software gets updated and they deal with security things. They get the exceptions so you don’t need to do bug reports. You don’t need to do as many bug reports. You get a lot of that information yourself instead of having to collect logs or that sort of thing. It feels very different from how we look at SaaS today in a sense that SaaS is kind of a business model. At the same time it feels a lot the same in the sense that there’s a very strong tie between what Jill was talking about in continuous delivery.

Edith:     Yeah.

Paul:      That to me modern SaaS has very, very parallels. Maybe very strong correlation with continuous delivery. I think if you can’t do continuous delivery on it, it’ll be very difficult to refer to it as a SaaS.

Edith:     Yeah. I had say continuous delivery has really kept in SaaS and I mean that very good. It’s brought down the costs.

Paul:      Right.

Edith:     Because I remember the old days where you would have these versions that different customers and then you would to coax them to upgrade.

Paul:      Right. You would have to back port changes to the old release branch and be able to ...

Edith:     A lot of times they couldn’t upgrade because it meant having to upgrade all the underlying stack also. Then you would got us this very complicated dance if you’re like, “Well, you’re on Sybase’s version blah.”

Paul:      Yup. The new version no longer supports Windows whatever or Unix whatever.

Edith:     This huge cost in old software or which was just making sure that you could work on all these old versions, do migrations to the scripts.

Paul:      I would think that almost one of the definitions of what is and what isn’t SaaS is whether or not there’s a migration plan. Can you continuously upgrade that software? When I looked at Circle’s on-prem thing, we’re not supporting 57 releases. We’re largely supporting the latest release. If you want, there’s a button that you click to upgrade to the latest release.

Edith:     That’s funny ... Go ahead. I was thinking more of the last hold outs against continuous deliveries SDKs.

Paul:      Okay.

Edith:     I think we talked about this before but we have some customer’s right now where we say, “Please. Please. Please. Move off that SDK.”

Paul:      Right. I’m impressed with ... There’s a bunch of people out there who do very interesting stuff around SDKs and I think Stripe is kind of the major one. Stripe versions their APIs.

Edith:     Yes.

Paul:      Stripe obviously is never going to on-prem because it’s payments and cloud and that sort of thing. Every time that they do a break in chains, they just make a new version of their SDK or of their API. You could whatever version that they API you like by sending a header or by default, you’re using whatever version that the API you were stuck on. They do a transformation from the old APIs to the new API so they almost never need to deprecate all the APIs.

Edith:     Interesting. Those are APIs not a SDK.

Paul:      I mean if you’re ... I don’t know how exactly they do their SDKs but I presume that their SDKs make calls to the APIs. If you’re on the old version, maybe that API doesn’t exist until you get an error but you’ll get a version error as opposed to something subtlety failing or something like that.

Edith:     Yeah. This is pretty inside baseball.

Paul:      Well, I think the major thing is that SDKs are largely small wrappers around APIs these days. It’s not like back in the old days when an SDK was an SDK and men were men.

Edith:     What exactly was that day? Was it like a fixed day in time that you remember?

Paul:      I’m thinking of when you downloaded the SDK to work on the hardware product or something like that. Some SDK came with Windows. Actually, if you’re looking at SDKs that come with Apple or phones or whatever, you’re still kind of trapped in that sort of model versus SDKs that come with SaaS are kind of small rappers around the API. They’re very often like literally tiny rapper and many of them you could almost define with a scheme and you could write the whole thing in 200 lines.

Edith:     Well, everything can be written in 50 lines I thought.

Paul:      When you’re looking then at what is in SaaS? If you haven’t got a migration policy or if there isn’t a way to migrate, I’m going to say that you couldn’t really refer to it as SaaS. I find it hard to think of an example.

Edith:     I think I know where you’re getting at because that’s not really a service. If you’re taking a Software as a Service and you’re just saying you’re on this version for forever, I think I agree with you but I’m hard-pressed to think of somebody that actually does that.

Paul:      That has a migration plan?

Edith:     No, that has no migration plan.

Paul:      Right.

Edith:     The closest thing it comes to is all that freeware or shareware that used to float around.

Paul:      Yeah. This is exactly it. If you’re selling ... You know like you were talking about whatever software relied on version 6 of Sybase or whatever that was, you’ve got no migration plan because you’ve got no maintenance contract. There’s a bunch of like libraries and bunch of kind of OSS software that shifts with that migration plans or without scripts to upgrade from 1 version to the other. I remember you talking about the company that did the upgrade from version 6 to version 7 and had no migration plan? What was this again?

Edith:     The reason why there’s a lot of V6 out in the world is because there was not really migration path from V6 to V7. They should have just started as a new product line -

Paul:      Got you.

Edith:     - because they switched from Tickle. V6 was Tickle.

Paul:      They rewrote it in Java.

Edith:     They rewrote it in Java.

Paul:      Everyone did.

Edith:     I’m sorry?

Paul:      Everyone rewrote it in Java. Whatever it was, it was rewritten in Java.

Edith:     Dissecting it like it was a smart thing to do when that Java was the wave of the future. That seems outdated now but at the time, it was, this was 2001, but they should have just said, “Here’s our Java version,” and just called V1 of Java instead of saying, “This is the next version.” What it basically did is it stalled everybody at V6 and then what happened was competitors came and said, “Well, the amount of effort to go from V6 to V7 is equivalent to you just moving to our platform.”

Paul:      Right.

Edith:     They got picked off by all the other competitors were like, “If you’re already going through all this effort,” and because they stopped doing updates on V6 for a while because they want everybody move to V7.

Paul:      SaaS then overall has sales people?

Edith:     Yes.

Paul:      Unlike kind of when it started? Very closely tied to continuous deliver?

Edith:     I’m arguing both sides of this now. I don’t think all SaaS has sales people. For example ...

Paul:      If you’re going to the SaaStr conference, you’re going to learn about sales people. A lot more than you can learn about SaaS.

Edith:     Yeah. I mean like so for example I’m thinking of a software we use, like we use Quip. We use Pipedrive. They used to have sales people but we’re at pretty low price point. We can’t economically support a sales person. I think we pay $39 a month or something.

Paul:      At some point you’ll like Dropbox, which we pay a relatively low price point for. We will hit sales people size at some point. There are sales people who sell Dropbox to larger companies for much, much larger price points.

Edith:     I had one more interesting point about on-prem. The original thing about SaaS was that you didn’t have to have the cross to find hardware. I have a friend right now who was selling very effectively on-prem and his bundling into his on-prem solution, the cost of the hardware.

Paul:      Okay.

Edith:     I saw this seems odd to me and I asked him why and he said, “Well, otherwise the people who buying on-prem would have to go and provision the hardware and order in that would create long delays." He wanted to get these contracts singed.

Paul:      This is the thing. People are selling servers that you rack rather than software that you install onto the servers.

Edith:     He’s going back. He’s actually selling the whole stack. He’s selling people ... Originally he started selling people software like it’s taking them too long to get hardware and they want to close this deal. They’re willing to pay for the hardware so he sells it as a bundle.

Paul:      What does that do to the margins?

Edith:     That was kind of my question. He says right now it doesn’t matter to him.

Paul:      Okay. It’s early stage. It’s ...

Edith:     Well, he’s selling the hardware for profit and mainly he just wants to get these customers on board and instead of waiting until a year for the next budget cycle for them to get their own hardware.

Paul:      How is that related to ...

Edith:     Basically it’s a SaaS company that’s twisted back on and now it’s ...

Paul:      Why is that a SaaS company?

Edith:     Well, he thinks of himself as a SaaS company but now they’re doing on-prem and selling hardware. I’m like will this ...

Paul:      Right. They do recurring revenue I presume.

Edith:     Yeah.

Paul:      Right. It’s SaaS by the new Wall Street definition of SaaS.

Edith:     When you look at it you’re like, “Hey. This is a lot like the old days.”

Paul:      Does it have a migration plan?

Edith:     I should ask him that.

Paul:      Thanks for listening to this episode of “To be Continuous” brought to you by Heavybit and hosted by me, Paul Biggar of CircleCI and Edith Harbaugh of LaunchDarkly.

Edith:     To learn more about Heavybit, visit heavybit.com. While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.
