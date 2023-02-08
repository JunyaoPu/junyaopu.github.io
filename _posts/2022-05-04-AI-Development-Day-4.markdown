---
layout: single
title:  "AI Dev Day 4: Segmentation Model with Fully Convolutional Networks"
date:   2022-05-04- 00:43:00 -0500
categories: AI
collection: AI
classes: wide
header:
    teaser: /assets/images/ai_day4/FCNs.png
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
U-Net is a type of fully convolutional network (FCN) architecture used primarily in the field of medical image segmentation. It was first introduced in 2015 by Olaf Ronneberger. U-Net is called so because of its U-shaped architecture, where the model has a symmetrical structure with downsampling and upsampling forming the "U" shape.

<style>
.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  min-width: 30%;
  max-width: 50%;
  width: 50vw;
}
</style>
<img class="center" src="/assets/images/ai_day4/Unet.png" alt="Unet"> 

The U-Net architecture consists of two parts: a encoding path for downsampling and an decoding path for upsampling, which eventually produce the final segmentation mask.

The downsampling path of the U-Net uses standard convolutional layers to extract features from the input image, utilizing filters of various sizes. On the other hand, the upsampling path employs transposed convolutional layers to increase the spatial resolution. These layers utilize a set of filters that perform the reverse operation of the standard convolutional layer.

Here is a demonstration of a 3x3 input image with a 2x2 filter in the standard convolutional layers. This is similar to the downsampling operation in the U-Net architecture, but with the use of multiple filters.
<style>
.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  min-width: 30%;
  max-width: 50%;
  width: 50vw;
}
</style>
<img class="center" src="/assets/images/ai_day4/Conv_layer.png" alt="Conv_layer"> 

The upsampling reverses the operation, but tries to train the transposed convolutional layers' filters to fit the dataset using the image features extracted from the downsampling.

