---
layout: post
title: An Interactive Ising Model Simulation
image: /assets/images/ising/ising.png
description: An interactive ising model simulation built in p5.js
category: projects
permalink: /projects/ising-model
related_posts: ""
---
Access the online simulation [here](https://ivar-rydstrom.github.io/ising_model/){:target="_none"}. View this project on GitHub [here](https://github.com/Ivar-Rydstrom/ising_model){:target="_none"}.

## Model
The Ising Model is a nearest-neighbor numerical model for ferromagnetic behavior of atomic dipole lattice systems. This model assumes atomic dipoles occupy one of two anti-parallel states, which is modeled as a magnetization value of either +1 or -1 for each quantized lattice unit.

Every turn, the algorithm iterates through each dipole and consideres the change in total energy of flipping that dipole. If flipping a dipole would result in a lower total energy, then it is always flipped. Otherwise, it is flipped randomly according to Boltzmann statistics. The total energy is modeled using only the interactions of nearest cardinal neighbors. [Learn more about the Ising Model here](https://en.wikipedia.org/wiki/Ising_model){:target="_none"}.

## Implementation
My implementation of this model uses the [p5.js](https://p5js.org/){:target="_none"} javascript framework and native HTML elements to provide an interactive web interface for manipulating model parameters in real time.

I used perodic boundary conditions in this approximation. This allows us to neglect edge effects by emulating an *infinite* lattice. I also simplified the problem to two dimensions for simplicity.

In addition to the primary Ising Model algorithm, I developed a "cluster searching" algorithm that searches the lattice for contiguous "clusters" of like-aligned dipoles. With this information, we are able to calculate some basic statistics about the size and number of clusters, which is highly insightful for analyzing critical parameters that lead to convergence.


[![Ising Model](/assets/images/ising/ising2.png){:.center-img style="width:65%;height:auto"}](https://ivar-rydstrom.github.io/ising_model/){:target="_blank" style="width:fit-content"}
*"Ising Model Simulation" interactive web interface running with a lattice size of 300x300.*

This work is inspired by the Chapter 8 problems and algorithm pseudocode in *An Introduction to Thermal Physics* by Daniel V. Schroeder, and was completed for a class final project in Physics 120, Thermal Physics.

[View this project on GitHub](https://github.com/Ivar-Rydstrom/ising_model){:target="_blank"}.