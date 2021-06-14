---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Home
permalink: /
---

<style>
    img {
    max-width: 100%;
    height: auto;
    }
</style>

Contact me for machine learning and engineering projects (or anything interesting).


## Latest activities:

<div>
{% for post in site.posts %}
    <span class="date">{{ post.date | date: "%B %-d, %Y"  }}</span> <br>
    <a href="{{ post.url }}" style="font-size:28px; text-decoration: none; color:#547DE8">{{ post.title }}<br><br></a>
{% endfor %}
</div>


<!--<img src="images/grass.jpg" width=700px> <br> <br>
<span style="font-size: 20px">Photo by <a href="https://unsplash.com/@p_kuzovkova?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Polina Kuzovkova</a> on <a href="https://unsplash.com/t/nature?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>-->



