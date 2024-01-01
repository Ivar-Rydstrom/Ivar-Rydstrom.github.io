---
layout: post
title: YouTube Replay Counter
image: /assets/images/youtube_replay_counter/cover.png
description: An injection script which seamlessly integrates a replay counter for YouTube videos
category: projects
permalink: /projects/youtube-replay-counter
related_posts: ""
tags: [computer science]
---
[View this project on GitHub](https://github.com/Ivar-Rydstrom/YouTube-Replay-Count).

***YouTube Replay Counter*** is a simple [Tampermonkey](https://www.tampermonkey.net/) injection script which adds a "plays" counter to the native YouTube player. In short, it tracks the total amount of times a video has been replayed.

![YouTube Replay Counter](/assets/images/youtube_replay_counter/plays.png){:.center-img style="width:65%;height:auto"}
*YouTube Replay Counter script injecting a "plays" count to the native YouTube player.*{:.caption}

The script uses browser cookies to track the total amount of plays each video has. During each watch session, it tracks a "watch delta" by periodically monitoring the video progress.
Once the watch delta exceeds a threshold (by default 75%), it will add one play to the counter stored in cookies. The next time it updates, it parses this cookie variable and displays the replay count neatly below the video player.
