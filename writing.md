---
layout: default
title: Writing
permalink: /writing/
---

# Writing

A collection of things I've written: essays, engineering notes, book reviews, and miscellaneous thoughts.

{% assign posts = site.posts | where_exp: "post", "post.project != 'opensilicon'" | sort: 'date' | reverse %}
{% for post in posts %}
**{{ post.date | date: "%Y-%m-%d" }}** — [{{ post.title }}]({{ post.url | relative_url }})  
{% if post.excerpt %}{{ post.excerpt | strip_html | truncate: 160 }}{% endif %}

{% endfor %}
