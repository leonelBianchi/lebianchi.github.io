---
layout: default
title: About
permalink: /about/

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
    font-size:16px; 
    text-decoration: none; 
    color:black;
    font-weight: 600;
    }

    .subtext {
        font-size:19px; 
        text-decoration: none; 
        color:#282828;

    }

    .date {
    font-size:15px; 
    text-decoration: none; 
    color:grey;
    }

</style>


## about

I'm from Buenos Aires, Argentina. I studied civil engineering at <a href="https://www.frba.utn.edu.ar/" target="_blank">Universidad Tecnológica Nacional Facultad Regional Buenos Aires</a>. I participated in different kind of projects related to structural dynamics, computational models, machine learning and statistics. One of my goals is to understand (and help understand) why we do what we do.

<a href="https://github.com/notravarius" Target="_blank">Github</a>
<a href="https://twitter.com/notravarius" Target="_blank">Twitter</a>

## writting

<div>
{% for post in site.posts %}
    <span class="date">{{ post.date | date: "%b %-d, %Y"  }}</span> 
    <a class="text" href="{{ post.url }}">{{ post.title }}<br></a>
{% endfor %}
</div>





