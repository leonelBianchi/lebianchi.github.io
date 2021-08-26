---
layout: post2
title: "Can we transfer learning?"
permalink: /:day/:month/:year/:title
published: true+
tags: "writting"
img: "images/pro_transfer_learning.jpg"

---
<style>
    img {
    width: 100%;
    height: auto;
    }
</style>

<span style="color:black">Summary: I share how machine learning can allow us to transfer learning from one thing to another, and if we could elevate human consciousness in the same way.</span>

<img src="../../../images/can_we_transfer_learning_1.jpg"> <br> <br>

The previous image is the result of a machine learning algorithm in the field of deep learning. Is the combination of two images: content image and style image. The first is to which we want to transfer the style. We transfer the style, and that style configures a learning.

<img src="../../../images/can_we_transfer_learning_2.jpg"> <br> 

The theory behind this concept is currently developed and investigated, and its very promising. Broadly speaking, it employs a pretrained convolutional neural network to transfer styles from an image to another, by minimizing the loss function that counts the differences between them and the generated image. It´s very useful to save computational cost and re-use parameters learnt from other tasks. It´s commonly seen in computer vision and natural language processing applications since they are fields where it requieres large amount of data to get good results,but the tasks we want to solve have many things in common. Why? In computer vision, when we train a neural network, every neuron "learns" something in particular. While some learn to delimit contours, others learn to differentiate colors, to say an example. So, if we want to identify the eyes in a face, its probably that a neural network previously trained to identify a mouse in a face could be very useful. Then, we will get a neural network with several parameters that are intialized with very good values.

However, can we imagine transfering learning between humans? or even between yourself? Is it already a property of the human being? Are we contantly tranfering our learning from the task that we previously learnt?

The concept of transfer learning could be revolutionary in search of the simulation of a human brain. We, as human beings,don't learn everything from scratch. Rather, either someone teaches us or we have a previous learning that allows us to incorporate a new one.

We are very far from simulating a human brain, we are not even close to understanding it, in the most basic thing one thinks. Even so, I think this concept is another variant for its understanding in the coming years.

## Output images

Here I share you how the output image was updated every 20 epochs.

<img src="../../../images/transfer.png"> <br> <br>

I made this model very quickly by taking two images at random. Using images that blend well, results can be much better. For example:


<img src="../../../images/transfer2.png"> <br> <br>
<img src="../../../images/transfer3.png"> <br> <br>


## Resources

The transfer style learning algorithm can be developed in the "Convolutional Neural Networks" course by Andrew Ng. There, you will create this algorithm from scratch. Since it is not correct to share private course code, I encourage you to take the course [here](https://www.coursera.org/learn/convolutional-neural-networks?specialization=deep-learning).




 








