---
layout: default
title: Bob!
---

This page will contain information about Bob.

![Bob](/images/bob_asof_20100623.jpg)

<div class="post">
  <h1>There are {{ site.tags.bob | size }} Bob related posts:</h1>
  <ul class="posts">
    {% for post in site.tags.bob %}
      <li><span>{{ post.date | date: "%Y-%m-%d" }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
</div>
