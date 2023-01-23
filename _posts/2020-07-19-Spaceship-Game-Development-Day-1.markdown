---
layout: single
title:  "Spaceship Game Dev Day 1: Planning the Seven Day Challenge"
date:   2020-07-19 00:43:00 -0500
categories: personal spaceshipchallenge
collection: sevendaychallenge
classes: wide
header:
    teaser: /assets/images/spaceship/day1_screenshot.png
---

# Motivation  
I've graduated from University of Waterloo in June, and free of my research obligations, I've had time to work on projects that I couldn't justify doing before. Learning to make this website was one of them!

I've always wanted to make my own game, and now is the time to do it before starting the job search. My game playing interests mostly center around building games, like city simulations such as City Skylines and the Sim City series. I've also enjoyed Minecraft, but always wished there was a block building game where I could build a spaceship, full of complex interacting systems, and survive on it in space. I haven't been fully satisfied by the existing offerings, and thus I have a game development project!

# The Challenge  
I want to develop my own spaceship building game in seven days. If it looks promising after I'll continue development, but I want to see where I'll end up after a week of work. Partially to motivate me to work efficiently, and to reign back my ambition in terms of creating features, and to stop myself from ignoring the need to get a real world job.

# Day 1  
I've decided to use OpenGL 3+ and GLFW for my game graphics. First, so I have a decent hope of cross platform compatibility between Windows and Linux, and secondly, I have some experience with OpenGL already from taking CS 688 at University of Waterloo. I've considered using the BGFX library to abstract the graphic's API calls. However, due to my self-imposed time constraint and focus on supporting only Linux and Windows, I've decided to stick with OpenGL. If DirectX offers a potential performance improvement on Windows, I can always add a separate set of rendering calls to it later, or switch over to BGFX.

## Achievements  
So what I did implement today?
* WASD / mouse FPS style controls (a starting point for now)
* Rendering multiple cubes with various offsets to screen using instanced rendering to avoid multiple draw calls. Important for performance if there are multi-thousand cube ships.

{% include figure image_path="/assets/images/spaceship/day1_screenshot.png" alt="Rendered a few cubes to my screen." caption="4 cubes drawn using one glDrawElementsInstanced() call." %}
