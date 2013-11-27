---
layout: frontpage
title: AmoredSoftware
---

ArmoredSoftware is an effort to build a cloud infrastructure where
software can protect itself rather than relying exclusively on its
environment.

## Recent Activities
-----

{% for post in site.posts %}
* [{{ post.title }}]({{ site.baseurl }}{{ post.url }})  {{ post.date | date_to_string }}
{% endfor %}

## Team
-----

ArmoredSoftware is run by The Information and Telecommunication
Technology Center at The University of Kansas.

{% include people.html %}

-----

ArmoredSoftware is supported by The United States Department of Defense.
