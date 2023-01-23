---
layout: single
title:  "Spaceship Game Dev Day 3: Intersection Testing"
date:   2020-07-21 00:43:00 -0500
categories: personal spaceshipchallenge
classes: wide
header:
    teaser: /assets/images/spaceship/day3_screenshot.jpg
---

# Day 3
Today I finished my octree implementation. Two days of work, but I think it's worth it. Using a proper data structure will allow me, and maybe future players to build very large ships, without encountering performance degradation. At least not with cube selection anymore! I have a video of me finally building something!

## Achievements  
So what I did implement today?
* Octree ray intersection testing using the "slab test" for each cube.
* Ability to add cubes while playing the game!
* Crosshairs to help select cubes.

{% include video id="NLp-7EPIFzs" provider="youtube" %}
