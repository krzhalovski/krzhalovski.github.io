---
title: "Weakly Convex Optimization"
date: 2020-07-21
tags: ["Optimization"]
excerpt: "Data Analysis"
mathjax: true
toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
toc_sticky: true
---

## Introduction
This post will explain in brief details the concept of weak convexity and the methods used to solve some important weakly convex problems such as Robust Matrix Sensing and Robust Phase Retrieval.

Many of the descriptions here will be very high-level and intended for non-technical readers. For additional explanation and in-depth mathematical analysis of the algorithms and proofs for their properties please visit this [link](https://github.com/krzhalovski/Weakly-Convex-Optimization/blob/main/Weak_Convexity.pdf)

## Weak Convexity
Firstly, a general notion and description of weak convexity is needed. In order to stay in the realm of sanity, we can view a weakly convex function as a function that can be made covex by adding a second, parameterized term to it. The key idea behind adding such a term is find a way to measure the progress of an algorithm by tracking a surrogate optimality measure that is easier to work with.

### Moreau Envelope
The Moreau Envelope is the surrogate measure that will enable us to exactly that. When we apply the moreau envelope to a weakly convex function, it gives us a continiously differentiable function that approximates the original function from below and more importantly, with proof provided in the paper, we can see that the problem of minimizing the original function is equivalent to minimizing the envelope which is always a smooth optimization problem. 

## Proximal Operators and Algorithms
An important concept that is needed to understand the algorithms discussed in the paper is the proximal operator.

The figure illustrates how the proximal operator works: the thick black line indicates the boundary of the domain of the convex function $f$. Applying the operator to the blue points moves them to the corresponding red points. The three points in the domain of the function stay in the domain and move towards the minimum of the function, while the other two move to the boundary of the domain and towards the minimum of the function. The parameter $\lambda$ controls the extent to which the proximal operator maps points towards the minimum of $f$.

<figure class="centerImage">
    <a href="/images/Weak_Convexity/Proximal.PNG"><img src="/images/Weak_Convexity/Proximal.PNG"></a>
</figure>

A proximal algorithm solves convex optimization problems using the proximal operators of the objective terms. For example, the proximal minimization algorithm, minimizes a convex function $f$ by repeatedly applying $prox_f$
to some initial point.

## Incremental Algorithms and Convergence Rates
Incremental algorithms are suited for solving the finite sum optimization problem:

$$\min_{x \in \mathbb{R}^n}f(x)=\sum_{i=1}^m f_i(x)$$

So the question is what are incremental algorithms? In short, if you know stochastic algorithms, then you will also know how incremental algorithms work. The only difference between the two, is how they sample the given data: stochastic algorithms randomly choose a function from the set, whereas the incremental algorithms choose them in an iterative fashion, starting from the first component function and ending with the last one in each epoch.

Although not intuitive at first glance why would these different sampling techniques make a difference, careful examination shows us that stochastic algorithms might suffer from selection bias, or simply oversampling and undersampling some composite functions with respect to the rest. Ultimatelly, they fulfill the same goal but incremental algorithms tend to converge faster because of this advantage.

## EMA methods

## Examples

## Experiments

## Conclusion
