---
title: "Setup"
layout: archive
permalink: /setup/
author_profile: true
---

Step-by-step guides to stand up the basic CTI tooling — written for people who
haven't worked with Docker before. Start with the tools, then deploy a platform.

{% comment %} MM's archive-single.html reads a bare `post` variable, so the loop var must be named `post`. {% endcomment %}
{% for post in site.setup %}
  {% include archive-single.html %}
{% endfor %}
