---
layout: post2
title: "Deep learning for damage detection"
permalink: /:day/:month/:year/:title
published: true
tags: "writting"
img: "images/pro_damage.jpg"
description: "Damage detection with deep learning (proof-of-concept)."
---

<style>
    img {
    max-width: 100%;
    height: auto;
    }
</style>

Fields: AI, Civil Engineering, Deep Learning, Machine Learning, Structural Health Monitoring, Technology.

*Summary: Deep learning model that takes dynamic properties of the structure (in this case a vehicular bridge) as input to predict in which area of the structure there is damage (simulated as a decrease in its rigidity). This allows remote and rapid monitoring of structures at low computational cost.*

<img src="../../../images/bridge.jpg"> <span style="margin-left:400px;">


# Abstract

The objetive of this project is to create a software based on a deep neural networks to identify damages in civil and mechanical engineering structures. This software will allow a continuous and fast remote monitoring of structures and buildings at a low economic and computational cost. To have a first aproximation of the model, we will use a pedestrian bridge and see how the model works. The supervised learning algorithm consists in 40,000 cases of damage events to train the model. The input of each event consists of natural frequencies and first mode of vibration of this particular structure with its random damage assigned to a particular element of the bridge.
The output of each event consists in the percentage reduction of the flexural stiffness of the element (this reduction is the hypothesis used as simulation of the damage).

# Part 1: Generation of training data

See the python script [here](https://github.com/leonelBianchi/Deep-Learning-for-Damage-Detection/blob/master/2%20-%20Damage%20Creation.ipynb).

## Properties

The propierties of the bridge to consider are:

* Width (b): 11 m
* Thickness (h): 1.80 m
* Elastic module: 23500000 kN/m2
* Density: 25 kN/m3
* Degrees of freedom: 5
* Length beams 1,6 (L1 = L6): 8 m
* Length beams 2,3,4,5 (L2 = L3 = L4 = L5): 8 m


<br><img src="../../../images/beam.png"> <br> <br>

## Dataset

The dataset are the natural frequencies and the first vibration mode from each damage event. To get this dynamic features we solve the dynamic equation with eigenvectors and eigenvalues using the previous properties for each event, modifying the stifness of each element at random. This entire calculation process is summarized in the following diagram:

<br><img src="../../../images/script_damage.png"> <br> <br>

<!--<br><img src="../../../images/matrix.png" width=1000px> <span style="margin-left:200px;">-->


Doing this, the event´s vector is generated:

vector = [EventID, ω1, ω2, ω3, ω4, ω5, v1, v2, v3, v4, v5, S1, S2, S3, S4, S5, R1, R2, R3, R4, R5]

Being:

* EventID: identification of the event
* ω1: natural frequency for vibration mode 1
* ω2: natural frequency for vibration mode 2
* ω3: natural frequency for vibration mode 3
* ω4: natural frequency for vibration mode 4
* ω5: natural frequency for vibration mode 5
* v1: vertical coordinate of mass 1 in vibration mode 1
* v2: vertical coordinate of mass 2 in vibration mode 1
* v3: vertical coordinate of mass 3 in vibration mode 1
* v4: vertical coordinate of mass 4 in vibration mode 1
* v5: vertical coordinate of mass 5 in vibration mode 1
* R1: stiffness reduction percentage of element 1
* R2: stiffness reduction percentage of element 2
* R3: stiffness reduction percentage of element 3
* R4: stiffness reduction percentage of element 4
* R5: stiffness reduction percentage of element 5

As we are going to generate 40,000 damage events, we will have a matrix of 40,000 vectors like the one above, each of them represents a different damage event.


See the python script [here](https://github.com/leonelBianchi/Deep-Learning-for-Damage-Detection/blob/master/2%20-%20Damage%20Creation.ipynb).


## Input

The inputs are the natural frequencies. The coordinates of each mass for each vibration mode were also calculated but are not taken into account in this particular project. So:

X_train =  [EventID, ω1, ω2, ω3, ω4, ω5]

## Output

The outputs are the stiffness reduction percentage of each element. So:

y_train = [EventID, R1, R2, R3, R4, R5]

# Part 2: Training the deep neural network

See the python script [here](https://github.com/leonelBianchi/Deep-Learning-for-Damage-Detection/blob/master/1%20-%20Neural%20Network%20Rev%201.ipynb).


The DNN is trained with the dataset generated before, wich was saved as csv file with size 40000 x 16. The data manipulation process and model generation can be summarized in:

## Reading the dataset

Using pandas we build a dataframe reading the csv file. 

## Dataset manipulation

We split the dataframe in training and test data (row separation)

* Train on 30000 samples 
* Validate on 10000 samples

Then, we split the dataframe in input and output, as we explained before:
* X_train 
* y_train 
* X_test
* y_test

## Model creation

To create the model we use Keras, an open-source software library that provides a Python interface for artificial neural networks using tensorflow. Using this library we avoid creating backpropagation algorithms and updating weights, which is an equivalent process in all neural network models and whose theoretical foundation is not the objective of this project. However, is truly important to know and understand how each parameter of the network behaves to get better results. In this project, we set the following:

* Input layer: 5 neurons
* Activation: ReLU
* Hidden layers: 80
* Output layer: 6 neurons
* Epochs: 25
* Optimizer: adam
* Loss: mean squared error

## Summary

First, we train the model by introducing the training data and setting the parameter that achieve the best performance.

<br><img src="../../../images/neuralnet1.png">

Then, we use the model to solve real world problems. In this case, the input data is generated from the signals given by the acelerometer located in the bridge. From that signal, it is possible to get input data needed. As output, the model tell us if any part of the beam has an important damage (stifness reduction +20%). 

<br><img src="../../../images/neuralnet2.png" >

# Part 4: Conclusions and results

The model achieved 90% accuracy and had no overfitting. This performance was achieved after testing different combinations of the parameters: function activations, batch size, neurons, layers, etc. However, can still be improved.

Here are some predictions:

<br><img src="../../../images/res2.png">
<br><img src="../../../images/res2.png">
<br><img src="../../../images/res3.png">

Finally, the graph loss vs epochs. We can see that the the convergence is reached and dont overfit the model since training loss is higher than validation loss, and it perfoms well achieving training and testing loss very close.
<br><img src="../../../images/loss.png">

# Additional Resources and Learning

* Dynamics of Structures, by Anil K. Chopra <br>
* Dynamics of structures, by Ray W. Clough and Joseph Penzien <br>
* Deep learning specialization, by Andrew Ng <br>
* Hands-On Machine Learning with Scikit-Learn and TensorFlow, by Aurélien Géron <br>

# Acknowledgement

<span>Cover photo by <a href="https://unsplash.com/@mannyribera13?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Manny Ribera</a> on <a href="https://unsplash.com/?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>
