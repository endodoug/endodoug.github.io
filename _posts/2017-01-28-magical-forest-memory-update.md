---
layout: post
title: "Magical Forest Memory Game Overhaul"
date: 2017-01-28
author: Doug Harper
tags: [iOS, Swift 3, SpriteKit, Game, App, Updates]
published: true
---

I am starting a complete overhaul of [Magical Forest Memory Match](https://itunes.apple.com/us/app/magical-forest-memory-match/id984939318?ls=1&mt=8 "Magical Forest Memory Match"), which I made as a SpriteKit learning project.  Currently, it's a simple one scene memory game that tracks your best score.  There's not much to it, but my 3 yr-old likes it and asks for it specifically.  So, my plan is to make a few more levels with the art work I currently have.  

## Here's the plan (Phase 1):

* Create a Main Menu scene
* Create a Game Over scene
* Add 4 new levels 3 easier, 1 more difficult than my current scene
* Kid-ify it a bit with some additional juice
* Add some more acheivements
* Remove a bug in the current game - reshuffle after complete game

A cool little note about something I discovered.  While converting from Swift 2.3 to Swift 3 I found a simple technique for implementing a Fisher-Yates [shuffle already exists in GameplayKit](https://developer.apple.com/reference/gameplaykit/gkrandomsource#//apple_ref/occ/instm/GKRandomSource/arrayByShufflingObjectsInArray: "Random shuffle in GamePlayKit").  It's a huge time saver for me... 

     func shuffle<C: MutableCollectionType where C.Index == Int>(list: C) -> C {

         var theList = list

         let shufflecount = theList.count
         for i in 0..<(shufflecount - 1) {
           let j = Int(arc4random_uniform(UInt32(shufflecount - i))) + i
           if i != j {
             swap(&theList[i], &theList[j])
           }
         }
         return theList 
       }
       
Replaced with this...

    let newSequence = GKRandomSource.sharedRandom().arrayByShufflingObjects(in: cardsSequence)
    
    
### Jan 29th

I tracked down the reshuffle bug using some simple print statements and found the array holding the cards needed to be reset before re-shuffling after a completed game.  

Added the Main Menu and Game Over scenes.  They're both just placeholders for now, my next step is to add some functionality to them and then complete the design.  


