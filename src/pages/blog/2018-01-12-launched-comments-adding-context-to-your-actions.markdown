---
author: tracil
comments: false
date: 2018-01-12 23:55:37+00:00
layout: post
link: https://launchdarkly.com/blog/launched-comments-adding-context-to-your-actions/
slug: launched-comments-adding-context-to-your-actions
title: 'Launched: Comments, Adding Context to Your Actions'
wordpress_id: 2176
categories:
- Product Updates
tags:
- DevOps
- feature flag driven development
- LaunchDarkly
---

A key part of problem identification is knowing what changed in the system. For developers this is often accomplished with comments in code this is to remind your '[Future Self](https://xkcd.com/1421/)' why you made the choices that you did. As we have built LaunchDarkly we have tried to follow our own best practices around naming flags with good descriptions, assigning clear owners to flags that map to specific areas of responsibility, and adding comments in our code to provide reminders on what a given flag is for.

However, as more teams using LaunchDarkly have implemented [feature flag driven development practices](https://blog.launchdarkly.com/feature-flag-driven-development/) the platform has become a crucial part of their change management process. For anyone that has experience with change management there is an acknowledgement that context matters. Standard audit logging is great to know who changed what, when; but lacks the _why_. In small systems or on small teams this often falls in the category of tribal knowledge, but in large systems and large organizations 30 seconds on formally documenting changes can save hours or days in the troubleshooting process.

Today, we are happy to rollout the ability to add comments on updates to flags. Now team members can have the option to add a brief comment on _why_ a change is being made.[![](https://blog.launchdarkly.com/wp-content/uploads/2018/01/image2018-1-10_15-54-26.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/01/image2018-1-10_15-54-26.png)

As we designed this feature we also thought it would be helpful to include these comments in your favorite established output path. So, when you do decide to add a little extra context folks will see it appear along with the who, what , and when sent to the audit log, through your established webhooks, slack channels, and Hipchat rooms.


### If it's for a developer, build it on top of an API


In keeping with our mantra around API-first development the new comments functionality is built on top of the REST API.  We added the ability to submit these optional comments with `PATCH` changes. With this launch, the [Update feature flag](https://apidocs.launchdarkly.com/v2.0/docs/update-feature-flag) resource supports comments, and support in other `PATCH` resources is forthcoming.






















Here's an example from our [API docs](https://apidocs.launchdarkly.com/docs/updates) for submitting a comment along with a JSON Patch document:

































**JSON**











<table cellpadding="0" cellspacing="0" border="0" >
<tbody >
<tr >

<td class="gutter" >


1




2




3




4

</td>

<td class="code" >





`{`




`  ``"comment"``: ``"This is a comment string"``,`




`  ``"patch"``: [ {``"op"``: ``"replace"``, ``"path"``: ``"/description"``, ``"value"``: ``"The new description"` `} ]`




`}`




</td>
</tr>
</tbody>
</table>






































### Oh, and one more thing




















While we're strong proponents of JSON Patch as a protocol for describing partial updates in our REST API, we've found that it can be pretty verbose for simple changes. We've added support for the [JSON Merge Patch](https://tools.ietf.org/html/rfc7386) protocol to address this. Here's an example merge patch document  that changes a feature flag's description:




















**JSON**











<table cellpadding="0" cellspacing="0" border="0" >
<tbody >
<tr >

<td class="gutter" >


1




2




3

</td>

<td class="code" >





`{`




`  ``"description"``: ``"New flag description"`




`}`




</td>
</tr>
</tbody>
</table>














Compare that to the equivalent JSON Patch document:















































**JSON**











<table cellpadding="0" cellspacing="0" border="0" >
<tbody >
<tr >

<td class="gutter" >


1




2




3




4




5




6

</td>

<td class="code" >





`{`




`  ``"name"``: ``"New recommendations engine"``,`




`  ``"key"``: ``"engine.enable"``,`




`  ``"description"``: ``"This is the description"``,`




`  ``...`




`}`




</td>
</tr>
</tbody>
</table>
























This addition also means that you can get fancy and combine these two new features and submit a comment along with a merge patch document:





**JSON**











<table cellpadding="0" cellspacing="0" border="0" >
<tbody >
<tr >

<td class="gutter" >


1




2




3




4

</td>

<td class="code" >





`{`




`  ``"comment"``: ``"This is a comment string"``,`




`  ``"merge"``: { ``"description"``: ``"New flag description"``}`




`}`




</td>
</tr>
</tbody>
</table>














Achievement unlocked. And now you'll know _why_.













