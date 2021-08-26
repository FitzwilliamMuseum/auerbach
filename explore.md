---
layout: default
permalink: /explore/
title: Explore Auerbach's work
---
<div class="container mb-3">
  <div class="row">
{% assign rows = site.works.size | divided_by: 2.0 | ceil %}
{% for i in (1..rows) %}
{% assign offset = forloop.index0 | times: 2 %}
{% assign sorted = site.works | sort:"dates" %}
    {% for author in sorted limit:2 offset:offset %}
    <div class="col-md-4 mb-3">
      <div class="card h-100" >
        <a href="{{site.baseurl}}{{ author.permalink }}" class="stretched-link">
          <img class="card-img-top" src="{{site.baseurl}}{{author.preview}}" alt="Card image cap" width="300" height="300"/>
        </a>
        <div class="card-body">
          <h3 class="lead mt-2">
            <a href="{{site.baseurl}}{{ author.permalink }}" class="stretched-link">{{author.title}}</a>
          </h3>
          {% if author.dates %}
            <p class="text-info">{{author.dates }}</p>
          {% endif %}
        </div>
      </div>
    </div>
    {% endfor %}
  {% endfor %}
  </div>
</div>
