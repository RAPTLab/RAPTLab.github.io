---
layout: default
permalink: /
---

### About RAPT Lab

Some pithy stuff here.

### Recent publications

A loop

### The RAPT Lab Team

{% assign items_grouped = site.data.members | group_by: 'status' | sort: 'role' %}
{% for group in items_grouped %}
<h3>{{group.name}}s</h3>
<ul>
{% for member in group.items %}
<li>{% if member.url %}<a href="{{ member.url }}">{% endif %}{{ member.first }} {{ member.last }}{% if member.url %}</a>{% endif %}{% if member.affiliation %}, {{ member.affiliation }}{% endif %}{% if member.country %} ({{ member.country }}){% endif %}{% if member.email %}, {{ member.email }}{% endif %}</li>
{% endfor %}
</ul>
{% endfor %}



