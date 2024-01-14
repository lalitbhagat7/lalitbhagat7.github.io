---
layout: page
permalink: /teaching/
title: teaching
description: Materials for courses you taught. Replace this text with your description.
nav: true
nav_order: 4
display_categories: [Teaching Assistant, Teaching Associate]
horizontal: false
---


<!-- pages/teaching.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized teaching items -->
  {% for category in page.display_categories %}
    <h2 class="category">{{ category }}</h2>
    {% assign categorized_teaching = site.teaching | where: "category", category %}
    {% assign sorted_teaching = categorized_teaching | sort: "importance" %}
    <!-- Generate cards for each teaching item -->
    <div class="container">
      <div class="row row-cols-2">
        {% for teaching_item in sorted_teaching %}
          <div class="col-sm mt-3 mt-md-0">
            <h3>{{ teaching_item.title }}</h3>
            <p>{{ teaching_item.description }}</p>
            <!-- Add more details about the teaching item as needed -->
          </div>
        {% endfor %}
      </div>
    </div>
  {% endfor %}

{% else %}
<!-- Display teaching items without categories -->

{% assign sorted_teaching = site.teaching | sort: "importance" %}

  <!-- Generate cards for each teaching item -->
  <div class="container">
    <div class="row row-cols-2">
      {% for teaching_item in sorted_teaching %}
        <div class="col-sm mt-3 mt-md-0">
          <h3>{{ teaching_item.title }}</h3>
          <p>{{ teaching_item.description }}</p>
          <!-- Add more details about the teaching item as needed -->
        </div>
      {% endfor %}
    </div>
  </div>
{% endif %}
</div>

<!--
    ---
    layout: page
    permalink: /teaching/
    title: teaching
    description: Materials for courses you taught. Replace this text with your description.
    nav: true
    nav_order: 4
    display_categories: [work]
    horizontal: false
    ---
    
    
    <!-- pages/projects.md -->
    <div class="projects">
    {% if site.enable_project_categories and page.display_categories %}
      <!-- Display categorized projects -->
      {% for category in page.display_categories %}
      <h2 class="category">{{ category }}</h2>
      {% assign categorized_projects = site.projects | where: "category", category %}
      {% assign sorted_projects = categorized_projects | sort: "importance" %}
      <!-- Generate cards for each project -->
      {% if page.horizontal %}
      <div class="container">
        <div class="row row-cols-2">
        {% for project in sorted_projects %}
          {% include projects_horizontal.liquid %}
        {% endfor %}
        </div>
      </div>
      {% else %}
      <div class="grid">
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
        <div class="row row-cols-2">
        {% for project in sorted_projects %}
          {% include projects_horizontal.liquid %}
        {% endfor %}
        </div>
      </div>
      {% else %}
      <div class="grid">
        {% for project in sorted_projects %}
          {% include projects.liquid %}
        {% endfor %}
      </div>
      {% endif %}
    {% endif %}
    
    </div>
    --!>
