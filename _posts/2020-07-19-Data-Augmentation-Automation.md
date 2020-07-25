---
title: "Data Augmentation Automation"
date: 2020-07-19
tags: ["Data Augmentation"]
excerpt: "Augmentation Automation"
mathjax: true
toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
toc_sticky: true
---

## Introduction

During the last few years, Deep Learning models have made incredible progress in classification problems thanks to the advances in deep network architectures, computational power and access to huge amounts of big data where they excel.

One of the most prominently used techiques for improving state of the are Deep Image Classifiers is Data augmentation. In this paper, we will test different ways of applying this technique and compare the results obtained to provide empirical evidence that these methods indeed improve the classification power of Deep Learning models.

Our experiments will show that using different kinds of data augmentation improves the generalizing capabilities of the models on both a subset of the Fashion MNIST dataset\cite{xiao2017} and of the full dataset. We will focus on obtaining good results where most of the classic models fail, namely on the differentiation of two specific classes of the MNIST dataset (shirt, tshirt/top).

Furthermore, we propose a way of speeding up the fine-tuning of augmentation parameters by using transfer learning by training a model using the original data and incrementally adding different augmentations to obtain the most robust model that generalizes the best. The paper and supplement code is available at [link]

## Dataset

In this paper we will be using data augmentation techniques to show that they indeed improve the accuracy of a CNN model on the [Fashion-MNIST](https://github.com/zalandoresearch/fashion-mnist) dataset. Fashion-MNIST is a dataset of article images—consisting of a training set of 60,000 examples and a test set of 10,000 examples. Each example is a 28x28 grayscale image, associated with a label from 10 classes. The dataset has no null values and is ready-usable. Each pixel has a value from 0 to 255 representing the color of the pixel. The only preprocessing that was needed was standardizing the values which we do with min-max feature scaling: $$\frac{X-X_{min}}{X_{max}-X_{min}}$$

Analyzing the dataset, we concluded that most of the classic ML models (SVMs, Random Forests, KNNs), as well as simple DNNs achieve an accuracy of 85\%-90\% and in all of them the main struggle was differentiating between two out of the ten classes, namely the shirt and t-shirt classes. In order to better evaluate the effects of the data augmentation we used two partitions of the dataset: one containing only samples of the two previously mentioned classes and one containing all of them. By doing this, we were able to speed up the processes of validating different augmentation techniques and combinations of the same, and test whether when applied to the whole dataset they obtained better results, i.e. whether the same augmentations could be used on different images to achieve a higher accuracy.

<table style="width:100%">
  <tr>
    <th>Classifier</th>
    <th>Accuracy</th> 
  </tr>
  <tr>
    <td>KNN</td>
    <td>0.840</td>
  </tr>
  <tr>
    <td>SVC</td>
    <td>0.861</td>
  </tr>
  <tr>
    <td>RF</td>
    <td>0.856</td>
  </tr>
  <tr>
    <td>CNN</td>
    <td>0.913</td>
  </tr>
</table>
