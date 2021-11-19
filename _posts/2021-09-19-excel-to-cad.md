---
layout: post2
title: "Excel a AutoCAD: Generacion Automática de Dibujos en AutoCAD Usando Valores de Planillas de Excel"
permalink: /:day/:month/:year/:title
published: true+
tags: "writting"
img: "images/pro_transfer_learning.jpg"
description: "Implementacion de macro para generar planos en AutoCAD tomando valores calculados en planilla de Excel (dimensiones, nombres, leyendas, espesores, cargas, unidades y magnitudes, formato, condicionales de forma, colores, capas y más.)"

---
<style>
    .center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  max-width: fit-content;
}



  .img_general {
width: 100%;
height: auto;
}

</style>

La sincronizacion Excel-AutoCAD no esta muy popularizada pero es muy sencilla. Entiendo que quizas a veces no conviene ya que cada proyecto es distinto y no tendria sentido armar algo que hay que mantener y actualizar por cada proyecto que se haga. Pero en casos donde siempre hacemos lo mismo, viene bien. Por ejemplo, en este caso se trata de bridas de union para estructuras metalicas de naves industriales. Siempre se usan los mismos tipos de bridas y depende el proyecto, se adoptan distintas dimensiones, distintos bulones y distintos tamaños. Todos ellos se calculan en una planilla de excel. 

La imagen de abajo muestra el formato general de brida que comunmente se usaba. 

<img src="../../../images/brida_1.jpg" class="center"> <br> 

Siguiendo el nombre de las distancias mostradas, se calculan en una planilla de excel de tal forma que verifiquen todas las solicitaciones (corte de bulones, flexión de ala y alma, tracción de bulones, soldadura brida-alma, soldadura brida-ala, entre otras.)

<img src="../../../images/brida_2.jpg" class="center"> <br> 

Lo que hacemos basicamente, es agregar un boton a la planillas que al clickearlo abra AutoCAD con los dibujos de todas las bridas calculadas, cada una con sus dimensiones y bulones adoptados.

Los puntos mas importantes a tener en cuenta para realizar los dibujos son:
* Ancho y alto de brida
* Espesor de ala y alma
* Diametro de bulones
* Cantidad de filas y columnas de bulones
* Distancia entre bulones
* Distancia entre bulones y borde de brida
* Espesor de cordon de soldadura en ala y alma
* Necesidad de agregar rigidizador o no
* Espesor de rigidizador

Con toda esa información, que se encuentra en la planillas, estamos en condiciones de automatizar el trazado de la polilínea. 

## Código 

A modo de ejemplo, asi tendrias que hacer para dibujar la brida (un rectangulo dado por las coordenadas de sus puntos). En sintesis, primero definis las variables con el tipo de dato que van a hacer. Luego asignas un valor a cada una de ellas (la celda que contiene su valor correspondiente en la hoja de cálculo). Definis la posicion (x,y) de cada punto referenciando a las distancias y por ultimo aplicas el objeto de cad para dibujar la polilinea. 

<script src="https://gist.github.com/notravarius/e457104a0687352b171eace762411a01.js"></script>

Esto mismo se aplica para dibujar los bulones y texto. Tambien dibujar cada cosa en su capa: soldadura en su capa, brida en su capa y texto en su capa. El codigo completo puede verse [aca](https://github.com/notravarius/excel2cad).

## Resultado

Agregando el codigo a excel junto a un boton, al ejecturalo veremos lo siguiente:

<img src="../../../images/brida_3.jpg" class="center"> <br> 

Es decir, se grafican las bridas que hayan sido completadas en la planillas cada una con sus dimensiones, formato, nombre y bulones correspondientes.
