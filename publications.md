---
layout: default
permalink: /publications/
---

## RAPT Lab Publications

{% assign groups = site.data.publications | group_by: "project" | sort: "name" %}
{% for group in groups %}
<h3>{{ group.name }}</h3>
<ul>
{% assign itemsSorted = group.items | sort: "date" | reverse %}
{% for item in itemsSorted %}
<li>{{item.date}}--{{item.citation}}
{% endfor %}
</ul>
{% endfor %}
