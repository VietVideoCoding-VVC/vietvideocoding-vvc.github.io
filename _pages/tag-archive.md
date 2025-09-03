---
layout: default
title: "Tags"
permalink: /tags/
---

<h2>Tags</h2>
<ul>
  {% assign tags = site.tags | sort %}
  {% for t in tags %}
    {% assign name = t[0] %}
    {% assign posts = t[1] %}
    <li>
      <a href="/tags/#{{ name | slugify }}">{{ name }}</a> ({{ posts | size }})
    </li>
  {% endfor %}
</ul>

<hr>
{% for t in tags %}
  {% assign name = t[0] %}
  <h3 id="{{ name | slugify }}">{{ name }}</h3>
  <ul>
    {% for post in site.tags[name] %}
      <li><a href="{{ post.url }}">{{ post.title }}</a> <small>({{ post.date | date: "%Y-%m-%d" }})</small></li>
    {% endfor %}
  </ul>
{% endfor %}
