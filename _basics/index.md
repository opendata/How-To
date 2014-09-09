---
layout: default
title: Basics of Open Data
---

{% for basics_page in site.basics %}
  * [{{basics_page.title}}]({{basics_page.url}})
{% endfor %}