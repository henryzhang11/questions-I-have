---
layout: post
title: how to set up blog on github that processes Latex code
---

1. Create a new Github repository following the link https://docs.github.com/en/get-started/quickstart/create-a-repo
2. Create /_layouts/default.html;

```
<!DOCTYPE html>
<html>
<head>
   <meta charset="utf-8">
   <title>{{ page.title }}</title>
   <script type="text/x-mathjax-config">
     MathJax.Hub.Config({
       tex2jax: {
         inlineMath: [['$','$'], ['\\(','\\)']],
         displayMath: [['$$','$$'], ['\\[','\\]']],
         processEscapes: true,
         processClass: "mathjax",
         skipClass: "no-mathjax"
       }
     });
   </script>
   <script type="text/javascript" async
     src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-MML-AM_CHTML">
   </script>
   <style>
       body {
           font-family: 'Calibri', sans-serif;
           margin: 7em 15%;
       }
   </style>
</head>
<body>

<div class="container">
   {{ content }}
</div>

</body>
</html>
```

4.
5. /_layouts/post.html; /_posts
/2023-08-22-my-first-post.md;.gitignore;_config.yml;index.md
