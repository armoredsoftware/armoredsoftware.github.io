---
layout: frontpage
title: {{ site.title }}
---

# Blog

{% for post in site.categories.blog %}
<a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a> - test

{{ post.content }}

-----

{% endfor %}
