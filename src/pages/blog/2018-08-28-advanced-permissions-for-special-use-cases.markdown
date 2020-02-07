---
author: tkeohane
comments: false
date: 2018-08-28 16:30:11+00:00
layout: post
link: https://launchdarkly.com/blog/advanced-permissions-for-special-use-cases/
slug: advanced-permissions-for-special-use-cases
title: Advanced Permissions for Special Use Cases
wordpress_id: 193309
categories:
- Feature Management
- Team &amp; News
tags:
- customer experience
- customize experience
- feature flag
- feature management
---

My biggest surprise in joining LaunchDarkly has been learning how wide a range of use cases that our feature management platform supports. In researching the company late last fall, I thought of the product as a tool for software development, a way to decouple deployment of code to a production environment from the exposing of that code to users. Valuable, certainly, but a somewhat narrow business opportunity. As is often the case, a little outside perspective helped me see something I had originally missed.

A friend of mine owns a small software company which produces a billing application for the insurance industry. He services a large number of small clients, who have mainly standardized needs. A few years ago I got to know him through a large customization project, in which the Fortune 500 company I worked for paid him to add a long list of features and capabilities to his core offering. We faced a build vs. buy decision and ending up in the middle: identifying a good core chassis, but paying to enhance it to fit our needs (high volume, data file input vs manual input, better reporting, etc.).

It was obvious from the outset that his company undercharges for the product—a mission critical system for the business at only $57 per month was a huge bargain for our multi-million-dollar revenue company (setting aside what we paid him to move our feature requests to the front of the queue). We spent the better part of a year scoping our needs, negotiating over what to include in his standard product, testing and releasing three tranches of upgrades. It was a successful outcome for both parties. We bought enhancements to the system that we needed, and he had development paid for by a customer that the rest of his customer base could enjoy. At the end of the process though, he didn't materially change his pricing. A lot of what we asked for he felt he couldn't sell to other customers, so those who did value our upgrades basically got them for no additional cost. We ended up buying quite a few seats, as it was essential for us, but even including the cost of customization it didn't add up to a big investment.

I recently caught up with my friend, and I learned though his business has been inching forward, its not at the rate he would like. He shared one challenge, that a growing number of his customers were asking for new features that they alone valued. As he works with mainly small companies, his customers are not in a position to pay for custom development like the project I led some years back. Putting on my business owner hat, I asked how he planned to satisfy these customers. I knew that a) separate versions of the product are hard to maintain, and not practical from an infrastructure perspective; b) other customers will balk at paying for features they don’t value; c) provisioning complexity would get much harder with each new feature that he released; and d) if he couldn't fulfill these needs, perhaps some customers would go elsewhere.

The solution to me was clear—he needed a way to provide a differentiated experience for these customers, coupled with an à-la-carte pricing structure. While there are several ways to implement that idea, feature flags (ideally in a management environment like LaunchDarkly's) provide a sensible solution. Such a platform would enable his company to have a consistent code base, and yet customize the experience for each client while easing the burden of managing the multitude of possible feature combinations.

Software users are demanding ever more personalized products, but that personalization is difficult to implement and price appropriately. Feature flags, with their ability to easily manage disparate user experiences, are a welcome solution to right-size software for each user, enabling vendors to capture appropriate value and users to pay for only what they need. These kinds of “longer-term” flags, purposefully built into the system and meant to remain as a tactic to facilitate release of features or functionality to a limited environment, are a use case I hadn’t considered. The discovery of novel applications of the feature flagging approach will undoubtedly continue, and the company is excited to see what other problems this fundamental technique can solve.
