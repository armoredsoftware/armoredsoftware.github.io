---
layout: frontpage
title: ArmoredSoftware Blog
---

# {{ page.title }}

{% for post in site.categories.blog %}
<a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>

{{ post.content }}

-----

{% endfor %}
