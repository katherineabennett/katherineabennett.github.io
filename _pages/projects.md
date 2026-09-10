---
layout: page
title: Research
permalink: /projects/
description: 
nav: true
nav_order: 2
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

## Exoplanet Atmospheres

<div style="display: flex; align-items: flex-start; margin-bottom: 30px;">
  <img src="/assets/img/atmospheres.jpg" alt="Exoplanet Atmospheres" style="width: 200px; margin-right: 20px; border-radius: 5px;">
  <div>
    <p>I am co-I on multiple JWST programs studying the physics and chemistry of giant exoplanet atmospheres, exploring topics ranging from atmospheric dynamics to planet formation.</p>
    <p>Current projects include investigations of hot Jupiter circulation patterns, atmospheric chemistry, and brown dwarf companions.</p>
  </div>
</div>

## Planet Formation

<div style="display: flex; align-items: flex-start; margin-bottom: 30px;">
  <img src="/assets/img/formation.jpg" alt="Planet Formation" style="width: 200px; margin-right: 20px; border-radius: 5px;">
  <div>
    <p>Description of your planet formation research goes here. You can include background, methods, key results, and links to related papers.</p>
  </div>
</div>

## Past Projects

<div style="display: flex; align-items: flex-start; margin-bottom: 30px;">
  <img src="/assets/img/past_project.jpg" alt="Past Project" style="width: 200px; margin-right: 20px; border-radius: 5px;">
  <div>
    <p>Description of past research...</p>
  </div>
</div>

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
