---
layout: single
title:  "AI Dev Day 5: Object Detection Model with YOLO Family"
date:   2022-05-04- 00:43:00 -0500
categories: AI
collection: AI
classes: wide
header:
    teaser: /assets/images/ai_day5/YOLO.png
---
# Introduction  
Object detection is a computer vision task that involves finding and locating objects within images or videos. Deep learning is often used to tackle object detection challenges by using neural networks to identify objects and draw bounding boxes around them. Some popular deep learning models for object detection include Faster R-CNN, YOLO, and RetinaNet. YOLO is considered to be the best object detection model for edge devices, such as the NVIDIA Jetson family, due to its simple implementation and fast inference speed.

# YOLO Family

## YOLO V1 (2015)
<a href="https://arxiv.org/pdf/1506.02640.pdf">YOLO V1</a>  was the first model of the YOLO Family and was introduced in 2015 by Joseph Redmon. Unlike the RCNN family, which employs a two-network setup, the YOLO model features a single convolutional neural network architecture. The simplicity of its single network design allows the YOLO model to readily achieve real-time object detection performance even on hardware with limited resources. However, it was not without its limitations and faced challenges in accurately detecting small objects and generating false detections.

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
<img class="center" src="/assets/images/ai_day5/yolov1.png" alt="yolov1"> 
YOLOV1 uses a single neural network architecture to predict both the bounding box coordinates and class probabilities for objects in an image.

## YOLO V2 (2016) 
<a href="https://arxiv.org/pdf/1612.08242.pdf">YOLO V2</a> was introduced in 2016 by Joseph Redmon and built upon the foundation of YOLO v1. It incorporated the use of anchor boxes and skip connections to enhance its performance. The use of anchor boxes significantly simplified the model's predictions by focusing on the ratio of the object's bounding box size rather than its absolute bounding box coordinates.This helped improve accuracy, especially for small objects.

<img class="center" src="/assets/images/ai_day5/anchor_boxes.png" alt="anchor_boxes"> 
Anchor boxes are used in YOLO models to provide a priori information about the size and aspect ratio of objects in an image. 

## YOLO V3 (2018)
<a href="https://arxiv.org/pdf/1804.02767.pdf">The YOLO v3 paper</a> is viewed as a technical report rather than a conventional research paper. It offers a comprehensive explanation of the YOLO v3 architecture.

The paper evaluates the performance of YOLO v3 on several benchmark datasets, including PASCAL VOC and COCO object detection challenges. The evaluation compares YOLO v3 to other object detection models, such as Faster R-CNN and SSD.

<img class="center" src="/assets/images/ai_day5/inf_time.png" alt="inf_time"> 
The diagram show that the YOLO v3 model outperforms other object detection models in terms of inference time with the COCO dataset.

Unfortunately, in the end of the YOLOv3 paper, Joseph Redmon expressed his concerns about the potential misuse of his work in military applications. As a result, he decided to step away from the development of YOLO after the release of YOLOv3.

## YOLO V4 (2020)
<a href="https://arxiv.org/pdf/2004.10934.pdf">The YOLO V4</a> was developed by Alexey Bochkovskiy in 2020, and it is the first version of the YOLO architecture that was not created by Joseph Redmon. The YOLO v4 model includes several new features and optimizations to enhance its accuracy and performance, including Cross mini-Batch Normalization, Bag of freebies and CIoU loss. These improvements allow YOLOv4 to surpass YOLOv3 in terms of accuracy and speed.

## WHY I DO NOT LIKE / TRUST YOLOV5
As a scientific researcher, I prefer that any work is documented and available through a publicly accessible paper. Currently, there is no paper to support YOLOv5, and the author had previously promised to publish a paper regarding the performance improvement of YOLOv5 back to 2020 <a href="https://github.com/ultralytics/yolov5/issues/1333">where is yolov5 paper?</a>, but it has yet to be released.

I appreciate the author who converted the Darknet YOLO version to PyTorch and made it easily accessible to the public. However, there is no accompanying research paper like YOLO v1 - v4.

# Achievements
After reading the post and paper provided in the links

* Having a strong understanding of the evolution of the YOLO family for object detection challenges.

# What's next
Hands-on projects focused on object detection and segmentation challenges.

