---
title: All Topics
layout: Static
cat-value: Topics
permalink: /Topics
---
<div class="slot-medium">
{% assign sorted_notes = site.notes | sort: 'category-order' %}
{% assign first_item = true %}
  {% for note_page in sorted_notes %}
    {% if note_page.category == "MOC" %}
      {% assign count = 0 %}
      {% for note in site.notes %}
        {% if note.category == note_page.cat-value %}
          {% assign count = count | plus: 1 %}
        {% endif %}
      {% endfor %}
      {% if count > 0 %}
        {% if first_item %}
          {% assign first_item = false %}
        {% else %},
        {% endif %}
      <a href="{{ note_page.url }}">{{note_page.title}}</a><sup>{{count}}</sup>
      {% endif %}
    {% endif %}
  {% endfor %}
  </div>
