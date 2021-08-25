---
title: Seven Portraits
permalink: /eras/seven-portraits
layout: default
era: 'seven'
preview: https://data.fitzmuseum.cam.ac.uk/imagestore/pdp/pdp28/preview_P_20_2000.jpg
dates: 1989 - 1990
order: 4
---
As with all of Auerbach's prints from this point onwards, this set was bitten, proofed and printed by Mark Balakjian and Dorothea Wight at Studio Prints, London, and published by Marlborough Graphics, London.

The series began in 1989 with two prints ( P.20-2000 & P.21-2000 ) made to accompany the 'de-luxe' edition of Robert Hughes's 1990 book on Auerbach, which partly dictated the format.

Like the earlier series (Six Etchings of Heads 1980-2), the subjects comprised family, friends and acquaintances who already sat for the artist.

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
