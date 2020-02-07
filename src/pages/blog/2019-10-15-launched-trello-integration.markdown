---
author: rmanalang
comments: false
date: 2019-10-15 13:00:57+00:00
layout: post
link: https://launchdarkly.com/blog/launched-trello-integration/
slug: launched-trello-integration
title: 'Launched: Trello Integration'
wordpress_id: 194382
categories:
- Product Updates
tags:
- feature flags
- trello
---

## Dark launch your features with Trello and LaunchDarkly


Teams around the world use [Trello](https://trello.com/) to manage software projects. Many of these teams use LaunchDarkly to launch features. I've been on a few of these teams.

Trello's hallmark as a productivity and collaboration tool has been its simplicity. I've always loved how Trello never got in the way of my team's workflow. With [Trello Power-Ups](https://trello.com/power-ups), my team had the ability to customize and enhance our workflow and processes to suit our needs.

Today, we're announcing our integration with Trello. We've built a [LaunchDarkly Power-Up](https://trello.com/power-ups/5d795c43ef5f7d1dc307da46) that brings LaunchDarkly's feature toggles directly into Trello. This Power-Up allows teams to bundle their feature flags on a Trello card.

![](https://blog.launchdarkly.com/wp-content/uploads/2019/10/ld-trello.gif)

You'll also be able to turn your flags on or off directly from the back of Trello cards. This makes deploying features so much simpler.


### How could this help me?


If your team uses Trello to manage your software projects, you're probably an Agile team using some variation of a Kanban or Scrum workflow. If so, you're likely writing stories and epics to describe your features. Many of these features map directly to feature flags inside LaunchDarkly. With this integration, you can attach your feature flags directly to your stories or epics. When it comes time to launch your feature, you can do it directly from the back of your Trello card. This also makes it easy to see the status of your feature – whether it's been launched or not.

This integration also respects your LaunchDarkly environment's rules (e.g., require comments or confirmation to change flag state).


### Sold! How do I get my hands on it?


You can [install the LaunchDarkly Power-Up from the Trello Power-Ups directory today](https://trello.com/power-ups/5d795c43ef5f7d1dc307da46)! From there, right-click on the LaunchDarkly link in the Trello sidebar, then click "Authorize Account" in order to authenticate with LaunchDarkly.

[![Trello-1](https://blog.launchdarkly.com/wp-content/uploads/2019/10/image2019-10-9_9-22-32-300x250.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/10/image2019-10-9_9-22-32.png)

Once you've authenticated, you'll see a "LaunchDarkly" button on the back of your cards:

[![Trello-2](https://blog.launchdarkly.com/wp-content/uploads/2019/10/image2019-10-9_9-24-2-300x115.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/10/image2019-10-9_9-24-2.png)

You can use that button to select flags from your projects and environments to attach to a card. However, you can also just copy and paste the URL of a LaunchDarkly flag directly to a Trello card. As a bonus, you can also drag-and-drop the URL to the card. Once it's attached, the flag will look like this on the back of the card:

[![Trello-3](https://blog.launchdarkly.com/wp-content/uploads/2019/10/image2019-10-9_9-27-48-1024x986.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/10/image2019-10-9_9-27-48.png)

Clicking on a toggle will bring up a confirmation dialog to activate your feature:

[![Trello-5](https://blog.launchdarkly.com/wp-content/uploads/2019/10/image2019-10-9_9-28-39-1024x428.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/10/image2019-10-9_9-28-39.png)

That's all it takes to monitor and manage flags from Trello. [Install the LaunchDarkly Power-Up](https://trello.com/power-ups/5d795c43ef5f7d1dc307da46) today!

If you're interested in more integrations, we want to hear from you. [Tell us directly](https://airtable.com/shrpIQHdxCcXbzSGK) on this form what you want to see. If you don't have a LaunchDarkly account, contact [sales@launchdarkly.com](mailto:sales@launchdarkly.com) or start a free trial to try it out now.
