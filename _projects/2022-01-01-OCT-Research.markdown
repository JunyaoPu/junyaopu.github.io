---
layout: single
title:  "An GPU-accelerated Monte Carlo Simulator for
Optical Coherence Tomography"
date:   2022-05-01 00:43:00 -0500
collection: projects
author_profile: true
toc: true
classes: wide
header:
    teaser: /assets/images/project_OCT.png
---
This was my undergraduate honours project that improved a existing Optical Coherence Tomography (OCT) simulator.

# Introduction
Numerical simulations of light propagation in tissue can enhance our understanding of the underlying principles of OCT and lead to improvements in OCT methods and hardware. In this project, I created a new inhomogeneous turbid media OCT simulator using an advanced sequential Monte Carlo (SMC) method that incorporates resampling techniques. This enhancement resolves the weight degeneracy issue, and resulting in faster simulation times and/or improved accuracy.

# My Contribution
I successfully integrated the multinomial resampling method into our simulator and validated our simulator result by comparing the A-scans of various media with those from a previous simulator.

# Project Details
For further information on the implementation of the GPU-accelerated Monte Carlo Simulator for
Optical Coherence Tomography, please refer to my master's thesis available in Github.<a href="https://github.com/JunyaoPu/junyaopu.github.io/tree/main/assets">An Improved Monte Carlo Simulator for
Optical Coherence Tomography</a>

# Project Poster
Here is the poster I created for a research competition at university. It describes the TRASE MRI method and how we implemented it using a GPU-accelerated simulator. In the MRI image example, we simulated a 24-cube of water sample and a sealed cell of He gas. We successfully reconstructed TRASE MRI images using our GPU-accelerated simulator, which was around 100 times faster than the CPU version.
<style>
.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  min-width: 80%;
  max-width: 80%;
  width: 80vw;
}
</style>
<img class="center" src="/assets/images/project_MRI_poster.png" alt="Sample of my training dataset."> 




