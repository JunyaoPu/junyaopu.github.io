---
layout: single
title:  "Futureship"
date:   2020-09-16 00:43:00 -0500
collection: projects
author_profile: true
taxonomy: spaceshipchallenge
classes: wide
sort_by: date
header:
    teaser: /assets/images/spaceship/ship_and_planet_1_small.jpg
---

I started this game as an experiment. I wanted to see how much of it I could write in seven days. This way I'd be focused, and work on the most important features to see if my ideas were feasible before investing a lot of time into the project. If I was satisfied with my progress after the challenge then I could continue working on it. (Update: I have.)

I've always enjoyed voxel cube building games because they provide simple and easy to learn gameplay, while still allowing the player to be exceptionally creative in what they build. I wanted this same experience but in space with ships and planets. This type of game has unique challenges as space is vast, planets are large, and ships are complex multi-functional objects. Part of this project's purpose was for my own education so I started from scratch with OpenGL and C++.

# Current State
The game engine is being optimized to improve FPS and reduce memory usage when playing with large planets and/or ships.

{% include figure image_path="/assets/images/spaceship/ship_and_planet_1.png" alt="Ship over planet." caption="A small ship with weapons and engines flying above a procedurally generated 1024<sup>3</sup> cube world. The world is rendered using a level of detail (LOD) algorithm to reduce the number of displayed cubes at a distance." %}

# Completed Features
* Octree data structure to track the creation and deletion of cubes in a memory efficient way.
* Level of detail algorithm to merge cubes into larger ones when viewed above a threshold distance.
* Large procedurally generated planets up to 1024 cubes in dimension (less than 1GB of memory required).
* Smooth lighting using "light cubes" as a light source.
* Moving ships with momentum and directionally dependent engines.
* Simple beam weapons that test for intersection and destroy blocks.

# Progress Posts
See my individual progress posts below. They start with the seven day challenge.
<div class="entries-{{ page.entries_layout }}">
{% assign entries = site.categories[page.taxonomy] %}

{% if page.sort_by == 'title' %}
  {% if page.sort_order == 'reverse' %}
    {% assign entries = entries | sort: 'title' | reverse %}
  {% else %}
    {% assign entries = entries | sort: 'title' %}
  {% endif %}
{% elsif page.sort_by == 'date' %}
  {% if page.sort_order == 'reverse' %}
    {% assign entries = entries | sort: 'date' | reverse %}
  {% else %}
    {% assign entries = entries | sort: 'date' %}
  {% endif %}
{% endif %}

{%- for post in entries -%}
  {%- unless post.hidden -%}
    {% include archive-single.html %}
  {%- endunless -%}
{%- endfor -%}
</div>
