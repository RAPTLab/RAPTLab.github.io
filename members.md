---
layout: default
permalink: /members/
---

## The RAPT Lab Team

<div>
{% assign groups = site.data.members | group_by: "status" | sort: "value" %}
{% for group in groups %}

    <h3>{{ group.name }}{% if group.name != "Lab Alumni"%}s{%endif%}</h3>


    {% assign itemsSorted = group.items | sort: "last" %}

    {% for item in itemsSorted %}

        <div class="row">
        {% if item.pic %}
            <div class="thinLeft">
                <img src="{{item.pic}}" alt="Photo of {{item.name}}" width="100" > 
            </div>
        {% else %}
            <div class="thinLeft"><i class="fa fa-user fa-5x" aria-hidden="true"></i>
            </div>
        {% endif %}
            <div class="right">
            <p>
                <strong>{{ item.first }} {{ item.last }}</strong>{% if item.pronouns %} ({{ item.pronouns }}) {% endif %} <em>{{ item.role }}</em><br>
                {% if item.affiliation %} {{ item.affiliation }}{% endif %}
            </p>

            {% if item.url %}
                <p><u>Website:</u> <a href="{{ item.url }}" target="_blank">{{item.url}}</a></p>
            {% endif %}

            {% if item.interests %}
                <p><u>Research interests:</u> {{ item.interests }}</p>
            {% endif %}

            </div>
        </div>
    {% endfor %}
    <br>

{% endfor %}
</div>