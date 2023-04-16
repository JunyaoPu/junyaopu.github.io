---
layout: single
title:  "AI Dev Day 9: Object Detection Model with R-CNN Family"
date:   2022-12-30- 00:43:00 -0500
categories: AI
collection: AI
classes: wide
header:
    teaser: /assets/images/ai_day9/RCNN.png
--- 

The R-CNN family includes several variations of the original R-CNN model, such as Fast R-CNN and Faster R-CNN. These models improve the speed and accuracy of object detection by optimizing the region proposal step and incorporating additional components for object tracking.

<a href="https://arxiv.org/pdf/1311.2524.pdf">R-CNN</a>(Region-based Convolutional Neural Networks) is a computer vision technique used for object detection in images.The R-CNN model first generates a set of region proposals, which are potential areas where an object might be located. It then extracts features from each region using a convolutional neural network (CNN). These features are then fed into a classifier that predicts the object category and a bounding box that indicates the object's location in the image.
<img class="center" src="/assets/images/ai_day9/RCNN.png" alt="R-CNN"> 

<a href="https://arxiv.org/pdf/1504.08083.pdf">Fast R-CNN</a> is an improvement over the original R-CNN model in terms of both speed and accuracy.The Fast R-CNN model uses a single convolutional neural network to extract features from the entire image, rather than processing each region proposal separately, as in the original R-CNN model. This makes the model faster and more efficient.

<a href="https://arxiv.org/pdf/1506.01497.pdf">Faster R-CNN</a> replaces the selective search algorithm used for region proposal in Fast R-CNN with a region proposal network (RPN) that is integrated into the convolutional neural network (CNN) architecture. The RPN generates region proposals based on the features extracted from the CNN, reducing the computational cost and improving the speed of the model.
