---
layout: page
title: Research
permalink: /projects/
description: 
nav: true
nav_order: 2
display_categories: ['Do nearby rocky exoplanets orbiting M dwarfs have atmospheres?', 'Can we learn about the geologic history of airless exoplanets?', 'What impact do flares have on planetary atmospheres?', 'Does atmospheric composition encode how giant planets formed?', 'Do giant planets have distinct morning and evening climates?']
horizontal: false
---

[View my publications on NASA ADS](https://ui.adsabs.harvard.edu/user/libraries/7Hh68u2QTgah-zm5u182GQ){:target="_blank"}

<style>
.projects h2.category {
  color: #000000 !important;
}

/* For dark mode */
html[data-theme="dark"] .projects h2.category {
  color: #ffffff !important;
}
</style>

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
