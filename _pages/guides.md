---
title: "Guides"
layout: archive
permalink: /guides/
author_profile: true
---

Practical, how-to guidance for putting Cyber Threat Intelligence into action. The
series below reads top-to-bottom as a single beginner journey — from making the
business case through to mapping threat-actor TTPs.

Every guide is tagged by **intelligence-cycle stage** and **difficulty** — browse
all tags on the [tag index](/tags/).

{% for post in site.posts %}
  {% include archive-single.html %}
{% endfor %}
