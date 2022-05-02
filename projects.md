---
layout: default
permalink: /projects/
---

## RAPT Lab Projects

{% for project in site.data.projects %}
### {{project.name}}<br>
<ul>
  <li>{{project.blurb}}</li>
  {% if project.url %}<br>For more info, see the project website at: <a href="{{ project.url }}" target="_blank">{{project.url}}</a>.{% endif %}
  </ul>
{% endfor %}
