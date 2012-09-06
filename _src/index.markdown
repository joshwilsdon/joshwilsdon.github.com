---
layout: default
title: Josh Wilsdon
---

{% for post in site.posts limit:5 %}
<div class="post">
  <h2>{{ post.date | date: "%Y-%m-%d" }} &raquo; <a href="{{ post.url }}">{{ post.title }}</a></h2>
  {{ post.content }}
</div>
{% endfor %}
<div>
  <h2>... Older posts live in <a href="/archive">the archive</a>.</h2>
</div>
