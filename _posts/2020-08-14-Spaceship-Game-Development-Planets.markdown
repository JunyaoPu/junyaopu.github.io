---
layout: single
title:  "Spaceship Game Dev: Planets"
date:   2020-08-14 00:43:00 -0500
categories: personal spaceshipchallenge
classes: wide
header:
    teaser: /assets/images/spaceship/cube_planet_9_small.jpg
---

# Why Planets
Why I do want planets in my game?
### Survival
Players could start off the game on a planet where they have to build a ship from scratch. Planets provide resources, but are limited in size, motivating the player to eventually build a ship and explore.

### Immersion
Exploring space isn't much fun without something to find. With procedurally generated planets players could find and settle on their favourite worlds, creating bases there. Visually planets are fun to see in space!

# How
In our universe planets are roughly spherical. A Minecraft style world is a plane of cubes. Planets return the player to their original position if they walk far enough along an axis. This can be accomplished using a plane by wrapping (teleporting) the player to the opposite of the edge they crossed. After some thought I realized this kind of motion is not analogous to a sphere, but rather a torus! Using shader hacks I could make the plane look spherical, using (phi, theta) to access (x,y) coordinates on the plane. This is suitable when the player is always constrained to the planet, since the planet is drawn relative to their position. However, for a free planet, the poles become identical, fairly nonsensical for a space game when the player can approach either one! See my drawing below, and visualize how the plane would wrap onto the sphere to see this.

{% include figure image_path="/assets/images/spaceship/plane_to_sphere.jpg" alt="Plane to sphere." caption="Plane to sphere." %}

Another option, as shown in the image below, is to inflate a cube, which is just a collection of six planes (easy to create in a voxel game using cubes). If I can live with the distortion, as any plane to sphere mapping creates, then it appears to be a solution. 

{% include figure image_path="/assets/images/spaceship/cube_to_sphere.png" alt="Cube to sphere." caption="Cube to sphere." %}

Circled in green is a typical bordering of cubes (or regions of cubes), like on a plane, minus the distortion. However, circled in red, where the corners of the original square sides meet, are two cubes (shaded green and red) sharing a connection with one cube (shaded purple), which is not allowed in a grid with only right angles. Therefore I cannot represent the inflated cube using a plane very well. Imagine a player walking around the point circled in red while building a railway. The railway would form a triangle, an inconsistent geometry for a cube world. Worst yet would be a confused player ending up with a three sided, yet enclosed, house, breaking immersion of a cube world.

If I abandon spheres altogether due to their poor mapping with planes I might consider having torus or ring worlds, which have direct mappings to planes. See the video below where I demonstrate a plane world folded into a ring world. As the player approaches the ring world it unfolds back into a plane eliminating distortion that could be annoying while building.

{% include video id="IJm1Wu359Y4" provider="youtube" %}

A similar solution can be done for a torus. A torus is especially bad for distortion since there are two directions of curvature. A sphere is a degenerate torus, yielding a possible mapping, but one side of the cubes collapse to zero at the poles creating maximum distortion since the cubes appear as triangular prisms.

A practical solution would be to use ring worlds, but my aesthetic sense finds a solar system of ring worlds weird. I want worlds which have many of the properties of spheres, but aren't spheres. Specifically, spheres make for good planets because they are:
* Symmetric, and approachable from any direction.
* Can be walked around.
* Efficient to render since when on the surface, you cannot see the other side of the planet like with a ring or torus world.

This leads me to an obvious solution, why not just use cubes for the planet shape? They are trivially built from blocks. No shader hacks required to make it appear the correct shape. All the properties I enjoy from spheres hold true for cube worlds. Lastly, it is consistent for a game where everything is made of cubes. The player can fully modify the cube planet. There are no regions of high distortion, or otherwise unbuildable regions. I don't need to use general meshes to fill in holes. I think they are aesthetically pleasing too.

{% include figure image_path="/assets/images/spaceship/cube_planet_6_small.jpg" alt="A procedurally generated cube world." caption="A procedurally generated cube world." %}

Above is a procedurally generated cube world I created. I use the [FastNoise](https://github.com/Auburn/FastNoise) library for my noise functions. I randomly choose different noise functions and settings to generate different terrains on each cube side. So far I've been experimenting with 256 or 384 cubed planets. I'd like to work my way up to 2048 cubed planets, but this will require some engine optimizations.
