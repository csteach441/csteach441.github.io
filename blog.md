---
title: Blog Posts
layout: default-vertical
permalink: /blog/

categories:
- blog
- index

tags: index blog
published: true
summary: an index of site blog posts
---

{% for post in site.categories.blog %}

* {{ post.date | date_to_string }} - [{{ post.title }}]({{ post.url }})

  {{ post.summary | replace: '<h3>','<h6>' | replace: '</h3>','</h6>' }}

  Tags: {% for tag in post.tags %} <a href="/tags/{{ tag }}">{{ tag }}</a>{% if forloop.last != true %},
  {% endif %} {% endfor %}

{% endfor %}
