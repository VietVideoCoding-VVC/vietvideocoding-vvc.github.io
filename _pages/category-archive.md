---
layout: default
title: "Categories"
permalink: /categories/
---

<h2>Categories</h2>
<ul>
  {% assign cats = site.categories | sort %}
  {% for cat in cats %}
    {% assign name = cat[0] %}
    {% assign posts = cat[1] %}
    <li>
      <a href="/categories/#{{ name | slugify }}">{{ name }}</a> ({{ posts | size }})
    </li>
  {% endfor %}
</ul>

<hr>
{% for cat in cats %}
  {% assign name = cat[0] %}
  <h3 id="{{ name | slugify }}">{{ name }}</h3>
  <ul>
    {% for post in site.categories[name] %}
      <li><a href="{{ post.url }}">{{ post.title }}</a> <small>({{ post.date | date: "%Y-%m-%d" }})</small></li>
    {% endfor %}
  </ul>
{% endfor %}
