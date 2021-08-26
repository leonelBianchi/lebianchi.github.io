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

    .text:hover {
    text-decoration: underline;
    }

    .text {
    text-decoration: underline;
    font-size:20px; 
    text-decoration: none; 
    color:#547DE
    }

</style>


<div>
<br><br>
{% for post in site.posts %}
    <span class="date">{{ post.date | date: "%B %-d, %Y"  }}</span> <br>
    <a class="text" href="{{ post.url }}">{{ post.title }}<br><br></a>
    <img  src="images/{{ post.img }}.jpg">
{% endfor %}
</div>


<!--<img src="images/grass.jpg" width=700px> <br> <br>
<span style="font-size: 20px">Photo by <a href="https://unsplash.com/@p_kuzovkova?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Polina Kuzovkova</a> on <a href="https://unsplash.com/t/nature?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>-->



