---
title: "Outi Lab - Publications"
layout: gridlay
excerpt: "Outi Lab -- Publications."
sitemap: false
permalink: /publications/
---

# Publications

{% assign items = site.data.publist %}
{% assign total = items | size %}
{% for item in items %}
  {% assign authors_list = item.authors | split: " and " %}
  {% assign author_count = authors_list | size %}
  {% assign highlight_index = item.highlight | minus: 1 %}
  {% assign pi_index = item.pihighlight | plus: 0 %}
  {% if pi_index < 0 %}
    {% assign pi_index = author_count | plus: pi_index %}
  {% endif %}
  {% assign final_authors = "" %}
  {% for author in authors_list %}
    {% assign idx = forloop.index0 %}
    {% if idx == highlight_index %}
      {% assign final_authors = final_authors | append: " <strong><em>" | append: author | append: "</em></strong>" %}
    {% elsif idx == pi_index %}
      {% assign final_authors = final_authors | append: " <strong><u><em>" | append: author | append: "</em></u></strong>" %}
    {% else %}
      {% assign final_authors = final_authors | append: " " | append: author %}
    {% endif %}
    {% unless forloop.last %}
      {% assign final_authors = final_authors | append: " and" %}
    {% endunless %}
  {% endfor %}

  {% assign reverse_index = total | minus: forloop.index | plus: 1 %}
  {{ reverse_index }}. **_{{ item.title }}_**  
  {{ final_authors }}  
  <a href="{{ item.url }}">{{ item.display }}</a>

  {% unless forloop.last %}
  {% endunless %}
{% endfor %}

