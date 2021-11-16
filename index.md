---
title:
layout: default
permalink: /index.html
---


## Contents

The content of the site is outlined below and can also be accessed using the top left navigation bar:

1. [Dataset]({{site.url}}{{site.baseurl}}/dataset)
2. [Challenges]({{site.url}}{{site.baseurl}}/challenges)
3. [Benchmarks]({{site.url}}{{site.baseurl}}/benchmarks)
4. [Publications]({{site.url}}{{site.baseurl}}/publications)
5. [Members]({{site.url}}{{site.baseurl}}/people)
6. [Collaborators]({{site.url}}{{site.baseurl}}/collaborators)
7. [Roadmap]({{site.url}}{{site.baseurl}}/roadmap)

## Important links

The important links are listed below:

1. Preprocessing and quality control using container technologies: [brainprep](https://brainprep.readthedocs.io).
2. Data download: [openBHB](https://zenodo.org).


## Collaborative benchmarking

The primary idea of the BHB project is to provide to the community a [large benchmarking dataset]({{site.url}}{{site.baseurl}}/dataset).
The dataset is splitted in two: 1) the openBHB dataset that is publicaly available for participants to train new models, and 2) the privateBHB dataset that is used to compare the performances of the submitted models.
The submitted models are ranked in the [benchmarks section]({{site.url}}{{site.baseurl}}/benchmarks) and form the baselines for the different challenges.


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

