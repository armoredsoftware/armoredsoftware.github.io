---
layout: frontpage
title: {{ site.title }}
---

{{ site.description }}

## Recent Activities
-----

{% for post in site.posts.blog %}
* [{{ post.title }}]({{ site.baseurl }}{{ post.url }}) - {{ post.date | date_to_string }}
{% endfor %}

## Team
-----

{% include people.html %}

-----

{{ site.title }} is supported by {{ site.sponsors }}
