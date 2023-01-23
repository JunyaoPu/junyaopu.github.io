---
layout: single
title:  "Spaceship Game Dev Day 5: Saving/Loading Ships"
date:   2020-07-27 00:43:00 -0500
categories: personal spaceshipchallenge
classes: wide
header:
    teaser: /assets/images/spaceship/day5_screenshot.jpg
---

# Day 5
To make my game worthwhile playing players must be able to save their ships, and load designs. If survival mechanics are later implemented then loading a ship would withdraw the necessary resources from a storage of some type. For now I want to just instantly load a ship to test my data structures. Since I use an octree to store my ship cubes I was tempted to serialize the entire tree to a binary file. However, loading a hierarchy such as an octree from file requires careful tracking of pointers between nodes, and the final data being stored. What is a simpler method of saving ships then? What if I just saved cube positions and attributes to file, and then recreated the octree when loading them. The major feature I need is the ability to ask my octree to store elements directly at specific coordinates (indicies), instead of using neighbour relationships such as when players are building a ship. Rebuilding the octree structure adds computation. However, less data is read from file since the tree structure is not stored. I'm categorizing this as a micro-optimization problem for now.

Something I've delayed implementing is cube deletion. With my octree this is done by deleting the appropriate node and its data. However, I have arrays of vertex attribute data associated with the cubes that are sent to the GPU. For example, the location of each cube. If I delete a cube with attribute data near the front of the array then I've created a discontiguous array, only solved by an expensive move operation (for std::vectors this is O(n), where n is the number of elements after the deleted element). The simplest solution I thought of was to copy the last element of the array to the entry that I'm deleting, since the order of the cubes aren't important. Then delete the now duplicate last entry, or if I want to avoid reallocating the buffer, just render one less cube. I believe this isn't a micro-optimization problem because cube deletion happens interactively, and the list of cubes for a ship could be very large.

## Achievements  
So what I did implement today?
* Block deletion. Requires careful handling of attribute arrays to avoid creating discontiguous buffers.
* Saving ships. Writes out all the positions and properties of cubes for a given ship to a file.
* Loading ships. Reconstructs the octree data structure from cube positions.
* Access of octree leaf nodes using indicies (e.g. from cube positions), instead of just neighbour relationships.

{% include video id="Kcqh-uTzrDE" provider="youtube" %}
