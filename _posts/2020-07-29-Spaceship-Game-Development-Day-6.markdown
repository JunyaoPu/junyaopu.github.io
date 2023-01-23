---
layout: single
title:  "Spaceship Game Dev Day 6: Colours and Lights"
date:   2020-07-29 00:43:00 -0500
categories: personal spaceshipchallenge
classes: wide
header:
    teaser: /assets/images/spaceship/day6_screenshot_2_small.jpg
---

# Day 6
This was a very long day. My game badly needed some attention graphics wise. The first step was to add multiple types of cubes. 

### Cube Types
In the future different cubes would impose different types of functionality, but for now I wanted cubes that just look different. This is an important functionality if players want to build aesthetically pleasant looking ships. Each cube instance now has a unique color that is supplied to it with a vertex array buffer. I'll eventually add textured cubes. Texturing cubes is programmatically / mathematically not too hard, but I have to make / find textures which can be time consuming. At least now I have the mechanics setup to handle multiple cube types in my game.

### Lighting
This was a complicated part of my game to implement. I'm familiar with ray-tracing type lighting. So I initially thought I'd use some type of Phong shading, but quickly realized that the number of lights possible is severely limited. Players should be able to make a ship hull entirely out of lights if they really want! A ship is also a collection of many scenes, each of which needs to be lit individually (have to occlude lights with blocks). Also, each side of a cube might be in independent lighting environments. As this is a building game I don't have the benefit of knowing a priori where lights, and objects will be.

What can I use to my advantage? Cubes and grids! I've added a separate light map octree. A light cube will populate this map using a breadth first update algorithm (propagate lighting values using FIFO queues). It will then queue up any cubes it encounters, and their sides, to update their lighting. This is done by calculating the average of the up to 8 surrounding light map values for each of the 4 vertices of that cube's side. The light values per vertex of each cube are stored in a SSBO. The interpolated light values are then used to modify the colours of each cube in the fragment shader to simulate light. Each cube face requires its own independent set of vertices resulting in 24 light values per cube.

{% include figure image_path="/assets/images/spaceship/day6_screenshot_2.png" alt="smooth lighting" caption="A sample cube structure with multiple lights." %}

I also implemented a simpler method where each cube face (instead of vertice) has a light value. Of course this means that light values can't be smoothly interpolated across cube faces, resulting in non-smooth lighting. However, it is computationally less expensive, making it a good option for slower machines. I also like having multiple implementations (especially simpler ones) as a debugging tool.

{% include figure image_path="/assets/images/spaceship/day6_screenshot_3.png" alt="non-smooth lighting" caption="The same cube structure but with non-smooth lighting." %}

## Achievements  
So what I did implement today?
* Smooth and non-smooth lighting.
* Multiple types / colors of cubes.

{% include video id="yeyPpCwgYlk" provider="youtube" %}
