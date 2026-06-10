---
title: "Resources"
layout: single
permalink: /resources/
author_profile: false
toc: false
---

The resources here are for informational purposes only. I do not endorse or vouch
for their accuracy, nor do I receive any benefit from referring them. Some may
require payment or subscriptions, so please review them carefully to decide
whether they meet your needs.

I follow the STIX 2 convention, referring to threat actors as **Intrusion Sets** —
related malicious activity over time, linked to the same adversary or group, with
a focus on TTPs rather than direct attribution. A **Threat Actor** is used when
attribution is tied to a specific identity.

<!-- Search box: filters the list below by tag (styling lives in custom.css) -->
<input type="text" id="search-box" placeholder="Search by tag…" onkeyup="filterResources()" />

<ul id="resource-list">
  {% for resource in site.data.resources %}
    <li class="resource-item" data-tags="{{ resource.tags | join: ',' }}">
      <a href="{{ resource.url }}" target="_blank" rel="noopener noreferrer">{{ resource.title }}</a>
      <br>
      <small>
        Tags:
        {% for tag in resource.tags %}
          <span class="tag" onclick="filterByTag('{{ tag }}')">{{ tag }}</span>
        {% endfor %}
      </small>
    </li>
  {% endfor %}
</ul>

<script>
  function filterResources() {
    const input = document.getElementById("search-box").value.toLowerCase();
    document.querySelectorAll(".resource-item").forEach(item => {
      const tags = item.getAttribute("data-tags").toLowerCase();
      item.style.display = tags.includes(input) ? "list-item" : "none";
    });
  }

  function filterByTag(tag) {
    document.getElementById("search-box").value = tag;
    filterResources();
  }
</script>
