---
layout: default
title: About
permalink: /about/

---

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





