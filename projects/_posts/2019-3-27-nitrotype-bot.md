---
layout: post
title: Nitro Type Bot Client
image: /assets/images/nitrotype_bot/nitro.png
description: A bot client that (poorly) plays Nitro Type using optical character recognition
category: projects
permalink: /projects/nitrotype-bot
related_posts: ""
tags: [computer science]
---
[View this project on GitHub](https://github.com/Ivar-Rydstrom/nitrotype-bot).

## Optical Character Recognition

Optical character recognition (*OCR*) is a technology capable of converting images of text into computer-parsable strings. They often come packaged as [APIs](https://en.wikipedia.org/wiki/API), and usually use some form of machine-learning-based artificial intelligence to identify text. In this project, I use an open-source OCR API by Google called [Tesseract](https://github.com/tesseract-ocr/tesseract).

[Learn more about OCR here](https://aws.amazon.com/what-is/ocr/).

## Using OCR to play Nitro Type

[Nitro Type](https://www.nitrotype.com/) is a typing test game where players compete against each other to type a certain passage as fast as possible. The player who types the passage fastest is dubbed the winner.

To make a bot capable of playing this game, I start by using the [OpenCV](https://opencv.org/) computer vision framework to grab frames from the screen. This image data is then processed and parsed into a format readable by Tesseract. The Tesseract API then returns the most probable string that the image contains, which gets used as the next keyboard input.

![Nitro Type bot](/assets/images/nitrotype_bot/bot.gif){:.center-img style="width:65%;height:auto"}
*Bot client working (with some manual assistance). Output stream on console shows highest certainty letter recognized from OCR.*{:.caption}

The biggest challenge was the the relatively low accuracy of the Tesseract API, which incorrectly predicts the next character nearly half of the time (in this particular application). This could be for a number of reasons, including unfamiliarity or lack of training data with the particular font used in the game. As OCR and other AI-driven services become more advanced in the future, it would be fun to revisit this project.

Take a look at the code on GitHub [here](https://github.com/Ivar-Rydstrom/nitrotype-bot).
