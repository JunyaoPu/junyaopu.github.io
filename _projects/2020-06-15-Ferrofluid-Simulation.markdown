---
layout: single
title:  "Ferrofluid Simulation"
date:   2020-06-15 00:43:00 -0500
collection: projects
author_profile: true
toc: true
classes: wide
header:
    teaser: /assets/images/ferrofluid_front_small.jpg
---

Ferrofluids are a type of magnetic fluid. They have all the properties normally associated with fluids, such as viscosity, surface tension and density. However, the magnetic properties of ferrofluids allow for the velocity and static shape of the fluid to be manipulated using applied magnetic fields. My goal with this project was to simulate ferrofluids using an Eulerian (grid) based simulation. I wanted to especially capture the Rosensweig instability, a characteristic feature of ferrofluids. This phenomena results in ferrofluids displaying a pattern of peaks on their surface when a sufficiently strong magnetic field is applied to the fluid.

# Examples
## Field Induced Motion
A ferrofluid droplet, in zero gravity, is accelerated by a magnetic field towards the bottom of the simulation domain where the magnet is located. Note the non-constant acceleration of the droplet as the magnetic field increases towards the bottom of the domain.
{% include video id="_pCorLhMZCM" provider="youtube" %}

## Rosensweig Instability
A strong magnet is placed below the initially flat block of ferrofluid. As time progresses the Rosensweig instability phenomena occurs, as seen by peaking on the surface of the fluid. Simulation resolution is 60x60x30.
{% include video id="-VFo63_UEq8" provider="youtube" %}

I found that my simulator can reproduce the critical magnetization trait of ferrofluids. This means that there is a minimum magnetic field required to produce the Rosensweig instability. Until that point is reached, the fluid does not create peaks. Strong magnetic fields also ellicit more, and faster peaking than weak magnetic fields.

The key limitation of my simulator lies in the struggle to achieve an equilibrium balance of forces, so that peaks can become stationary and form the hexagonal pattern characteristic of the phenomenom. Chiefly, the forces due to surface tension, magnetic force, pressure, and gravity must balance with each other. It should be noted that achieving stable surface tension is already a challenge in fluid simulation!

# Technical Details

I first developed an [Eulerian fluid simulation]({% link _projects/2020-06-16-Eulerian-Fluid-Simulation.markdown %}) to serve as the base of my ferrofluid simulation. I then added the machinery to model a magnet, do magnetic potential solves, and apply the resulting magnetic force to the fluid.

You can find out more about both my ferrofluid and fluid simulation techniques in my <a href="https://uwspace.uwaterloo.ca/bitstream/handle/10012/15859/Honke_Michael.pdf?sequence=3&isAllowed=y"> thesis</a>. You can see the code for my ferrofluid simulator on my <a href="https://github.com/mlhonke/simFerro">GitHub</a>, noting that all my general non-magnetic fluid code is a separate <a href="https://github.com/mlhonke/simFluid">general fluid simulator repository</a>, which is included as an external static library by my ferrofluid simulator.
