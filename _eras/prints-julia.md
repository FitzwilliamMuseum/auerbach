---
title: Prints of Julia
permalink: /eras/prints-of-julia
layout: default
era: julia
preview: https://data.fitzmuseum.cam.ac.uk/imagestore/pdp/pdp28/preview_P_12_2001.jpg
order: 6
dates: 1981 - 2001
---

The artist's wife Julia Auerbach has been a regular weekly sitter for the artist over a long period. Since her appearance in the first set of etched portrait heads in 1989 she has appeared as a subject in numerous prints.

Julia was the main subject of study in Auerbach's etchings in the years 1998-2001, when she was usually drawn in the reclining pose that she adopted to save getting too tired.

In some of the prints she is asleep.

<div class="container mb-3">
  <div class="row">
  {% assign rows =  site.works.size | divided_by: 2.0 | ceil %}
  {% for i in (1..rows) %}
  {% assign offset = forloop.index0 | times: 2 %}
  {% assign sorted =  site.works | sort: "dates" %}
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
