---
layout: post2
title: "Access Granted to GPT-3: Interaction with the API."
permalink: /:day/:month/:year/:title
published: true+
tags: "writting"
img: "images/gpt_exponential.jpg"
description: "After 6 months of requesting access to use the OpenAI API of the most robust natural language processing model to date called GPT-3, they gave me my keys. Here I am going to share some interactions that I had with the model that made me a little nervous."
---
<style>

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

    .date {
    font-size:15px; 
    text-decoration: none; 
    color:grey;
    }

</style>


I had access to the GPT-3 API. Here I show some examples of how it works. Each sentence written here below is an input that I give to the model. After clicking on it, you will be able to see the output of the model, without any modification.

<div>
    {% for post in site._other %}
        <span class="date">{{ post.date | date: "%B %-d, %Y"  }}</span> <br>
        <a class="text" href="{{ post.url }}">{{ post.title }}</a><br>
        <br>
    {% endfor %}
</div>




 








