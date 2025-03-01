---
title: "Outi Lab - Publications"
layout: gridlay
excerpt: "Outi Lab -- Publications."
sitemap: false
permalink: /publications/
---


# Publications

Publications

{% for publi in site.data.publist %}

{{ publi.title }} 

{% for author in publi.authors %}
{% if forloop.index == publi.highlight %}
{{ author }}
{% elsif forloop.index == publi.pihighlight | abs %}
{{ author }}
{% else %}
{{ author }}
{% endif %}
{% if forloop.last == false %}, {% endif %}
{% endfor %}

{{ publi.display }}

{% endfor %}
