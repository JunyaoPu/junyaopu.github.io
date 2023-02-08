---
layout: single
title:  "Research Day 2: A Cheat Sheet for My Master's Thesis (2)"
date:   2022-06-01- 00:43:00 -0500
categories: Research
collection: Research
classes: wide
header:
    teaser: /assets/images/research_day2/TT_Conv.png
---
My thesis actually utilized a superior TT-Conv layer formulation that employed a brilliant trick to compute multiple filters with multiple images simultaneously, instead of computing each activation map individually. 

# Final Formulation
The concept behind the final formulation in my thesis was to expand the tensor dimensions. For instance, a batch of N RGB images (64x64x3) could be represented by a 4th order tensor.

<style>
.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  min-width: 20%;
  max-width: 20%;
  width: 50vw;
}
</style>
<img class="center" src="/assets/images/research_day2/Image_tensor.png" alt="Image_tensor"> 

This can be expanding to a 5th order tensor like
</style>
<img class="center" src="/assets/images/research_day2/Image_tensor_2.png" alt="Image_tensor_2"> 




# Formulation Details
For more detailed information, please refer to my master's thesis available online on mspace <a href="https://mspace.lib.umanitoba.ca/handle/1993/36582">Design and implementation of a convolutional neural network using tensor-train decomposition</a>

Or the project post on my personal page <a href="https://junyaopu.github.io/projects/">Junyao's Research & Development Page - Projects </a>


