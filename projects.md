---
layout: default
permalink: /projects/
---

## RAPT Lab Projects

{% for project in site.data.projects %}
<b>{{project.name}}</b>
{{project.blurb}}<br/>
{% if project.url %}{{project.url }} <br/> {% endif %} 
<br/>
{% endfor %}
