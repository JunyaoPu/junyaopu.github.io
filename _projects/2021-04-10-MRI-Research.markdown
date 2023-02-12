---
layout: single
title:  "A GPU-accelerated Monte Carlo Simulator for TRASE Magnetic Resonance Imaging (MRI)"
date:   2021-04-10 00:43:00 -0500
collection: projects
author_profile: true
toc: true
classes: wide
header:
    teaser: /assets/images/project_MRI.png
---
I completed a 6-month research project at the University of Manitoba under the supervision of Dr. Christopher Bidinosti and Dr. Sherif Sherif. I developed a GPU-accelerated Monte Carlo simulator using NVIDIA CUDA C for a new MRI technique called TRASE (Transmit Array Spatial Encoding) MRI. TRASE MRI is a fast and non-invasive method that uses RF phase-gradient fields to achieve spatial encoding, providing high temporal and spatial resolution.

# Research Goal
To build a GPU-accelerated Monte Carlo simulator for TRASE MRI, one would need to have a strong understanding of the TRASE MRI method, as well as experience with programming for GPU acceleration. This would likely involve using a programming language such as CUDA to parallelize the simulation, as well as optimizing the simulation for performance on a GPU. Additionally, one would need to have experience with MRI image reconstruction techniques, and be familiar with the software and libraries commonly used in this field.

# My Contribution
My research has led to a significant acceleration of the simulation, with experiments showing 100 times faster execution on a GPU compared to a CPU. I also successfully implemented and tested the simulator for normal image reconstruction and diffusion using the Transmit Array Spatial Encoding method. Additionally, I identified potential areas for further optimization, particularly in the memory transfer between the CPU and GPU, which could result in even more significant reductions in computational time.

# Project Details
For further information on the implementation of the TRASE MRI method, refer to the paper available online..<a href="https://nrc-publications.canada.ca/eng/view/accepted/?id=dcb1afce-003d-449d-b833-c5ace85ef71e">MRI using radiofrequency magnetic field phase gradients</a>

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




