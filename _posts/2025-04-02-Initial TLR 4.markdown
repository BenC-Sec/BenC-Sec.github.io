---
layout: posts
title: "Initial Threat Landscape Report: Part 4 - Threat Actor TTPs"
permalink: /initial tlr RTA/
hide_date: true
order: 3
---

Mapping Threat Actor TTPs using MITRE ATT&CK

You can find the first part of this series here: <a href="/initial tlr lan/">Initial Threat Landscape Report: Part 1 - Language </a>

## Where to start?

<blockquote style="margin-top: 10px; margin-left: 20px; font-style: italic; color: #f4f938;">
  "My business is the analytical framework"<br>
  <span style="font-style: normal; font-weight: bold;">— Todd Gitlin</span>
</blockquote><br>

A great resource for threat actor TTPs is MITRE ATT&CK. This is a knowledge base that maps actual observed adversary behavior to a matrix organized by tactics (actor objectives), techniques (methods) and procedures (the specific actions taken), providing a structured way to analyse and defend against threats.

<!-- If your organisation already has a CTI strategy in place see the Mature Cyber Threat Landscape Report  -->

## TTPs

Once a representative for each threat actor classification has been identified, head over to the MITRE website and download the Navigator layer for the actor. 

On the MITRE Threat Actor's page click the layers button and select download <br><br>
<img src="/assets/images/MAL.png" alt="Confused executive cartoon" style="width:200px;"> 

For some threat actors such as Script kiddies or Hacktavist, you will not find a TTP layers on MITRE's website. You can look at previous reporting on activity by those actors in the relevant Country and Sector and make a best guess to begin with. I have included an example layer for Script Kiddy <a href="../assets/files/Attack_layers/script_kiddies.json" download>here</a>.

## MITRE ATT&CK Navigator

Another great resource provided by MITRE is the ability to display TTPs on the matrix. Here I show how to upload the identified TTPS to produce a view of all priority TTPs to the business based on the identified representative threat actors.

Once you have created or ownloaded the layers from MITRE, go to the <a href="https://mitre-attack.github.io/attack-navigator/">MITRE ATT&CK Navigator</a> page and select Upload from local.<br>

<img src="/assets/images/UFL.png" alt="menu bar" style="width:500px;"> 

Once you've uploaded the first layer, open a new tab by clicking the cross and upload the next layer.

<img src="/assets/images/UFL2.png" alt="new tab" style="width:500px;"> 


Once all layers have been uploaded, click on the cross again but this time select Create layer from other layers.<br>

For domain choose an Enterprise ATT&CK<br>
For expression enter a + b + c for each layer

<img src="/assets/images/layers.png" alt="new tab" style="width:500px;"> 

This new layer presents a list of TTPs to begin comparing against mitigations that the business already has in place. This is an <a href="../assets/files/Attack_layers/combined_ttps.json" download>example</a> for Script Kiddies, TA505 and RedCurl.

The resulting mapping is too big to display but this is a snapshot of the first few tactics with their subtechniques expanded.

<img src="/assets/images/TTPs_MITRE.png" alt="new tab" style="width:600px;"> 

Note: You can export MITRE ATT&CK Navigator layers as Excel files.

The next part, <a href="/initial tlr Gap/">Initial Threat Landscape Report: Part 5 - Gap analysis of TTPs & Mitigations </a> outlines the process of identifying mitigations for these TTPs, followed by a gap analysis to highlight high priority techniques lacking adequate defenses.




