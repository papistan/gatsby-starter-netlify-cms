---
author: rgulati
comments: false
date: 2018-06-07 21:07:45+00:00
layout: post
link: https://launchdarkly.com/blog/launched-summary-events-new-debugger/
slug: launched-summary-events-new-debugger
title: 'Launched: Summary Events, New Debugger'
wordpress_id: 193126
categories:
- Product Updates
tags:
- analytics
- debug
- debugger
- feature flag
---

Every time a feature flag is evaluated by your software it creates an event to let our service know that the flag was used. However, recording event data for every user on every interaction creates a ton of noisy data that provides little value. The data volume gets even worse in long-term high-volume uses like percentage rollouts or kill switches.

Today, we are announcing two new features that dramatically reduce the amount of data we generate in these situations, giving you faster and more cost-efficient feature flags. Introducing Summary Events and the new Debugger.


### **Summary Events**


Rather than sending unique information for each and every flag evaluation, a summary event contains a compact summary of many flag evaluation results. This summary cuts the amount of data generated and bandwidth used by 10x.

There are cases where you need full, user-level granularity in your data—for example A/B testing or data export using the Analytics Data Stream (ADS). We’ll automatically send detailed information for any flag used by an A/B testing goal. You can enable detailed event information on a per-flag and per-environment basis for the ADS, recording granular data where you need it and avoiding the noise when you don’t.




















[![](https://blog.launchdarkly.com/wp-content/uploads/2018/06/ADS.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/06/ADS.png)






















### Debugger


The LaunchDarkly Dev Console has been redesigned as the new Debugger. We listened to your feedback and used it to build a more capable, more usable debugger. The debugger can handle higher volumes of traffic, and now it’s much easier to see what’s happening on a busy product. This incredibly useful because you can see exactly how often a flag is being evaluated, and what the results are in real time.





[![](https://blog.launchdarkly.com/wp-content/uploads/2018/06/debugger.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/06/debugger.png)






















You can disable Summary Events for individual flags directly from the Debugger when you need it.




























[![](https://blog.launchdarkly.com/wp-content/uploads/2018/06/debug.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/06/debug.png)






















If you need to see the results of a particular flag, you can click the “Debug“ button to send detailed info. We’ll send that detailed information for that flag for 30 minutes, and then revert to the original summarized behavior.

























### How to Start Using Summary Events


The new Debugger is now available to everyone—check it out in your LaunchDarkly site.

If you created an account after 5/11/18, you are already using summary events. If you’ve been using LaunchDarkly longer, you’ll need to make sure your SDKs are up-to-date and meet the minimum version requirements (read more in our docs [here](https://docs.launchdarkly.com/v2.0/docs/debugger)). As you update each SDK to the new versions, they will automatically begin sending summary events.

If you have more questions about Summary Events, the Debugger, or anything else about the platform please let us know: [support@launchdarkly.com](mailto:support@launchdarkly.com).
