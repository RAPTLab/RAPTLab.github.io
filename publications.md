---
layout: default
permalink: /publications/
---

## RAPT Lab Publications

{% assign projects = site.data.publications | group_by: 'project' %}
{% assign projectsSorted = projects | sort: "name" %}
{% for y in projectsSorted %}
<h3>{{ y.project }}</h3>
<ul>
  {% assign yearTitlesSorted = y.items | sort: 'date' | reverse %}
  {% for t in yearTitlesSorted %}
  <li>{{ t.citation }}</li>
  {% endfor %}
</ul>
</li>
{% endfor %}
