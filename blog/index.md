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
    <li>
        <span>{{ post.date | date_to_string }}</span> » {% if post.highlight %}&starf; {% endif %}<a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>