---
layout: single
title:  "AI Dev Day 4: Segmentation model with Fully Convolutional Networks"
date:   2022-05-04- 00:43:00 -0500
categories: AI
collection: AI
classes: wide
header:
    teaser: /assets/images/ai_day4/Unet.png
---
# Introduction  
Image segmentation is a process in computer vision where an image is partitioned into multiple segments or regions, each of which corresponds to a different object or part of an object. 


## Semantic segmentation

## Instance segmentation

## <a href="https://arxiv.org/pdf/1411.4038.pdf">Fully Convolutional Networks (FCNs)</a>
Fully Convolutional Networks (FCNs) are a type of deep learning architecture for image segmentation tasks. They are called "fully convolutional" because they consist only of convolutional layers, without any fully connected (dense) layers.

FCNs use convolutional layers to perform both feature extraction(downsampling) and upsampling, which allows them to handle input images of different sizes and produce corresponding segmentation maps. The upsampling operation is achieved through transposed convolutions or other upsampling methods, which increase the spatial resolution of the feature maps.

## <a href="https://arxiv.org/pdf/1505.04597.pdf">Unet</a>
