---
layout: page
permalink: /teaching/
title: Teaching
description: Teaching experience, grouped by institution.
nav: true
nav_order: 4
---

{% assign institutions = site.teachings | group_by: "institution" %}
{% for group in institutions %}
  <h3 class="group-heading">{{ group.name }}</h3>
  <ul class="teaching-list">
    {% assign courses = group.items | sort: "year" | reverse %}
    {% for course in courses %}
      <li>
        <div class="course-name">{{ course.title }}</div>
        <div class="course-meta">
          {{ course.term }} {{ course.year }}{% if course.role %} &middot; {{ course.role }}{% endif %}{% if course.instructor %} &middot; {{ course.instructor }}{% endif %}
        </div>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
