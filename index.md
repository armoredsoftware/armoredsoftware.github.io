---
layout: frontpage
title: {{ site.title }}
---

{{ site.description }}

## Recent Activities
-----

<ul>
{% for post in site.categories.blog limit:10 %}
<li><a href="({{ site.baseurl }}{{ post.url }})">{{ post.title }}</a> - {{ post.date | date_to_string }}</li>
{% endfor %}
</ul>

{% include blog-date-10.html %}

## Team
-----

{% include people.html %}

-----

{{ site.title }} is supported by {{ site.sponsors }}
