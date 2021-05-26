---
layout: default
permalink: /publications/
---

## RAPT Lab Publications

{% assign items_grouped = site.data.publications | group_by: 'project' | sort: 'date' | reverse %}
{% for group in items_grouped %}
<h3>{{group.name}}</h3>
<ul>
{% for item in group.items %}
<li>{{item.citation}}</li>
{% endfor %}
</ul>
{% endfor %}
