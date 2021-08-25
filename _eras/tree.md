---
title: Tree at Tretire
permalink: /eras/tree-at-tretire
layout: default
era: tretire
preview: https://data.fitzmuseum.cam.ac.uk/imagestore/pdp/pdp24/preview_P_93_1999.jpg
dates: 1975-6
order: 2
---

Auerbach's only two landscape prints, proofed and printed at White Ink Studio and published by Marlborough Graphics, London.

The subject is the view from the upstairs window of a house at Tretire in Herefordshire, which the artist studied in numerous drawings before working directly from life on the plate. Both prints combined an etched plate with a layer of screenprint drawn on the same scale as the plate. Auerbach had used a drawn layer in a similar way in a set of screenprints made from his paintings in the 1960s.

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
