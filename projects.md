---
layout: default
permalink: /projects/
---

## RAPT Lab Projects

{% for project in site.data.projects %}
<b>{{project.name}}</b><br>
<ul>
  <li>{{project.blurb}}</li>
  {% if project.url %}<li><a href="{{ project.url }}" target="_blank">{{project.url}}</a></li>{% endif %}
<li>Add: members, collaborators, pubs, grant info.</li>
  </ul>
{% endfor %}
