---
title: Latest Prints
permalink: /eras/latest-prints
layout: default
era: latest
preview: https://data.fitzmuseum.cam.ac.uk/imagestore/pdp/pdp28/preview_P_26_2000.jpg
order: 7
dates: 1994 - 2006
---


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
