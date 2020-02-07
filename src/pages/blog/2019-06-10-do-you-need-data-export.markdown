---
author: dparzych
comments: false
date: 2019-06-10 17:26:05+00:00
layout: post
link: https://launchdarkly.com/blog/do-you-need-data-export/
slug: do-you-need-data-export
title: Do You Need Data Export?
wordpress_id: 193985
categories:
- General
- Product Updates
tags:
- data export
---

When a company releases a new feature, you may be thinking to yourself "Do I need to start using this?" When developing a product some features can be used by all customers while others target a narrower audience. Knowing whether a specific feature is right or wrong for your organization needs to be examined. This blog is an attempt to answer that question for our recently launched [Data Export ](https://launchdarkly.com/features/data-export/)feature.

Data Export provides a real-time feed of feature flag evaluations and was developed for organizations with specific characteristics. Ask yourself the following questions to see if Data Export is right for you.



 	
  * Do you have an existing data science team that can analyze and understand the data?

 	
  * Do you have internal data tools and processes in place to analyze data?

 	
  * Are you looking to merge LaunchDarkly data with other sources of information?


If you answered yes to the above questions, keep reading to learn more.


## What can Data Export help me with?


For every event processed Data Export gives you the time the flag was evaluated, the variation served, and the criteria used to determine which variation to serve. For any given user you are able to determine what variation they received and what effect that variation has along various dimensions.

_**Experimentation**_

LaunchDarkly collects detailed information about the feature flag evaluations, the users, and the reasons why a specific flag was served to a specific user. Information and analytics about your customers are stored in many places - Google Analytics, Marketo, Mixpanel. Merging this information with LaunchDarkly data can tell you whether customers that receive different variations exhibit different behaviors. 

You can see which variation results in:



 	
  * More time spent on the site

 	
  * A higher conversion rate

 	
  * A larger average contract size


Being able to measure or score the results of an experiment or A/B test that align with business goals can lead to more successful experiments and provider greater business value.

_**Debugging**_

Anybody that has ever been responsible for troubleshooting and debugging problems knows the value of information. If you are serving multiple variations of a feature, but only some of those are throwing an error, knowing what users received which variation can help you quickly reduce the amount of time necessary to resolve a problem. Data Export can detect data anomalies that are not visible in the in-app debugger.

_**Data enhancement**_

There are many ways you can target users. When you combine LaunchDarkly targeting rules with other data sources the possibilities are endless. Enriching your customer profiles can lead to advanced and granular user targeting. You can conduct predictive product pathing that automatically enables or disables features for cohorts based on data calculations.


## What do I need to get started?


Data Export is best used in companies with an existing team of data scientists/analysts/engineers. You need somebody or a team of people who can analyze and understand the data. And speaking of the data, the data needs somewhere to go. You need to have an existing data warehouse and visualization tools in place. Visualization tools like Tableau, PowerBI, Amplitude, or Looker can be used to analyze the LaunchDarkly data.



If you are interested in trying Data Export [contact LaunchDarkly sales](https://launchdarkly.com/contact-sales/).
