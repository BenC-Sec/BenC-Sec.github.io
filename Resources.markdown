---
layout: default
title: Resources
permalink: /resources/
order: 4
---

Note: The resources recommended here are for informational purposes only. I do not endorse or vouch for their accuracy, nor do I receive any benefit from referring them. Some may require payment or subscriptions, so please review them carefully to determine if they meet your needs.

I follow the STIX 2 convention, referring to threat actors as Intrusion Sets, which represent related malicious activity over time, linked to the same adversary or group, with a focus on TTPs rather than direct attribution. A Threat Actor, on the other hand, is used when attribution is tied to specific identities.

<h1>Cyber Threat Intelligence Resources</h1>

<!-- Search Bar -->
<input type="text" id="search-box" placeholder="Search by tag..." onkeyup="filterResources()" />

<ul id="resource-list">
  {% for resource in site.data.resources %}
    <li class="resource-item" data-tags="{{ resource.tags | join: ',' }}">
      <a href="{{ resource.url }}" target="_blank">{{ resource.title }}</a>
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

<style>
  .tag {
    background-color: #0073e6; /* Blue background */
    color: white; /* White text */
    padding: 3px 7px;
    border-radius: 5px;
    font-size: 0.85em;
    margin-right: 5px;
    cursor: pointer;
    display: inline-block;
    transition: background-color 0.3s ease;
  }
  
  .tag:hover {
    background-color: #005bb5; /* Darker blue on hover */
  }
  
  #search-box {
    padding: 8px;
    width: 100%;
    max-width: 300px;
    margin-bottom: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }

  .resource-item a {
    font-size: 1.1em; /* Adjust this value for desired size */
    font-weight: 500;
  }  
</style>

<script>
  function filterResources() {
    let input = document.getElementById("search-box").value.toLowerCase();
    let resources = document.querySelectorAll(".resource-item");

    resources.forEach(item => {
      let tags = item.getAttribute("data-tags").toLowerCase();
      item.style.display = tags.includes(input) ? "block" : "none";
    });
  }

  function filterByTag(tag) {
    document.getElementById("search-box").value = tag;
    filterResources();
  }
</script>

