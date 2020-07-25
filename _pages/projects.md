---
layout: archive
permalink: /projects/
title: Data Science Projects
author_profile: true
---

{% include base_path %}

{% for tag in group_names %}
  {% assign posts = group_items[forloop.index0] %}
  <h2 id="{{ tag | slugify }}" class="archive__subtitle">{{ tag }}</h2>
  {% for post in posts %}
  {% endfor %}
{% endfor %}