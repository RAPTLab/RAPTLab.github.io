---
layout: default
permalink: /
visibility: Lab
---

## About RAPT Lab

We are broadly interested in how people learn in complex, real-world circumstances. However, as our acronym indicates we have a number of areas we focus on depending on the project:

<ul><strong>Representations:</strong> Representations are anything that stands for something else. A name, word, picture or diagram can each refer to the same object or idea, transforming how we understand that object or idea. We are interested in all kinds of representations including drawings, pictures, graphs, plays, skits, and computer simulations.</ul>
<ul><strong>Activity:</strong> We build on sociocultural theories of learning, which highlight the fact that people are always acting in a social world, often in pursuit of one or more goals.</ul>
<ul><strong>Play:</strong> Play is both a powerful motivator and a key element of human learning and development. We are interested in exploring what kinds of play, and how it can be organized to support learning.</ul>
<ul><strong>Technology:</strong> We design new technologies that help bring people together to learn in new ways.</ul>


Most of our projects combine these ideas together! 
<!-- 
<br>
<img src="assets/img/rapt_network.png" alt="Pic of the RAPT elements connected to eaach other" width="450">
-->

## Recent publications

  <ul class="pubs">

{% assign publications = site.data.rapt_web_data.publications | sort: "date" | reverse %}
{% assign pubCounter = 0 %}

{% for publication in publications   %}

  {% if page.visibility == 'All' and publication.visibility == 'Project' or  publication.visibility == 'Lab'  %}    
      {% continue %}
  {% endif %}

    {% if page.visibility == 'Lab' and publication.visibility == 'Project' %}    
        {% continue %}
    {% endif %}

<li>{{publication.citation}}        


    {% for link in publication.links %}
      {% if link.url %}<a href="{{link.url}}" target="_blank"><i class="fa-regular fa-file-lines"></i>{{link.linklabel}}</a>
      {% endif %}
    {% endfor %}

      {% assign project_infos = site.data.rapt_web_data.projects | where: "name", publication.project %}
      {% for project_info in project_infos %}
        {% if project_info.more %}<a href="{{project_info.more}}"><i class="fa-solid fa-dna"></i>{{project_info.name}} project info</a>{% endif %}
        {% if project_info.url %}<a href="{{project_info.url}}" target="_blank"><i class="fa-solid fa-arrow-up-right-from-square"></i>{{project_info.name}} website</a>{% endif %}
      {% endfor %}

    </li>

    {% assign pubCounter = pubCounter | plus: 1 %}
    {% if pubCounter >= 4 %}
      {% break %}
    {% endif %}
  {% endfor %}

  </ul>
