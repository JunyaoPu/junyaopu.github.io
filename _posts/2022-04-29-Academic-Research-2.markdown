---
layout: single
title:  "Research Day 2: A Cheat Sheet for My Master's Thesis (2)"
date:   2022-04-29- 00:43:00 -0500
categories: Research
collection: Research
classes: wide
header:
    teaser: /assets/images/research_day2/TT_Conv.png
---
My thesis actually utilized a superior TT-Conv layer formulation that employed a brilliant idea to compute multiple filters with multiple images simultaneously, instead of computing each activation map individually. 

# Final Formulation
(I have a fondness for creating equations using LaTeX, as formatting equations elegantly on a website can be quite a challenge.)

The concept behind the final formulation in my thesis was to expand the tensor dimensions. For instance, a batch of N images (I_1 x I_2 x C) could be represented by a 4th order tensor.

<style>
.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  min-width: 35%;
  max-width: 35%;
  width: 50vw;
}
</style>
<img class="center" src="/assets/images/research_day2/Image_tensor.png" alt="Image_tensor"> 

this can be expanding to a 5th order tensor
<img class="center" src="/assets/images/research_day2/Image_tensor_2.png" alt="Image_tensor_2"> 

the TT representation of this 5th order tensor (images) can be show as
<img class="center" src="/assets/images/research_day2/image_tt.png" alt="image_tt"> 

it also can be show by using the tensor graphical representation
<img class="center" src="/assets/images/research_day2/tensor_to_tt.png" alt="tensor_to_tt"> 

On the other hand, a batch of M filters (J_1 x J_2 x C) could be represented by a 4th order tensor as well
<img class="center" src="/assets/images/research_day2/Filter_tensor.png" alt="Filter_tensor"> 

this 4th order tensor will be expanded into a be 5th order tensor
<img class="center" src="/assets/images/research_day2/Filter_tensor_2.png" alt="Filter_tensor_2"> 

the TT representation of this 5th order tensor (filters) can be show as
<img class="center" src="/assets/images/research_day2/filter_tt.png" alt="filter_tt"> 

By utilizing both the TT representations of the images and filters, the fully overlapping correlation with partial mode-2 correlation between each TT core can be calculated as
<img class="center" src="/assets/images/research_day2/result_tt.png" alt="result_tt"> 
or
<img class="center" src="/assets/images/research_day2/result_ptt.png" alt="result_ptt"> 

the tensor graphical representation of the computational process given by following diagram
<img class="center" src="/assets/images/research_day2/tt_computation.png" alt="tt_computation"> 

Finally, By reconstructing the original tensor from those TT cores, we will obtain the result or activation map with a single computation, rather than one map at a time as given by the initial formulation.

The final formulation is more efficient and faster than the initial one. We have implemented this formulation and tested it on a plant image classification problem, resulting in very good results.

# What's next
New training algorithm using Bayesian inference, NO BACKPROPAGATION!

# Formulation Details
For more detailed information, please refer to my master's thesis available online on mspace <a href="https://mspace.lib.umanitoba.ca/handle/1993/36582">Design and implementation of a convolutional neural network using tensor-train decomposition</a>

Or the project post on my personal page <a href="https://junyaopu.github.io/projects/">Junyao's Research & Development Page - Projects </a>


