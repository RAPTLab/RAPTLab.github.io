---
layout: default
permalink: /members/
---

## The RAPT Lab Team

{% assign items_grouped = site.data.members | group_by: 'status' | sort: 'role' %}
{% for group in items_grouped %}
<h3>{{group.name}}s</h3>
<ul>
{% for member in group.items %}
<li>{% if member.url %}<a href="{{ member.url }}" target="_blank">{% endif %}{{ member.first }} {{ member.last }}{% if member.url %}</a>{% endif %}{% if member.affiliation %}, {{ member.affiliation }}{% endif %}. <em>RAPT Lab {{ member.role }}</em></li>
{% endfor %}
</ul>
{% endfor %}


{% assign groups = site.data.members | group_by: "status" | sort: "value" %}
{% for group in groups %}
<h3>{{ group.name }}</h3><ul>
{% assign itemsSorted = group.items | sort: "last" %}
{% for item in itemsSorted %}<li>{{item.citation}}</li>{% endfor %}
<li>{% if item.url %}<a href="{{ item.url }}" target="_blank">{% endif %}{{ item.first }} {{ item.last }}{% if item.url %}</a>{% endif %}{% if item.affiliation %}, {{ item.affiliation }}{% endif %}. <em>RAPT Lab {{ item.role }}</em></li>
</ul>
{% endfor %}

