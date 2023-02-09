---
layout: single
title:  "AI Dev Day 3: CNNs from LeNet to ResNet"
date:   2022-05-04- 00:43:00 -0500
categories: AI
collection: AI
classes: wide
header:
    teaser: /assets/images/ai_day3/CNN.png
---
# Introduction  
The history of Artificial Neural Networks (ANN) can be traced back to the 1940s and 1950s, when neuroscientists and computer scientists first started investigating the idea of constructing machine learning models that would resemble the structure and function of the human brain. Today, ANNs are applied in various fields, including image and speech recognition, natural language processing, and autonomous vehicles. The Convolutional Neural Network (CNN) is a subclass of ANNs, primarily utilized for image processing, owing to the strength of the convolutional layer. Notable CNN architectures include LeNet, AlexNet, VGG, and ResNet.

# The LeNet (1998)
<a href="http://vision.stanford.edu/cs598_spring07/papers/Lecun98.pdf">The LeNet model</a>, introduced by Yann LeCun in 1998, was designed for the recognition of handwritten digits, such as those found in the MNIST dataset. The MNIST dataset contains 70,000 images of handwritten digits, ranging from 0 to 9, with their corresponding labels. It is widely used as a benchmark for evaluating the performance of different image classification algorithms. The images are 28x28 pixels in size and are grayscale, with pixel values ranging from 0 (black) to 255 (white).

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

# The AlexNet (2012)

<a href="https://proceedings.neurips.cc/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf">The AlexNet</a> was designed by Alex Krizhevsky in the year 2012 and was one of the first deep learning models to attain remarkable results on the ImageNet challenge, with a top error rate of approximately 15.3%. The second-best model had an error rate of around 26%. The architecture of AlexNet comprises of 8 layers, with 4 of them being convolutional layers and the remaining 4 being fully connected layers.

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
<img class="center" src="/assets/images/ai_day3/AlexNet.png" alt="AlexNet"> 

The success of AlexNet was achieved through the use of large-scale training data from ImageNet and the high performance computational resources provided by GPU acceleration. This success paved the way for further research and development in deep learning and opened the doors to practical AI in computer vision.

Although AlexNet was a significant achievement in deep learning and computer vision, it had some limitations, including its simple architecture with only convolutional and fully connected layers and its tendency to overfit due to its large number of parameters across the 8 layers. To address these limitations, the VGG network was developed using smaller filters and a deeper network architecture, which helped to overcome the overfitting issue seen in AlexNet.

# The VGG (2014)

<a href="https://arxiv.org/pdf/1409.1556.pdf">The VGG network</a> was introduced in 2014 by researchers at the University of Oxford and is well-known for its outstanding performance in image classification. The VGG-16 model won the ImageNet recognition challenge in 2014 with a top 5 error rate of 7.3%. The VGG architecture features multiple stacks of convolutional layers followed by one or more fully connected layers, which is similar to AlexNet, but deeper and has fewer parameters. Additionally, VGG uses small filters (3x3) and a large number of convolutional layers, resulting in increased depth and improved feature representation. The architecture of VGG-16 is given below.

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
<img class="center" src="/assets/images/ai_day3/VGG_16.png" alt="VGG-16"> 

The use of small filters and a larger number of convolutional layers in the VGG network results in a deeper architecture compared to AlexNet. This allows it to capture more complex features in images, leading to improved accuracy in image classification tasks. Additionally, VGG has fewer parameters than AlexNet, making it easier to train and less susceptible to overfitting.

So, it can be concluded that deeper networks tend to have better performance. However, why not make the VGG network deeper? Although the VGG network can be made deeper, it suffers from the vanishing gradient problem. The vanishing gradient problem occurs when the gradients of the parameters during backpropagation become very small, making it difficult for the network to train. To overcome this issue, researchers from Microsoft Research employed various techniques, such as skip connections and batch normalization, in the design of ResNet, enabling the network to have a depth of up to 152 layers, which is 8 times deeper than VGG nets, while still maintaining lower complexity.

# The ResNet (2015)

<a href="https://arxiv.org/pdf/1512.03385.pdf">The ResNet</a>, introduced in 2015 by researchers at Microsoft Research, uses residual connections to address the vanishing gradients problem and enable the network to learn residual functions. This allows ResNet to have much deeper architectures, such as ResNet-152, bit without suffering from the vanishing gradients problem. The residual connections also make it easier to train ResNet on large datasets, leading to improved performance in image classification tasks. The ResNet-152 model won the ImageNet recognition challenge in 2015 with a top 5 error rate of 3.57%. Below is an example of a residual block with bottlenecking for .

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
<img class="center" src="/assets/images/ai_day3/Residual_block.png" alt="Residual block"> 

While advanced CNNs like VGG and ResNet have achieved excellent performance in image classification problems, they can also be used in other areas of computer vision, such as segmentation and object detection. For example, Unet, DeepLab, Faster-RCNN, and YOLO use VGG or ResNet as the backbone to extract features from images or videos.

# Achievements
After reading the post and paper provided in the links

* Have a good understanding of how the CNNs evolve and how we improved the CNNs performance on image classification problem.

# What's next
We are able to deal with image classification problem with CNNs. Let's dive into segmentation problem for computer vision!

