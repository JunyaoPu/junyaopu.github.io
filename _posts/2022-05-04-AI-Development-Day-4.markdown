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


## Semantic segmentation and instance segmentation
Both Semantic and Instance Segmentation involve predicting a segmentation mask on the original input image. The goal of Semantic Segmentation is to assign a semantic label, such as "person", "car", "dog", "cat", etc., to every pixel in the segmentation mask.

Instance Segmentation is a variation of Semantic Segmentation, as it not only classifies each pixel into its class, but also distinguishes between different instances of the same object class.

# Segmentation model with Unet

## <a href="https://arxiv.org/pdf/1411.4038.pdf">Fully Convolutional Networks (FCNs)</a>
Fully Convolutional Networks (FCNs) are a deep learning architecture. They are referred to as "fully convolutional" because they are composed entirely of convolutional layers, with no fully connected layers.

FCNs utilize convolutional layers to carry out both feature extraction (downsampling) and upsampling, allowing them to process input images of varying sizes and generate the corresponding segmentation maps. Upsampling is achieved through the use of transposed convolutions or other upsampling techniques, which increase the spatial resolution of the feature maps.

## <a href="https://arxiv.org/pdf/1505.04597.pdf">Unet</a>
U-Net is a type of fully convolutional network (FCN) architecture used primarily in the field of medical image segmentation. It was first introduced in 2015 by Olaf Ronneberger.

U-Net consists of a contracting path (downsampling) followed by an expansive path (upsampling) that leads to the final segmentation mask.
