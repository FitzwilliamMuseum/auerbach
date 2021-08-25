---
title: Six Etchings of Heads 1980-2
permalink: /eras/six-etchings
layout: default
era: 'heads'
preview: https://data.fitzmuseum.cam.ac.uk/imagestore/pdp/pdp24/preview_P_14_2000.jpg
dates: 1980 - 1982
order: 3
---

Auerbach's first series of portrait etchings, proofed and printed by Terry Willson at Palm Tree Studios, and published by Bernard Jacobsen, London.

In 1980 Auerbach visited the artist Joe Tilson in Somerset and made an etching of him. Tilson bit the plate and his son Jake printed it. Back in London, Auerbach etched the rest of the set: all portraits of artists who, like Tilson, were old friends (Kitaj, Kossoff and Freud) or relatives who already sat for him (his wife Julia and his cousin Gerda Boehm).

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
