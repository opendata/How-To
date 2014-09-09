---
layout: default
title: How to Work with Open Data
sectionpage: true
---

{% for process_page in site.processes %}
  {% unless process_page.sectionpage %}
  * [{{process_page.title}}]({{process_page.url}})
  {% endunless %}
{% endfor %}