---
layout: default
permalink: /projects/
---

## RAPT Lab Projects

{% for project in site.data.projects %}
<b>{{project.name}}</b><br>
{{project.blurb}}<br>
{% if project.url %}<a href="{{ project.url }}" target="_blank">{{project.url}}</a><br>{% endif %}
Add: members, collaborators, pubs, grant info.<br>
{% endfor %}
