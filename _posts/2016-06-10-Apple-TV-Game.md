---
layout: post
title: "Apple TV Game - Project Journal"
date: 2016-06-10
author: Doug Harper
tags: [Apple TV, Game. Apps]
published: true
---

Starting a brief Journal documenting the progress of a new game that I'm building for Apple TV.  I've been following a tutorial from Justin Dike at [CartoonSmart](http://cartoonsmart.com/ref/511/ "CartoonSmart") and building a two-player tank battle type game.  Currently, the code is complete... for the most part, I'll make some tweaks as I move forward.  I've also got some art work ready and now it's time to put it all together. 

![Tanks](/images/Tanks-Side-by-Side.png "Tanks for AppleTV Game")

## Tank Battle Game
I chose to build a classic tank battle game for several reasons, here's the list...

* Learn the in's and out's of preparing an app for the AppleTV
* Expand/Practice Swift and SpriteKit
* Become familiar with tvOS
* Connect external controllers
 
## Todo List
* Hook up the "Lives" left labels and set it up as images instead of labels
* Include a wins counter that updates as a new level is presented
* Find and add in the proper sound effects
* Complete 5 levels and a game over menu
* Add in Fabric
* Ad in Game Center Achievements
* Marketing artwork
* Game Description (outsource)

Add the wins counter was much easier than I was trying to make it out.  I guess you just pass in the info you need win transitioning to a new `GameScene`

    if let scene = GameScene(fileNamed: "Level" + String(levelToLoad)) {
        
        scene.currentLevel = theLevelToLoad //
        scene.blueWins = blueWins
        scene.greenWins = greenWins
        scene.forcedOnePlayerMode = forcedOnePlayerMode
        
        self.view?.presentScene(scene, transition: SKTransition.fadeWithColor(SKColor.blackColor(), duration: 2))
        
      }

This is working for me, but I need to verify it's the correct way to update my wins SKLabel.

Got the game sound effects up and running.  I also found a great background song for the Main Menu Scene and have it playing, but I need to change it defer to the user's Music... if playing.  

