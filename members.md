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



