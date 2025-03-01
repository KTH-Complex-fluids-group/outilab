---
title: "Outi Lab - Publications"
layout: gridlay
excerpt: "Outi Lab -- Publications."
sitemap: false
permalink: /publications/
---


# Publications

<!-- Only show the specific publication: "Rapid wetting of shear-thinning fluids" -->

{% comment %}
  We remove Group highlights and Full list sections. Instead, we directly list the single publication.

  We also highlight authors based on "highlight" and "pihighlight". 
  For highlight=2, we bold italic the second author in the authors list.
  For pihighlight=-3, we bold italic the author at index (length - 3) from the end.
{% endcomment %}

{% assign target_title = "Rapid wetting of shear-thinning fluids" %}
{% assign item = site.data.publist | where: "title", target_title | first %}

{% if item %}

{%- comment -%}
  1) Print the title in bold italic, then a line break.
  2) Print authors on a new line, with some specified authors bold/italic.
  3) Then a new line with link.

  We'll parse the authors by splitting on " and "
{%- endcomment -%}

{% assign authors_list = item.authors | split: " and " %}
{% assign author_count = authors_list | size %}

<!-- highlight => highlight 2nd author (index=1, 1-based to 0-based) -->
{% assign highlight_index = item.highlight | minus: 1 %}
<!-- pihighlight => highlight from the end, if negative -->
{% assign pi_index = item.pihighlight | plus: 0 %}  {# ensure numeric #}
{% if pi_index < 0 %}
  {% assign pi_index = author_count | plus: pi_index %}
{% endif %}

<!-- Build the authors string with the specified highlights -->
{% assign final_authors = "" %}
{% for author in authors_list %}
  {% assign idx = forloop.index0 %}
  {% if idx == highlight_index or idx == pi_index %}
    {% assign final_authors = final_authors | append: " <strong><em>" | append: author | append: "</em></strong>" %}
  {% else %}
    {% assign final_authors = final_authors | append: " " | append: author %}
  {% endif %}
  {% if forloop.last == false %}
    {% assign final_authors = final_authors | append: " and" %}
  {% endif %}
{% endfor %}

<!-- Now display them -->

<!-- 1) Title -->
**_{{ item.title }}_**  <br />
<!-- 2) Authors with highlights -->
{{ final_authors }}  <br />
<!-- 3) Link -->
<a href="{{ item.url }}">{{ item.display }}</a>

{% else %}
<p>No publication found matching "{{ target_title }}".</p>
{% endif %}
