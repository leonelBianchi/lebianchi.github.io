---
layout: post2
title: "Solving implicit equation through solution space regression"
permalink: /:day/:month/:year/:title
published: true+
tags: "writting"
img: "images/pro_transfer_learning.jpg"
description: "It was needed to solve an equation to get a useful metric, but it was also necessary that the solution be expressed in a very simple way. It turns out that to solve it, you need to use the LambertW function. Since we needed a simple formula as a solution, we came up with an indirect way to solve it."

---
<style>
    .center {
  display: block;
  margin-left: auto;
  margin-right: auto;
}



  .img_general {
width: 100%;
height: auto;
}

</style>

How would you solve the following equation? <br> <br>

<img src="../../../images/equation_1.png" class="center"> <br> 

Ok, we can solve it by approximation using numerical methods (Newton could be a possibility, for example). We put the equation as "something" equals zero, and using optimization techniques or numerical methods we can minimize it, setting zero as target value. That could be a possibility but it's not what we are looking for. What we would like to have is simple formula that returns X given k and t. I mean X = F(k,t)

So I come up with the following. If we call: <br> <br>

<img src="../../../images/equation_2.png" class="center"> <br> 

Then we can get: <br>

<img src="../../../images/equation_3.png" class="center"> <br> 

But it has no solution either. One way I thought is to derive both sides of the equation, but since the orginal equation domain is different from its derivative, the solution for the derivative is not a solution for its primitive. So, what can we do now? 

There is a solution space out there for that equation and to know how it looks we can optimize it for a given K value and get its corresponding Z value. If we do that for ~ 40,000 k values, we get 40,000 data points. A polinomyal regression for that group of data points can be understood as the solution space of the equation. Take a look at the python code:

<script src="https://gist.github.com/notravarius/e8e81bf8c0e7c25aa72ccb8f0ccc1822.js"></script>

[source code](https://github.com/notravarius/implicit-equation-solution) 


<br>

With that code, you can generate a 4th degree polynomial regression for that group of data points. I used the logarithm of the Z values, because I could figure out that the solution space follows a logarithm trend, but we can adopt whatever function that better fits the data. Here I show different regressions:

<br>

<img src="../../../images/equation_4.png" class="img_general"> <br> 

<img src="../../../images/equation_5.png" class="img_general"> <br> 

You can see that a 2nd degree regression is very accurate. I finally adopted a 4th degree because when evaluating, it returned much better results. A 5th degree regression was very similar so I was not necesarry to continue increasing the degrees. That aside, now we have simple formula to get Z given K, which is: <br> 

<img src="../../../images/equation_6.png" class="center"> <br> 

Replacing in the equation before, we get that X depends only on K and t <br> 

<img src="../../../images/equation_7.png" class="center"> <br> 

Where:  
  A = -0.0116787739<br> 
  B = 0.0835902446 <br> 
  C = -0.317746063<br> 
  D = 1.99637801<br> 
  E = 0.000209194991<br> 

## Comments

Probably very obvious, but it's important to remember that we don't have to worry about any statistical concept here such as overfitting, confidence or whatever that comes to your mind when looking at the "overfitted" regression showed above. Why? Because we are trying to find the solution space for a given equation, which has an unknown function that describes it. We are not estimating anything or dealing with any kind of prediction from data. That equation descibres a concrete phenomenon that always happen. So, to get the polynomial that better fits the data, I adopted a 4th degree polynomial, which was the one that returned better results. 

This methodology seems to be very obvious but we sometimes forget that brute force can sometimes play an important role to solve problems we are not used to solve in that way. However, if you are able to find a better way solve it, do not hesitate to contact me and share your alternative!


