---
layout: default
title: Home
---

# Parker's Place

Hello.

I'm Parker, an engineer interested in hardware, software, semiconductors, science, and building things.

This is my little corner of the internet. I use it for things that deserve a home outside of social media: writing, projects, notes, and the occasional rabbit hole.

## Currently

- [Resume](/about/)
- [OpenSilicon](/opensilicon/)
- [Projects(/projects/)
- [Writing](/writing/)

## Recently

{% assign recent_posts = site.posts | sort: 'date' | reverse %}
{% for post in recent_posts limit:5 %}
**{{ post.date | date: "%Y-%m-%d" }}** — [{{ post.title }}]({{ post.url | relative_url }})  
{% endfor %}

---

last updated: {{ site.time | date: "%Y-%m-%d" }}
