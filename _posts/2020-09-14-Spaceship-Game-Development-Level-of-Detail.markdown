---
layout: single
title:  "Spaceship Game Dev: Level of Detail"
date:   2020-09-14 00:43:00 -0500
categories: personal spaceshipchallenge
classes: wide
header:
    teaser: /assets/images/spaceship/octree_lod.png
---

# Problem
When large objects are viewed at a distance individual cube level details become insignificant to the visual experience, yet continue being rendered. In my game planets use a significant amount of memory, and with large numbers of faces being rendered reducing FPS. When the player views the entire planet they are far enough away that individual cubes are difficult to distinguish. To improve memory usage and FPS these individual cubes can be instead rendered approximately.

# Solution
A dynamic level of detail (LOD) algorithm only renders individual cubes when they are close enough to significantly contribute to the player's view. Otherwise, a lower detail representation is used.

# Implementation
A LOD algorithm has two main operations, switching to the full detail representation when the object is viewed closely, and the inverse, switching to a low detail representation when the object is viewed from afar. Large objects can be divided into regions. Each region is either at a low or full LOD depending on its distance to the viewer.
## Switching to a Lower Detail
The octree data structure used to store cubes in my game yields a natural lower detail representation of individual cubes. When an area of a structure is overly detailed the finest level of cubes in the octree can be discarded instead rendering the coarser parent level. Each parent node contains at most eight child cubes. The mode cube type of the children can be used to set the type of cube to be used for the coarser (lower detail) representation. See the image below for an example of LOD being applied to coloured squares stored in a quadtree.

{% include figure image_path="/assets/images/spaceship/octree_lod.png" alt="Octree based LOD example." caption="A basic example of LOD being applied to coloured squares stored inside a quadtree. The dashed lines indicate the borders of the parent nodes, which group sibling nodes (denoted with solid lines) together. The mode colour of each group of siblings is used to set the colour of the larger parent node." %}

In this simple example, 16 squares are reduced to 4 squares. The same operation occurs in the game, but with cubes instead of squares, cube types instead of colours, and by using an octree instead of a quadtree.

## Switching to a Higher Detail
As the player moves towards a structure the full detail representation will be required, switching at a preset distance determined by the game's performance on their hardware. The structure is loaded from disk, replacing the low detail representation with the full detail one.

## Octree Operations
I had to add several new operations to my octree data structure.
* Delete all descendents of a specified node. Implemented using recursion through all descendents, and a callback function that performs an action on each descendent node. The callback function handles removing the node from the octree, and deleting any data associated with that node. Used to delete the section of my octree that will have a lower LOD representation.
* Saving structure of octree to file. Originally to save structures I wrote the cubes to a file and recreated the structure of the tree on each load. As mentioned, my LOD implementation uses the octree structure to create the low detail representation. Therefore to create a low LOD representation directly from file the structure of the tree needs to be represented in that file. The parent nodes are just stored by using a unique label placed before their children. Now cubes can be grouped together as siblings and a mode cube type calculated without loading the entire structure into memory to recreate the octree structure.

# Demo
Eventually I'll want to use LOD for ships, however planets are currently the most resource hungry structure in my game. Watch as I move around a 1024<sup>3</sup> planet, and see my LOD algorithm reduce and increase detail. Make sure to use fullscreen / higher resolution since the LOD shift is subtle, which is important for game playability.

{% include video id="wK72_BEfxj4" provider="youtube" %}

I currently have two levels of detail, full and 1/8<sup>th</sup> detail, which is given by the parent octree level of the nodes storing individual cubes. I could extend my algorithm to further reduce detail by using higher/coarser octree levels.

### Performance
With LOD enabled a 1024<sup>3</sup> planet, as shown in the video, takes 720MB of memory and renders at 126 FPS. Without LOD the same planet takes 2.8GB of memory and renders at 48 FPS.

# Final Thoughts
The performance advantage of my LOD implementation is significant, and I believe the effect on gameplay minimal. Of course for very low end hardware the LOD switches could become more intrusive as LOD switching would be done at closer distances. I was excited to figure out how to do dynamic LOD switching. However, I think I missed a couple more obvious optimizations. 

I realized while implementing the LOD algorithm that often far cubes need to be shown, but not interacted with. They need to be rendered, taking GPU memory, but can be dropped from main memory if the player won't be interacting with them.

There is also the standard approach of face merging, where planar faces are combined to reduce the total amount of rendered faces. I think this could yield large FPS improvements for planets, since bodies of water are optimal for face merging.

The strength of my LOD algorithm is that it optimizes both FPS, through reducing the number of rendered faces, and memory by storing fewer larger cubes. The disadvantage is that it affects the visual quality of the game, whereas the above two optimizations wouldn't.
