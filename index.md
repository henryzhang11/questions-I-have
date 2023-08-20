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

{% for post in site.posts %}
   [{{ post.title }}]({{ site.baseurl }}{{ post.url }})
{% endfor %}

{% for post in site.posts %}
  <div><a href="{{ post.url }}">{{ post.title }}</a></div>
{% endfor %}
