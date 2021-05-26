---
layout: default
permalink: /publications/
---

## RAPT Lab Publications

{% assign items_grouped = site.data.publications | group_by: 'project' %}
{% for group in items_grouped | sort: 'date' | reverse %}
<h3>{{group.name}}</h3>
<ul>
{% for item in group.items %}
<li>{{item.citation}}</li>
{% endfor %}
</ul>
{% endfor %}
