---
layout: default
permalink: /publications/
---

## RAPT Lab Publications
{% comment %} Get the set to group by year, then for each year grab the list of pubs to generate a bullet for each. {% endcomment %}
{% assign citations = site.data.publications |  sort: "date" | reverse | group_by: "date"  %}
<ul class="pubs">
{% for citation in citations %}


<h2>{{citation.name}}</h2> 

  {% assign itemsSorted = citation.items | sort: "citation"%}
  {% for item in itemsSorted %}

  <li>
  {{item.citation}}      
  
    {% for link in item.links %}
      {% if link.url %}[<a href="{{link.url}}" target="_blank">{{link.linklabel}}</a>]
      {% endif %}
    {% endfor %}
    
    {% assign project_infos = site.data.projects | where: "name", item.project %}
      {% for project_info in project_infos %}
        {% if project_info.more %}[<a href="{{project_info.more}}">{{project_info.name}} project info</a>]{% endif %}
        {% if project_info.url %}[<a href="{{project_info.url}}" target="_blank">{{project_info.name}} website</a>]{% endif %}
      {% endfor %}
  {% endfor %}
  </li>

{% endfor %}
<br>
<strong>NOTE</strong>: Additional publications are currently being imported so if there is something you expect don't see but are curious about please contact JDanish AT iu.edu.

