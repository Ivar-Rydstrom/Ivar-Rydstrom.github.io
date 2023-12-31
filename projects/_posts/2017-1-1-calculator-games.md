---
layout: post
title: Graphing Calculator Games
image: /assets/images/calc/cover.png
description: Games developed for the TI-84 Plus CE, all in native TI-BASIC
category: projects
permalink: /projects/calculator-games
related_posts: ""
tags: [computer science]
---
The Texas Instruments graphing calculator family offers the amazing ability for users create custom programs that can be executed in the global context of the calculator. Scripts can be written in [TI-BASIC](https://en.wikipedia.org/wiki/TI-BASIC), a dialect of the [BASIC](https://en.wikipedia.org/wiki/BASIC) language family designed specifically for Texas Instruments calculator products. These scripts have full global control of the calculator, allowing for automated execution of any task that a normal user could do manually. 

Of course, the intended use case of equation scripting and quality-of-life shortcuts can be extended, enabling creative applications such as graphics engines and games.

![TI-84 Plus CE Calculator](/assets/images/calc/ti84.jpg){:.center-img style="width:25%;height:auto"}
*The TI-84 PLUS CE Graphing Calculator.*{:.caption}

The biggest limiting factor is the extremely underwhelming hardware resources avaliable on graphing calculators. The processer in a TI-84 Plus CE features a single core with a measly clock speed of just 48 MHz (compare with modern computer processors with clock speeds of over 4 GHz multiplexed over perhaps dozens of virtual cores). Additionally, the documentation and language support for TI-BASIC is very poor. I found the [TI-Basic Developer](http://tibasicdev.wikidot.com/) site to be an invaluable resource for exploring features of the language.

These limitations force programmers to be extremely crafty and constantly conscious of hardware resources, which has motivated the implementation of highly creative resource-conscious algorithms to replace those used in everyday programming.

## Snake

Although the game [***Snake***](https://en.wikipedia.org/wiki/Snake_(video_game_genre)) is generally considered a classic programming problem solved easily with the use of [object orientation](https://en.wikipedia.org/wiki/Object-oriented_programming), Snake is extremely difficult to implement on a graphing calculator. TI-BASIC does not support object orientation, and otherwise has extremely limited data storage recourses. There are only 27 numeric variables avalable for storing numbers, and lists can only store up to 999 elements (only 99 on TI-83 series calculators). Generally speaking, the calculator will likely run out of physical RAM far before filling up even a single list.

A game like Snake calls for appending a new element to the end of a list every time a new "snake segment" is aquired. My early attempts to implement this game involved appending the `X` and `Y` position values of each segment to two individual lists, and keeping track of each segment based on their shared index in these lists. In practice, this implementation was simply too resource-taxing for the calculator. It was unable to iterate through even a single list each frame, as aquiring only a few segments would slow the framerate to nearly a hault.

![Snake Game](/assets/images/calc/snake3.png){:.center-img style="width:65%;height:auto"}
*My implementation of the "Snake" game played on a TI-84 Plus CE.*{:.caption}

My final implementation only keeps track of two segments: the head and tail positions. The head simply represents the location where a new segment is drawn every frame, and the tail represents the location where they are deleted. Between frames, the drawn state of the screen is preserved. When a new segment is aquired, it simply adds a frame "delay" between the head and the tail such that the tail is delayed behind the head by an ammount of frames equal to the length of the snake.

In this way, my implementation of snake only stores the location of two segments, regardless of how long the snake actually is. This allows it to run consistently on calculator hardware.


![Snake code library](/assets/images/calc/snake_lib.png){:.center-img style="width:65%;height:auto"}
*Auxiliary programs emulating callable "functions" in my Snake implementation, as seen in the program execution menu.*{:.caption style="width:50%"}

## Flappy Bird

![Flappy Bird Game](/assets/images/calc/flap1.png){:.center-img style="width:65%;height:auto"}
*Flappy Bird Clone game played on a TI-84 Plus CE.*{:.caption}

The widly popular 2013 game [***Flappy Bird***](https://flappybird.io/) is one of the most re-created games of all time, especially after its removal from the App Store and Google Play Store in 2014. I had my hand at re-creating this popular game, myself, in TI-BASIC.

My clone utilizes the convienient `Menu` framework built into the calculator language which enabled me to offer different difficulty levels and gamemodes for players to experiment with. 

![Flappy Bird Menu](/assets/images/calc/menu.png){:.center-img style="width:65%;height:auto"}
*Difficulty selection menu in my Flappy Bird clone.*{:.caption}

![Flappy Bird Code](/assets/images/calc/flap_code.png){:.center-img style="width:65%;height:auto"}
*A code sample of the DRAW sub-program powering Flappy Bird Clone.*{:.caption}

## Pong

[Pong](https://en.wikipedia.org/wiki/Pong) competes for the title of earliest ever invented video game, with a year of inception of 1972. The two-player game pits opponents against each other as they compete to richochet a ball into the opponent's score zone using a moving platform.

To implement this multiplayer game, I utilized the calculator as two connected controllers with a mirrored control scheme that accommodates for two simultaneous players. Unfortunately, Texas Instruments calculators feature only [one-key-rollover](https://en.wikipedia.org/wiki/Key_rollover), so both players must share the same priority queue for button inputs.

![Pong](/assets/images/calc/pong3.png){:.center-img style="width:65%;height:auto"}
*"Pong" played on a TI-84 Plus CE.*{:.caption}

## PI Calculator

An extremely creative algorithm for calculating PI involves simulating linear momentum collisions between two massses interacting with an immovable wall. Math YouTube channel [3Blue1Brown](https://www.youtube.com/@3blue1brown) introduces this method [here](https://www.youtube.com/watch?v=jsYwFizhncE&ab_channel=3Blue1Brown). Miraculously, the total number of collisions will always be an order of magnitude factor of the correct value of pi!

Notice that the figure below features 313 collisions, and will eventually get one final count after about ~1 additional minute of simulation. This is a factor of 100 from `pi = 3.14`. The mathematics that powers this phenomenon is quite complicated; look into [3Blue1Brown's explanation](https://www.youtube.com/watch?v=jsYwFizhncE&ab_channel=3Blue1Brown) if you are interested. Also, play with an online version of this simulation I made [here](https://robloxcom-corporation.github.io/Robloxcom-Testing-Enviroment/pi-blocks.html).

![PI Calculator](/assets/images/calc/pi_walls.png){:.center-img style="width:65%;height:auto"}
*PI-calculating physics simulation running on a TI-84 Plus CE: ~5 minutes into calculation.*{:.caption}
