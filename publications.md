---
layout: default
permalink: /publications/
---

## RAPT Lab Publications

{% assign groups = site.data.publications | group_by: "project" | sort: "date" | reverse %}
{% for group in groups %}
<h3>{{ group.name }}</h3>
<ul>
{% for item in group.items %}
<li>{{item.date}}--{{item.citation}}
{% endfor %}
</ul>
{% endfor %}