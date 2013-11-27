---
layout: frontpage
title: ArmoredSoftware
---

# Blog

{% for post in site.categories.blog %}
<a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>

{{ post.content }}

-----

{% endfor %}
