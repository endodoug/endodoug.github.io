---
layout: post
title: "My 3 Favorite Xcode Tips for Beginners"
date: 2016-03-28
author: Doug Harper
tags: [Demo, Swift, Admob]
published: false
---

Here are 3 of my favorite Xcode features that can help beginners learn a little quicker. 

## Quick Help Window

The Quick Help window/inspector is probably one of the most used features in Xcode.  Don’t overlooked it when you’re deep into learning mode and trying to figure out what your code is doing.  Just control click on an item in your code to get the Quick Help window. Beginners may not understand all of the description jargon, but it’s always useful to see the declaration and declared-in values.  **Pro tip:** Command + Option click to open a declared-in: file in the assistant editor.

## Distance Between Objects in Interface Builder

I’m obsessed with proper alignment, even when working on a simple example app… maybe I should have been a designer.   Interface Builder has a few alignment tools, but I find it easier/quicker to select an object an hold down the option key to find the distance to other storyboard objects. 

![Find the distance between objects](/images/optionDistances.gif "Xcode Interface Builder distances")

## Highlight Symbol In Scope

What in the world is _highlight symbol in scope_? It's a faint underline you get when you click on a piece of code.   If you look closer you’ll see Xcode has also underlined all the relevant (more precisely, in scope) uses of that same code.  Beginners often struggle with `self`, at least I did, using this feature can help gain a better understanding of how `self` is being used in many situations - like the class init below.   **Pro tip:** Control + Command E toggles to allow edit all at the same time. Thanks to [@ericasadun](https://twitter.com/ericasadun "Erica Sadun twitter") for this awesome tip.  

![Highlight Symbol in Scope](/images/HighlightSymbolInScope.gif "Highlight In Scope gif")

## Debug View Hierarchy

[Debug View Hierarchy is a powerful debugging tool](https://www.raywenderlich.com/98356/view-debugging-in-xcode-6 "View Debugging in Xcode"), but it’s also very helpful in visualizing exactly how your app is put together.   Go to the Storyboard and run your app.  Now look down at the bottom of Xcode, or just above the console if it’s open.  
     ![Debug View Hierarchy Menu](/images/DebugViewHiearchy.png "Debug View Hierarchy Menu")

Click on the Debug View Hierarchy and Xcode will present an exploded view of your app.

![Debug View Hierarchy](/images/debugHierarchy.gif "Debug View Hierarchy gif")

I hope you find one of these helpful. Please let me know if you have a favorite Xcode tip.
