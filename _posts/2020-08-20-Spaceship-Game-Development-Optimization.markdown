---
layout: single
title:  "Spaceship Game Dev: Optimization"
date:   2020-08-20 00:43:00 -0500
categories: personal spaceshipchallenge
classes: wide
header:
    teaser: /assets/images/spaceship/cube_planet_1024_small.jpg
---

# When Do I Optimize?
I avoided some basic optimizations for a cube rendering engine at the start of this project. My basic cube rendering method was working alright for small ships. However, as I mentioned in my previous [post]({% link _posts/2020-08-14-Spaceship-Game-Development-Planets.markdown %}), I needed to start optimizing to go beyond a 384<sup>3</sup> sized planet. I started to hit both memory and FPS restrictions of my computer.

## Rendering Optimization
A very basic optimization is to not render cubes that are completely surrounded by other cubes. However, this results in expensive cube addition, as many cubes have to be checked to determine if they are completely surrounded. A better option is to switch to face based, instead of cube based rendering.

Each cube has only its visible faces rendered. This automatically handles completely hidden cubes. For planets I saw a 4-5x FPS speed up over cube based rendering with hidden cubes removed. This makes intuitive sense as usually only 1-2 faces of a cube is ever shown when on the surface of planet.

Future work would include merging faces together to further improve FPS. I'm skeptical to implement this immediately due to the added cost of adding / removing cubes as each such operation would require rerunning the merging algorithm.

## Memory Optimization
A 1024<sup>3</sup> planet alone would take 1GB to store, assuming 1 byte per block. I hadn't been too careful regarding cube properties, and my cube class reached 40 bytes per cube. I trimmed my cube class down to 16 bytes, but a 1024<sup>3</sup> planet still needed too much memory.

A major optimization was to switch the way I was thinking about planets. Instead of thinking of them as solid objects I realized I can represent them as hollow shells, with no blocks inside. When a player removes a block, I can add internal blocks at that time. These can be randomly generated based on the terrain properties of that area, and the player's position. As the player mines or damages a planet the removed blocks can offset the memory cost of the newly generated blocks. This limits me from pre-generating underground structures for the player to find, which I don't see as a critical gameplay feature for a spaceship game.

Generating only the surface cubes works well with my underlying **octree** data structure, since its sparse nature allows it to only stores cubes that exist. If I was instead using contiguously allocated arrays I would be allocating memory effectively for a surface as thick as the array's height.

# Current Benchmark
I mentioned previously that I'd like to have 2048<sup>3</sup> planets. However a 1024<sup>3</sup> planet already looks quite massive. I can't say I wouldn't mind even bigger planets, but I need to keep memory and FPS in mind. From a gameplay perspective a 1024<sup>3</sup> planet takes almost 14 minutes (if flat terrain) for a player to complete one full loop around at a typical 5 block / second movement speed. That covers only a narrow band around 4 out of the 6 faces. A 1024<sup>3</sup> planet should be plenty large to build a base, and get a first ship together.

On my computer (Ryzen 1700X, GTX 1070) a 1024<sup>3</sup> planet takes 3GB of system ram, 11MB of disk space (compressed), and runs at 40-50FPS. It takes 5 seconds to generate. 

{% include figure image_path="/assets/images/spaceship/cube_planet_1024_2_small.jpg" alt="A 1024 cube planet." caption="A 1024x1024x1024 cube planet with procedurally generated terrain." %}

# Next Optimizations
Looking at the 1024<sup>3</sup> planet individual cubes are very difficult to see from space, which motivates the development of a level of detail (LOD) system. Dynamic LOD would greatly improve both FPS and system memory usage. You'll see more on this in my next post!
