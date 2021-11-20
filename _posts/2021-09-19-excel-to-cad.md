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



  img {
    width: 100%;
    height: auto;
}

</style>

La sincronizacion Excel-AutoCAD no esta muy popularizada pero es muy sencilla. Entiendo que quizas a veces no conviene ya que cada proyecto es distinto y no tendria sentido armar algo que hay que mantener y actualizar por cada proyecto que se haga. Pero en casos donde siempre hacemos lo mismo, viene bien. Por ejemplo, en este caso se trata de bridas de union para estructuras metalicas de naves industriales. Siempre se usan los mismos tipos de bridas y depende el proyecto, se adoptan distintas dimensiones, distintos bulones y distintos tamaños. Todos ellos se calculan en una planilla de Excel. 

La imágen de abajo muestra el formato general de brida que comunmente se usaba. 

<img src="../../../images/brida_1.jpg" class="center"> <br> 

Siguiendo el nombre de las distancias mostradas, se calculan en una planilla de Excel de tal forma que verifiquen todas las solicitaciones (corte de bulones, flexión de ala y alma, tracción de bulones, soldadura brida-alma, soldadura brida-ala, entre otras.)

<img src="../../../images/brida_2.jpg" class="center"> <br> 

Lo que hacemos basicamente es agregar un botón a la planilla que al clickearlo abra AutoCAD con los gráficos de todas las bridas calculadas, cada una con sus dimensiones y bulones adoptados.

Los puntos mas importantes a tener en cuenta para realizar los gráficos son:
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

A modo de ejemplo, así tendrias que hacer para graficar la brida (un rectángulo dado por las coordenadas de sus puntos). En síntesis, primero definís las variables con su tipo de dato. Luego asignas un valor a cada una de ellas (la celda que contiene su valor correspondiente en la hoja de cálculo). Definís la posición (x,y) de cada punto referenciando a las distancias y por último aplicas el objeto de CAD (ya incorporado en Visual Basic) para dibujar la polilínea. 

<script src="https://gist.github.com/notravarius/e457104a0687352b171eace762411a01.js"></script>

Esto mismo se aplica para dibujar los bulones y texto. Tambien dibujar cada cosa en su capa: soldadura en su capa, brida en su capa y texto en su capa. El código completo puede verse [aca](https://github.com/notravarius/excel2cad).

## Resultado

Agregando el codigo al backend de Excel y vincularlo a un boton, si este es ejecutado, se abre AutoCAD con todos los gráficos:

<img src="../../../images/brida_3.jpg" class="center"> <br> 

Es decir, se grafican las bridas que hayan sido completadas en la planillas cada una con sus dimensiones, formato, nombre y bulones correspondientes. Cabe aclarar que para lograr eso, se hace un loop a través de todas las filas de la tabla. Aquellas que no se encuentren vacías se grafican. Esto puede verse en el script completo.

## Comentarios

En ingeniería no esta muy usado, quizas porque nadie se puso hacerlo y los propios ingenieros no estan muy en el tema. Sí se usan en software de cálculo que permiten exportar los detalles facilmente, pero nada que sea personalizado por el usuario a su propio interes. Creo que puede ser una buena oportunidad para crear algo copado que facilite la vida a todos los estudios de ingenieria para automatizar sus trabajos facilmente. Si lees esto y te interesaría armarlo, avisame!

