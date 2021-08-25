---
title: Early drypoints
permalink: /eras/early-drypoints
layout: default
era: early
preview: https://data.fitzmuseum.cam.ac.uk/imagestore/pdp/pdp28/preview_P_8_2000.jpg
dates: circa 1954
order: 1
---

These are the earliest prints in the exhibition, dating from around 1954 when Auerbach was still a student at the Royal College of Art. They were printed by the artist (using the back of a spoon to apply pressure) and never formally editioned as a set. The dozen or so sets that survive went to fellow artists and friends, such as James Kirkman, who gave his set to the Fitzwilliam. There is considerable variation in printing, and some of the sets were made up with earlier proofs that Auerbach had printed before burnishing away, or adding, work on the plate.

<div class="container mb-3">
  <div class="row">
  {% assign rows =  site.works.size | divided_by: 2.0 | ceil %}
  {% for i in (1..rows) %}
  {% assign offset = forloop.index0 | times: 2 %}
  {% assign sorted =  site.works | sort: "object" %}
      {% for author in sorted limit:2 offset:offset %}
      {% if author.era contains page.era %}
      <div class="col-md-4 mb-3">
        <div class="card h-100" >
          <a href="{{site.baseurl}}{{ author.permalink }}" class="stretched-link">
            <img class="card-img-top square" src="{{author.preview}}" alt="Card image cap" width="300" height="300"/>
          </a>
          <div class="card-body">
            <h3 class="lead mt-2">
              <a href="{{site.baseurl}}{{ author.permalink }}" class="stretched-link">{{author.title}}</a>
            </h3>
            {% if author.dates %}
            <p class="text-info">{{author.dates}}</p>
            {% endif %}
          </div>
        </div>
      </div>
      {% endif %}
      {% endfor %}
    {% endfor %}


  </div>
</div>
