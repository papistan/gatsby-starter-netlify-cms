---
author: heidiw
comments: false
date: 2017-08-28 21:30:39+00:00
layout: post
link: https://launchdarkly.com/blog/all-the-pretty-ponies/
slug: all-the-pretty-ponies
title: All the Pretty Ponies
wordpress_id: 1990
categories:
- DevOps
tags:
- 0wnage
- feature flags
- pwnie awards
- security
- SHA-1
- WannaCry
---

August is always full of security awareness in the wake of DefCon, BlackHat USA and their associated security conference satellites. Las Vegas fills with people excited about digital and physical lockpicking, breakout talks feature nightmare-inducing security vulnerabilities, and trivially simple vote machine hacking. The ultimate in backhanded awards are given out to companies and organizations who made the world less secure, usually because of an overlooked flaw.

[The Pwnie Awards](https://pwnies.com/) (pronounced pony) are the security industry recognizing and mocking organizations who have failed to protect their data and their users. There are categories for:



 	
  * Server-side Bug

 	
  * Client-side Bug

 	
  * Privilege Escalation Bug

 	
  * Cryptographic Attack

 	
  * Best Backdoor

 	
  * Best Branding

 	
  * Most Epic Achievement

 	
  * Most Innovative Research

 	
  * Lamest Vendor Response

 	
  * Most Over-hyped Bug

 	
  * Most Epic Fail

 	
  * Most Epic 0wnage

 	
  * Lifetime Achievement Award


And last but not least:



 	
  * Best Song 


This year’s best song is a parody of Adele’s _Hello_—[Hello From The Other Side](https://www.youtube.com/watch?v=d_TmocWyEDY) is complete with a demonstration of the exploit and a lyrical summation of what they’re doing. 

Across the industry, security vulnerabilities are given a tracking number (Common Vulnerabilities and Exposures or CVE) and described in a semi-standard system. This helps everyone understand which category they fall into  so they can read and understand vulnerabilities that may be outside their area of expertise. This also helps us talk about vulnerabilities without resorting to sensational names like “Heartbleed”.

Since it is August and the 2017 awards have been announced, I got to wondering whether any of the Pwnie-winning vulnerabilities could have been prevented by feature flags. There are several that could possibly have been mitigated by the ability to turn a feature off, but I chose this one: 


**Pwnie for Epic 0wnage**
0wnage, measured in owws, can be delivered in mass quantities to a single organization or distributed across the wider Internet population. The Epic 0wnage award goes to the hackers responsible for delivering the most damaging, widely publicized, or hilarious 0wnage. This award can also be awarded to the researcher responsible for disclosing the vulnerability or exploit that resulted in delivering the most owws across the Internet.




**WannaCry**
Credit: North Korea(?)




Shutting down German train systems and infrastructure was Child’s play for WannaCry. Take a legacy bug that has patches available, a leaked ("NSA") 0day that exploits said bug, and let it loose by a country whose offensive cyber units are tasked with bringing in their own revenue to support themselves and yes, we all do wanna cry.




An Internet work that makes the worms of the late 1990s and early 2000s blush has it all: ransomware, nation state actors, un-patched MS Windows systems, and copy-cat follow on worms Are you not entertained?!?!?


WannaCry was especially interesting because [it got “sinkholed”](https://www.pcmag.com/news/353663/researcher-accidentally-thwarts-wannacry-ransomware) by a security researcher called MalwareTech. (I know, he’s under indictment. Security researchers are _interesting_ people.) He noticed that the ransomware was calling out to a domain that wasn’t actually registered, so he registered the domain himself. That gave lots of people time to patch their systems instead of getting infected.

As an industry, we tend to think of server uptime as a good thing. But is it? Not for any single server, because if it’s been up for a thousand days, it also hasn’t been rebooted for patches in over three years. You may remember early 2017 when [Amazon S3 went down](https://aws.amazon.com/message/41926/)? That was also due to a restart on a system that no one had rebooted in ages.

So how can feature flags help keep production servers current?



 	
  * It’s safer to make a change in production if you know you can revert it instantly using a feature flag kill switch.

 	
  * Small, iterative development means that you can ship changes more quickly with less risk—the more often you reboot a server, the less important that particular server’s uptime is.

 	
  * Many infrastructures today are built with the concept of ‘infrastructure as code’ through the use of automation tooling. These automation configurations can also benefit from the use of feature flags to roll-out system or component versions alongside your application updates.


Second we have: 


**Pwnie for Best Cryptographic Attack (new for 2016!)**
Awarded to the researchers who discovered the most impactful cryptographic attack against real-world systems, protocols, or algorithms. This isn't some academic conference where we care about theoretical minutiae in obscure algorithms, this category requires actual pwnage.




[The first collision for full SHA-1](http://shattered.io/)
Credit: Marc Stevens, Elie Bursztein, Pierre Karpman, Ange Albertini, Yarik Markov




The SHAttered attack team generated the first known collision for full SHA-1. The team produced two PDF documents that were different that produced the same SHA-1 hash. The techniques used to do this led to an a 100k speed increase over the brute force attack that relies on the birthday paradox, making this attack practical by a reasonably (Valasek-rich?) well funded adversary. A practical collision like this, moves folks still relying on a deprecated protocol to action.


SHA-1 was a cryptographic standard for years, and you can still select it as the encryption for a lot of software. This exploit makes it clear that we need to stop letting anyone use it—and for their own good.

How a feature flag might have made this better:



 	
  * Turn off the ability to select SHA-1 as an encryption option

 	
  * Force current SHA-1 users to choose a new encryption option


Some feature flags are intended to be short-term and will be removed from the code once the feature is fully incorporated. Others exist longer-term, as a way to segment off possible dangerous sections of code that may need to be removed in a hurry. Feature flags could be combined with detection, like I suggested for the SHA-1 problem, and used to drive updates and vulnerability analysis.

It’s easy for us to think of deployment as something a long way from security exploits that involve physical access to computers and networks, but security exploits are “moving left” at the same time as all the rest of our technology. Fewer of us manage physical servers, and fewer security vulnerabilities relate to inserting unknown USB sticks into our laptops. Instead, we’re moving to virtual machines and containers, and so are our vulnerabilities. Constructing code, cookbooks, and scripts that allow us to change the path of execution after deployment gives us more options for stay far, far away from the bright light of the Pwnie Awards.
