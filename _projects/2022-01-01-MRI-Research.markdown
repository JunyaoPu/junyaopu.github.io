---
layout: single
title:  "The Monte Carlo Simulation of TRASE MRI"
date:   2022-01-01 00:43:00 -0500
collection: projects
author_profile: true
toc: true
classes: wide
header:
    teaser: /assets/images/project_MRI.png
---

EDIT

# Research Goal
To build a GPU-accelerated Monte Carlo simulator for TRASE MRI, you would need to have a strong understanding of the TRASE MRI method, as well as experience with programming for GPU acceleration. This would likely involve using a programming language such as CUDA to parallelize the simulation, as well as optimizing the simulation for performance on a GPU. Additionally, you would need to have experience with MRI image reconstruction techniques, and be familiar with the software and libraries commonly used in this field.

# My Contribution
My research contribution in building a GPU-accelerated Monte Carlo simulator for TRASE MRI includes:

1.A significant speed-up of the simulation, with an experiment showing a 900-times faster execution on GPU compared to CPU.

2.Successful implementation and testing of the simulator for normal image reconstruction and diffusion using the Transmit Array Spatial Encoding method.

3.Identification of potential areas for further optimization, specifically in the memory transfer between CPU and GPU, which could lead to even more computational time reduction.

# Project Details
For more detailed information on the implementation of the TRASE MRI method, you can refer to the paper available online.<a href="https://nrc-publications.canada.ca/eng/view/accepted/?id=dcb1afce-003d-449d-b833-c5ace85ef71e">MRI using radiofrequency magnetic field phase gradients</a>

# Simulation Example
EDIT
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
<img class="center" src="/assets/images/project_CNN_data.png" alt="Sample of my training dataset."> 




