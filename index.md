---
title:
layout: default
permalink: /index.html
---


## Contents

The content of the site is outlined below and can also be accessed using the top left navigation bar.

1. [Dataset]({{site.url}}{{site.baseurl}}/dataset)
2. [Challenges]({{site.url}}{{site.baseurl}}/challenges)
3. [Benchmarks]({{site.url}}{{site.baseurl}}/benchmarks)
4. [Publications]({{site.url}}{{site.baseurl}}/publications)
5. [Members]({{site.url}}{{site.baseurl}}/people)
6. [Collaborators]({{site.url}}{{site.baseurl}}/collaborators)
7. [Roadmap]({{site.url}}{{site.baseurl}}/roadmap)


## Benchmarking deep learning models on brain MRI BHB-10K dataset

The idea of the BHB project is to provide the community with a large benchmarking dataset.
For this purpose, the project hosts state-of-the-art CNN models implemented in Pytorch that are used as baselines for different challenges such as age and sex prediction.



{% assign challenges_sorted = site.challenges | sort: 'added' | reverse  %}
{% assign benchmarks_sorted = site.benchmarks | sort: 'added' | reverse  %}

<!-- Section -->
<section>
    <header class="major">
      <h2>Challenges</h2>
    </header>
    <div class="posts">
    {% for item in challenges_sorted limit: 6 %}
      <article>
        <h3>{{ item.title }}</h3>
        <a href="{{item.ramp_url}}" class="image"><img src="{{site.url}}{{site.baseurl}}/images/resources/{{item.icon}}" alt="" /></a>
        <p>{{ item.teasing }}</p>
        <ul class="actions">
            <center>
            <li><a href="{{item.ramp_url}}" class="button medium">More</a></li>
            </center>
        </ul>
      </article>
    {% endfor %}
    </div>
</section>

