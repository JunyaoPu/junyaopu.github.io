---
layout: single
title:  "AI Dev Day 3: From LeNet (1998) to ResNet (2015)"
date:   2022-05-04- 00:43:00 -0500
categories: AI
collection: AI
classes: wide
header:
    teaser: /assets/images/ai_day3/CNN.png
---
# Introduction  
The history of Artificial Neural Networks (ANN) can be traced back to the 1940s and 1950s, when neuroscientists and computer scientists first started investigating the idea of constructing machine learning models that would resemble the structure and function of the human brain. Today, ANNs are applied in various fields, including image and speech recognition, natural language processing, and autonomous vehicles. The Convolutional Neural Network (CNN) is a subclass of ANNs, primarily utilized for image processing, owing to the strength of the convolutional layer. Notable CNN architectures include LeNet, AlexNet, VGG, and ResNet.

# LeNet (1998)
<a href="http://vision.stanford.edu/cs598_spring07/papers/Lecun98.pdf">LeNet</a>

The LeNet model was introduced by Yann LeCun in 1998 for the recognition of handwritten digits, such as those found in the MNIST dataset.

{% include figure image_path="/assets/images/ai_day3/MNIST.png" alt="MNIST dataset" %}

The MNIST dataset consists of 70,000 images of handwritten digits, ranging from 0 to 9, along with their corresponding labels. It is widely used as a benchmark to evaluate the performance of different image classification algorithms. The images have a size of 28x28 pixels and are grayscale, with pixel values ranging from 0 (black) to 255 (white). Due to its simplicity and accessibility, the MNIST dataset is considered a "hello world" of machine learning, making it a popular starting point for learning and experimenting with image recognition techniques.

Even though LeNet was introduced in 1998 and was a groundbreaking model that had a significant impact on the development of deep learning and computer vision, it is not as widely used today as it once was. The main reason for this is the lack of good datasets for training the model. Additionally, with the advancement of GPUs and distributed computing, the training of much larger models has become possible, which has further increased their capacity and performance.

# AlexNet (2012)
<a href="https://proceedings.neurips.cc/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf">AlexNet</a>

# VGG (2015)
<a href="https://arxiv.org/pdf/1409.1556.pdf">VGG</a>

# ResNet (2015)
<a href="https://arxiv.org/pdf/1512.03385.pdf">ResNet</a>

