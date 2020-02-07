---
author: rgulati
comments: false
date: 2018-07-10 21:05:50+00:00
layout: post
link: https://launchdarkly.com/blog/launched-filters/
slug: launched-filters
title: 'Launched: Filters'
wordpress_id: 193175
categories:
- Product Updates
tags:
- feature flags
- feature management
- filters
---

Many of us maintain more feature flags than we can handle. You might have started out with just a couple of flags, at some point realized how amazing feature flagging is, and now you just have too many to manage. Even using tags, you could have long lists of flags to scroll through. Some of you asked us for a ‘filters’ feature to help search for flags, and we heard you.

Today, LaunchDarkly has rolled out filters! Now you can use filters to help search through all of your flags, and find the specific ones you need to work with. You can filter flags by:



 	
  * The status of a flag: active, inactive, launched, or new

 	
  * The type of a flag: permanent or temporary

 	
  * The tags your team created


[![](https://blog.launchdarkly.com/wp-content/uploads/2018/07/Screen-Shot-2018-07-02-at-5.21.57-PM-1024x567.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/07/Screen-Shot-2018-07-02-at-5.21.57-PM.png)

Filters are a great tool to easily identify and eliminate flag debt in your code. For example, if you filter by ‘status: inactive’ and ‘type: temporary’ you will find all the temporary flags that have not been used in the past seven days. These may represent flag debt that you can eliminate. Review them, then take action!

[![](https://blog.launchdarkly.com/wp-content/uploads/2018/07/Screen-Shot-2018-07-02-at-5.24.12-PM-1024x567.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/07/Screen-Shot-2018-07-02-at-5.24.12-PM.png)

Looking for kill switches that you haven't had to use? (By the way, good job!) Filter your flags by 'status: inactive' and 'type: permanent'. By filtering for specific use cases, your team can better manage flags within your code and address technical debt.

[![](https://blog.launchdarkly.com/wp-content/uploads/2018/07/Screen-Shot-2018-07-02-at-5.23.45-PM-1024x567.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/07/Screen-Shot-2018-07-02-at-5.23.45-PM.png)

As expected, you can also filter flags by tags you've given them. This helps you look at all the flags within each tag and their status or type. If you are new to tags, check out [this](https://launchdarkly.com/blog/launched-put-a-tag-on-it/) post.

[![](https://blog.launchdarkly.com/wp-content/uploads/2018/07/Screen-Shot-2018-07-02-at-5.27.33-PM-1024x565.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/07/Screen-Shot-2018-07-02-at-5.27.33-PM.png)

And finally, you can sort your flags by oldest, newest, or alphabetical order. Instead of scrolling to the bottom of the page looking for the last flag you created, you can sort by 'newest'. Who doesn't love a good sorting feature?!

[![](https://blog.launchdarkly.com/wp-content/uploads/2018/07/Screen-Shot-2018-07-02-at-5.28.22-PM-1024x568.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/07/Screen-Shot-2018-07-02-at-5.28.22-PM.png)

We created filters so you can easily find the flags you need, and get rid of the flags you don't use. You can quickly understand which flags are 'new', 'inactive', 'temporary', or 'permanent'. Despite the hundreds of flags you may have, you can now easily access your flags in a fast and efficient manner. The filters feature is now available on your LaunchDarkly dashboard.

If you have more questions about filters, or anything else about the platform please let us know: [support@launchdarkly.com](mailto:support@launchdarkly.com).
