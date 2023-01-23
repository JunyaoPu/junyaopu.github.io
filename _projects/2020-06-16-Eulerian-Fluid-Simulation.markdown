---
layout: single
title:  "Eulerian Fluid Simulation"
date:   2020-06-16 00:43:00 -0500
collection: projects
author_profile: true
toc: true
classes: wide
header:
    teaser: /assets/images/stair_fluid_sim_frame.png
---

As part of my research at University of Waterloo I developed a grid (Eulerian) based fluid simulator. The code is available on my <a href="https://github.com/mlhonke/simFluid">GitHub</a>. The fluid simulator was to be used as part of my ferrofluid simulation project. Therefore, knowing that the ferrofluid simulator would add significant computational complexity (a large linear system to solve), I wanted to keep my fluid simulation computationally fast, while still able to capture intricate surface details. See some basic tests of my simulator. 

# Examples
The code for these examples can be found <a href="https://github.com/mlhonke/simFluid/tree/master/examples"> here</a>.

## Freefall
Water, initialized as a block, is used to fill a container. Simulation resolution is 60x60x60.
{% include video id="PRE7OZY8Nag" provider="youtube" %}

## Stairs
Water falls down stairs. Simulation resolution is 60x60x60.
{% include video id="oHb2bw7PInI" provider="youtube" %}

# Technical Details
A focus was placed on using the GPU as much as possible. All conjugate gradient solves are done using cuSPARSE and cuBLAS. Advection is easily parallelized for GPU. While level set is computationally efficient, I needed a better surface tracking methodology for capturing detailed surfaces.

I implemented a variation of the Particle Level Set (PLS), but instead of using particles scattered around the interface, I seeded them directly on the interface. This somewhat emulates how mesh vertices are used in mesh based surface tracking. However, by using a level set, topological changes are handled automatically. Sign particles are used to determine which side of the interface a grid point lies on. All particle operations, including seeding, and grid redistancing from particles, are parallelized for the GPU.

Next, I needed accurate surface tension if I was going to using this fluid simulator as the base for my ferrofluid simulation. To determine how much surface tension to apply, I used height function based curvature estimation, popularized for level sets by Sussman et al. However, I used the idea of normal aligning my stencils for better fitment. Instead of using the level set for determining surface heights, I used the surface particles directly, from my modified PLS implementation. This greatly increased the accuracy of the measured curvatures.
