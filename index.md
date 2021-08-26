---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Home
permalink: /
---

<style>
    img {
    width: 250px;
    height: 250px;
    }

    .text:hover {
    text-decoration: underline;
    }

    .text {
    text-decoration: underline;
    font-size:13px; 
    text-decoration: none; 
    color:#547DE
    }

    .media-container {
    display: flex;
    flex: 1 1 0px;
    width: 32%;
    flex-wrap: wrap;
    flex-direction: row;
    justify-content: space-between;
   
    }


</style>


<div class="media-container">
<br><br>
    {% for post in site.posts %}
        <div class="media">
            <span class="date">{{ post.date | date: "%B %-d, %Y"  }}</span> <br>
            <a class="text" href="{{ post.url }}">{{ post.title }}<br><br></a>
            <img  src="{{ post.img }}"><br><br>
        </div>
    {% endfor %}
</div>





<!--<img src="images/grass.jpg" width=700px> <br> <br>
<span style="font-size: 20px">Photo by <a href="https://unsplash.com/@p_kuzovkova?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Polina Kuzovkova</a> on <a href="https://unsplash.com/t/nature?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>-->



