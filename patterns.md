---
layout: default
permalink: /patterns/
---

## Patterns

{% for pattern in site.data.patterns %}
### {{pattern.name}}<br>
<ul>
  <li>{{project.blurb}}</li>
  {% if project.url %}<li><a href="{{ project.url }}" target="_blank">{{project.url}}</a></li>{% endif %}
<li>Add: members, collaborators, pubs, grant info.</li>
  </ul>
{% endfor %}
