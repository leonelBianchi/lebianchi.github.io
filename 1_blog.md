---
layout: default
title: Blog
permalink: /blog/
---

<div>
{% for post in site.tags.writting %}
    <span class="date">{{ post.date | date: "%B %-d, %Y"  }}</span> <br>
    <a href="{{ post.url }}" style="font-size:28px; text-decoration: none; color:#547DE8">{{ post.title }}</a>
{% endfor %}
</div>