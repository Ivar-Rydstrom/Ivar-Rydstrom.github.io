---
layout: post
title: Interactive Ising Model Simulation
image: /assets/images/ising/ising.png
description: A web-based physics simulation built in p5.js
category: projects
permalink: /projects/ising-model
related_posts: ""
tags: [physics, computer science]
---
Access the online simulation [here](https://ivar-rydstrom.github.io/ising_model/). View this project on GitHub [here](https://github.com/Ivar-Rydstrom/ising_model).

## Model
The Ising Model is a nearest-neighbor numerical model for ferromagnetic behavior of atomic dipole lattice systems. This model assumes that atomic dipoles occupy only one of two anti-parallel states, which is modeled as quantized magnetization values of either +1 or -1 for each lattice unit.

Every turn, the algorithm iterates through every dipole and considers the projected change in total energy if each individual dipole were to be flipped. If flipping a dipole would result in a lower total energy, then it is always flipped. Otherwise, it is flipped randomly according to temperature and current-energy-state dependent Boltzmann statistics. The total energy is modeled using only the interactions of nearest cardinal neighbors. [Learn more about the Ising Model here](https://en.wikipedia.org/wiki/Ising_model).

![Ising Model GIF](/assets/images/ising/sim.gif){:.center-img style="width:65%;height:auto"}
*Ising Model Simulation with lattice size of 100x100. Simulation converges quickly due to small temperature value of 0.2.*{:.caption}

## Implementation
My implementation of this model uses the [p5.js](https://p5js.org/) JavaScript framework and native HTML elements to provide an interactive web interface which allows the user to manipulate parameters in real time.

In this approximation of a real lattice system, I used [periodic boundary conditions](https://en.wikipedia.org/wiki/Periodic_boundary_conditions). This allows us to neglect edge effects by emulating an *infinite* lattice. I also simplified the problem to two dimensions for simplicity.

In addition to the primary Ising Model algorithm, I developed a "cluster searching" algorithm that searches the lattice for contiguous "clusters" of like-aligned dipoles. With this information, it is able to calculate some basic statistics about the size and number of clusters, which is highly insightful for analyzing critical parameters that lead to convergence.


[![Ising Model](/assets/images/ising/ising2.png){:.center-img style="width:65%;height:auto"}](https://ivar-rydstrom.github.io/ising_model/){:style="width:fit-content"}
*[Ising Model Simulation](https://ivar-rydstrom.github.io/ising_model/) interactive web interface running with a lattice size of 300x300 after 450 iterations.*{:.caption}

This work is inspired by the Chapter 8 problems and pseudocode in [*An Introduction to Thermal Physics* by Daniel V. Schroeder](https://physics.weber.edu/thermal/), and was completed for a class final project in Physics 120, Thermal Physics.

[View this project on GitHub](https://github.com/Ivar-Rydstrom/ising_model).