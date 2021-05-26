---
layout: default
permalink: /projects/
---

## RAPT Lab Projects

{% for project in site.data.projects %}
{{project.name}}
{{project.blurb}}
{% if project.url %}{%project.url %}{% endif %}
{% endfor %}
