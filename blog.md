---
layout: frontpage
title: ArmoredSoftware
---

# Blog

Test here...

{% for post in site.categories.blog %}
<a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>

{{ post.content }}

-----

{% endfor %}
