---
layout: default
title: What Should Agencies Publish?
sectionpage: true
---

The most important data for agencies to publish is the data that they know to be valuable. The data that they’re asked for often, the data that they rely on, the data that their experience tells them is a crucial output of their agency. But, for various reasons, that’s not always enough to go on. So here, broken down by agency, is a list of the datasets that tend to be valuable to publish.

{% for agency_page in site.agencies %}
  {% unless agency_page.sectionpage %}
  * [{{agency_page.title}}]({{agency_page.url}})
  {% endunless %}
{% endfor %}
