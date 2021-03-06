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

### Feb 3rd 

Over the last few days I created the Main Menu and Game Over scenes spending alot of time researching ways to improve the code I had already written.  I guess it was a good excercise, but I should have thought about how much time it cost me to save a few lines of code.  I'm still tweaking the artwork, button placement, & transitions for each menu, but the functionality works good.  A few things accomplished: 

- Moved the background music code to a seperate file so all the scenes have access to it and can start/stop when needed.
- Added a new Menu class for any menu to inherit from.  
- Added some artwork for the new menus, subject to change of course.
- Created Level 2 and included some dummy material.

I'm getting lots of ideas while working on the update, but don't want to make this a "never ending project."  So, I've been writing them down and self-evaluating the effort vs reward.  For now, I'm going to find some better sound effects for matches, misses and game over... something more kid friendly and less jarring.  I'm also going to change the character reveal actions to the cool animation effect I learned at Alt-U.  It's really smooth, looks great and will be worth the effort to improve overall quality of the game.

### Feb 7th

I've made a lot of progress in the last few days and it's starting to come together nicely.  Tonight was an accidental live demo with my son, he cleared levels 1 & 2 without help.  It was much more fun for him than the original version and he had a lot of excitement getting the matches.  

- Completed the Main Menu.
- Three "free" levels are functional.
- Added user default keys for each level to record a best score for individual levels.
- Added a rate button to the Main Menu and it links directly to the reviews tab in the App Store.
- Added a button click animation to the Main Menu buttons.

Although the levels are all functional, I need to tweak the card sizes and reveal animations to for levels 2 & 3.  I've got to start a client project next week, so I need to focus my attention and get this done before the weekend is over.

### Feb 15th

Added In-App purchase option to buy two new levels. For the re-launch, I'm adding bigger/more difficult levels as premium options.  The next update will include premium options that will be more kid/learning friendly, I hope to get some feedback before the next update so I can polish it a little more.  The two new levels are also completely functional, the only thing left is to add a few acheivements and a Leaderboard for the final level.

### Feb 18th

Removed the GameCenter Leaderboard for all level except the final level, which is the most difficult and only available as in-app purchase.  I also added the restore button for in-app purchasing and included another button to display GameCenter's Achievements.  Finally, I went into iTunesConnect and created a new version, supplied new screenshots, descriptions, et... then submitted the update for review.  Everything went smooth and the new/improved [Magical Forest Memory Match](https://itunes.apple.com/us/app/magical-forest-memory-match/id984939318?ls=1&mt=8 "Magical Forest Memory Match Game") is available in the App Store.  It took a little longer than I anticipated but it was well worth it.  

### Feb 23rd

I added in some Twitter Fabric - Answers code so I can track downloads and events.  I'm hoping to get a couple benefits from this update. 

1.  I can track app installs, so I'll be able to run an effective ad campaign on Twitter - paying for successful app installs instead of link clinks, which is pretty much a waste of money.
2. Fabric has some built-in events for games -> Level Start and Level End.  This is great to see how players are interacting within the game.

For the next update I'm going to track button clicks on my in-app purchase button to see if I can improve on the look of the purchase option & see what kind of conversion rate I'm getting.  

This update also include a tweak to the character reveal transition.  I added an animated pop to the character.
