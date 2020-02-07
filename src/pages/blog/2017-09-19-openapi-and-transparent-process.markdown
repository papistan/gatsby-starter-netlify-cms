---
author: heidiw
comments: false
date: 2017-09-19 18:10:59+00:00
layout: post
link: https://launchdarkly.com/blog/openapi-and-transparent-process/
slug: openapi-and-transparent-process
title: OpenAPI and Transparent Process
wordpress_id: 2032
categories:
- Product Updates
tags:
- api
- feature flags
- OpenAPI
- transparent process
---

At LaunchDarkly, we’ve put a bunch of time into making our console fast and usable, and we’re pretty proud of it.




However, we’re aware there are lots of reasons people would want to use an API to create and manage feature flags. Since we are using our API to drive the dashboard, it’s easy for us to keep everything in sync if we make changes to the API. And we wanted to make it easy for our customers to do the same.




We started out with [ReadMe](http://readme.io/), which is an excellent industry standard. That let us get our documents published and dynamic. For further refinements, we went to Swagger/OpenAPI. We liked it because:






 	
  * It’s a well-known and widely-used format

 	
  * It allows us to generate usable code snippets and examples in many languages automatically

 	
  * It’s easy to add context and documentation to as we go.

 	
  * We can host it on readme.io or other places, depending on our traffic needs.




We created our REST specification using OpenAPI, and you can find our documents here: [LaunchDarkly OpenAPI](https://github.com/launchdarkly/ld-openapi).




We’re still working on adding examples, descriptions, and context, but we think that the documentation is stronger and more usable already.




As always, if you have any comments, you can contact us here, or make comments [directly in the repository](https://github.com/launchdarkly/ld-openapi).



