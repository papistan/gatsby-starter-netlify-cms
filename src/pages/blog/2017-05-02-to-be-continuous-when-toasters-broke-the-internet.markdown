---
author: andreaech
comments: false
date: 2017-05-02 14:56:39+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-when-toasters-broke-the-internet/
slug: to-be-continuous-when-toasters-broke-the-internet
title: 'To Be Continuous: When Toasters Broke The Internet'
wordpress_id: 1708
categories:
- To Be Continuous
tags:
- Bolt
- botnet
- DDoS
- Dyn
- Harvey Mudd
- IoT
- Marc Andreessen
- security
---

In the latest episode of To Be Continuous, Edith and Paul discuss the massive DDoS attack against Dyn, a major DNS provider, in late 2016. They examine the security flaw that enabled millions of IoT devices to be hijacked and discuss how it could have been avoided.

They conclude that to minimize such attacks, all devices that connect to the internet should have easily updatable firmware, and that the IoT industry needs greater regulation. This is episode #31 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->

This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.




TRANSCRIPT




**Edith Harbaugh:** Hey Paul.







**Paul Biggar**: Hey.

**Edith:** So, the internet was brought down, basically by toasters.

**Paul:** Right, explain, tell us more.

**Edith:** So, by sentient toasters. Basically, there was a major internet outage because a DNS server was attacked by a botnet. A botnet of IoT devices. To back up, a DNS is basically a switching system of the internet. Think of it as a telephone book that tells people how to get through to the right place. If everybody calls at the same time, it basically overwhelms the switchboard. So what happened is, there are many, many Internet of Things devices out there, and several hundred thousand of them were hijacked, to all call at the same time.

**Paul:** Were they all toasters?

**Edith:** The joke is they were toasters, but, probably they were more likely security cameras, maybe monitors. Just anything that has a way to call out.

**Paul:** How were they all compromised? Were they all compromised with different compromises? Did people do like 20 different compromises to build this up or was it all like the same firmware?

**Edith:** So what happened was, devices by one manufacturer were shipped very smartly with a way that you could reset the password, so that this couldn't happen. So many people did as they should, which is logged in to a web app and changed the password. Smart, right?


<blockquote>The issue is that there was a backdoor. That if you had telnet or SSH access,all these devices could still be accessed with their factory password. </blockquote>


So all these people are duped.

**Paul:** They were told there was security and there actually wasn't?

**Edith:** It's like if you were sold a house where you locked the front door very sturdily, you got the master key changed, and then there's a backdoor which anybody could get into.

**Paul:** So it wasn't just that they were insecure to some sort of software attack that could get some DNS, DDoS going. It was actually that they were insecure for their own purpose like baby monitors, over the internet.

**Edith:** I'm not sure I understand you.

**Paul:** So could people access the security cameras over the internet as a result of this?

**Edith:** I don't know, to be honest.

**Paul:** It seems likely.

**Edith:** It seems that you could change the password, or find out what the password was, or snip it or something like that, once you're in over SSH. Yeah, so basically all these devices are massively insecure. And even if you've reset the password multiple times. There's still this backdoor. They're accessible any time by a telnet. So to me this just seems, at best, an oversight, and at worst, malicious. That a manufacturer could ship all these devices where people basically could lose control of them.

**Paul:** I think it's difficult to look at this as malicious.

**Edith:** The analogy I would draw is it's like those hoverboards that were very popular and they exploded.

**Paul:** So I'd use the phrase negligence. More than malicious. Certainly shipping things these days, without security built into it, like as much as we talk about continuous delivery, there is a baseline of security that you need in your model and typically. The market kind of handles this, to a certain extent. If you ship a website and it doesn't have SSL people will hopefully notuse it.

At least for security and passwords and that kind of thing, but with Internet of Things,


<blockquote>People aren't used to needing security in their handheld devices, in their remote controls, in their televisions, so now there is a low bar of security that isn't being met. </blockquote>


**Edith:** Yeah and I think it's extremely negligent, in a way that is similar if not more harmful than, you know, the whole Samsung Notes scandal that just happened.

**Paul:** The Samsung Note is the one that [caught fire](http://www.techradar.com/news/samsung-galaxy-note-7-battery-fires-heres-why-they-exploded)?

**Edith:** Yeah, that repeatedly caught fire, and eventually just got completely banned from any plane. That is actually easier to trace because you can look at a Samsung Note in somebody's hand and say like, you're not allowed to fly with that. These Internet of Things bots are more dangerous.

**Paul:** So, a manufacturer made them, one manufacturer made all these. And then they were sold under lots of different brands?

**Edith:** They were a subcomponent that a lot of people then embedded.

**Paul:** So the manufacturer who made it, what were they making? Was it, a motherboard, a camera sensor?

**Edith:** It was a sensor that was embedded in a lot of different devices.

**Paul:** So obvious continuous delivery question of, how does one end up in this problem, how does one deal with this, what is the situation there?

**Edith:** I mean in my opinion, I actually worked at an early IoT company before we called it IoT.

**Paul:** Is this the plant one?

**Edith:** Yeah that's the plant one. And I'm sorry, it was before I met you, so I could not give you a plant t-shirt.

**Paul:** Yeah, I know, that would have been amazing, to go with my LaunchDarkly t-shirt.

**Edith:** Yeah, and by the way, it looks lovely on you.

**Paul:** Thank you, thank you. I had it tailored.

**Edith:** Yeah, so this is how I first got into continuous delivery. We shipped a plant sensor which would measure the soil, the temperature, and the water of a plant. It had firmware in it that we could update.

And this was actually very important to us because we were continually improving our algorithms. And of course, we made the really basic mistake that we forgot about daylight savings time. Which everybody forgets for one or another reason. So when we built this component, we deliberately designed it so the firmware could be updated.


<blockquote>So to me it's very negligent that these devices were shipped where people could not update the firmware that changes the password. </blockquote>


**Paul:** Who couldn't update the firmware? I mean it seems like the manufacturer could almost like root themselves to update the firmware.

**Edith:** My understanding is they can't.

**Paul:** Wow, okay, I guess I'm not surprised.

**Edith:** Yeah so in my opinion these devices should all be recalled because they're just a lurking dangers to allow in the field.

**Paul:** So, I guess there's two layers of problem with the device. Are attackers able to remotely take over and access private information which is being sent? And I would say that for a large class of things, that is true.

**Edith:** Yeah, and it sounds trivial. Who really cares about how often you brush your teeth? But actually, there are a lot of things that you do care about other people knowing about you.

**Paul:** Oh yeah, absolutely. There are sites full of people's baby monitors. You can tell when people are home so that you know when to burgle their houses. You know, people have cameras in their living rooms, in their bedrooms. There are definitely lots of stuff that people don't want to be sending out all over the internet. And if you assume that the people who are breaking into these are criminal gangs, which I think is correct, there's this big blackmail component at the very least.

**Edith:** Yeah, mine would be pretty boring, it would be me sitting around reading.

**Paul:** I think you could be blackmailed for that. What is Edith reading this week?

**Edith:** Nothing that exciting.

**Paul:** So, the second layer of this is, can they be used to attack infrastructure? Or they can be used just as DDoS devices?

**Edith:** Well, a botnet.

**Paul:** A botnet, exactly. So let's suppose that there wasn't the first layer, that there were no privacy implications from this at all. No-one could set your house on fire by turning the toaster on all the time or something like that, and the only thing was botnet. Would we recall them then?

**Edith:** I think we would, because basically, if you consider that, a flammable device is a danger.

**Paul:** Sure, but ignore the flammable.

**Edith:** So if you consider this botnet can at any time, take down a major component of the internet. I mean, so there are cases where, when the DNS server was down, people's nests couldn't be used and they were overheating houses. You know, it was causing a real danger.

**Paul:** Yeah, I mean, sure it's causing a danger, but it's quite a distance from the actual cause of the danger. You have to have a device that has to be rooted, that then is botnet-ed to, take down DNS which isn't protected, and then someone else's nest goes down?

Or someone else's watch doesn't work or their GPS directions don't work. Or something along those lines. There's a long chain of causality, and, at some point on the chain of causality responsibility gets weaker.

**Edith:** I'm surprised you say that, because I think the chain is very short.

**Paul:** Well it's different people's devices that are affected by this, the person's nest, which doesn't work, is not the same as the person who ran the botnet.

**Edith:** Well it could be. In a bizarre twist.

**Paul:** I mean, it could be, it could be, yeah sure. That would be hilarious, if the owner of a botnet like the mafia gangster of the botnet, had his house burned down by the nest caused by the DNS outage.

**Edith:** Well it's like that old joke, you know, the call is coming from inside the house. Like, literally, the call, like the reason why your internet is down is because you have a lot of IoT devices. A friend of mine, he has a very hi-tech house. He has this beautiful weekend house that I stayed in once, and literally, even the sink I think is IoT.

**Paul:** And then the sink doesn't work because the DNS is down. I mean, it is ridiculous, the amount of stuff that doesn't work, and should be tested against DNS and that sort of thing. But I would just say that that's a failure in the nest more than anything else. Your thermostat should not be able to burn down your house. Under any circumstances, if anything should be recalled in this situation, it's the nest.

**Edith:** Oh really? I'm surprised.

**Paul:** Yeah, and a thermostat that can be burned down if someone else does a action, which is entirely normal?

**Edith:** Well, electrical devices are not regulated per se by the government but there is a standard they have to meet. You cannot just make a device that doesn't meet electrical standards.There's an expectation that people have that when they buy a toaster, and they plug it into the wall, it will not burst into flames.

And that's why it will be recalled, and I think, IoT is going to have to go to some sort of standards of similar conduct.

**Paul:** Yes but no. Talking about whether the nest should be recalled, the problem is not that the nest itself is insecure. The problem is that under normal operating conditions, it has a risk of overheating. And I'm including major internet outage as normal operating conditions because that's how the internet works.

**Edith:** Yeah, I think I am agreeing with you. I guess I'm pushing a little bit on, do you think these botnets should be regulated?

**Paul:** Right, so that's the other question. I think regulated is a good response to it. If you look at this from a manufacturer's perspective, there's no way they're going to recall it.

**Edith:** It's kind of a tragedy of a commons, that right now they have no financial incentive to make these secured or licensed.

**Paul:** If you want to see what people are going to do you just look at where their incentives are. They will absolutely not recall it. They may issue a patch, if possible, but then no one will apply it anyway because that's not where people's incentives are either. I mean, frankly,


<blockquote>The people who were responsible were not the ones who're affected so they have no incentives at all to fix it. </blockquote>


**Edith:** And they're probably unknowing.

**Paul:** Getting a patch out there probably requires dealing with all of their customers, sending out marketing materials or, you know, doing a recall, which they have no incentive for. There's multiple steps on the chain. None of whom have any incentive to fix the problem.

**Edith:** Yeah, that's totally the tragedy of the commons.

**Paul:** Right, and that's the situation that you want regulation in.

**Edith:** Regulation within the industry?

**Paul:** Well I just mean that as a principle. You know, when markets cannot solve a thing by themselves, you need regulation in order to accomplish it.

You may also need regulation in the event that a market is accomplishing things by themselves. I'm not taking an extremely libertarian stance here but, when the incentives are badly aligned, that's typically where regulation comes in.

**Edith:** Yeah, I think it comes back to this, and it's funny because the way I remember it, in one of our very first episodes, we were talking about what should or shouldn't have continuous delivery. And I actually disagreed with you then, because you said even a gas meter, like a gas station pump, should have continuous delivery, and that's actually why that's the background of our Twitter account. And now I've come around to your point of view, I think the fact is anything can be vulnerable.

**Paul:** Right, everything is vulnerable.

**Edith:** Yeah, that means that it must be updatable.

**Paul:** Right, if it runs software, it is vulnerable.

**Edith:** Yeah, and to be honest, this telnet bug is the one that's happening right now, there might be something that happens in the future that's completely different. So it is not possible to know everything that can go bad, therefore you must be able to update. Yeah so the same with the nests with the DNS failure, like they must be updatable.

**Paul:** Right, guarantee the nests are updatable. This creates quite a challenge, because whenever you buy a device, the first thing you need to do is set up its wifi.And you kind of wonder, why does my smart toaster need wifi?


<blockquote>And, for most devices, the only thing that they need wifi for, is to reach the NTP server, the date & time server. But of course, they also need it to make updates. But neither of those are particularly useful to end users, so if you buy a thing and then you're like, "why do I need to set up on the wifi?" </blockquote>


**Edith:** Well, as long as you're not on the wifi you're fine, because then it can't be hijacked.

**Paul:** Yes, true.

**Edith: T**hen you're not vulnerable. Then you're not an Internet of Thing, you're just a thing.

**Paul:** But you need to be on the wifi to get your dates updated.

**Edith:** And I think Internet of Things is becoming more and more pervasive, I mean I know, people are already talking about smart refrigerators, that can sense when you're low on something and reorder.

**Paul:** Yup, that would be, awful.

**Edith:** The reordering? Or that the smart refrigerators will then be hijacked?

**Paul:** All of it, just sounds like a fucking disaster.

**Edith:** Why?

**Paul:** I dunno, it's just like, complexity everywhere.

**Edith:** You're a simple guy.

**Paul:** Do you remember when your parents couldn't use the VCR? Probably not your parents.

**Edith:** No.

**Paul:** Okay.

**Edith:** When my mom visited me, she was proud because they donated books they'd found in our attic of one of the first computers. Like the manuals from it. They donated it to the computer history museum in Mountain View. So yes, they could set the time on the VCR.

**Paul:** I think I probably shouldn't use your parents as the example

**Edith:** They also were the people who could set it so that it could record programs when they were away, and by the way it was also a Beta VCR.

**Paul:** There is a cliche, a stereotype of people who cannot use their VCRs. And at this point, I've forgotten even where I was going with this.

**Edith:** You were talking about smart fridges and you said they were awful.

**Paul:** Right, okay, so the level of complexity in all of these smart devices and the combined complexity of all the smart devices is just exhausting. Like I've been interested in an Apple Watch, because it's just another thing.

**Edith:** And I think many people are with you on that one. The Apple Watch is kind of flopping. I do think stuff like Snapchat seems like they're going to make a good go of it with their smart glasses.

**Paul:** Snapchat is the analogy I make for people whose parents can't use VCRs.


<blockquote>For my generation, Snapchat is the VCR. I can use Snapchat from a UI perspective, if I remember which way to drag the thing. But I don't understand Snapchat as a network. </blockquote>


And I feel that like the smart fridges, the smart fucking everything, it's all the same. I can imagine myself sitting in a house full of smart devices going nothing is fucking working. The fridge isn't on, and now I need to get out like my console, and Python until I can figure out why it's not working.

**Edith:** Well so are you even against smart cars then, I mean, because they're coming, I see them driving around San Francisco, and they're here.

**Paul:** So I'm pro smart cars, and that's just because people are stupid. But no one dies if you misuse your existing fridge.

**Edith:** Well you might get botulism, you know, food poisoning.

**Paul:** Yeah, you might get food poisoning.

**Edith:** Yeah, because if it's thawing out your chicken and refreezing it repeatedly, that's bad.

**Paul:** It is difficult for a normal human to abuse their fridge so much that that happens, whereas it is very very easy for a normal human to kill another human with their multi-ton vehicle that they drive around. While sleepy and drunk.

**Edith:** Or just, you know, cranky.

**Paul:** Or just kind of like, vaguely looking the wrong direction for half a second too long, it's insane that we ever let people drive cars.

**Edith:** I don't own a car anymore. It is interesting to see the smart cars driving around San Francisco and think "wow, the future is here".

**Paul:** I mean this is the thing about San Francisco that when you're here, you just don't get this wherever else you are, the future is not there.

**Edith:** It is interesting though, I think, software is far more pervasive and will continue to be far more pervasive than anybody right now realizes.

**Paul:** Except. [Marc Andreessen](https://www.forbes.com/profile/marc-andreessen/). I feel that like there's a level of thinking about the future that we're like two steps removed from.

**Edith:** I think people don't realize how much software is already part of their everyday life. And that it will continue, and this is why I feel so strongly about it. That these IoT devices need to be regulated and governed, because they will continue to have an impact on people's lives.

**Paul:** If you take the principle of, there's no incentive structure for it to happen right now, and therefore you need regulation because downsides can happen, and both privacy downsides as well as infrastructural downsides, then yes. It makes perfect sense. I guess the downside is, that whenever you look at regulations, they always come in terrible.

**Edith:** I'm not saying government regulation, because it should be industry groups.

**Paul:** Industries, self regulation.

**Edith:** Yeah, I mean that's the way it is with electrical devices. But there does need to be an understanding that, it is not okay to sell something that cannot be updated. Or if you want to sell something it must be updatable, because of the threats and use cases that we know of today.

**Paul:**


<blockquote>Anything that end-to-end connects to the internet must be updatable. </blockquote>


**Edith:** Yeah, because of the threats, and to go back to your point, the use cases that you know today, are going to be different. You cannot know every edge case, you cannot know every error, even with the self driving cars. I mean they need to be able to be continually updated. Because it's going to come out that for one out of every five million, a weird edge case happens.

**Paul:** Oh and self driving cars will undoubtedly be updatable. Tesla's already are.

**Edith:** It's funny, I talked to Adrian Cockcroft, a smart dude by the way, he's at AWS now. And he was talking about the shift of how Tesla was doing so much better because they're used to updating, versus Mercedes. Which is used to making a car, and making a new model every seven years, and just the tectonic shift in thinking.

**Paul:** I mean, I can't imagine what it must be like to be in the car industry right now.

**Edith:** Well, because if you're used to "hey we're going to ship a model" at best, every 10 years.

**Paul:** Yeah, and it's built, throughout their entire organization, like no one is thinking about what happens, or how does the entire company get orientated around the idea of software that updates itself?

**Edith:** Yeah, particularly when you're used to doing it the old way. So I wrote out my Econ thesis on the car industry. On Jaguar. The car industry is built around stability. And manufacturing the same thing over and over. It is the opposite, and it was funny, because lean startup did kind of come out of Toyota. But still, they're not used to revving a car every day.

**Paul:** So it's interesting to look at, how deep you have to go in the understanding of how to build a car to make one that's updatable. So


<blockquote>Tesla was shipping hardware that wasn't used, because they knew that they would use it later, when the software got there. That's, a crazy level of forward planning, that you can't do if you're not in that mindset. </blockquote>


**Edith:** Yeah, and I think we touched on this when Scott Raney visited us, the Air Force is having a lot of trouble right now because they basically built a plane where the software doesn't work.

**Paul:** Yeah, I can't even understand that. There's something so wrong with this thing.

**Edith:** Yeah, so the pilot literally cannot take off, because all the different systems don't talk to each other. And avionics right now, is very software heavy. The old days of fly-by-wire are just dead. So that's great, and this goes back to your example, that's great until you're sitting in a $2 trillion paperweight.

**Paul:** Right. A very expensive, very large paperweight. Yeah, think of what coulda been done with those two trillion.

**Edith:** I gotta look up the exact number.

**Paul:** No, I mean it might not be two trillion, but it's in the trillion zone.

**Edith:** Planes are expensive.

**Paul:** The incentives of the military industrial complex are expensive.

**Edith:** I think this is interesting, I think it makes me think more about the ramifications. Smart devices cannot be dumb. Let me rephrase, smart devices need to be built under the assumption that they need to continue to get smarter. I'm not arguing for a Terminator style scenario, where they get smarter than us.

**Paul:** Well, so you end up with a problem where,


<blockquote>Even if they are updatable, there's not necessarily an incentive for them to be updated. So hardware manufacturers typically, you know, make money from selling new hardware, right? And the components, the manufacturers are the same, there isn't really money in something that you've already shipped, and that you've already sold. </blockquote>


**Edith:** Yeah, so at my plant company, we tried to get around this by charging people literally for fertilizer, so we said "if you want to get fertilizer information, you pay us a dollar a month".

**Paul:** So there's a very good blog post, do you know Bolt? They're a hardware VC. They have [a really good blog post](https://blog.bolt.io/the-3-business-models-that-matter-for-connected-hardware-startups-32fbf59506e5) about the bad business models of hardware. And basically,


<blockquote>Selling consumables is great, only where the consumable is the thing that you want to consume. So, selling coffee as your consumable is great, because people expect to buy coffee. But selling toner or selling blades in the Gillette model is not the thing that people actually want, so people feel ripped off by their blades or by their toner.</blockquote>


Because the thing that they want is paper to come out, or is, you know, shaving smoothness. Anyway so, hardware business models are fascinating. And there's a bunch of VCs, I think, all the VCs, or most of them will not invest in a hardware business model that does not have a recurring revenue component.

**Edith:** Yeah, I mean I feel that's per standard, so the plant company, so we sold the devices, and the idea was always that we would generate ancillary revenue somewhere. So one of the things we tried was, recommending plants. And the issue was, we could recommend plants, then we're going to refer people to Burpee, and get a cut from Burpee, and this is back in 2007 or 2008. And Burpee is like "we don't care if you refer us a lot of business, we're kind of this old line, a hundred year old seed company, we're not going to give you a cut".

**Paul:** Could you sell all the seeds yourself?

**Edith:** We investigated doing that, but just logistically, we didn't have enough.

**Paul:** Oh, what you should've done, is a subscription model.

**Edith:** You get a seed, plant a month.

**Paul:** Yeah, plant a month.

**Edith:** You know that's brilliant. So we even started to look at the plant stuff, but there's a ton of regulation around plants.

**Paul:** Oh really?

**Edith:** Yeah, like what plants could be shipped to what states. There are all these agricultural rules around that. So we started to walk down that, and we were like, we don't have enough funding to build a supply chain.

**Paul:** Even for little seed packets?

**Edith:** Even for seed packets, there's a lot of regulation around that.

**Paul:** So, lets completely backseat drive your decisions of 10 years ago. I wonder if you could have experimented and invalidated the business model without building the entire supply chain. Look at all your customers, like 50% are in California.

**Edith:** So in a way we were experimenting by sending the traffic to Burpee.

**Paul:** Oh okay, right. I would say, was there enough?

**Edith:** At the time, no.

**Edith:** So I mean we shipped enough devices that like 4% of people were actually clicking, but it was not enough. We had to keep shipping a lot more devices.

**Paul:** You want more of a dropcam model, where to get value from your thing, everyone must buy from you. Keurig is the same.

**Edith:** Yeah. And, you know, we shipped enough devices that we sold a million in the first year, but that was not enough to.

**Paul:** That is a lot.

**Edith:** A million dollars worth. Yeah, it was really fun because, I got to do all the marketing because there was these hardware dudes who'd built the device and I joined as their first full time product manager in marketing, and they didn't know anything about marketing, but I got to do all this stuff. I got to do the Google AdWords. I got to do Facebook ads, I got to experiment with anything I wanted.

**Paul:** How did you end up as a marketer, from a CS degree?

**Edith:** A long chain of events. Well number one, I got an engineering degree. And an engineer sees a new problem field, and thinks they can attack it. So I was just like okay, we don't have any marketing. I had from a company that had a very successful Google Ads campaign. It was very successful, and I was like "okay, I'll just go build the Google Ads".

The hubris of an engineer is you think you can do anything.

**Paul:** So you got a lot of engineers starting companies. Well how hard can it be? Turns out, it's very hard.

**Edith:** So I went to Harvey Mudd College and it was really hard. It was at the time ranked the number one school in the states, and they would just throw really hard problems at us, you know. Not only learn this thing, but learn about a program to solve it, and that was really good training for life. So I was like okay, I'll just go learn how to do that.

**Paul:** So do you think that all of these IoT companies can learn to ship software updatable firmware?

**Edith:** I hope so, and I think the number one thing I keep coming back on is,


<blockquote>You will never be able to solve all the problems that are going to come up in the future. So all you can do is plan for updatable devices. </blockquote>


**Paul:** I would say that in order for more manufacturers to have the incentives in the right place, they need a cut of the ongoing revenue from their components. Or at least that support contract. And every component needs a support contract and with it a guarantee that they will address security concerns.

**Edith:** Well it's kind of like when people start a coal mine, they have to pay into a super fund.

**Paul:** Exactly like that.

**Edith:** Im serious. It was like, "okay this is a guarantee against any future disaster that you're paying into it now. Because otherwise, people would not open a coal mine".

**Paul:** Right, I mean this thing wasn't created by accident, I mean it was created as a result of an accident no doubt, but there's been a long history of mining disasters.

**Edith:** Yeah, well Paul it was fun as always to talk to you today. Sorry no chocolate. This was a little bit of a last minute podcast.

**Paul:** Yeah well, hopefully, next time we talk it'll be under better circumstances.

**Edith:** Me too. Thanks guys.


