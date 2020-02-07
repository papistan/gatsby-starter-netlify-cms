---
author: sagarwal
comments: false
date: 2018-12-13 23:22:30+00:00
layout: post
link: https://launchdarkly.com/blog/launched-file-based-source-option-for-testing-launchdarkly-sdks/
slug: launched-file-based-source-option-for-testing-launchdarkly-sdks
title: 'Launched: File-Based Source Option for Testing LaunchDarkly SDKs'
wordpress_id: 193607
categories:
- Product Updates
tags:
- feature management
- integration testing
- local testing
- SDKs
- testing
- testing feature flags
---

LaunchDarkly provides SDKs in all major programming languages, powered by a worldwide service that propagates feature flag changes to your application in milliseconds, ensuring that your users get the experience that is right for them. We're committed to making feature flagging a seamless part of your process at every step of the workflow, from development to testing to production.

We've always supported local development and testing by allowing developers to put the client in offline mode to return defaults, or by giving devs their own environments in LD. But sometimes the defaults aren't the values you actually want to test.

We're happy to announce that we've added a new capability to all of our server SDKs that allow you to develop and test your code using [flag values that you can store in a file](https://docs.launchdarkly.com/docs/reading-flags-from-a-file).

This new file-based option allows you to develop locally without having to connect to LaunchDarkly. That way your local environment can include feature flag evaluations without having to use an external service or write your own feature flag mocks. This capability is intended for local testing, integration testing, and other non-production environments only.

The files for flag evaluation can be standard JSON or YAML, and you have the option to have the file-based source include just basic information about a flag (name and value). For example:
<table cellpadding="0" cellspacing="0" border="0" >
<tbody >
<tr >

<td class="code" >





`{`




`  ``"flagValues"``: {`




`    ``"my-string-flag-key"``: ``"value-1"``,`




`    ``"my-boolean-flag-key"``: ``true``,`




`    ``"my-integer-flag-key"``: ``3`




`  ``}`




`}`




</td>
</tr>
</tbody>
</table>


You can also include more detailed information, such as flag rules, targets, or segments. In fact, if you want to test using the exact state of all of your LaunchDarkly flags today, you can do so by simply requesting the latest state of all flags from our API and saving that output to a file. Check out the [docs](https://docs.launchdarkly.com/v2.0/docs/reading-flags-from-a-file) for more detailed instructions.

The file-based option for testing feature flag evaluations is currently available in LaunchDarkly's Go, Java, .NET, Ruby, and Python SDKs. Full support for file-based sources for all server-side SDKs is coming over the next few months, and [file-based source option documentation](https://docs.launchdarkly.com/v2.0/docs/reading-flags-from-a-file) will be updated as SDKs are updated.

Get started by upgrading to the latest SDKs, and then [follow these instructions](https://docs.launchdarkly.com/v2.0/docs/reading-flags-from-a-file) to try it out for yourself. And as always, feel free to contact [support](mailto:support@launchdarkly.com) with any questions.
