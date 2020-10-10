---
title: "Certificates"
layout: single
permalink: /certificates/
---

{% for image in site.static_files %}
    {% if image.path contains 'images/statements' %}
        <img src="{{ site.baseurl }}{{ image.path }}" width=700 height=900/>
    {% endif %}
{% endfor %}