---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Home
permalink: /
---

<style>
    

    .text:hover {
    text-decoration: underline;
    }

    .text {
    text-decoration: underline;
    font-size:17px; 
    text-decoration: none; 
    color:#547DE
    }

    .date {
    font-size:12px; 
    text-decoration: none; 
    color:grey;
    }

    .media-container {
    text-align: left;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
   
    }

    .media {
    flex-basis: 40%;
    flex-grow: 1;
    margin-top: 15px;
    }

    .media img {
    width: 80%;
    height: 80%;
    }
</style>


<div class="media-container">
<br><br>
    {% for post in site.posts %}
        <div class="media">
            <span class="date">{{ post.date | date: "%B %-d, %Y"  }}</span> <br>
            <a class="text" href="{{ post.url }}">{{ post.title }}<br><br></a>
            <img  src="{{ post.img }}"><br>
        </div>
    {% endfor %}
</div>





<!--<img src="images/grass.jpg" width=700px> <br> <br>
<span style="font-size: 20px">Photo by <a href="https://unsplash.com/@p_kuzovkova?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Polina Kuzovkova</a> on <a href="https://unsplash.com/t/nature?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>-->



