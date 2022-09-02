---
layout: page
title: Readings
description: Favorite reads 
permalink: /readings/
---

I struggle to stay on top of my readings. This is an effort made to make my commitments to books public haha. 
I will be sharing my thoughts on some of my favorite books. Let's connect on [Goodreads](https://www.goodreads.com/user/show/75194625-eugene-baraka).


<ul>
  {% for post in site.categories.readings %}
    <li>
        <span>{{ post.date | date_to_string }}</span> » {% if post.highlight %}&starf; {% endif %}<a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
