---
layout: default
title: Home
---

# Welcome to my blog!

Here are my posts:

<ul class="posts">
{% for post in site.posts %}
   <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>

<ul class="posts">
{% for post in site.posts %}
 -[{{ post.title }}]({{ site.baseurl }}{{ post.url }})
{% endfor %}
</ul>
