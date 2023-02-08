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
The concept behind the final formulation in my thesis was to expand the tensor dimensions. For instance, a batch of N images (I_1 x I_2 x C) could be represented by a 4th order tensor.

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

this can be expanding to a 5th order tensor like
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
<img class="center" src="/assets/images/research_day2/Image_tensor_2.png" alt="Image_tensor_2"> 

The TT representation of this 5th order tensor (images) can be show as
<style>
.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  min-width: 70%;
  max-width: 70%;
  width: 50vw;
}
</style>
<img class="center" src="/assets/images/research_day2/image_tt.png" alt="image_tt"> 


On the other hand, a batch of M filters (J_1 x J_2 x C) could be represented by a 4th order tensor as well.
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
<img class="center" src="/assets/images/research_day2/Filter_tensor.png" alt="Filter_tensor"> 

this 4th order tensor will be expanded to a be 5th order tensor as well
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
<img class="center" src="/assets/images/research_day2/Filter_tensor_2.png" alt="Filter_tensor_2"> 

The TT representation of this 5th order tensor (filters) can be show as
<style>
.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  min-width: 10%;
  max-width: 10%;
  width: 50vw;
}
</style>
<img class="center" src="/assets/images/research_day2/filter_tt.png" alt="filter_tt"> 


# Formulation Details
For more detailed information, please refer to my master's thesis available online on mspace <a href="https://mspace.lib.umanitoba.ca/handle/1993/36582">Design and implementation of a convolutional neural network using tensor-train decomposition</a>

Or the project post on my personal page <a href="https://junyaopu.github.io/projects/">Junyao's Research & Development Page - Projects </a>


