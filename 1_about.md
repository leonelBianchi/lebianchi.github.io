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


## <u>about</u>

I'm from Buenos Aires, Argentina. I studied civil engineering at <a href="https://www.frba.utn.edu.ar/" target="_blank">Universidad Tecnológica Nacional Facultad Regional Buenos Aires</a>. I participated in different kind of projects related to structural dynamics, computational models, machine learning and statistics. Open to collaborate on any kind of project and try to make it happen.

<a href="https://github.com/notravarius" Target="_blank">Github</a>
<a href="https://twitter.com/notravarius" Target="_blank">Twitter</a>

## <u>writting</u>

<div>
{% for post in site.posts %}
    <span class="date">{{ post.date | date: "%b %-d, %Y"  }}</span> 
    <a class="text" href="{{ post.url }}">{{ post.title }}<br></a>
{% endfor %}
</div>

## <u>education </u>

* Civil Engineer. Universidad Tecnológica Nacional Facultad Regional Buenos Aires. 2016-2021.

## <u>work experience</u>

* Semi Senior Data Science Analyst at Nielsen Company. Member of Global Analytics Incubator Team. Working with machine learning stuff and numerical solutiuons. 2021.

* Internship in structural engineering office. Assistance to senior engineers in the design of steel structures and generation of documentation: Mainly industrial warehouses. 2020

* Math professor. Linear Algebra and Mathematical Analysis for engineers and economists. 2017-2019

## <u>research and academic experience</u>

* Member of the research group GADE (Group of Analysis
and Design of Structures). Universidad Tecnológica Nacional, Facultad Regional
Buenos Aires.

* Research Project: "Adaptive Computational Analysis in Structural Mechanics".
Undergraduate researcher. Finite element method. Simulation of physical
processes. Visualization of model outputs on the mechanical deformation of
complex microstructures.

* Research Project: "Numerical Methods Applied to Structural Dynamics".
Undergraduate Researcher. Vibrations. First approach to structural health
monitoring. Machine learning proof-of-concept for structural damage.

* Teacher Assistant of course "Numerical Methods" at Universidad Tecnológica Nacional Facultad Regional Buenos Aires.

## <u>publications</u>

* <a href="https://jornadasaie.org.ar/jornadas-aie-anteriores/2021/26jaie-trabajos/101_TRABAJO.pdf" target="_blank">"Characterization of Pile Failure Dimensions Using Neural Networks" (in spanish).</a>  26° Jornadas Argentinas de Ingeniería Estructural, 2021. 







