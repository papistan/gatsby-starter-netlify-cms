---
author: andreaech
comments: false
date: 2016-05-18 23:32:27+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-have-we-forgotten-how-to-code/
slug: to-be-continuous-have-we-forgotten-how-to-code
title: 'To Be Continuous: Have We Forgotten How To Code?'
wordpress_id: 897
categories:
- To Be Continuous
tags:
- Closure
- CORBA
- kik
- Linux
- Maven
- microservices
- Node.js
- open source
- open source software
- Pyhon
- ruby
- The Inmates are Running the Asylum
---

In this episode, Paul and Edith discuss the fallout after the widely covered ‘[left-pad](https://www.npmjs.com/package/left-pad)‘ incident, and while they agree that these sorts of moments move the entire open-source community forward, they wonder – have we forgotten how to code?re. This is episode #19 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.





**TRANSCRIPT**

**Edith:** Hey Paul. Somebody unpublished a module called left-pad and the Internet basically exploded. Now, it's been a couple of weeks since then so there's a lot of different topics to cover in terms of what this means for Open-source, whether it means that people have forgotten how to program.

**Paul:** LaunchDarkly. Sorry, the left-pad... Obviously I'm looking at my own T-shirt.

**Edith:** You're looking at your LaunchDarkly T-shirt?

**Paul:** The left-pad incident was pretty interesting and one of the things that we did when coming up to this is just like looking at all the hacker news, discussions, and comments on it. There's wildly varying positions on what this means for open-source. What it means for whether people can program. What it means about the Node ecosystem. To kick this off, why don't you give us a recap of the entire incident.

**Edith:** In short, a programmer had a module called kik, K-I-K. Which is also a very popular messaging app. Even I've heard of it and I'm not a teenager. The Kik lawyers contacted the dude, said, "Please take down your module. Change it." The programmer said, "No. I basically don't believe in copyright laws." Then, the Kik people contacted NPM, the NPM people took down the module called kik. The guy, I'd say I kind of a fit of pique said, "Okay, you took down my one module. I'm going to take down all my modules." Basically, I'm taking my marbles and going home.

**Paul:** Okay.

**Edith:** He took down all of his modules, one of which turned out to be an incredibly popular module called left-pad which did basically what the name implied. It inserted left pads. Without this in NPM, the quote I read was, "Builds all over the world started to fail very quickly."

**Paul:** As I understand it, left-pad was used by another module which is used by another module which is used by something core or like this incredibly popular module.

**Edith:** It was basically turtles on top of turtles on top of turtles and at the bottom turtle was this guy who...

**Paul:** Took his marbles and went home.

**Edith:** Yeah, or yanked the bottom Jenga, basically.

**Paul:** Gotcha. All the builds started to fail, people's deploys started to fail and people got pissed.

**Edith:** People got pissed because they didn't even realize that they had this dependency. What happened was NPM basically republished it. They said that, "Even though you're the original publisher."

**Paul:** There was a lot of outcry on the Internet and then they republished it.

**Edith:** NPM just basically said, "You don't have the rights to unpublish this."

**Paul:** Gotcha. They had an unpublish button as I understand it. He did something that was built into NPM to remove a module.

**Edith:** Since then, they've tightened their rules a lot. They've basically said that this should be something that's used extremely rarely if at all and not that you can just do capriciously.

**Paul:** One thing that's interesting about the NPM ecosystem, and the Node ecosystem in general, is they've had a bunch of things like this. Things that are security related or that are drama related and people have repeatedly come out and said, "Node.js is a tar pit" or "ghetto" or whatever it is that people use to describe poor ecosystems. That Node programmers don't know how to code and so on and so on. What it looks to me like is each of incidents brings the Node ecosystem quite a bit forward to the points that... Node is relatively new.

It hasn't had 15 years before prime time in the way that Ruby or Python did or 20 years before it got big and it's a real bottom-up thing. Someone built it and there were some stewards and then someone else took over and then NPM took over. It's this sort of weird language from an ecosystem perspective and it didn't have the same advantages that Java had or that C or C++ had in order to get to maturity. Each of these incidents propels it closer to maturity.

**Edith:** Yeah. I compare it somewhat to when electricity first started coming out. You were just working through all issues that could happen. For example, a power line went down or a transformer blew. You work through,


<blockquote>Okay, what are our points of failure. Let's not make that a point of failure again.</blockquote>


**Paul:** NPM changed their policies on the namespaces, right?

**Edith:** Yep. Now you can't have an individual contributor being able to unpublish even if they originally published. Now you have to contact them and it's much more stringent.

**Paul:** Gotcha. Their response, despite people... Well, people were annoyed at their response.

**Edith:** It seems perfectly rational to me.

**Paul:** I think it seems perfectly rational, and this is the thing about the Internet. There's always some set of people who are annoyed at everything you do.

**Edith:** The Internet if full of billions of people. There's got to be some sort of standard deviation or otherwise it would be a very boring Internet.

**Paul:** Right, and this is why there's always haters on hacker news. No matter what you do, if you do it one way there'll be one group of haters. If you do it the other way there'll be a different group of haters. With left-pad there was people who were annoyed that NPM retroactively decided that they had ownership over their namespace which previously they had sort of gifted to people in the community, the first people to take the namespace.

**Edith:** You mean the original thing about K-I-K?

**Paul:** There's that, but also the left-pad. They took away the sort of autonomy of the left-pad author.

**Edith:** I read a good article that basically says part of Open-source is, if it truly is Open-source do you maintain the rights to it or is it a community project?

**Paul:** The traditional way of deciding that sort of ownership was the fork.

**Edith:** Yeah.

**Paul:** You could go and you could fork. When you forked your weren't necessarily entitled to the same name, you weren't entitled the same trademarks. When Debian forked Firefox, they called it Ice Weasel. When Jenkins was forked, or Hudson was forked it became Jenkins. Even Emacs has had multiple forks and GCC got forked. They all got new names, but what was the fork here it wasn't even a fork. It was a republish of the same thing, the same software, in a namespace that the original author didn't control. Typically, you own the URL, if you have a software library you own the URL. They did own, in some sense, the URL within NPM or the name within NPM space and NPM, the sort of owners of that namespace, overwrote it.

**Edith:** I think they did what was necessary for good order.

**Paul:** Sure. I completely agree. I think that was that was a good decision.

**Edith:** I mean, to take this to a logical conclusion, what if you had a module named left-pad and you decided that, like as a prank, you were going to rewrite it to be right-pad. Sure, that's... Is that within your rights? Kind of, but it's a real jerk thing to do that you probably want to prevent.

**Paul:** This is kind of one of the dangers of the whole ecosystem around centralized package managers of, sort of trusted package managers.

**Edith:** Yeah.

**Paul:** Where there's no actual trust involved. What I mean by that is what is published does not have any gatekeepers.

**Edith:** Yeah, exactly.

**Paul:** It's great. It allows an ecosystem to grow much faster, but it has safety concerns because people generally don't pin their packages to an exact version.

**Edith:** You're basically pinning it to a floating value.

**Paul:** You're pinning it to a floating value and that floating value could change. There's no guarantee of what a minor number means, what major number means, what a patch means, of what a patch even means. There's some sort of like general community guidelines in semantic versioning, but there's no enforcement of that.

**Edith:** Yeah, and I mean this basically goes back to the whole Cathedral versus Bazaar.

**Paul:** It's very Bazaar.

**Edith:** Well, bizarre and Bazaar.

**Paul:** Intentionally so. It's the thing that allows a community to grow. Is there a point at which Open-source communities need to like, batten down the hatches to prevent that sort of behavior or to prevent that sort of risk?

**Edith:** It's really interesting. I think this goes back to something we talked about with Nadia and Sean [a couple episodes ago](https://blog.launchdarkly.com/to-be-continuous-open-source-economics/) about when you buy from a corporation you have some sort of guarantee of standards that they publish somewhere that, "This is our guarantees", versus with Open-source you don't normally have those same sort of guarantees.

**Paul:** Even when you do it tends to be a...

**Edith:** There's no enforcement mechanism.

**Paul:** Right. There's no enforcement mechanism in the Bazaar.

**Edith:** There's no... Like, so with a company. If a company has said, "Okay, we're going to release twice a year and it's going to have this level of quality and they break that. You can walk with your feet or your money.

**Paul:** Right.

**Edith:** If an Open-source project stops or does something you don't like there's very little enforcement.

**Paul:** Theoretically, you could walk. You could fork the thing, but when you end up in an ecosystem that has massive network effects in the way that NPM does you can't walk with it. Because dependencies is all transitive, the left-pad was a turtle way at the bottom of the stack.

**Edith:** It was almost like a turtle hatchling.

**Paul:** To fork left-pad you would have to fork the entire NPM ecosystem.

**Edith:** It's not even... The fork is not the issue. The issue was that people were depending on it being in a certain place in a certain way. It wasn't that it wasn't forked, it was just like this entire structure at the bottom was gone.

**Paul:** I guess what I'm saying is that if you get pissed off with a certain set of developers or a certain set of practices within the NPM community, because they're so interlinked, you don't have the traditional Open-source option of forking.

**Edith:** Absolutely.

**Paul:** You could rename it. You could pick a different library, but because of the way... I'm not sure if they still do this because I read something about it. NPM, it used to be that the version of software that your library took was the version that library got. Do you know what I mean by that? Okay. Let's say I have a... There's some software. Let's call it left-pad.

**Edith:** Let's call it right-pad.

**Paul:** Right-pad. Right-pad version one is being used by library A and right pad version two is being used by library B. In the Java ecosystem and many, many other ecosystems only one version of Right Pad would be used.

**Edith:** Yeah.

**Paul:** I believe in NPM, both versions of right-pad would be used. Library A will use version one and library B will use version two. That's definitely the way that it used to be, I'm not sure if they've actually changed that.

**Edith:** I don't know, but that sounds very messy very quickly.

**Paul:** Both options are terrible.

**Edith:** Yeah.

**Paul:** There isn't a right way to do it. Really what it depends on... The NPM way of doing it, every library get it's own version of the dependencies is fantastic because it lets that library do what it actually intended to do under the covers. If however, you start having an object that gets sent around, that two modules are... Let's say receives a, I think a http packet or somebody like that would be a good example. Let's say you take a http packet from one module, you send it to another module and they have different understandings of the shape of that object or what functions you can run on that object. Then that's messy.

**Edith:** Yeah, absolutely.

**Paul:** On the other hand, if you override the version of right-pad that some other libraries using it you end up with all sorts of problems. This is a major problem in the sort of the Maven ecosystem. At CircleCI we use Closure and Closure is built on top of the Maven ecosystem and we would have bugs where the library that we used... One library that we used had a dependency and that was in the package file before another thing and so that's the version of the packets that we used.

**Edith:** Yeah.

**Paul:** We would have to pick... To resolve that we have to pick the library that works and often that there isn't a library that works for both or there isn't a sort of sub dependency that worked for both. There's a clusterf*ck no matter which way you do it.

**Edith:** We run into the same issues with our SDKs because we have dependencies on other libraries that sometimes get flipped.

**Paul:** Right. Disaster.

**Edith:** On the other hand... I mean the bigger point I think was... There was an interesting backlash, I think, that everybody kind of projected what they wanted on the NPM thing. People said, "People don't know how to program anymore." Why do you even use it if they call it left-pad?


<blockquote>Why don't you just grind your own wheat and make your own bread from scratch and eat it at lunch also.</blockquote>


**Paul:** I have no sympathy at all for this view of the world.

**Edith:** That you should make everything from scratch?

**Paul:** That we've forgotten how to program because we left-pad.

**Edith:** The fact that we have modules available that make it easier and easier and easier to program is a good thing.

**Paul:** I think it's kind of different to that. I think it's more of a curmudgeon view of the world. It's a get off my lawn ..

**Edith:** Wait. That you're the curmudgeon?

**Paul:** No, the people who complain have we forgotten how to program anymore. I think it's a [No True Scotsman](http://rationalwiki.org/wiki/No_True_Scotsman) kind of argument. Real programmers know how to write their own left-pad. Real programmers write in statically typed languages. Real programmers write in C. Real programmers - I'm going back in time here - Real programmers write in assembly. Real programmers hand code their... Tweak the needles on the...

**Edith:** They do their own garbage collection.

**Paul:** Garbage collection. What is this? Garbage collection is for amateurs coders. You can just as easily have written, "Have we forgotten how to manually allocate memory?"

**Edith:** Or you might as well say nobody knows how to make their own transistors anymore. I mean the entire computer revolution has been that you no longer have to assemble a computer by hand.

**Paul:** Right. Each layer of the ecosystem allows a vastly larger number of people to take part in it. I think the thing that we're seeing now... This has been happening for five or 10 years, but what's getting really, really big now is people who only know how to Front-End program. People who only know JavaScript, and HTML, and CSS, and they go to boot camps and they come out... Maybe have some like vague rails understanding and they call themselves coders and we the real programmers who know how to write a quick-sort and who know how to write a left pad, we don't welcome them to our community and frankly, I have felt this in the past I've have since changed my mind, but it's a very, very common perspective.

**Edith:** I think it goes back to the medieval times.

**Paul:** Mm-hmm. I totally see it.

**Edith:** The entire reason why there were guilds and apprenticeships was because people didn't want their knowledge to be cheap.

**Paul:** Right.

**Edith:** Like, so it used to be the reason why being a doctor takes seven years is because they wanted it to be something that only a few could do and they can then charge a lot of money.

**Paul:** You can protect your industry to protect your own value to society.

**Edith:** Yeah.

**Paul:** Or just your earnings even.

**Edith:** Your earnings. If somebody could go to boot camp and learn for six months and become an adequate coder in front-end, suddenly it's very hard to justify charging, or getting paid, $180,000.

**Paul:** Right. The more programmers there are in the ecosystem, the more people available to hire, the less valued your skills become.

**Edith:** I'm certainly going to argue both sides. I think a talented programmer does have a deeper knowledge of the bubble sort, the quicksort. I think there's a place in the world - and welcoming place to be honest - for people to do lighter coding and that there's people with more time on the job can become more sophisticated.

**Paul:** One of the ways that I learned to look at programmers is that


<blockquote>there's people who write the tools and there's people who use the tools.</blockquote>


**Edith:** Yeah, exactly.

**Paul:** To say... I think a lot of people think, "Oh, only real programmers write the tools." I was are susceptible to this because I worked in compilers and we wrote the tools that the tool makers wrote.

**Edith:** Did you have a factory that made mini factories?

**Paul:** I wish. I think what we see with people who are at the end of the chain. The people who are for harnessing the libraries in the NPM ecosystem and then the browser and that sort of thing to build really fast, really like innovative things

**Edith:** Yeah.

**Paul:** That frankly the tool makers would never have thought of. I don't think that that's looking at the world through tool makers are the real programmers and the other guys are kind of they use the tools. I think it's not a very good way to look at the world. I think the... Everyone's focusing on where their real value is.

**Edith:** I think a lot of the wave of innovation that we've seen in the last 10 years has been because programming is a lot easier.

**Paul:** Right, exactly.

**Edith:** LIke the fact that there's... You know, Uber was because you didn't really need a lot of fancy programming when they first started out. Now they have incredibly complex programs. Just to get a basic...

**Paul:** We're seeing this happening in the AI revolution that's happening at the moment. Facebook launched its platform today and I'm not sure what the platform does exactly, but now to build bots is infinitely cheaper than it was like a year ago. Building AI and connecting people to do these things is so, so much easier than it was a year ago and a million times easier than it was like 10 years ago.

**Edith:** I remember it used to be to even get like a basic web app up, you had to have knowledge all the way up and down a stack.

**Paul:** Right.

**Edith:** Now, with AWS, and Heroku, and DigitalOcean you can get stuff up just much quicker and then you could focus on what's the true business value of what you're building instead of just it's so hard just to get words on a page.

**Paul:** I've been talking... I'm not sure if I've talked about it on the podcast, but certainly this is an idea that I've been running through awhile. In the future, people are going to build with very, very simple understanding of - or possibly no understanding - of the tools beneath them.

**Edith:** I think that's great.

**Paul:** You're going to be able to build something that's like at the level of complexity of like a Tinder or a Snapchat with just one product manager who's not not really a coder in the way that maybe now or maybe five years ago that we thought of a coder, but they're going to be building applications with barely any coding knowledge at all.

**Edith:** I think that's great

**Paul:** Oh yeah. Completely great.

**Edith:** I compare it to the industrial revolution where it used to be that just getting power was a task in of itself. The reason why there were mills on streams was they had to locate them there so they could grind the wheat. Suddenly, when there was electricity, you could focus on, "Hey, not everything has to be around a river. Let's build factories everywhere. Let's make cool stuff." That was the... It wasn't just about generating power, it was, "What can we build now that we have power?"

**Paul:** As a necessary part of this, you end up with something like left-pad.

**Edith:** Yeah.

**Paul:** Left-pad is a little bit trivial in that sense, but I think that one of the most entertaining parts of this thing is that left-pad had a quadratic bug in it. Accidentally, the left-pad had some form of quadratic behavior in it and no doubt it would've got fixed in a later version and everyone got automatically upgraded and so on. The idea that you're coding your own version of left-pad means that you're probably going to have quadratic behavior in it and that's going to be used to exploit your system at some later date in the future.

**Edith:** I totally agree with your metaphor that there'll be less and less coding and more and more value.

**Paul:** Right.

**Edith:** I do think though, to argue the other side, I do think though that... I'm thinking more about what you said about the people who build the tools.

**Paul:** Okay.

**Edith:** I do think they need to have a different skill set then. I mean, I go back to the...

**Paul:** You have a different set of users, you have a different set of responsibilities and they do different things and have different properties.

**Edith:** It reminds me very much of... I love Richard Feynman I read all his books when I was growing up and he talked about how he'd learned so much from assembling and reassembling radios.

**Paul:** Okay.

**Edith:** Which just wasn't something that was possible when I was a kid because we've gone to solid-state electronics.

**Paul:** Oh, okay.

**Edith:** I think we're starting to see a similar transition in coding.

**Paul:** That people can't take apart their things?

**Edith:** I think, in 20 years people will be amazed at how much access we had to different...

**Paul:** Different components like how open the ecosystems were. That sort of thing?

**Edith:** Yeah. Just that things that we take for granted now will become completely opaque.

**Paul:** People are lamenting this and have been lamenting this for a long long time. One of the first comments I saw on hacker news on the Facebook messenger platform thing today is, "Whatever happened to the open ecosystems? We had IRC, do we really need to this thing?" I agree to a certain degree that the open ecosystems are...

**Edith:** You agree to a degree?

**Paul:** I agree that open ecosystems have some value. What I think that people often don't get - especially in the Open-source ecosystems - is that usually the best product wins. The openness, basically no one cares. Especially now that these tools go from early adopter to like mass market in such a short period of time. Like, IRC is a fucking wasteland. All the tools around AIM and Pidgin and that sort of thing. Around the IM ecosystem are terrible. XMPP, the protocol doesn't allow you to do anything remotely like what Facebook platform or what WeChat which is what Facebook platform is going to become. As a result, they lose. Primarily they don't have 900 million people on them.

**Edith:** You know, when you were talking it reminded me very much of Steve Jobs and Apple computers. Because originally the computers were the province of the hobbyists who would literally build them from hand from parts. Like Radio Shack.

**Paul:** Yep.

**Edith:** Then, he said, "Okay, now it's this closed box that you can't open.

**Paul:** Yep.

**Edith:** Everybody's like, "You're not going to sell any." He sold gajillions.

**Paul:** He eventually sold gajillions. If you're in San Francisco you'll see that there's only Macbooks. If you see someone using a Windows computer...

**Edith:** It's funny because I'm looking around the podcast room and there's six separate Apple products for three people.

**Paul:** Right. There's actually five computers for three people.

**Edith:** I blame our producer Ted for the proliferation.

**Paul:** Everyone in this ecosystem is familiar with Linux. At least all the engineers, let's say within this ecosystem, have used Linux. Used Linux on the server, maybe they used Linux as a kid or when they were growing or at least in some way younger on a Dell.

**Edith:** I remember when Linux was new.

**Paul:** Well, we'll just move on from that. What I'm saying though is it's not like we were unfamiliar with Linux. I used Linux for many years and I eventually got sick of it. Apple products were a much, much better product and so I couldn't dig into the, you know, deep deep down into... Well, actually didn't do that very much on Linux anyway.

**Edith:** Yeah.

**Paul:** I could, theoretically, if I learned all the stuff and all the vast, vast competing bullshit goes on in the Linux development community, in the Linux desktop community. Frankly, I couldn't use WiFi so I switched.

**Edith:** It's an eternal debate of product manager versus engineers except for the product manager is Stockholm Syndromed.

**Paul:** This goes back to our discussion from a few weeks about how [Open-source needs product managers](https://blog.launchdarkly.com/to-be-continuous-open-source-economics/)?

**Edith:** Well, no. I remember... This is when I worked for a content management system and I would go on customer visits with our architect and the architecture designed a system for architects.

**Paul:** Of course.

**Edith:** Where you could tweedle everything, disassemble everything on the fly, have complete control. We go out to these newspapers or hotels and they're just like, "I just want to put a picture of a horse on page." Like, "I do not want to twizzle all this stuff." It was amazing because the architect, we'd go to the same meeting, we'd go back and he's like, "Did you see how excited they were bout my configuration?" I'm like, "Marriott screamed at you."

**Paul:** Actual Stockholm Syndrome.

**Edith:** I was the product manager at the time and I was just like, "No, they do not want your configuration. They want less configuration. They are tired of configuring."

**Paul:** There are definitely engineers who can only design for themselves, can only empathize with their own usage.

**Edith:** Yeah. It goes back to... I mean, have you read "[The Inmates are Running the Asylum](https://www.amazon.com/Inmates-Are-Running-Asylum-Products/dp/0672326140)"?

**Paul:** I haven't.

**Edith:** It's a really good book. It's about, as the tin says, you know engineers designing for... They think everybody wants all this control and people just want to turn on the tap water and have water come out.

**Paul:** Going back to the left-pad debate. A lot of the people who are screaming about the, "Have we forgotten how to code", are basically applying their worldview to a whole bunch of people who have a different world view.

**Edith:** Yeah. I mean, to continue on the electricity example. No, I don't want to have to do my own electricity. I just want to flip the switch and have it come on.

**Paul:** Right. Oh, but I want to be able to dig into my house and I want to be able to change the voltage because I might have a thing that something, something, something.

**Edith:** I might have brought back a hairdryer from Australia and I urgently need to use it.

**Paul:** I need one in every room so every room has to have a 110 thing and a 220 thing.

**Edith:** That house is going to burn to the ground.

**Paul:** Right. Exactly. And the system is built around having people's houses not burn down to the ground. This is kind of - again back to left-pad - the NPM people have a vested interest in not letting people's houses burned to the ground.

**Edith:** Well, yeah. I think it's like with anything. You don't realize it's an issue until it's an issue.

**Paul:** Right. What did they do to fix that? What was their...

**Edith:** Like I said. They changed their policy. They said you can no longer unpublish.

**Paul:** Okay.

**Edith:** It's for rare emergencies so basically a "Contact Us" instead of a button.

**Paul:** They stood by the kik naming decision

**Edith:** Yep.

**Paul:** They stood by the ability to remove the kik package. Good thing the kik package wasn't at the bottom of that turtle thing.

**Edith:** You know, that might have been an interesting thing. I mean, what if it turned out that he kik was actually...

**Paul:** Left-pad was kik.

**Edith:** Yeah. It's interesting. I actually think the Kik people were in the right. I think it was something that was very easy to confuse. Kik is a well-known brand.

**Paul:** Right. Why was it called kik?

**Edith:** The guy said he thought... The non-Kik guy. The programmer just said he liked the name.

**Paul:** Oh, yeah. That happens all the time. You got a three letter thing that sounds a bit like a common word in English and that's going to happen.

**Edith:** He also said that he didn't believe in copyright law.

**Paul:** Well, seems like a very expected result of when you don't believe in a thing that all the rest of society believes in.

**Edith:** Yeah.

**Paul:** Eventually, society's going to step in and just sort of move you aside.

**Edith:** I thought the way you handled the Uber logo was very gracious.

**Paul:** Well, I mean, we don't own the idea of sort of two concentric circles.

**Edith:** What?

**Paul:** I know, right? Theirs was a square and a circle so you might argue that it wasn't even like our logo, but certainly when I look at it I see the Circle logo and it reminds me every time.

**Edith:** Does it make you feel good that you could go all over the world now and see CircleCI's logo?

**Paul:** No, because it's not actually CircleCI's logo. It's Uber's logo. At least until they have their next top-down redesign.

**Edith:** I think the overall thing is I think the system is still working out what it means to truly have [microservices](https://blog.launchdarkly.com/why-microservices-need-feature-flags/). I think that this is a good trend.

**Paul:** Sorry. Microservices? How does this tie to microservices?

**Edith:** Well, the left-pad was basically a microservice.

**Paul:** Well, the left-pad was a library. Now, someone made left-pad as a service.

**Edith:** LPaaS?

**Paul:** Yeah. LPaaS is now category in the way that normal PaaSes are. Someone took left-pad, put it behind a REST API and published it. Humorously, not for actual money I think. I'm sure you could pay them.

**Edith:** People pay for feature flags.

**Paul:** I wonder what is their monetization, then. Is there a management service behind left-pad that you can control. Like, have how much padding your developers can have. You can have an audit trail of how often people pad their strings and you might want to make sure that your developers aren't padding strings too often.

**Edith:** I feel like you're teasing me but I'm not completely sure.

**Paul:** No, no, no. The general way that people turn something like this into a service is they provide a management layer behind it. I mean, feature flags is the same thing. Your product is the management layer of the feature flags, not the idea that you can write an if statement in code.

**Edith:** Yeah, I mean that's certainly why people are using us. A feature flag is easy, management is hard.

**Paul:** It's the same CircleCI. People don't buy it in order to run a test somewhere because they have plenty machines that they could run tests on. They buy the management service, the unifying place where everyone is doing this thing, where everyone on their team is doing this thing.

Back to the microservice idea. I think one of the difficult things that people have to deal with is where do you make the boundaries of your microservice. If you're being strict on the use of the word micro, left-pad would very easily be like the level of micro that people are talking. I think that's a little small, personally. I kind of think of it as like, "We have our billing service and then once billing gets small enough that we need to abstract it into like the PayPal service, and the Stripe service, and the invoicing service." That's a result of how large our architecture or our customer base is.

**Edith:** I don't know. I think it's an entirely appropriate size. It reminds me of like, I get asked a lot, "What's the appropriate level of feature flag?" My basic answer is, "Whatever you want." You can do it with literally with every check-in.

**Paul:** You could have a different flag for every... Do people do that?

**Edith:** Sometimes.

**Paul:** That's interesting. Is that how people do their continuous deployment in the LaunchDarkly world?

**Edith:** Then we have people who do it at a much, much higher level just for like a major infrastructure project.

**Paul:** Gotcha. Oh, that's interesting. As you deploy a new web server it would check the feature flag for what version that is? Is that the kind of level we're talking about?

**Edith:** Yeah.

**Paul:** That's really cool.

**Edith:** Yeah. I think of feature flagging as a technique and I think people sometimes expect us to be more prescriptive than we are.

**Paul:** Okay.

**Edith:** In terms of how much... Like, what you said about microservices. How much should I feature flag? I think I give what comes across as a bit wishy-washy which is, "however much you want."

**Paul:** Right.

**Edith:** I think people think they have to... At one end is the people who have wholly bought into trunk based development and they feature flag everything.

**Paul:** Oh, okay. I guess once you can feature flag everything you buy into trunk based as opposed to branch based.

**Edith:** Yeah. If you're full trunk.

**Paul:** That actually makes a lot of sense.

**Edith:** Yeah.

**Paul:** If you start from the start your branch is your feature flag you probably get very, very good at making sure that you don't break shit as a result of it. You also get very good at the idea that everything goes out with a feature flag.

**Edith:** Yeah.

**Paul:** One of the problems that we had with feature flags, initially when he started using it, was that people would build a new feature and it would start by like eviscerating the old feature and then they'd build a new feature in it's place and it would look perfect and then someone would say, "Oh, we should put a feature flag in this." Well, that would take me another two days. I'd have to go back and redo all this work, put it over there, put it behind a feature flag. I see that it got very difficult to build a competency of, "We're building this other feature on the side and then we're going to switch to it by a feature flag.

**Edith:** The way I think of it is you're building a new railroad track.

**Paul:** Right.

**Edith:** The first way is basically... There's this is hilarious cartoon I've seen of like, somebody trying to fix a railroad track while the train is moving. The feature flag way is more like, "Hey, let's build another track."

**Paul:** Then we're ready to switch to it.

**Edith:** That reminds me of microservices. Microservice is kind of a made up term so I think everybody's still trying to figure out, "What does that actually mean? How micro and mini are these in macro?"

**Paul:** As far as I can tell, microservices are just services around architecture.

**Edith:** Yeah.

**Paul:** They're really... Anyone who's using microservices is largely building SOAs and microservices is the common term that people use to describe it and no one's really that concerned with making them micro.

**Edith:** Yeah. Well, I didn't think SOA fell out of so much of favor.

**Paul:** Because it got tied to things like SOAP. Software is a very fashion oriented world.

**Edith:** It's funny that way.

**Paul:** It really is. Maybe everything else is.

**Edith:** No. Terms are popular. Like, CORBA used to be the thing and now people are like, "CORBA?"

**Paul:** CORBA is the kind of thing that you associate it with service oriented architectures.

**Edith:** No, CORBA was before it.

**Paul:** I kind of put them in a similar box.

**Edith:** Under the box of old things.

**Paul:** The box of old things that I've touched once or twice and happy that I'm never near them again.
