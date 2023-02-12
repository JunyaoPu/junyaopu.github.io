---
layout: single
title:  "A GPU-accelerated Monte Carlo Simulator for
Optical Coherence Tomography (OCT)"
date:   2022-04-04 00:43:00 -0500
collection: projects
author_profile: true
toc: true
classes: wide
header:
    teaser: /assets/images/project_OCT.png
---
This was my undergraduate thesis honours project that improved a existing Optical Coherence Tomography (OCT) simulator.
For further information on the implementation of the GPU-accelerated Monte Carlo Simulator for
Optical Coherence Tomography, please refer to my undergraduate thesis available in Github.<a href="https://github.com/JunyaoPu/junyaopu.github.io/tree/main/assets">An Improved Monte Carlo Simulator for Optical Coherence Tomography</a>

# Introduction
Numerical simulations of light propagation in tissue can enhance our understanding of the underlying principles of OCT and lead to improvements in OCT methods and hardware. In this project, I created a new inhomogeneous turbid media OCT simulator using an advanced sequential Monte Carlo (SMC) method that incorporates resampling techniques. This enhancement resolves the weight degeneracy issue, and resulting in faster simulation times and/or improved accuracy.

# My Contribution
I successfully integrated the multinomial resampling method into our simulator and validated our simulator result by comparing the A-scans of various media with those from a previous simulator.

# Example
In this example, I placed one ellipsoid and two spheres, constructed with a total of 5,248 vertices and 29,697 tetrahedron meshes. My simulator was capable of performing an A-scan at any point along the z-axis.

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
<img class="center" src="/assets/images/project_OCT_sample.png" alt="Example of tetrahedron mesh of the medium in the OCT simulation."> 


