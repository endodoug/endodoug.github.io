---
layout: post
title: "Apple TV Game - Project Journal"
date: 2016-06-10
author: Doug Harper
tags: [Apple TV, Game. Apps]
published: false
---

Starting a brief Journal documenting the progress of a new game that I'm building for Apple TV.  I'm following a tutorial from Justin Dike at [CartoonSmart](http://cartoonsmart.com/ref/511/ "CartoonSmart") and building a two-player tank battle type game.

## Topics to Learn
* Connecting an Extended Game Controller
* Setting up the Standard and Micro Controllers correctly


### Day 1
Starting off by connecting a external game controller, I have a Steel Series Nimbus - which is recommended by Apple.  The basic steps are importing GameControllers to the GameScene and configuring them in the project Capabilities.
![Controller Configuration in Xcode](/images/GameControllerConfiguration.png "Controller Configuration in Xcode")

It's important to set up observers to detect if/when controllers are connected and disconnected, this is also a good time to set the player index - Player 1, Player 2, etc...   
