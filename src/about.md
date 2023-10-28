---
title: About
layout: "base.njk"
---

# About Ryan Saul

* Engineering Manager at Streem
* Contract for hire

{% for post in collections.posts %}
- [{{ post.data.title }}]({{ post.url }})
{% endfor %}