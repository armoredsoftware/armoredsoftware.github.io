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

{% include people.html %}

ArmoredSoftware is run by The Information and Telecommunication
Technology Center at The University of Kansas.

### Faculty

* Perry Alexander (PI)
* Andy Gill (Co-PI)
* Prasad Kulkarni (Co-PI) 

### Staff

* Leon Searl

### Students

### Subcontractors

* Ed Bishop

## Sponsors
-----

ArmoredSoftware is supported by The United States Department of Defense.
