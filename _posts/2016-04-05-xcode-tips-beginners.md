---
layout: post
title: "My 3 Favorite Xcode Tips for Beginners"
date: 2016-03-28
author: Doug Harper
tags: [Demo, Swift, Admob]
published: false
---

Xcode is a great tool and there are many great tools/features to help you work efficiently.  Here are 3 of my favorite features that can help beginners learn a little quicker. 

## Quick Help Inspector

The quick help inspector is probably one of the most used features in Xcode.  Don’t overlooked it when you’re deep into learning mode and trying to figure out what your code is doing.  Just control click on an object in your code to get the quick help popup. Beginners may not understand all of the description jargon, but it’s always useful to see the declaration and declared-in values.  **Pro tip:** Command + Option click to open a declared-in: file in the assistant editor.

## Distance Between Objects in Interface Builder

I’m obsessed with proper alignment, even when working on a simple example app… maybe I should have been a designer.   Interface Builder has a few alignment tools, but I find it easier/quicker to select an object an hold down the option key to find the distance between to other storyboard objects. 

![Find the distance between objects](/images/optionDistances.gif "Xcode Interface Builder distances")

## Highlight Symbol In Scope

What in the world is _highlight symbol in scope_? It's feint underline you get when you click on a piece of code.   If you look closer you’ll see Xcode has also underlined all the relevant (more precisely, inscope) uses of that same code.  Beginners often struggle with `self`, at least I did, using this feature can help gain a better understanding of how `self` is being used in many situations - like this class init.   **Pro tip:** Control + Command E toggles to allow edit all at the same time.   
