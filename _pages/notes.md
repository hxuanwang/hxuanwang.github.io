---
layout: page
permalink: /notes/
title: Notes
description: Short notes and results, including items not posted to arXiv.
nav: true
nav_order: 3
---

{% assign notes_sorted = site.notes | sort: 'date' | reverse %}
{% for note in notes_sorted %}
<div class="entry">
  <div class="entry-title">{{ note.title }}</div>
  {% if note.authors %}
    <div class="entry-authors">{{ note.authors }}</div>
  {% endif %}
  <div class="entry-venue">Note &middot; {{ note.date | date: "%B %Y" }}{% if note.arxiv == false %} &middot; not posted to arXiv{% endif %}</div>
  {{ note.content }}
  {% if note.pdf %}
    <div class="entry-links"><a href="{{ note.pdf | relative_url }}">PDF</a></div>
  {% endif %}
</div>
{% endfor %}
