---
author: dparzych
comments: false
date: 2019-10-24 16:43:05+00:00
layout: post
link: https://launchdarkly.com/blog/nine-experimentation-best-practices/
slug: nine-experimentation-best-practices
title: Nine Experimentation Best Practices
wordpress_id: 194440
categories:
- Feature Management
tags:
- AB tests
- best practices
- experimentation
- feature flag
---

Running experiments helps you bridge gaps between technical and business teams as you learn about user engagement patterns and application behavior. Experiments can validate that your development teams’ efforts align with your business objectives. You can configure an experiment from any feature flag (front-end, back-end, or operational), but what makes a good experiment?

Experiments use metrics to validate or disprove gut feelings about whether a new feature is meeting customers’ expectations. With an experiment, you can create and test a hypothesis regarding any aspect of your feature development process.



 	
  * Will adding white space to the page result in people spending more time on the site?

 	
  * Do alternate images lead to increased sales?

 	
  * Will adding sorting to the page significantly increase load times?


Experiments provide concrete reporting and measurements to ensure that you are launching the best version of a feature that positively impacts company metrics.


## General experimentation best practices


Let’s first talk about best practices around creating an experiment. Even with a solid foundation of feature flagging in your organization, missteps in these areas can yield flawed results. Consider these best practices for experimentation.


### 1. Create a culture of experimentation


Experiments can help you prove or disprove a hypothesis, but only if you are willing to trust the outcome and not try to game the experiment. Creating a culture of experimentation means:



 	
  * People feel safe asking questions and questioning the answer. Sometimes the results of an experiment may not be what you were expecting. It’s ok to question the results and explore anomalies.

 	
  * Ideas are solicited from all team members—business stakeholders, data analysts, product managers, and developers.

 	
  * A data-driven approach is used to put metrics first, not as something that is only useful in dashboards after a feature ships.


Part of creating a culture of experimentation is providing the tools and training to allow teams to test and validate their features.

Tools needed for experimentation:

 	
  * Tools to help you collect relevant metrics can include monitoring, observability, and business analytics tools.

 	
  * Tools to help you segment users.

 	
  * Tools to clean and analyze the results.




### 2. Define what success looks like as a team


Experiments help you determine when a feature is good enough to release. How do you define what “good enough” is, and who is involved in creating the definition? Experiments can involve a cross-functional team of people or only a handful, depending on the focus of the experiment. If an experiment is on whether to add a “free trial” button to the home page, you may need to involve people from demand generation, design, and business development.
A good experiment requires well-defined and agreed-upon goals and metrics by all stakeholders. Ask yourself, “What does success look like?” Success means improving a specific metric by a specific amount.  “Waiting to see what happens” is not a goal befitting a true experiment. Goals need to be concrete and avoid ambiguous words. Tie goals and metrics to business objectives like increasing revenue, time spent on a page, or growing the subscription base.

Examples of poor goals include vague and ambiguous statements:



 	
  * Users will be happier with the home page. 

 	
  * The response time of search results will improve. 


Examples of better goals include concrete statistics: 



 	
  * Paid conversions from a trial will improve by 7%.

 	
  * The response time of search results will decrease by 450ms. 


Looking at a single metric is good; looking at related metrics is even better. Identify complementary metrics and examine how they behave. If you get more new subscribers—that’s great, but you also want to look at the total number of subscribers. Say you get additional subscribers, but it inadvertently causes existing subscribers to cancel. Your total number of subscribers may be down as a result, does that make the experiment a success? I would say no. 


### 3. Statistical significance


The number of samples will depend on your weekly or monthly active users and your application. No matter the size of the samples, it is important to maintain a relatively equal sample size. Significantly more samples in one cohort can skew the results. 

Think about how and when users access your application when starting an experiment. If users primarily use your application on the weekends, experiments should include those days. If users visit a site multiple times over the course of a couple of weeks before converting and before the experiment starts, early results may be skewed, showing a positive effect when it was neutral or negative. 


### 4. Proper segmentation


There are two aspects to segmentation. First, how will you segment your users, and second, how will you segment the data? A successful experiment needs two or more cohorts. How you segment your users will vary based on your business and users. Some ways to segment users: 



 	
  * Logged in vs. anonymous 

 	
  * By company 

 	
  * By geography 

 	
  * Randomly 


However you segment users, make sure the sample sizes are balanced. Having skewed cohorts will result in skewed results. 

When analyzing the data after an experiment, you may want to do additional segmentation to see if the results vary based on other parameters. 

In[ AirBnB’s experimentation blog](https://medium.com/airbnb-engineering/experiments-at-airbnb-e2db3abf39e7), they described an experiment where they received neutral results when they were expecting to see an uplift. Analyzing the results per browser, they uncovered a bug in IE that skewed the results. When the bug was fixed, they saw the improvement they expected. If there was not a culture of experimentation where it was ok to question the result and look for answers, this feature might not have rolled out. 

Caution: don’t go digging to find data to support your hypothesis. The segmentation should be done to understand anomalies better, not make a case to call the experiment a success. 


### 5. Recognize your biases


And this brings us to the subject of biases. Everybody is biased. This isn’t a bad thing; it is a matter of how our brains work. Understanding your biases and the biases of others around you will help when running experiments. Our biases influence how we process information, make decisions, and form judgments.

Some biases that may creep in: 



 	
  * Anchoring bias - our tendency to rely on the first piece of information we receive. 

 	
  * Confirmation bias - searching for information that confirms our beliefs, preconceptions, or hypotheses. 

 	
  * Default effect - the tendency to favor the default option when presented with choices. 

 	
  * And my personal favorite, the bias blind spot - our belief that we are less biased than others. 


It is common in an experiment to scrub the data to remove outliers. This is acceptable, but make sure you aren’t eliminating outliers due to bias. Don’t invalidate the results of your experiment by removing data points that don’t fit the story. 


### 6. Conduct a retro


Experiments are about learning. So after every experiment, hold a retrospective. Ask: 



 	
  * Was the experiment a success? Did we get the results we expected? Why or why not? 

 	
  * What questions were raised by the experiment? What questions were answered?

 	
  * What did we learn? 


And most importantly, should we launch the feature? You can still decide to launch a feature if the results of an experiment were neutral. 


## Experimentation feature flags best practices


Now that we’ve covered the basics of experiment best practices, let’s dive into best practices around using feature flags in your experiment. Well done feature flagging is a foundation for a well-run experiment. 

If you’ve embraced feature management as part of your teams’ DNA, any group that wants to run an experiment can quickly do so without involving engineering. Follow these best practices to get the most from your existing feature flags. 


### 7. Consider experiments during the planning phase


The decision of whether to wrap a feature in a flag begins during the planning phase. This is also the right time to think about experiments. When creating a feature, evaluate the metrics that will indicate whether the feature is a success—clicks, page load time, registrations, sales, etc. 

Talk with the various stakeholders to determine whether an experiment may be necessary and provide them with the essential information on the flag, such as the name of the flag, to configure an experiment. 


### 8. Empower others


When giving others the ability to run experiments, make sure you have the proper controls in place to avoid flags accidentally being changed or deleted. Empower other teams to create targeting rules, define segments, and configure roll-out percentages while preventing them from toggling or deleting flags. 


### 9. Avoid technical debt


Experimentation flags should be short-lived. This means removing a flag after an experiment completes and is either rolled out to 100% of users or not released. Put processes and reminders in place to remove the flag. We highlighted some creative ways to do this in our[ short-term and permanent best practices](https://launchdarkly.com/blog/best-practices-short-term-permanent-flags/) blog. 

 To get started with your own experiments, check out the[ LaunchDarkly documentation](https://docs.launchdarkly.com/docs/experimentation).

Are you looking for other best practices? Check out the other blog posts in the series.

[Long-term and short-term flags best practices ](https://launchdarkly.com/blog/best-practices-short-term-permanent-flags/)

[Operational flags best practices ](https://launchdarkly.com/blog/operational-flags-best-practices/)

[Release management flags best practices ](https://launchdarkly.com/blog/release-management-flags-best-practices/)




