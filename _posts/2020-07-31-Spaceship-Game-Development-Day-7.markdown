---
layout: single
title:  "Spaceship Game Dev Day 7: Textures and Transparency"
date:   2020-07-31 00:43:00 -0500
categories: personal spaceshipchallenge
classes: wide
header:
    teaser: /assets/images/spaceship/day7_screenshot_2_small.jpg
---

# Day 7
I finally added some textures to my game. I'm not an artist, so if I develop this game further I'll work with someone who is much more knowledgeable on graphics design to create a coherent texture pack. 

Loading and rendering one texture was fairly straightforward. However, I'm rendering every cube with one instanced rendering call. I've decided each type of cube will have a unique texture. To avoid multiple rendering calls I've loaded and stored all my textures into a texture array. I created a new shader attribute to indicate (using an index) which texture a cube needs. To pass the index to the fragment shader I learned about the "flat" qualifier which tells OpenGL to not interpolate that value. I found using a texture array to be simpler than using a texture atlas, which requires a 2D offset into the image of textures. All my textures are the same size, so they can fit in an array without wasted space. I could see a texture atlas being preferred when multiple textures of different sizes need to be stored for one rendering call. The depth of a texture array is limited to 2048, but I could always have multiple texture arrays, or a combined atlas/array approach if I ever run out of space.

As shown below, I added an outline texture, and a carpet texture to test my game engine. Note that the colour of the block is stored separately, and multiplied with the texture. I would like to give players the option to choose any RGB value to create aesthetically pleasing ships.

{% include figure image_path="/assets/images/spaceship/day7_screenshot.png" alt="smooth lighting" caption="The structure from day 6, but now with some textures." %}

Windows are an important type of cube to have. Unfortunately rendering transparent objects isn't trivial to implement. It breaks the assumption made by the GPU that obscured objects aren't visible. 

The first step was to add a second instanced rendering call to my game for all objects with transparency. This required some refactoring to generalize the rendering process in my engine for multiple calls. Using a separate render call, I can switch to a shader just for transparent objects. In there I use the "discard" command to not render any pixels with an alpha value of zero. I could have done this in my main cube shader, but that would have possibly created thread divergence on the GPU. Using the "discard" method means I don't need to worry about the order of my transparent object set. The only requirement is that they are rendered last. If I want to have translucent objects, like stained glass cubes, then I'll have to sort from far to near, and use blending. Alternatively I could try using order-independent-transparency rendering. A problem for the future if I need translucent blocks.

In the interior scene below you can see that multiple sets of windows are rendered correctly. Watch the video to see that the rendering is correct when viewed from both sides.

{% include figure image_path="/assets/images/spaceship/day7_screenshot_2_small.jpg" alt="non-smooth lighting" caption="Transparency through multiple windows renders correctly." %}

## Achievements  
So what I did implement today?
* Texturing, using texture arrays to allow continued use of instanced render calls.
* Transparent blocks, by using "discard" in the fragment shader.

{% include video id="XeBAmXOBi7U" provider="youtube" %}
