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
    font-size:17px; 
    text-decoration: none; 
    color:#547DE
    }

    .subtext {
        font-size:8px; 
        text-decoration: none; 
        color:black;

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
    justify-content:: center;
   
    }

    .media {
    flex-basis: 40%;
    flex-grow: 1;
    margin-top: 25px;
    margin-bottom:25px;
    }

    .media img {
    width: 80%;
    height: 80%;
    margin-top: auto;
    margin-bottom: auto;
    }
</style>

<h2 style="text-align:center;">posts</h2>

<div class="media-container">
<br><br>
    {% for post in site.posts %}
        <div class="media">
            <img src="{{ post.img }}"><br>
            <span class="date">{{ post.date | date: "%B %-d, %Y"  }}</span> <br>
            <a class="text" href="{{ post.url }}">{{ post.title }}<br></a>
        </div>
    {% endfor %}
</div>





<!--<img src="images/grass.jpg" width=700px> <br> <br>
<span style="font-size: 20px">Photo by <a href="https://unsplash.com/@p_kuzovkova?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Polina Kuzovkova</a> on <a href="https://unsplash.com/t/nature?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>-->



