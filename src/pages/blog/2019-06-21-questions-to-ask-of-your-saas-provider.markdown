---
author: dparzych
comments: false
date: 2019-06-21 17:22:36+00:00
layout: post
link: https://launchdarkly.com/blog/questions-to-ask-of-your-saas-provider/
slug: questions-to-ask-of-your-saas-provider
title: Questions to Ask of your SaaS Provider
wordpress_id: 193990
categories:
- DevOps
tags:
- Personally Identifiable Information
- SOC 2
---

When looking to deploy a new SaaS solution there are lots of questions to be answered. I spent three days at Microsoft Build earlier this month, many of the people stopping by the booth had similar questions. These questions are some of the most common questions to ask of a SaaS provider. If you are considering any SaaS solution, below are some questions you should be asking of your vendor.


### **What are your security practices?**


Security should be at the front of your mind when considering a SaaS solution.

_**Storage of Personally Identifiable Information (PII)**_

It seems no company is immune to a data breach, when using a SaaS solution you need to ensure your information and your customer's personal information is safe. PII is information used to trace an individual's identity such as name, social security number or date of birth. The first question to ask is whether any PII data is being captured and stored. If the answer is yes dig in deeper to understand how they transmit and store that information. PII should be encrypted when being transmitted and stored.

LaunchDarkly does not require any PII to be passed to the service. [Private User Attributes ](https://launchdarkly.com/blog/launched-private-user-attributes)can be used to target customers based on PII without transmitting that information back to LaunchDarkly. LaunchDarkly receives information that an attribute such as a date of birth was provided during the flag evaluation, but the actual value is not transmitted.

**_Penetration Testing_**

Penetration testing is the practice of testing applications, systems, and networks to find potential security vulnerabilities. The goals of penetration testing are to identify points that an attacker can exploit and measure compliance of the organization's security policy. Penetration tests should be conducted by a third-party at least once a year.

LaunchDarkly conducts penetration testing every six months with an independent third-party.

_**Security Audits and Certifications**_

An indication of solid security practices are companies that have gone through independent audits and certifications. Depending on your industry and geographic location, this will influence what types of certifications you are interested in. Two of the most common certifications to inquire about are SOC-2 and mISO 27001.

SOC-2 is an auditing procedure within North America that defines criteria for managing customer data along five principles–security, availability, processing integrity, confidentiality, and privacy. ISO 27001 is an international certification with requirements on how to run an information security management system (ISMS). The certification focuses on preserving confidentiality, integrity, and availability of information throughout the risk management process.

For companies or individuals concerned about security, ensuring SOC-2 and ISO 27001 (depending on their location) audits and certification is at the top of the list of requirements when looking at a SaaS provider. A SOC-2 certification is conducted by outside auditors to determine to what extent a vendor complies with the five principles.

Launch Darkly has received SOC 2 Type II certification for Trust Services principles and is ISO 27001 certified. More information about our security practices and certifications can be found [here](https://launchdarkly.com/security/).


### **What is your SLA?**


Service Level Agreements (SLAs) are another critical component of a SaaS solution. An SLA is a legal agreement between a SaaS vendor and its customers. AN SLA typically includes:



 	
  * Measurable objectives regarding performance, availability, and/or reliability over a specific period of time.

 	
  * Tracking and reporting guidelines.

 	
  * Description of what outages the vendor is not liable for (typically acts of nature).

 	
  * How a customer will be compensated if the target is not met (refund, credit, etc).


LaunchDarkly offers an SLA to customers on an enterprise plan. The most up-to-date information on our SLA can be found [here](https://launchdarkly.com/policies/terms-of-service/enterprise-sla/).


### **What happens if the service isn’t available?**


Having an SLA doesn't mean a service will be available 100% of the time. Knowing the business and customer impact if a mission-critical service is unavailable is important. If a service isn't available, does that mean your entire application stops working? What fallback mechanisms are in place to ensure your customers are not impacted by a service interruption?

LaunchDarkly has been built with redundancy in mind to protect our customers:



 	
  * We are hosted in multiple availability zones in AWS.

 	
  * We utilize a CDN.

 	
  * The last known config is cached locally.

 	
  * Default or fallback values are required when configuring your feature flags.

 	
  * And for those needing an extra level of redundancy, we can be deployed with a [relay-proxy](https://docs.launchdarkly.com/docs/the-relay-proxy#section-relay-proxy-mode) and optional Redis cache.


While we may not be able to avoid disasters, [we have designed our systems for failure](https://launchdarkly.com/blog/designing-for-failure-to-avoid-disaster/).


### **Does this work for on-premises or internal applications?**


Not all applications are available on the public internet. If you have an internal application or an application hosted on-premises knowing whether the service will work can be a show-stopper. Talk to the vendor about your infrastructure, and ask questions about theirs:



 	
  * What resources does the service need to connect with?

 	
  * Where are those resources in your infrastructure?

 	
  * Can those resources connect to the internet?

 	
  * What options are available to manage or reduce outbound connections to the service?


Have a conversation about the benefits you get from your on-premises infrastructure and what options are available to you. The [relay-proxy](https://github.com/launchdarkly/ld-relay) mentioned above is one way LaunchDarkly can be deployed to work with on-premises applications.


### **Why wouldn’t I just build this myself?**


The [not invented here bias ](https://en.wikipedia.org/wiki/Not_invented_here)frequently appears when exploring a SaaS solution. "Why should we buy something we can just have a few developers quickly write some code to do the same thing?" What may seem like a quick and easy project can take on a life of its own.

I recently heard Jeffrey Snover speak about classifying things as core vs mission-critical. Core is something that makes the company money and differentiates you from competitors. Mission-critical is something that is necessary but it won't give you a competitive advantage. Build what differentiates you, buy what doesn't.

We've put together a page with more details to help you explore the [build vs ](https://launchdarkly.com/build-vs-buy/)buy dilemma.
