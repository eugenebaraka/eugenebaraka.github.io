---
layout: page
title: All posts
description: 
permalink: /blog/
---

<div class="tags">
  {% assign tags = site.tags | sort %}
  <a href="{{ site.baseurl }}/blog" class="tag">all</a>
  {% for tag in tags %}
    <a href="/tag/{{ tag | first | slugify }}" class="tag">{{tag | first }}</a>
  {% endfor %}
</div>




<ul class="post-list">
  {% assign mainPosts = site.posts %}
  {% for post in mainPosts %}
    <li class="post-item">
      {% assign date_format = site.minima.date_format | default: "%b %-d, %Y" %}
      <span class="post-meta">
        {{ post.date | date: date_format }} &verbar; 
        {% for tag in post.tags %}
          <a href="/tag/{{ tag | slugify }}" class="tag-link">{{ tag }}</a>
        {% endfor %}
        <h4><a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a></h4>
        <p style="color:#828282">{{ post.description }}</p>
      </span>
    </li>
  {% endfor %}
</ul>