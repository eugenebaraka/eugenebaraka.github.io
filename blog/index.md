---
layout: page
title: Blog
description: My learning journey in data science
permalink: /blog/
---

Stories about my journey in data science. Thoughts about productivity and some 
reflections on my professional life. 


<ul>
  {% for post in site.categories.blog %}
  {% if post.type == "post" %}
    <li>
        <span>{{ post.date | date_to_string }}</span> » <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
        <meta name="description" content="{{ post.summary | escape }}">
        <meta name="keywords" content="{{ post.tags | join: ', ' | escape }}"/>
    </li>
  {% endif %}
  {% endfor %}
</ul>
