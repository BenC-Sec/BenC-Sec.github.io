---
layout: posts
title: "Initial Threat Landscape Report: Part 1 - Language"
permalink: /initial tlr lan/
hide_date: true
order: 3
---

Communication in a business friendly language and format

To see why starting with an initial TLR has benefits, take a look at <a href="/providing value/">Providing Business Value </a>

## Where to start?

<blockquote style="margin-top: 10px; margin-left: 20px; font-style: italic; color: #f4f938;">
  “The two words 'information' and 'communication' are often used interchangeably, but they signify quite different things. Information is giving out; communication is getting through.”<br>
  <span style="font-style: normal; font-weight: bold;">— Sydney J. Harris</span>
</blockquote><br>

<!-- If your organisation already has a CTI strategy in place see the Mature Cyber Threat Landscape Report  -->

## What language does the business speak?

All functions within a business, including CTI, should ultimately support the organization's core objectives. When CTI is framed around these objectives, it creates a common language that enables clearer communication.

Business objectives typically include:

  * Profitability: Protecting revenue and minimizing financial loss.

  * Efficiency: Streamlining operations and minimizing disruptions.

  * Reducing Spending: Avoiding unnecessary costs.

  * Increasing Productivity: Ensuring employees and systems can operate without interruption.

  * Sustaining Operations: Maintaining business continuity.

A simple example:

❌ Treat actors can use WinRAR to archive files before uploading them to SaaS applications. 

✅  Threat actors can use WinRAR to archive files before uploading them to SaaS applications. Exfiltrated data may include PII or intellectual property, potentially causing significant reputational damage and financial penalties due to regulatory violations. 

If a recent example can be provided with the estimated cost to the victim even better.

## MITRE ATT&CK - a standardized vocabulary for TTPs

The <a href="https://attack.mitre.org/matrices/enterprise/">MITRE ATT&CK Framework </a> provides a common taxonomy that allows TTPs to be consistently compared across different adversary groups using the same standardized terminology.

By incorporating the MITRE ATT&CK framework in the Threat Landscape Report, not only are the TTPs clearly indicated, but readers can also easily research and understand the associated behaviors.

A simple example:

❌ Treat actors can use WinRAR to archive files before uploading them to SaaS applications. 

✅  Threat actors can use WinRAR (T1560.001 Archive via Utility) before uploading them to SaaS applications (T1567.002 Exfiltration to Cloud Storage). Exfiltrated data may include PII or intellectual property, potentially causing significant reputational damage and financial penalties due to regulatory violations. 

Use of the MITRE ATT&CK Framework provides many other benefits which will be explored in later posts.

## Report Writing Style

There are many good resources available for <a href="https://www.youtube.com/watch?v=vwKlNZ6mxak">report writing </a>, but based on my experience, there are a few key themes to focus on and others to avoid.

✅  Short punchy sentences <br>
✅  Effective use of paragraphs, bullet points <br>
✅  Consistency of tense, acronyms, names <br>

❌ Long sentences with unnecessary words <br>
❌ Large walls of text <br>
❌ Uncited statements <br>

The next part, <a href="/initial tlr GTE/">Initial Threat Landscape Report: Part 2 - General Threat Environment</a> begins the iterative process of identifying threats to the organisation.

