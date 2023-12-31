---
layout: post
title: Ascii Roguelike
image: /assets/images/ascii_roguelike/gameover.png
description: A turn-based procedurally-generated roguelike game played in a terminal for Irvine Hacks 2020.
category: projects
permalink: /projects/ascii-roguelike
related_posts: ""
tags: [computer science]
---
[View this project on GitHub](https://github.com/irvinehacks2019/ascii_roguelike).

# Irvine Hacks

[Irvine Hacks](https://irvine-hacks-9612.devpost.com/) is a 12 hour in-person hackathon event for high school students hosted by [Redwood Code Academy](https://redwoodcodeacademy.com/). For the 2020 edition, my team consisting of [Raymond Wong](https://github.com/Raymond-exe), [Kabir Kwatra](https://github.com/Kab1r), [Dante Cofano](https://github.com/dantecofano), and I developed a turn-based [roguelike game](https://en.wikipedia.org/wiki/Roguelike) using ascii-art graphics that runs in the command line.

It features a procedurally generated dungeon maze that the player must traverse while collecting weapons and defeating monsters. The game gets progressively more difficult as the player advances to deeper levels of the roguelike adventure.

![Game Board](/assets/images/ascii_roguelike/game1.png){:.center-img style="width:65%;height:auto"}
*Ascii Roguelike game board printed in a console. Player (`@`) avoids an Orc (`O`), and a Behemoth (`B`).*{:.caption}

The game is built in vanilla Java, and takes advantage of basic inheritance class structures to implement different kinds of monsters and interactable entities. The procedural generation algorithm ensures that all parts of the maze are generated such that they are accessible to the player and the monsters.

The most impressive feature is probably the basic enemy pathfinding algorithm used to direct the enemies towards the player through the randomly generated maze.

![Game Board](/assets/images/ascii_roguelike/game2.png){:.center-img style="width:65%;height:auto"}
*Player information screen.*{:.caption}

[Find ***Ascii Roguelike*** on GitHub here](https://github.com/irvinehacks2019/ascii_roguelike).

[See Raymond Wong's improved version, ***Ascii Dungeon***, here](https://github.com/Raymond-exe/Ascii-Dungeon).