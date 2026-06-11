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

{% comment %} Oldest-first so the series reads Part 1 → Part 4 (dates run in reading order). {% endcomment %}
{% for post in site.posts reversed %}
  {% include archive-single.html %}
{% endfor %}
