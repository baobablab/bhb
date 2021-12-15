---
title:
layout: default
permalink: /index.html
---

<br/>

## Download the openBHB dataset

The openBHB dataset is freely available for download on the [IEEE DataPort](https://ieee-dataport.org/open-access/openbhb-multi-site-brain-mri-dataset-age-prediction-and-debiasing) service.

## Contents

The content of the site is outlined below and can also be accessed using the top left navigation bar:

1. [Dataset]({{site.url}}{{site.baseurl}}/dataset)
2. [Challenges]({{site.url}}{{site.baseurl}}/challenges)
3. [Publications]({{site.url}}{{site.baseurl}}/publications)
4. [Members]({{site.url}}{{site.baseurl}}/people)
5. [Collaborators]({{site.url}}{{site.baseurl}}/collaborators)
6. [Roadmap]({{site.url}}{{site.baseurl}}/roadmap)

## Reproducible research

The preprocessing and quality control was performed using container technologies using the [brainprep](https://brainprep.readthedocs.io) module.

## Collaborative benchmarking

The primary idea of the openBHB project is to provide to the community a [large benchmarking dataset]({{site.url}}{{site.baseurl}}/dataset).
The dataset is splitted in two: 1) the openBHB dataset that is publicaly available for participants to train new models, and 2) the openBHB and privateBHB test sets that are used to compare the performances of the submitted models.
All challenges built upon the openBHB dataset are described in the [challenges section]({{site.url}}{{site.baseurl}}/challenges).


{% assign challenges_sorted = site.challenges | sort: 'added' | reverse  %}

<!-- Section -->
<section>
    <header class="major">
      <h2>Last Challenges</h2>
    </header>
    <div class="posts">
    {% for item in challenges_sorted limit: 6 %}
      <article>
        <h3>{{ item.title }}</h3>
        <a href="{{item.url}}" class="image"><img src="{{site.url}}{{site.baseurl}}/images/resources/{{item.icon}}" alt="" /></a>
        <p>{{ item.teasing }}</p>
        <ul class="actions">
            <center>
            <li><a href="{{item.url}}" class="button medium">More info</a></li>
            <li><a href="{{item.challenge_url}}" class="button medium">Challenge page</a></li>
            </center>
        </ul>
      </article>
    {% endfor %}
    </div>
</section>

