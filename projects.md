---
layout: default
permalink: /projects/
---

## RAPT Lab Projects

{% for project in site.data.projects %}
### {% if project.full_name %}  {{project.full_name}} {% else %} {{project.name}} {% endif %}

  <p>{% if project.logo %}<img class="projectlogo" src="/assets/img/project_logos/{{project.logo}}" alt="Project logo for {{project.name}}" width="150" >{% endif %}{{project.blurb}}</p>

 {% if project.more %}<p><a href="{{ project.more }}">more ...</a>.</p>{% endif %}

{% endfor %}
