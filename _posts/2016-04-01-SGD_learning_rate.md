---
layout: post
title: "Learning Rate or descent step in Stochastic Gradient Descent."
author: 
modified:
excerpt: 
tags: [Deep Learning]
---

Why do we use stochastic gradient descent algorithm:

1. Traditional Gradient Descent
cons: (1). Time consuming to compute n gradients in one iteration.
(2). Easy to trap in local optimum.

2.  Stochastic Gradient Descent.

(1). Can avoid local optimum.
(2). Able to solve scalable data.

Tricks in choice of learning rate and updating.
a. Experiment with the learning rate $latex \gamma_0 &s=2$ using a small sample of the training set.

b. Step decay. $latex \gamma_{t+1} = \gamma_t - step &s=2$.

c. 1/t decay. $latex \gamma_t = \frac{\gamma_0}{1+\gamma_0 \lambda t}&s=2$

d. Exponential decay.  $latex \gamma_t = \gamma_0 e^{-kt}&s=2$

e. Momentum.
Description:
When updating the parameter, use the direction of w(t-1) at the last iteration.
Ads:
(1) Smooth out the variations, when using one data to update is too sensitive sometimes.
(2) Speed up when direction are the same.
Usage:
$latex \Delta w(t) = \gamma_t g(t) + \alpha \Delta w(t-1)&s=2$  alpha is usually 0.9

$latex w(t+1) = w(t) - \Delta w(t)&s=2$

f.  Adaptive learning rate. AdaGrad.
Description:
It provides a specific learning rate for each parameter.
Usage:

$latex \gamma_{i,t} =\frac{\gamma_0}{ \sqrt{\sum_{\hat{t} = 1}^t g_{\hat{t},i}^2}} &s=2$

d. RMSprop.
Description:
It keeps running average of its recent gradient magnitudes and divides the next gradient by this average, so that loosely gradient values are normalized.
Usages:
$latex MS(w,t) = 0.9 MS(w,t-1) + 0.1 g_t^2 &s=2$

$latex \Delta w(t) =\frac{ \gamma g_t }{MS(w,t)+u} &s=2$

$latex w(t+1) = w(t) - \Delta w(t) &s=2$

e. Combine RMSprop and momentum trick.

Reference:

1. Bottou, Léon. "Stochastic gradient descent tricks." Neural Networks: Tricks of the Trade. Springer Berlin Heidelberg, 2012. 421-436.

2. http://www.willamette.edu/~gorr/classes/cs449/momrate.html

3. Toronto CSC321 Lecture notes. http://www.cs.toronto.edu/~tijmen/csc321/

4.  Stanford CS231 Lecture notes. http://cs231n.stanford.edu/
