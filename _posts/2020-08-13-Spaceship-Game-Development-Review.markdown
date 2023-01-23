---
layout: single
title:  "Spaceship Game Dev Challenge: Review"
date:   2020-08-13 00:43:00 -0500
categories: personal spaceshipchallenge
classes: wide
header:
    teaser: /assets/images/spaceship/debug_engines_and_weapons.png
---

# Review
In seven days I implemented a cube voxel engine from scratch, using OpenGL and C++. I could have started with an existing engine. However, I have to support quite a different range of game play behaviours than a Minecraft clone would, such as the free flight of ships. A lot of time has been used setting up an octree data structure to store cubes. Are octrees the right data structure to use? 

I decided to use octrees because battles in space will involve a lot of weapons being fired destroying cubes on ships. To avoid lag during large battles efficient ray intersection testing must be available, a strength of octrees. I'm also using the octree as a type of sparse data structure since it only stores cubes where they exist. There are no contiguously allocated arrays, such as when using a Minecraft style chunk data structure. When using octrees no memory is wasted on empty or void cubes. Minecraft style chunks of course have much better cache coherency than octrees. If necessary, I could combine the two approaches, and contiguously store groups of cubes at a certain octree level (e.g. level 3 would store groups of 8x8x8 cubes contigously), or have an octree of chunks. Like with a lot of these kind of choices it is best to implement, test, and see what works. Currently octrees are working well.

My favourite part of this project has been implementing the lighting system. It was satisfying to visually see the graphical improvement. From a physics point of view I'm essentially dictating how light works in this universe I'm creating for the game.

# Continued Work
To make my game engine into a game I need to make ships more than just collections of cubes that move together. Some basic gameplay properties of ships are engines and weapons. These will eventually become sophisticated and varied systems requiring power, fuel and controls, but to test my game engine I created a debug weapon and engine. Ships require an engine pointing in each direction to enable motion in the opposite direction. The acceleration is calculated from the engines' thrust and the ship's mass. This gameplay element will also be implemented for ship rotation, calculating the angular acceleration using the engine's position and the ship's center of mass.

{% include figure image_path="/assets/images/spaceship/debug_engines_and_weapons.png" alt="Debug weapons and engines." caption="Basic engines and weapons for ships." %}

To test weapons and cube destruction I've added a basic beam weapon (the cube with the yellow dot in the above image). I am using billboards for the beams. I can add textures to them later to improve their appearance. I use ray intersection testing on nearby surrounding ships to damage blocks. Each weapon has a damage / second property, and each cube has a strength property and becomes damaged over time eventually being destroyed. Weapons fire outward along their normal. A gameplay element would be for the player to upgrade their weapon controls to allow them to group multiple beams together.

{% include video id="AHoTThxEhxQ" provider="youtube" %}

# Gameplay Motto
I don't want a good ship to be built just by randomly combining large numbers of blocks. My gameplay motto is "Basic ship easy, good ship hard". I want the player to easily figure out how to build a basic ship, but leave no obvious solution for the "best" ship. Currently, more engines, more weapons creates a better ship. This is too simple. I'll have multiple engine / weapon types that require supporting systems to make ship building more interesting!
