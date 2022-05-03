---
layout: default
permalink: /projects/
---

## RAPT Lab Projects

{% for project in site.data.projects %}
<div class="row">
<h3>{% if project.full_name %}  {{project.full_name}} {% else %} {{project.name}} {% endif %}</h3>
{% if project.logo %}
  <div class="left">
  <img src="/assets/img/project_logos/{{project.logo}}" alt="Project logo for {{project.name}}" width="150" >
  </div>
{% endif %}
<div class="right">
  <p>{{project.blurb}}</p> {% if project.more %}<p><a href="{{ project.more }}">[more about {{project.name}}]</a></p>{% endif %}
  </div>
</div>
{% endfor %}
