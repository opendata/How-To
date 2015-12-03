---
layout: default
title: Basics of Open Data
sectionpage: true
---

{% for basics_page in site.basics %}
  {% unless basics_page.sectionpage %}
  * [{{basics_page.title}}]({{basics_page.url}})
  {% endunless %}
{% endfor %}