---
layout: single
title:  "AI Dev Day 3: CNNs from LeNet (1998) to ResNet (2015)"
date:   2022-05-04- 00:43:00 -0500
categories: AI
collection: AI
classes: wide
header:
    teaser: /assets/images/ai_day3/CNN.png
---
# Introduction  
The history of Artificial Neural Networks (ANN) can be traced back to the 1940s and 1950s, when neuroscientists and computer scientists first started investigating the idea of constructing machine learning models that would resemble the structure and function of the human brain. Today, ANNs are applied in various fields, including image and speech recognition, natural language processing, and autonomous vehicles. The Convolutional Neural Network (CNN) is a subclass of ANNs, primarily utilized for image processing, owing to the strength of the convolutional layer. Notable CNN architectures include LeNet, AlexNet, VGG, and ResNet.

# <a href="http://vision.stanford.edu/cs598_spring07/papers/Lecun98.pdf">LeNet</a> (1998)

The LeNet model, introduced by Yann LeCun in 1998, was designed for the recognition of handwritten digits, such as those found in the MNIST dataset. The MNIST dataset contains 70,000 images of handwritten digits, ranging from 0 to 9, with their corresponding labels. It is widely used as a benchmark for evaluating the performance of different image classification algorithms. The images are 28x28 pixels in size and are grayscale, with pixel values ranging from 0 (black) to 255 (white).

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
<img class="center" src="/assets/images/ai_day3/MNIST.png" alt="MNIST dataset."> 

Due to its simplicity and accessibility, the MNIST dataset is considered a "hello world" of machine learning and is a popular starting point for learning and experimenting with image recognition techniques.

Although LeNet was a groundbreaking model that had a significant impact on the development of deep learning and computer vision, it is not as widely used today due to the lack of good datasets for training the model and the advancement of GPUs and distributed computing, which have enabled the training of larger models with increased capacity and performance.

# AlexNet (2012)
<a href="https://proceedings.neurips.cc/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf">AlexNet</a>

# VGG (2015)
<a href="https://arxiv.org/pdf/1409.1556.pdf">VGG</a>

# ResNet (2015)
<a href="https://arxiv.org/pdf/1512.03385.pdf">ResNet</a>

