---
layout: default
title: Home
---

# Welcome to my blog!

Here are my posts:

<ul class="posts">
{% for post in site.posts %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>
