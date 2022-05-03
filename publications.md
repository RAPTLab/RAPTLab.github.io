---
layout: default
permalink: /publications/
---

## RAPT Lab Publications

{% comment %} 
Get the set to group by year, then for each year grab the list of pubs to generate a bullet for each. 
{% endcomment %}

 {% assign citations = site.data.publications |  sort: "date" | reverse | group_by: "date"  %}


{% for citation in citations %}
<h3>{{ citation.name }}</h3> 

  <ul class="pubs">
  {% assign itemsSorted = citation.items | sort: "citation"%}
  {% for item in itemsSorted %}<li>{{item.citation}}        
    {% for link in item.links %}
      {% if link.url %}<a href="{{link.url}}" target="_blank">[{{link.linklabel}}]</a>
      {% endif %}
    {% endfor %}
    
    {% assign project_info = site.data.projects | find: "name", item.project %}
        <br>{% if project_info.url %}<i class="fa-solid fa-up-right-from-square pubicon">{% endif %}{% if project_info.url == nil %} <i class="fa-solid fa-masks-theater pubicon">{%endif%}
        </i>{{item.project}}{% if true %}: <a href="{{project_info.url}}" target="_blank">{{project_info.url}}</a>{% endif %}
    </li>
  {% endfor %}
  </ul>
{% endfor %}

