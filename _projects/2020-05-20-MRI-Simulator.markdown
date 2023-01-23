---
layout: single
title:  "A Highly Parallelized Bloch Simulator for Magnetic Resonance Imaging"
date:   2020-05-20 00:43:00 -0500
collection: projects
author_profile: true
toc: true
classes: wide
header:
    teaser: /assets/images/gre_timesteps.png
---

As my undergraduate thesis project I wanted to make a full simulation of the MRI process that was capable of running on both CPU and GPU. Maybe that sounds ambitious, but let us break the problem down. 

A real MRI scanner has an input, a program, and an output. Medically, that input is often a person's head. In reality, a lot of MRI research is done using samples called "phantoms". These are very simple samples that we know what they should look like as outputted images from our scanner. Phantoms let us test how well the scanner is working. The simplest phantom is a container of water. Since MRI works by exciting water molecules, and then detecting the signal emitted from them, we would expect to see the shape of the container on the output image. That is, if the scanner is working properly. If it isn't, we see a distorted image of that sample container.

# Motivation
If we can validate the output of MRI scanners using phantoms as an input, why do we want to simulate the process? Like a computer processing a job, an MRI scanner uses a program to run a scan. Writing successful programs for MRI scanners is a challenge, and a continued area of research. MRI scans can also be very time consuming, due to natural physical restrictions, which a simulation can fast forward through. A simulation can be used to verify and optimize these scanner programs, before they are ever used. Lastly, time on a MRI scanner is expensive, so it's best to have tried the experiment in a simulator first.

# My Project
MRI simulation has received significant attention previously. However, the simulator I developed simulates the full MRI pipeline (you see a simulated image at the end), models diffusion, can operate at low field strengths, and uses the GPU for a performance boost. Generating a full image, rather than just measuring total signal, requires a significantly more complex MRI program (to encode water molecules with spatial information), and the accompanying image reconstruction algorithm to convert the simulated signal into an image. The simulator models diffusion of water, which certain types of imaging, e.g. Diffusion Tensor Imaging (DTI), uses to resolve brain structures based on their characteristic diffusion values. Lastly, since the simulator can model precession of the hydrogen atoms for low magnetic fields, it can be used to simulate low field field MRI systems. These systems are less expensive and more portable than traditional high field MRI scanners, making these low field scanners ideal for developing countries and rural communities.

My simulator is an extension of Trevor Vincent's <a href="https://github.com/trevor-vincent/lowfield_diffusion_mri_gpu">MRI simulator</a>, also supervised by Dr. Christopher Bidinosti. I was therefore able to start with a simulator that solved the Bloch equations for low magnetic fields, and modelled diffusion on the GPU. I extended this simulator to have full imaging capability with a GPU compatible pipeline.

# Technical Details
If you're interested in the details you can review the code: <a href="https://github.com/mlhonke/mri_sim">here</a> or see my thesis: <a href="/assets/files/undergrad_mri_sim_thesis.pdf">here</a>. All GPU functionality was achieved using NVIDIA's CUDA library. 

# Example
I mentioned that diffusion can be used by a MRI scanner to learn more about the sample. In this example I placed five simulated water samples with different diffusion coefficients along the bottom. Moving from left to right the diffusion coefficient increases. Therefore the signal decays faster due to phase incoherence (water mixes and destructively accelerates the decay of its signal). This results in progressively dimmer circles.

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
<img class="center" src="/assets/images/mri_simulator_happy.png" alt="Example of my simulator's output."> 

Running this experiment on GPU increases the performance by a factor of 50x.
