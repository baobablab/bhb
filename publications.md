---
title:
layout: page_select
entry: biblio
permalink: publications.html
---

<h2> Publications </h2>

{% assign today = site.time | date: '%Y' %}
{% assign biblio_sorted = site.biblio | sort: 'year' | reverse %}
{% assign year = today | minus: 5 %}

<div class="bibliography">
  {% assign count = 1 %}
  {% for entry in biblio_sorted %}
    {% if entry.year > year and entry.bestof %}
    <li>
      <div class="text-justify  {{entry.cat}} {{entry.subcat}}">
        <b>{{count}}.</b>
        {% assign count = count | plus:1 %}
        {% if entry.journal %}
            {{entry.author}}: {{entry.title}}, {{entry.journal}} ({{entry.year}})
        {% elsif entry.booktitle %}
            {{entry.author}}: {{entry.title}}, {{entry.booktitle}} ({{entry.year}})
        {% else %}
            {{entry.author}}: {{entry.title}} ({{entry.year}})
        {% endif %}
        {% if entry.doi %}
          <a href="http://doi.org/{{entry.doi}}" class="icon fa-link" target="_blank"><span class="label">DOI</span></a>
        {% endif %}
      </div>
    </li>
    {% endif %}
  {% endfor %}
</div>
<hr>


