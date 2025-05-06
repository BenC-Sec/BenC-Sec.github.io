---
layout: posts
title: "Initial Threat Landscape Report: Part 3 - Converging on specific threats"
permalink: /initial tlr CST/
hide_date: true
order: 3
---

Continuing the ongoing process of identifying and assessing threats to the business.

You can find the first part of this series here: <a href="/initial tlr lan/">Initial Threat Landscape Report: Part 1 - Language </a>

## Where to start?

<blockquote style="margin-top: 10px; margin-left: 20px; font-style: italic; color: #f4f938;">
  "That is the only way I ever heard of true research going. I asked a question, devised some method of obtaining an answer, and got a fresh question. Was this possible or that possible? You cannot imagine what this means to an investigator, what an intellectual passion grows upon him! You cannot imagine the strange, colourless delight of these intellectual desires!"<br>
  <span style="font-style: normal; font-weight: bold;">— The Island of Doctor Moreau by H. G. Wells</span>
</blockquote><br>


<!-- If your organisation already has a CTI strategy in place see the Mature Cyber Threat Landscape Report  -->

## Refining Down to Targeted Country and Industry

Now that relevant Threat Actor classifications have been identified, it is time to start identifying specific actors in reports and other sources.

How to identify a relevant specific actor? The country and industry your business operates in is a good first step. <br>
Note: Consider also the location of the business's customer base if different. 

Note: A standard for Threat Actor naming does not exist and as such Threat Actors are referred to by <a href="https://docs.google.com/spreadsheets/u/1/d/1H9_xaxQHpWaa4O_Son4Gx0YOIzlcBWMsdvePFX68EKU/pubhtml#">multiple</a> names.

## Initial Search to Identify Possible Threat Actors

Example:

Searching for APTs targetting the UK and Legal sector

<a href="https://attack.mitre.org/groups/">MITRE ATT&CK Groups</a>  identifies:

APT17
* Targetting legal : Yes
* Targetting UK : Unknown

APT19
* Targetting legal : Yes
* Targetting UK : Unknown

HAFNIUM
* Targetting legal : Yes
* Targetting UK : Unknown

WIRTE
* Targetting legal : Yes
* Targetting UK : No

RedCurl <br>
Note: Not identified with initial search but retrospectively after being linked to a recent attack
* Targetting legal : Unknown
* Targetting UK : Yes

<a href="https://cloud.google.com/security/resources/insights/apt-groups#advanced-persistent-threats-apts">Google Cloud Security APT groups</a> identifies the following:

APT1
* Targetting legal : Yes
* Targetting UK : Yes

APT17
* Targetting legal : Yes
* Targetting UK : Yes

APT19
* Targetting legal : Yes
* Targetting UK : Unknown

<a href="https://www.esentire.com/blog/unraveling-the-many-stages-and-techniques-used-by-redcurl-earthkapre-apt">A google search </a> identifies a recent attack against a UK Law firm. 

RedCurl / EarthKapre 
* Targetting legal : Yes
* Targetting UK : Yes

Initial research indicates that RedCurl is of primary interest being linked to a recent attack (though beware of mis-attribution in attacks). APT17 and APT19 are of secondary interest being mentioned in multiple sources.

Note: I've used a very limited amount of sources for this example, and more should be used at this initial stage of identifying possible APT groups targetting the business. 

## Focusing Research Efforts on Identified Threat Actors

After identifying Threat Actors that are likely targetting the relevant country & sectors to the business, it is time to start building Threat Actor Profiles, which I will be covering in a future post.

For the purposes of the Initial TLR however, it is only necessary at this stage to focus on one representative threat per threat actor classification. By limiting the scope, we keep the report to a manageable size, reduce research effort, and ensure we meet the report's objectives at this stage, while acknowledging that it does not capture all potential threats.

The next part, <a href="/initial tlr RTA/">Initial Threat Landscape Report: Part 4 - Threat Actor TTPs </a> will show how to identify the likely Tactics, Techniques and Procedures (TTPs) used by the identified threat actors. It will also identify mitigations against them.




