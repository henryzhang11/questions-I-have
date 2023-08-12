---
title: Home
---

# Welcome to My Blog

This is the homepage of my blog. Check out my latest posts below:

<ul>
{% for post in site.posts %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
    <small>Posted on {{ post.date | date: "%B %d, %Y" }}</small>
  </li>
{% endfor %}
</ul>

Feel free to explore and connect with me if you have any questions!
