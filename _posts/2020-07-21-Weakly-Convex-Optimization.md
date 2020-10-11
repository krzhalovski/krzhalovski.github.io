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

The figure illustrates how the proximal operator works: the thick black line indicates the boundary of the domain of the convex function f. Applying the operator to the blue points moves them to the corresponding red points. The three points in the domain of the function stay in the domain and move towards the minimum of the function, while the other two move to the boundary of the domain and towards the minimum of the function. The parameter λ controls the extent to which the proximal operator maps points towards the minimum of f.

<figure class="centerImage">
    <a href="/images/Weak_Convexity/Proximal.PNG"><img src="/images/Weak_Convexity/Proximal.PNG"></a>
</figure>

## Convergence Rates

## Stochastic Optimization

## EMA methods

## Examples

## Experiments

## Conclusion
