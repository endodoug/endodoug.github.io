--- 
layout: post
title: "Journal Notes - Feb. 29, 2016"
date: 2016-02-29
author: Doug Harper
tags: [Swift, Notes]
published: false
---

Goals: 
Code everyday
Start an original new project


Monday - blog post Preparing for First iOS Job
Tuesday - updated and submitted MMA Quotes version 1.1 to App Store
Wednesday - coding fundementals of functions began working on Food Truck interactive book
Thursay - coding fundamentals of classes continued working on Food Trucks.
Friday - struggled with adding travis to my github acct. 
Saturday - Coding Fundamentals videos
Sunday - coding excercises variadic parameters

March 2, 2016 - coding fundamentals of arrays. `append(_:)` adds an element to the end of an array.  Arrays are ordered and have a set position.  When working with sets `insert(_:)` simply inserts an item into the set, there is no order.  Arrays allow duplication of elements, but sets do not... so if you could add the same string 1000 times, but the set would only contain it once.

Mar 3, 2016 - Dallas App Developersa meetup

March 8, 2016 - If you don't specify what a case is equal to the compiler automatically assigns a String of the same name 😎

`enum ColorName : String {
  case Black  = "Black"
 }` is the same as 
 
 `enum ColorName : String {
  case Black
}`

March 9, 2016 - Watched Swift2 Essentials on Lynda.com.  Added Alexandria to Awesome-Swift. Continued learning about Enums, Structs, Classes
Swift Std Library Team suggests you create a new model by designing the interface using a protocol first.

March 10, 2016 - Continued working on Enums, Structs & Protocols UFC Playground

March 11, 2016 - Finished up Enums and will do quick review after bedtime.

March 12, 2016 - Started UFC Demo Tutorial app. Set up storyboard and autolayout.

March 13 - 18, 2016 - Working on TaterTalk and continuing watching Swift2 Essentials
* `private` keyword makes the constant/variable private to the class which creates it.
* use `override init` to add instructions and initialize **custom classes**.
* when we create a custom initializer, we should also call the `init(coder aDecoder: NSCoder)` initializer. -> (coder aDecoder) Xcode will suggest with fixit.
* `UIImage.imageRenderingMode(.AlwaysTemplate)` lets you color an image in code.
* `edgeInsets` in UIKit are great for buttons that use image backgrounds
* `tableView.estimatedRowHeight` - set it to any positive number.  It will dynamically draw the row height to fit your content.  The more accurrate your estimate the less work the program will have to do.
* 
