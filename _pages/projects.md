---
layout: page
title: projects
permalink: /projects/
description: A collection of my random projects
nav: true
display_categories: [work]
horizontal: false
---
<div class="projects">
  {% assign categorized_projects = site.projects %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
    <div class="container">
      <div class="row row-cols-2">
      {% for project in sorted_projects %}
        {% include projects_horizontal.html %}
      {% endfor %}
      </div>
    </div>
  {% else %}
    <div class="grid">
      {% for project in sorted_projects %}
        {% include projects.html %}
      {% endfor %}
    </div>
  {% endif %}
</div>
