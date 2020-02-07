---
author: mattdel
comments: false
date: 2019-11-14 00:01:41+00:00
layout: post
link: https://launchdarkly.com/blog/spooky-scenarios-in-debugging/
slug: spooky-scenarios-in-debugging
title: Spooky Scenarios in Debugging
wordpress_id: 194522
categories:
- DevOps
tags:
- debugging
- DevOps
- test in production
---

Rick Zucker, an experienced Site Reliability Engineer (SRE) Manager, spoke at the October Test in Production Meetup in Seattle, co-hosted by LaunchDarkly and the Seattle DevOps Meetup. He shared about spooky scenarios in debugging and lessons learned from those scenarios.


<blockquote>"So, what are the lessons? Well, again, be careful about what you take for granted, and as always, consider corner cases that aren't recommended but are permitted. And if you're in QA you definitely need to be thinking that. You always look for all those. And also just be observant about everything." – Rich Zucker, SRE Manager</blockquote>


View the slide deck of Rick's presentation and read the full transcript below to learn best practices for debugging. If you’re interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/).



FULL TRANSCRIPT

Rick Zucker: Okay. So, we're supposed to have a Halloween theme here, and therefore we're talking about spooky scenarios. In this case, it's mostly the spooky scenarios in debugging. So, I will be... A bit of an introduction of at least who I am. And then I'm going to go over two scenarios from debugging, these are things that I actually dealt with. And then I'm going to talk about a related situation from a related discipline, and then obviously some sort of summary.

So, my background is I was software developer many, many, many years ago, but then I spent most of my time doing hardware QA on CPUs, on processors. And I've recently switched over to doing DevOps and SRE, and currently an SRE manager at a big internet company.

Scenario number one. So, we're working on [inaudible 00:07:39] for command, control, communication intelligence. And it really was... This was just office apps out in the field for the military long before a lot of the things that we currently have. It provided email, and they had data-driven graphics, and they have laser disks, so disks like this big with maps on it and read that off, and then we were sending data around from one station to another, which showed where different units were. And then it was in these big hard cases with foam that would hold everything in place.

So, the original system used Apple 2 computers, to give you an idea of how far back we're talking. So, the workstation was an Apple 2 computer, and each communication link was controlled by another Apple 2 computer, so each node will have five Apple 2's plus the laser disk. And then when I started working on this we were switching over with a new system that was based on the Motorola 68000, which was powerful enough that that one computer could handle all four communication links. So, that was the thing that we were doing for [inaudible 00:08:54], and this was written in Pascal, UCSD p-System if any of you remember that or have heard of it.

So, first scenario. So, system just wasn't working right. We were having some problem we didn't know what it was. In those days, we didn't really have a debugger, so what do you do? Lots and lots of print statements. Still sometimes that seems like the only debugger I have. I am helping my son who is studying computer science at Western, and it's like, "You have to have print statements in there".

So, we saw that packets were getting corrupted, so we were trying to figure out what the heck is going on. And we could tell, because we'd put in all these print statements that the packet was basically getting corrupted despite there not being any assignment to that variable. So, you would have a print statement before and after and the value would change what we were assigning to something else. So, what the heck was going on?

One thing to know in UCSD Pascal you have 255 character variable names, but only the first eight matter. After that it doesn't matter. So, here two variables that it might have been: data packet Tx, data packet Rx, T and R are in the eighth location, so this is fine, this is two different variables. Everything should work fine.

Well, we'd noticed the system has a two-pass compiler. Because you know how many times you run a compiler, you're watching the output, and it runs through the compiler and there you see it, okay Pascal compiler, and then it runs through the linker, and you could link from other languages. So what happened was it took Fortran linker now, we kept on seeing that. Now does anybody know why it's important that it was a Fortran linker? Or am I the only one who's been around long enough to know this. Not sure?

It was probably. Fortran only has six character variable names. So, what's happening with the Fortran linker? It maps both variables onto the same location because the first six characters are the same even though the first eight are unique. So, basically we hit a compiler bug. As I thought about it a bit more, I'm not sure if it's fair to call this a compiler bug. The Pascal compiler was doing exactly what it was supposed to, the Fortran linker was doing exactly what it was supposed to. The problem was it was really a compiler system bug I would say.

In a way, it's almost like copy and paste. Your taking codes from somewhere else and putting it in another location, but it doesn't quite work now. I've seen this in hardware. I'm sure we've all seen things like this in other parts of software. But the real problem is we trust our compilers, we don't think that that's the problem that we're having so that's why I consider this sort of spooky because everything, it's like, "My code's fine. What's wrong with this thing?"

So, I think that one of the lessons is be careful when combining two pieces of software together, but eventually if you're just so stumped eventually you have to really doubt the thing that you should never doubt. I've heard there was a science fiction book in June that sort of said, "What's the thing you would never doubt?" That's the thing that's going to break you. If you don't remember what it is I can tell you some other time afterwards.

And it was only because we'd solved the compiler, the output every time we ran it that we realized, "Oh, Fortran linker." I programmed in Fortran on that system before I had ever [inaudible 00:13:18].

Scenario two. I was working on the design of a CPU chip, and I was doing what was considered QA. We called it pre-silicon validation or verification. My area was focused on multi-processor scenarios, so I was trying to break cache coherence. I wrote lots of very bad parallel programs, so like have a cache line where this processor writes this portion, that processor writes that portion and thrashes to back and forth because you're trying to put the hardware under stress, just the same way as QA of software you are trying to break things. So, a lot of things you don't normally do.

And almost all the bugs it found they were either... Things are broken into clusters and then units, where either the memory cluster or the bus cluster which has a lot to do with cache coherence.

So, one thing to think about is that normal programs try to align data properly. In fact, there are some processors that only let you align things, so if you consider in this situation, that's a 32-byte cache line and you have 32-bit word you're storing, and each of those are in four-byte boundaries there. That's the way things are supposed to be.

When I was in QA, the last thing I would do is what you're supposed to do. If it's legal, we would do it. You should hear some of the things the architects would say, it's like "you're doing what? You can't do that." And I said, "It's not this bad, we can.” Actually, these days even if it's not in the spec, it doesn't fail, doesn't fault, we would try to do it [inaudible 00:15:17]. That's how you find security holes.

Okay, so I would do things like, okay, be off by three bytes or something like that. So, I deliberately misaligned the data, you know you mix these things, you randomly add them in together. So, we have a case where the test was going wrong, we were trying to figure out what's wrong in the hardware. And it's doing a write to the wrong address. So, as usual I sort of remembered the cluster in the bus cluster. Obviously, this is a very simple CPU diagram, but it gets the point across. There was, I don't know how many stages that were in the pipeline. There were a lot.

Anyways, so I started looking at the memory bus cluster, and as I said that's the area I knew because that's where I found all my bugs. So, it turns out the address that was coming to the memory cluster was correct, was what we were writing. We were writing based on what it told us. I needed to get help from the execution cluster, okay how are you calculating the address and the address calibration unit, we looked at it, everything was fine, no idea what's going wrong.

Okay, let's take a look at the decode of the instruction, the little bytes that it was sending on. That was all in sync.

Okay, let's take a look at the fetch and pulling the data out of the instruction cache. Go back and look in the instruction cache, split I and D caches. It also has the wrong address. Okay, this is getting pretty weird, so someone suggested take a look at memory. Now this is simulated memory, it's a software model. I think I forgot to say it because it's hard for me to see that side, and it's too small on my screen to read it. But this is a simulator running at 10 hertz, so really you got to trace things a lot.

Anyway, so the address was wrong in the main memory, in the object code. Okay. So, next we don't know what the heck is going on. Okay, so we check the object file itself after it's been assembled, because all of this is an assembly line, but you want to control the machine completely.

So, the assembler generated the wrong address. Last time it was a compiler bug. This time it's an assembler bug. We ended up having to write a macro so that we could generate the code ourselves, but what it was in some ways is that it's a corner case, so we're already doing things they don't expect us to do, and then it’s a corner case for quote-unquote, "Bad code," but it's still legal code.

So, what are the lessons? Well, again, be careful about what you take for granted, and as always consider corner cases that aren't recommended but are permitted. And if you're in QA you definitely need to be thinking that. You'll always look for all those. And also, just be observant about everything. There as much to see here, but it's something to think about.

So, sometimes you have to be paranoid. Now that shouldn't be your first choice, but sometimes you have to be. I guess my question is who else is paranoid and doesn't trust anything? Security people. This is a scenario, this is from a former co-worker of mine, runs his own business. That's his Twitter handle, and he has a business doing hardware security. He does a lot of training; in fact, I think he was just up here a few weeks ago. He was trying to do a proof of concept of a device to securely wipe flash drives, because think about it, you've got some information on your flash drive and you want to wipe it, but maybe you don't trust the computer or something. It's either especially private data or secure data and so you want some way to do it, and so he was trying to demonstrate that you could create a standalone device. And so, the device wouldn't have a USB interface. It had a serial interface for programming it, and it had that onboard microcontroller, and it could operate standalone.

So, the question is what do you trust? So first he's got to program the serial cable. Do you trust the serial cable? What do people think? Well, he said, "you know trust the serial cable." He just goes down to PCH Cables, grabs a random cable. This is a guy by the way who has been one of those involved in breaking into voting machines and using special cables to demonstrate how you can steal from people’s phones, but he thinks with a random cable he will be okay.

How about the micro-controller? Well, he considered this sort of out of the scope of the issue. I mean you could say, "Maybe the microcontroller was not viable in what's a fairly standard design,” but what about the IDE compiler? So that he didn't trust. He had to download the IDE package and it wasn’t signed, and it used HTTP not HTTPS, which is one reason why we need to move to the next generation so that that's built in, and he said, "No. Okay, I don't trust thing. I would not market this product with my name on it." So, in a way this is like the ultimate release fraud. He didn't produce a product because he didn't trust that he could do it securely enough.

I would say lessons learned is, how much do you trust your supply chain? You have to really think about some of those things. That gets to the heart of it. And think about where might the bad actors take over? What can you control, and whom can you trust?

So, I would say in conclusions, some problems in places you would never suspect, and sometimes you eventually have to think that. What's the Sherlock Holmes saying that, "Rule out the impossible. Whatever is possible, then that [inaudible 00:22:24] must be the problem." And I would still say this, start normally but eventually you're going to get to the point where you have to be really skeptical about things. And remember tools, they're just software. How perfect is the software that you write? So, that's my spooky tales for Halloween.

Any questions? Yes.

Speaker 4: Did you guys write a linter or something for the [inaudible 00:23:04] versions, so you got [inaudible 00:23:04].

Speaker 4: Did you write a linter or something that made it so that when you guys wrote it more than eight characters or six characters it was automatically throwing errors or?

Rick: No, we didn't think of doing that. This was back in 1984 and on a microcomputer. The idea, we never considered. I don't think I'd heard of linters then. I didn't even know C at that point. Would have been a good idea.

Host: Anyone else?

Rick: Any other questions?

Host: All right give Rick a big hand.
