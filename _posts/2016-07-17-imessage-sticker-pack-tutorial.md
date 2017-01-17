---
layout: post
title: "iMessage Sticker Pack Tutorial"
date: 2016-07-17
author: Doug Harper
tags: [Tips, Tutorial, Xcode, apps, iMessage]
published: true
---

A Sticker Pack app is a great first project for any developer/artist to get started with iOS.  It’s simple way to get some experience with Xcode and see what it takes to get an app ready for the App Store.   Here’s how to make your own Sticker Pack for iOS 10, just like [Pocket Ninja](https://itunes.apple.com/us/app/pocket-ninja-stickers/id1130768510?ls=1&mt=8 "Pocket Ninja iMessage Stickers").

![iMessage Sticker Pack](/images/Jelly-Stickers.png "iMessage Sticker Pack on iPhone 6")

## Requirements
* [Xcode 8](https://developer.apple.com/xcode/ "Xcode") 
* Artwork
* [Apple Developer Account](https://developer.apple.com/programs/ "Apple Developer Account") - if you want to upload to the App Store 

## Prepare Your Stickers

Stickers come in 3 sizes small, medium, and large.  Currently, I was unable to mix the sizes within a single app, so you'll have to stick with one size for each project.  Here’s what Apple recommends in their documentation.

> Valid image files must meet the following specifications:
> 
> * The image must be a PNG, APNG, GIF or JPEG file.
> * The file must be less than 500KB.
> * The image cannot be smaller than 100 x 100 points, and can not be larger than 206 x 206 points.

> To best match the browser, use sticker images of the specified size. 

> * Small. 100 x 100 points.
> * Medium. 136 x 136 points.
> * Large. 206 x 206 points.

Keep in mind you’ll need to provide Xcode with @3x images, so you’ll be creating your  stickers at 300 x 300 px (small), 408 x 408 px (medium), 618 x 618 px (large) 

![iMessage Sticker in Sketch](/images/JellyStickers.png "iMessage Sticker in Sketch")

## Prepare Your Icon

For me, prepping my icons required more work than the actual stickers, the sizes are different than I’m used to.  A few are very small, so consider how your icon will look at a tiny size.  I made a Sketch template that you can download - [iMessage Sticker Icon Template](http://endodoug.github.io/download/iMessage-App-Icon-Template.sketch).  Just change the icon image and background color then export to your folder.

## Simple App

Now the easy part! Creating our Sticker Pack Application.

1. Open Xcode and choose Create a new Xcode project.
2. In iOS > Application choose Sticker Pack Application.
3. Name your application and hit the Create button.
4. Click on the Stickers.xcstickers workspace & open the Sticker Pack Folder.
5. Drag in the stickers you created and set the sticker size in the Attributes Inspector.
6. Open the iMessage App Icon. 
7. Drag in the icons you created, be sure to add any that don't autofill.
8. Build and Run!  

{% include youtubePlayer.html id="1WiEaqsSDQ8" %}





