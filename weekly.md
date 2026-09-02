---
layout: page
title: Weekly Notes
permalink: /weekly.html
---

Industry-wide notes — any fast food company, not just the four I formally cover. Length varies week to week; some weeks are a couple bullets, some are longer.

<ul>
  {% assign weekly_posts = site.posts | where_exp: "post", "post.categories contains 'weekly'" %}
  {% for post in weekly_posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a> — {{ post.date | date: "%b %-d, %Y" }}
    </li>
  {% endfor %}
  {% if weekly_posts.size == 0 %}
    <li><em>No posts yet.</em></li>
  {% endif %}
</ul>
