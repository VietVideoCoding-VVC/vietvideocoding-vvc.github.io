---
layout: post
title: "Bài viết của Thuong Nguyen Canh"
author: thuongnguyencanh
permalink: /author/thuongnguyencanh/
---

<div class="author-archive">
  {% assign author_id = page.author %}
  {% for post in site.posts %}
    {% if post.author == author_id %}
    <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a> — {{ post.date | date: "%b %d, %Y" }}</li>
    {% endif %}
  {% endfor %}
</div>
