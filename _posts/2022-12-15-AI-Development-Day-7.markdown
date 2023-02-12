---
layout: single
title:  "AI Dev Day 7: Generative Adversarial Network"
date:   2022-12-15- 00:43:00 -0500
categories: AI
collection: AI
classes: wide
header:
    teaser: /assets/images/ai_day7/GAN.png
--- 
I'm interested in Generative Adversarial Networks (GANs) because they demonstrate outstanding generative abilities, producing high-quality synthetic images, videos, music, and computer code. The concept of GANs was first introduced by Ian Goodfellow in 2014 and has since been applied to various domains, including computer vision, audio, and text generation.


<style>
.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  min-width: 80%;
  max-width: 80%;
  width: 50vw;
}
</style>
<img class="center" src="/assets/images/ai_day7/GAN.png" alt="GAN"> 

The core of GANs lies in the simultaneous training of two neural networks: a generator network (G) and a discriminator network (D). The generator network creates synthetic data (I_G), while the discriminator network attempts to distinguish between real (I_R) and generated data (I_G). This dynamic interaction allows the generator network to continuously improve its synthetic data generation ability.


These papers provide a great starting point for understanding the technical details of GANs and how they work.
<a href="https://arxiv.org/pdf/1406.2661.pdf">Generative Adversarial Networks</a>

<a href="https://arxiv.org/pdf/1710.10196.pdf">Progressive Growing of GANs for Improved Quality, Stability, and Variation</a>

<a href="https://arxiv.org/pdf/1812.04948.pdf">StyleGAN: Generative Adversarial Networks with Style-based Generator Architecture for Flexible Image Synthesis</a>
