---
layout: single
title:  "Research Day 1: A Cheat Sheet for My Master's Thesis"
date:   2022-06-01- 00:43:00 -0500
categories: Research
collection: Research
classes: wide
header:
    teaser: /assets/images/research_day1/TT_Conv.png
---
# Initial Formulation
This is made with LaTeX due to its excellent equation formatting.
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
<img class="center" src="/assets/images/research_day1/From_Correlation_To_Convolutional_layer_31024_1.png" alt="sheet_1"> 

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
<img class="center" src="/assets/images/research_day1/From_Correlation_To_Convolutional_layer_31024_2.png" alt="sheet_2"> 


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
<img class="center" src="/assets/images/research_day1/From_Correlation_To_Convolutional_layer_31024_3.png" alt="sheet_3"> 

Everything on the above formulation was good, however it is just my first idea of my TT-Conv layer formulation back to 2021.

# Final Formulation
My thesis actually was using a better TT-Conv Layer formulation with a brillion trick to compute the mulltiple filters with multiple images at onece instead of computing each activateion map. 

The idea of the final formulation on my thesis is to expanding the tensor dimensions. For example, a batch of N RGB images (64x64x3) can be represented by a tensor 
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
<img class="center" src="/assets/images/research_day1/Image_tensor.png" alt="Image_tensor"> 


# Project Details
For more detailed information, please refer to my master's thesis available online on mspace <a href="https://mspace.lib.umanitoba.ca/handle/1993/36582">Design and implementation of a convolutional neural network using tensor-train decomposition</a>

Or the project post on my personal page <a href="https://junyaopu.github.io/projects/">Junyao's Research & Development Page - Projects </a>


