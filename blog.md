---
layout: frontpage
title: {{ site.title }}
---

# Blog

Test...

{% for post in site.categories.blog %}

<a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>

{{ post.content }}

-----

{% endfor %}
