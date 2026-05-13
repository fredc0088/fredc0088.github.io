---
layout: page
title: projects
permalink: /projects/
description: A selection of my professional and personal projects, ranging from distributed systems to NLP tools.
nav: true
nav_order: 2
display_categories: [Work, Research]
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display projects filtered by categories -->
  {% for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {% assign projects = site.projects | where: "category", category %}
  <div class="grid">
    {% for project in projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endfor %}

{% else %}

<!-- Display projects without categories -->
  <div class="grid">
    {% for project in site.projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
{% endif %}
</div>
