---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Home
permalink: /
---

<style>
    
    .h2 {
        font-weight: 600;
        text-align: center;
        
    }

    .text:hover {
    text-decoration: underline;
    }

    .text {
    text-decoration: underline;
    font-size:22px; 
    text-decoration: none; 
    color:black;
    font-weight: 600;
    }

    .subtext {
        font-size:19px; 
        text-decoration: none; 
        color:black;

    }

    .date {
    font-size:15px; 
    text-decoration: none; 
    color:grey;
    }

</style>

<h2 style="text-align:center;">posts</h2><br>
<hr>
<div>
    {% for post in site.posts %}
        <span class="date">{{ post.date | date: "%B %-d, %Y"  }}</span> <br>
        <a class="text" href="{{ post.url }}">{{ post.title }}</a><br>
        <span class="subtext">{{ post.description }}</span> <br><br>
        <hr>
    {% endfor %}
</div>





<!--<img src="images/grass.jpg" width=700px> <br> <br>
<span style="font-size: 20px">Photo by <a href="https://unsplash.com/@p_kuzovkova?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Polina Kuzovkova</a> on <a href="https://unsplash.com/t/nature?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>-->



