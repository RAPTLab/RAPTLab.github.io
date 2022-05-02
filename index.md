---
layout: default
permalink: /
---

## About RAPT Lab

We are broadly interested in how people learn in complex, real-world circumstances. However, as our acronym indicates we have a number of areas we focus on depending on the project:
<ul><strong>Representations:</strong> This refers to anything that we recognize might stand for something else to help us think about it. We are interested in all kinds of representations including drawings, pictures, graphs, plays, skits, and computer simulations.</ul>
<ul><strong>Activity:</strong> We build on sociocultural theories of learning, which highlight the fact that people are always acting in a social world, often in pursuit of one or more goals.</ul>
<ul><strong>Play:</strong> Play is both a powerful motivator and a key element of human learning and development. We are interested in exploring what kinds of play, and how it can be organized to support learning.</ul>
<ul><strong>Technology:</strong> We design new technologies that help bring people together to learn in new ways</ul>

We often combine these ideas together! 

## Recent publications

  <ul class="pubs">

{% for publication in site.data.publications limit:5 %}

<li>{{publication.citation}}        


    {% for link in publication.links %}
      {% if link.url %}<a href="{{link.url}}" target="_blank">[{{link.linklabel}}]</a>
      {% endif %}
    {% endfor %}
    </li>
  {% endfor %}

  </ul>
