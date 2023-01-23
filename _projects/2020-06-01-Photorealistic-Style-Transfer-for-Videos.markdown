---
layout: single
title:  "Photorealistic Style Transfer for Videos"
date:   2020-06-01 00:43:00 -0500
collection: projects
author_profile: true
#toc: true
classes: wide
header:
    teaser: /assets/images/car_road_style.png
---

At the end of 2017, Rahul Iyer, Dishant Mittal and myself embarked on creating a new type of style transfer using neural networks for a University of Waterloo course project ([Stat 946](https://uwaterloo.ca/data-analytics/teaching/deep-learning-2017)). We were inspired by two papers. The first paper is by Ruder et al. [1]. They developed a temporally coherent method of transferring the style of one image to a video. The second paper is by Luan et al. [2], who created a method of doing photorealistic style transfer between images. Photorealistic style is different from artistic style, which was the type of style in the seminal work for style transfer by [Gatys et al.](https://arxiv.org/abs/1508.06576) in 2015. Photorealistic style includes visual information such as time of day, and season. Artistic style is allowed to influence the shape of objects, where as photorealistic style does not included such distortions.

We continued this line of research by creating a photorealistic style transfer algorithm for videos. We created a new loss function that combined the temporal elements of [1] and the photorealistic penalities of [2]. You can read more about the algorithm in our <a href="/assets/files/photorealistic_style_transfer_video_poster.pdf">project poster</a>.

# Examples
In these examples the video on the left is the origin video, the image in the middle is the style photo, and the video on the right is the stylized video.
## Season Transfer
{% include video id="6Q8gu70f2Uk" provider="youtube" %}

## Time Transfer
{% include video id="YAqPm6xy6nw" provider="youtube" %}

Considering we only had a few weeks to develop this project, I think the results are quite decent. The main limitation to our algorithm is the quality of the image segmentation, where labels are assigned identifying the content of the image or frames. Any errors in this step will cause styles to be transferred to the wrong objects, or to only part of an object if it isn't fully identified.

# Citations
[1] Ruder, M., Dosovitskiy, A., Brox, T.: Artistic style transfer for videos. In Rosen-
hahn, B., Andres, B., eds.: Pattern Recognition, Cham, Springer International Pub-
lishing (2016) 26–36

[2] Luan, F., Paris, S., Shechtman, E., Bala, K.: Deep photo style transfer. CoRR,
abs/1703.07511 2 (2017)
