---
author: dparzych
comments: false
date: 2019-12-03 22:07:07+00:00
layout: post
link: https://launchdarkly.com/blog/black-friday-feature-management/
slug: black-friday-feature-management
title: How to Mitigate Outages on Black Friday Next Year
wordpress_id: 194631
categories:
- Continuous Delivery
- DevOps
- Feature Management
tags:
- black friday
- cyber monday
- experimentation
- feature flag
- feature management
- infrastructure
---

Black Friday and Cyber Monday bring massive savings for the savvy shopper, but they also bring sleepless nights for engineering and operations teams as they battle incidents. Code freezes get implemented weeks, if not months, ahead of time. And bulking up your infrastructure isn’t enough to prevent outages. Even cloud computing companies like [Amazon have experienced incidents on Prime Day](https://fortune.com/2018/07/20/amazon-crash-prime-day/) due to overloaded infrastructure. 

Outages vary in severity. For retailers, an outage between Thanksgiving and Cyber Monday will have a more significant impact than an outage on other days of the year. According to [Practical eCommerce](https://www.practicalecommerce.com/sales-report-2018-thanksgiving-black-friday-cyber-monday), consumers spent $7.9 billion online shopping between Thanksgiving Day and Cyber Monday in 2018. But that doesn’t mean it was smooth sailing for everyone. 




 	
  * A [third-party component from Coremetrics](https://blog.catchpoint.com/2018/11/26/black-friday-performance-third-party-outage-strikes-again/) resulted in performance problems for many retailers. 

 	
  * [Walmart, Lowes, Ulta Beauty, and J. Crew ](https://www.businessinsider.com/walmart-lowes-black-friday-nightmare-tech-issues-2018-11)were just a few of the major retailers that experienced issues related to high traffic or other factors. 


According to [Retail Touchpoints](https://www.retailtouchpoints.com/features/news-briefs/site-outages-plague-walmart-j-crew-lowe-s-best-buy-office-depot-during-black-friday-weekend), high traffic is one reason for outages. But it’s not just high traffic that causes problems. Outages can result from “overburdened APIs, slow third-party technology integrations, sites heavy with graphics, or a failure to look at regional performance levels.”  

While you can’t prevent an outage, you can prepare for issues that may pop up by utilizing feature management. We've come up with a fictional yet highly plausible story below to illustrate the point. See how feature flags helped Barley Bones, a purveyor of graphic t-shirts, overcome some of the issues highlighted above on one of the biggest shopping weekends of the year. 


### The ballad of Barley Bones on Black Friday


Last year’s holiday shopping season was not a good one for Barley Bones. Leading up to Thanksgiving weekend, the engineering team had a six-week code freeze, during which they focused on bug squashing, testing, and fire drills. Nonetheless, when Black Friday arrived, they were plagued with one incident after another. 

Some of the main issues they encountered were: 



 	
  * A non-essential third-party component drastically slowed down the response time of their product pages, resulting in lost sales. 

 	
  * Their API servers were overburdened, resulting in issues with inventory.

 	
  * A limited-time promotion went out, sending so much traffic to the site that customers received errors.


They knew something needed to change for a better shopping season next year.  

After everybody had a chance to rest and recover, the Barley Bones team researched what they could do to improve. One of the developers remembered picking up a book on [Effective Feature Management](https://launchdarkly.com/effective-feature-management-ebook/) at a conference. Reading through it, they decided this might be the answer to the challenges they faced.  

They set up processes to make feature management a central part of their CI/CD pipeline. Starting small, they introduced feature flags for [release management](https://launchdarkly.com/blog/release-management-flags-best-practices/), and slowly expanded to include [operational flags](https://launchdarkly.com/blog/operational-flags-best-practices/) and [experimentation.](https://launchdarkly.com/blog/nine-experimentation-best-practices/)  

As Black Friday approached, the team was confident their feature management strategy would make for a much smoother holiday shopping season. They had started flagging six months prior. All teams – engineering, operations, marketing, support, product management, design, sales – were included in the process. 

Let’s take a look at how their use of feature flags made a difference during this year’s Black Friday weekend. 


### Third-party SNAFUs


Third-party tags help Barley Bones extend the functionality of their website. They include snippets from over 20 different vendors for analytics, payment validation and processing, social media integrations, and more. Most third-party tags are embedded in the form of <script> tags, which load JavaScript code. 

Historically, new tags were added with minimal testing, given that there are many ways in which loading and executing this code can slow performance and damage the user experience—resulting in critical problems during peak shopping days. 

During the year, a new process was put in place for new tags. Each tag was wrapped around a feature flag. A ring deployment was used to roll the tag out slowly. This methodology enabled the performance team to identify any adverse impact such as page load times or a decrease in conversions related to the tag. If a problem popped up, the tag could quickly be turned off with a kill switch, a short-term flag to turn off a feature if something goes wrong during a release. 

Additionally, the operations team worked with business stakeholders to identify which tags were essential. For Black Friday, operations knew if a problem occurred with a non-essential flag they could quickly disable it via a circuit breaker, a permanent flag to disable a feature based on an event.  

The Barley Bones site uses the Magento e-commerce application, which renders PHP templates. The application framework and template system: 



 	
  1. Gathers variables that the template will reference. 

 	
  2. Renders a specific template using the given variables.

 	
  3. Renders the template into HTML.

 	
  4. Serves the HTML to the browser.


They used these templates to keep all third-party tags in a single location. In this template, a conditional which surrounds each tag and checks a feature flag:



At 7:35 PM on Thanksgiving night, alerts went off indicating a failure with their secondary analytics provider. This third-party component had been classified as non-essential, as other solutions collected similar metrics. With the primary analytics provider working fine, the engineer who received the alert toggled the circuit breaker for the analytics, removing it from the page and thus minimizing the impact to customers. 


### Overburdened APIs  


Barley Bones uses APIs to manage their inventory. The website, store personnel, and B2B platforms use these APIs to check available stock. During the holiday shopping season, they wanted to make sure that this API wasn’t overburdened resulting in incorrect inventory reports.  

When looking for options to shed API load by deprioritizing requests, they asked themselves three questions: 



 	
  1. How can these deprioritized requests be identified?

 	
  2. What functional change should be made to how those requests are handled?

 	
  3. Where should that change be implemented?


Barley Bones only sells within the United States of America. They decided to prioritize requests from US-based IP addresses and deprioritize requests from outside the US. What to do with those requests was a more complicated question. They could refuse requests by returning a 503 -Temporarily Unavailable response, which works well when the traffic is of a low enough value. Alternatively, they could implement a priority queue or response caching. 

Regarding implementation, they wanted to implement the throttling in the part of the infrastructure that provided the most control without adding additional load to their problems. In this case, the load is happening at the inventory database; the API server is firing queries at the database and just waiting for them to come back. 

In the end, they chose a mixed strategy. They implemented a limiter in the form of a priority queue which would always prioritize US-originating requests over others, and keep the number of requests in process to an upper bound which was configurable with a feature flag. At times of excess load on the inventory database, they would lower that upper bound. They also set a maximum lifetime for requests to be held in the queue.

Barley Bones’ API server is a Node.js application, so they used the [bottleneck](https://www.npmjs.com/package/bottleneck) library to implement their throttling strategy, with feature flags configuring the upper bound for concurrent requests at runtime. This gave them the ability to throttle requests to the API on the fly if it was becoming overwhelmed with requests. 

They created a limiter for use throughout the application—limiting the number of concurrent requests to an upper bound, which they could reduce by an order of magnitude with a feature flag.



The application used a custom function named queryInventory() to send queries to the inventory database. The team created a new version of this function that wrapped the original function with the limiter and geolocated each request to set its priority. This way, all API endpoints that query the inventory database automatically use the priority queue.



To make the limiter dynamically reconfigurable without restarting, the team used the event subscription feature of the LaunchDarkly Node.js SDK:



At 9:27 AM on Black Friday, the team received an alert that orders for out-of-stock items were being placed. Investigation showed the inventory API was overburdening the database with a large number of requests from international locations. The team toggled the API throttling flag to limit the maximum number of concurrent requests. The change reduced the load, and the inventory API once again reported correct inventory numbers.


### Collect diagnostic information  


The team knew that even with these feature flags in place, they needed to expect the unexpected. They deployed a flag to modify the logging level automatically when an incident occurs. Verbose logs are great when debugging but not so good during high-traffic times. When an alert is triggered, an API request is sent to automatically change the logging level to debug mode, collecting relevant information to help the team troubleshoot.  

For the configuration, the team first created a multivariate flag. Instead of just providing true/false values, it was configured to provide the values used for the primary log levels: FATAL, ERROR, WARN, INFO, DEBUG. The app reads this flag at startup and sets its log level accordingly.

Usually, the flag is set to one of the quieter logging levels (ERROR or WARN). Barley Bones has an Application Performance Monitoring (APM) solution that alerts them when performance or availability passes set thresholds. When the threshold is crossed, the alert initiates automated workflows in other systems.  

In this case, the alert triggers an external webhook, calling a version of [this JavaScript function](https://codesandbox.io/s/pagerduty-webhook-processor-6p2nk) hosted on AWS Lambda. This Lambda function calls into LaunchDarkly’s REST API and flips the flag.

When the Barley Bones team received a performance alert on Black Friday afternoon, they immediately looked at the app logs. The alert had already switched the app’s logging into DEBUG mode, which meant that by the time the engineers went to look, there was already enough information for them to make a diagnosis and quickly resolve the problem.


### Traffic spikes


At 10 AM on Cyber Monday, a promotional email was sent out for an extra 10% off and free shipping on all orders placed within the hour. To prepare for the significant increase in traffic, the team identified non-essential items such as comments, social media widgets, and 360-degree videos of the items on the home page and product pages. 

When the email went out at 10 AM, systems were monitored closely. When signs of heavy traffic appeared, the features were toggled off. Using feature flags to disable parts of the page is very common – in fact, the Barley Bones team had already done that in the “Third-Party SNAFUs” section above. 

But in this case, disabling elements of the page template from being rendered was not enough to reduce load. For example, the comments feature required multiple database queries to gather the data _before_ sending that data to the template. 

This time, the app in question was written in Java. The app’s getProductComments() method contained the database calls. Multiple views in the application use it, instead of wrapping each instance in a flag check, the safer solution was to add a flag check at the start of the method. That way, the team kept the flag logic in one place, and didn’t have to worry about missing any of the call sites:




### Looking ahead


While cyber week wasn’t without incident, feature flags helped the team successfully manage those incidents. Barley Bones had its most successful Cyber Week ever in terms of sales and employee morale. The operations team was able to enjoy Thanksgiving dinner without worrying about what might go wrong. 

Looking ahead, Barley Bones is going to expand their use of feature flags to: 



 	
  * Reduce the length of their code freezes. With feature flags in place for release management, Barley Bones can deploy code a week or two before Black Friday without releasing it to all users. 

 	
  * Run experiments throughout the year to collect metrics on which features result in higher sales. 




### Credit and thanks


Thank you to the following people who were involved in the creation of this blog post. 



 	
  * Yoz Grahame, my co-author and provider of the code samples.

 	
  * Yus Ngadiman for the logging example and code snippets.

 	
  * Arlington Albertson for validating the pain points retailers face around Black Friday.


