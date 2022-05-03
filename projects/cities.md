---
layout: default
permalink: /projects/cities
---

{% comment %} ------------------------------------------------------------------ {% endcomment %} 
{% comment %} Set the variable here so that we can use the same code as much as possible {% endcomment %} 
{% assign thisProject = "Cities on the Edge" %}

{% assign projects = site.data.projects | where: "name", thisProject %}
{% for project in projects %}

## The {% if project.full_name %}  {{project.full_name}} {% else %} {{project.name}} {% endif %} Project

  <p>{% if project.logo %}<img src="/assets/img/project_logos/{{project.logo}}" alt="Project logo for {{project.name}}" width="150" >{% endif %}{{project.blurb}}</p>

  {% if project.url %}<p>Project website: <a href="{{ project.url }}" target="_blank">{{project.url}}</a>.</p>{% endif %}

  {% endfor %}

{% comment %} ------------------------------------------------------------------ {% endcomment %} 
{% comment %} Add more details here if you want {% endcomment %} 


{% comment %} ------------------------------------------------------------------ {% endcomment %} 
{% comment %} Auto-generated pubs list {% endcomment %} 

### Publications on the {{thisProject}} Project


{% assign citations = site.data.publications |  sort: "date" | reverse | group_by: "date" %}
{% for citation in citations %}
{% assign itemsSorted = citation.items | where: "project",thisProject %}

{% if itemsSorted.size > 0 %}
<h3>{{ citation.name }}</h3>
  <ul class="pubs">
  {% for item in itemsSorted %}<li>{{item.citation}}        
    {% for link in item.links %}
      {% if link.url %}<a href="{{link.url}}" target="_blank">[{{link.linklabel}}]</a>
      {% endif %}
    {% endfor %}
    </li>
  {% endfor %}
  </ul>
  {% endif %}
{% endfor %}

