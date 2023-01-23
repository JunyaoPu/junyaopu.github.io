---
layout: single
title:  "Spaceship Game Dev Day 4: Cameras and Ships"
date:   2020-07-26 00:43:00 -0500
categories: personal spaceshipchallenge
classes: wide
header:
    teaser: /assets/images/spaceship/day4_screenshot.jpg
---

# Day 4
A spaceship building game wouldn't be that much fun without being able to fly the ships! A lot of physics can become involved with ship flight mechanics such as momentum (both translational and rotational) that require knowing the ship's mass distribution. However, I need to build the basics first, on which realistic flight mechanics can be added later to. Recall on [Day 1]({% link _posts/2020-07-19-Spaceship-Game-Development-Day-1.markdown %}) I implemented a FPS style camera just to get started. Of course this isn't sufficient for full 3D flight, so I had to start by reviewing quaternions (a while since I used them while studying physics) to create a free camera. Having a true free moving camera I can abstract this type of motion into a general class for any objects with this type of movement. Therefore my player's camera while piloting a ship, and their ship are both considered "free flying" objects. I probably want to use FPS-style, plane constricted, camera/movement for players or objects under the influence of gravity.

## Achievements  
So what I did implement today?
* Quaternion based free flight camera.
* Basic ship flight using WASD + mouse. Ships inherit the same properties that a free flight camera does from a general free flight object class.
* Ability to attach a camera to a ship so that it tracks with the ship's movement. Each ship can receive a list of objects to move with them.

{% include video id="xv-K5vDswnI" provider="youtube" %}
