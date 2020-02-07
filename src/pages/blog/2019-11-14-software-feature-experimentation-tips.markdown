---
author: dparzych
comments: false
date: 2019-11-14 23:45:50+00:00
layout: post
link: https://launchdarkly.com/blog/software-feature-experimentation-tips/
slug: software-feature-experimentation-tips
title: Software Feature Experimentation Tips
wordpress_id: 194544
categories:
- Feature Management
tags:
- AB tests
- experimentation
---

_This was originally published in App Developer Magazine on October 7, 2019._

Every new feature starts as an idea. Not all ideas are good ideas. Therefore, not every new feature is a good idea. So how do you know which feature is a good idea and which one isn’t? You experiment.

The idea of experimenting with users or in production may sound scary and complicated, but it doesn’t have to be. The questions below shed some light on common questions surrounding experimentation and can help you determine if experimentation is right for you.


### What is experimentation?


According to the dictionary, experimentation is the action or process of trying out new ideas, methods, or activities.

Experimentation is different from testing. With testing, you verify and confirm behavior. With experimentation, you discover, learn, and change behavior. Experiments lead to new knowledge. Testing shows whether something works or is broken.

Experiments you can run on your application, feature, or infrastructure include:


#### A/B testing


A/B tests, also called A/B/N testing or split tests, are one of the most common types of experiments. The experiment compares two or more versions of a page to determine which one performs better in terms of engagement, conversions, or some other metric. The better performing version of the page is deployed for all users. An A/B test refers to a test with two versions while an A/B/N test refers to tests with multiple versions.


#### Multi-armed bandits


A multi-armed bandit is a variation of an A/B test. Instead of waiting for a finite period of time for a test to complete, a multi-armed bandit test uses algorithms to increase traffic allocations to better-performing variations.


#### Chaos experiments


The third type of experimentation focuses more on finding out what doesn’t work rather than what does. Chaos engineering is the process of intentionally injecting failure into a system to determine how it responds to unexpected disruptions. The disruption could be too many database connections, DNS errors, or a failure with a third-party provider. Experimenting with how your systems behave when things go wrong helps you find and fix problems, or create runbooks on what to do in those situations.


### Why experiment?


Experiments should regularly be run on applications and infrastructure. Experiments help you validate changes proposed to a product will have the expected impact on the user's experience. You can learn which features will impact users the most. You can iterate and make changes to a feature if it doesn’t have the impact you expected. Or you can choose not to move forward with a feature.

Experimentation lets you spend less time on things that won’t make as big of a difference. As humans, we are notoriously bad at predicting what will or will not have the greatest impact.

This is because of our inherent biases. Experiments help us get past our biases.

An experiment may reveal a feature we thought customers would love is not well understood or is being misconfigured. This doesn’t mean give up on the feature. It means to examine what needs to be tweaked or modified and iterate on the feature. Then run another experiment to see if the changes made a difference. Of course, sometimes the results of an experiment may indicate it is best to give up and focus on something else.

Experiments help you iterate and improve. When running a chaos experiment, you can see what processes need adjusting in a controlled environment rather than when everyone is feeling pressure to rapidly resolve a problem.


### When should you experiment?


How often you experiment will vary. Some companies run monthly chaos experiments while others prefer quarterly. Pick a cadence or schedule that works for you.

Experiments require analysis. You don’t want to get bogged down in analyzing data for every feature. Consider using experiments for:



 	
  * Major features

 	
  * Total site redesigns

 	
  * Significant changes in functionality

 	
  * Performance tweaks


For example, you want to improve page load times but aren’t sure whether optimizing images or minifying CSS and JS files will improve times more. An A/B/N experiment can help you determine which project to tackle first. Create three versions of a page. One is the control, one has images optimized, and one has CSS and JS minified. You can then collect performance metrics on these three pages to see which loads the fastest. If the image optimization page loads faster you prioritize that project over the minification project.


### Who should be involved in the experiments?


The type of experiment dictates whose involvement is necessary.



 	
  * Chaos experiments require involvement from engineering and operations.

 	
  * An experiment regarding a price change may require involvement from sales leadership or the executive team.

 	
  * Analyzing whether a change in the color of a call to action button would require marketing involvement.


Think about the goals and objectives of the experiment and who has a stake. Involve them in the experiment. Experiments generate data that needs analysis. Make sure you have people and tools available to extract insights from the data.


### Where should I experiment?


Run experiments in production. No environment will be identical to production. Time and money will be wasted trying to create an exact clone of your production environment. Nothing will be exactly like production, and your users are in production.

You can reduce worries that an experiment will go awry and cause a backlash by setting up appropriate controls and kill-switches.


### How long should an experiment run?


The amount of time an experiment runs is less important than having the right sample size. Not having the right sample size can result in misleading and incorrect data. The control and test groups both need to have a similar number of evaluations for statistically significant results.

Use this [calculator](https://www.evanmiller.org/ab-testing/sample-size.html) to help determine what your sample size should be.

Diving into the unknown can be scary. But the results of a well-run experiment are worth it. Start small and see what you can learn.
