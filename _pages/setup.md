---
title: "Setup"
layout: archive
permalink: /setup/
author_profile: true
---

Step-by-step guides to stand up the basic CTI tooling — written for people who
haven't worked with Docker before. Start with the tools, then deploy a platform.

{% for doc in site.setup %}
  {% include archive-single.html post=doc %}
{% endfor %}
