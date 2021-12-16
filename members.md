---
title:
layout: page_select
entry: people
permalink: /people.html
---

{% assign people_sorted = site.people | sort: 'position' %}
{% assign people_array = 'pi' | split: ',' %}
{% for profile in people_sorted %}
  <!-- If not equal to previous then it must be unique as sorted -->
  {% if profile.position == "pi"  %}
    {% continue %}
  {% endif %}
  {% unless profile.position == previous %}
    {% assign people_array = people_array | push: profile.position %}
  {% endunless %}
  {% assign previous = profile.position %}
{% endfor %}
{% assign people_sorted = site.people | sort: 'joined' %}

{{people_array}}

{% for item in people_array %}

<div class="pos_header">
{% if item == 'postdoc' %}
    <h3>Postdoctoral Fellows</h3>
{% elsif item == 'pi' %}
    <h3>Principal Investigators</h3>
{% elsif item == 'gradstudent' %}
    <h3>Graduate Students</h3>
{% elsif item == 'engineer' %}
    <h3>Research Engineers</h3>
{% elsif item == 'visiting' %}
    <h3>Visiting Scholars</h3>
{% elsif item == 'alumni' %}
    <h3>Alumni</h3>
{% endif %}
</div>

<div class="content list people">
  {% for profile in people_sorted %}
    {% if profile.position contains item %}
    <div class="list-item-people {{profile.cat|replace: ' ', '-'}} {{profile.subcat|replace: ' ', '-'}}">
      <p class="list-post-title">
        {% if profile.site %}
            <a href="{{ profile.site }}">
        {% elsif profile.page %}
            <a href="{{site.url}}{{site.baseurl}}/{{ profile.url }}">
        {% else %}
            <a>
        {% endif %}
        {% if profile.avatar %}
            <img width="200" src="{{site.url}}{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
        {% else %}
            <img width="200" src="{{site.url}}{{site.baseurl}}/images/people/default.png"></a>
        {% endif %}
        {% if profile.site %}
            <a class="name" href="{{ profile.site }}">{{ profile.name }}</a>
        {% elsif profile.page %}
            <a class="name" href="{{site.url}}{{site.baseurl}}/{{ profile.url }}">{{ profile.name }}</a>
        {% else %}
            <a class="name">{{ profile.name }}</a>
        {% endif %}
      </p>
    </div>
    {% endif %}
  {% endfor %}
</div>
<hr>

{% endfor %}
