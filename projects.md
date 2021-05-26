---
layout: default
permalink: /projects/
---

## RAPT Lab Projects

{% assign items_grouped = site.data.projects %}

{% for item in group.items %}
{{item.name}}
{{item.blurb}}
{% if item.url %}{%item.url %}{% endif %}
{% endfor %}
