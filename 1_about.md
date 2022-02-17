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
    font-size:17px; 
    text-decoration: none; 
    color:#19232d;
    font-weight: 600;
    }

    .subtext {
        font-size:17px; 
        text-decoration: none; 
        color:#19232d;

    }

    .date {
    font-size:17px; 
    text-decoration: none; 
    color:grey;
    }

</style>


## about

I'm from Buenos Aires, Argentina. I studied civil engineering at <a href="https://www.frba.utn.edu.ar/" target="_blank">Universidad Tecnológica Nacional Facultad Regional Buenos Aires</a>. I participated in different kind of projects related to structural dynamics, computational models, machine learning and statistics. Open to collaborate on any kind of project and try to make it happen.

<a href="https://github.com/notravarius" Target="_blank">Github</a>
<a href="https://twitter.com/notravarius" Target="_blank">Twitter</a>

## writting

<div>
{% for post in site.posts %}
    <span class="date">{{ post.date | date: "%b %-d, %Y"  }}</span> 
    <a class="text" href="{{ post.url }}">{{ post.title }}<br></a>
{% endfor %}
</div>

## education

Civil Engineer. Universidad Tecnológica Nacional Facultad Regional Buenos Aires.

## work experience

Semi Senior Data Science Analyst at Nielsen Company. Member of Global Analytics Incubator Team. Working with machine learning stuff and numerical solutiuons.

Internship in structural engineering office. Assistance to senior engineers in the design of steel structures and generation of documentation: Mainly industrial warehouses.

## research experience

Teacher Assistant of course "Numerical Methods" at Universidad Tecnológica Nacional Facultad Regional Buenos Aires.

## publications

Characterization of Pile Failure Dimensions Using Neural Networks (in spanish).  26° Jornadas Argentinas de Ingeniería Estructural, 2021.







