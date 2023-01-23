---
layout: single
title:  "Spaceship Game Dev Day 2: Octrees"
date:   2020-07-20 00:43:00 -0500
categories: personal spaceshipchallenge
classes: wide
header:
    teaser: /assets/images/spaceship/spaceship_day2.jpg
---

# Day 2
Simply storing each cube in a list isn't going to work well for my game. Realizing that one of my tasks today is to implement cube selection (the user is able to select a cube to add another one to it), brought me back to thinking about how to do object picking. The easy hacky method is to colour each object with a unique RGB value, read back the framebuffer data, and get the colour under the cursor. While easy to implement, the downsides are unfortunately numerous. First, reading data back from the framebuffer to the CPU is slow. I'm also rendering an extra frame to do this with the unique RGB values of my objects. While never displayed to the user, it could cause perceptible lag. Also, I really need six colours, not just one per cube, to know which side has been clicked on.

The proper way, and useful for other game events, like knowing if a ship cube is hit by a weapon shot, is to do ray casting. Using inverse transforms I can take the cursor position and convert it to world space. Then I can shoot a ray from this position, along the normal direction from the camera. Now I have to test if the ray intersects any of my cubes. If the cubes are stored in a list, then I would potentially have to search every cube to find the one hit. Instead, I've decided to implement my own octree. It has the following features:
* Inserts and accesses elements by using neighbour relationships. This mirrors how players will be building/destroying ships.
* Starts with a leaf (a cube), and builds coarser layers as a ship is expanded in dimension.
* The octree stores the position of its top level parent. When a coarser layer is added, this position is recalculated. When travelling from the root to a leaf, this position can be propagated through the tree, if the cubes themselves don't store their locations.

The octree means a 4096 cube set, which if stored in a list could take 4096 operations to find an intersection, can only take a maximum of 32 operations (if the intersection is unique to one leaf) to find the intersection (4 levels, 8 cubes per level = 32 intersection tests). That's of course only if the cubes are all stored in the same 16x16x16 volume to minimize the octree size to have only 4 levels.

## Achievements  
So what I did implement today?
* The above octree structure, without intersection searches (left for tomorrow).

{% include figure image_path="/assets/images/spaceship/spaceship_day2.jpg" alt="Quad/Octree diagram" caption="A 3 level quad tree (as drawn) to help me implement my octree." %}
