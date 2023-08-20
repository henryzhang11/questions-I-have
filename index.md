---
layout: default
title: Home
---

# Welcome to my blog!

Here are my posts:

{% for post in site.posts %}
   [{{ post.title }}]({{ site.baseurl }}{{ post.url }})
{% endfor %}

<div class="post-list">
  {% for post in site.posts %}
    <div><a href="{{ post.url }}">{{ post.title }}</a></div>
  {% endfor %}
</div>
