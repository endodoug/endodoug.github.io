---
layout: post
title: "Create a Picker View with Enums"
date: 2016-03-21
author: Doug Harper
tags: [Tutorials, Swift, Enums, Picker View]
published: false
---

I’ve been working with enums for a couple weeks, learning how powerful and convenient they can be.  Here’s a quick example of a picker view that will be populated using and enum/array combination.  

I’m going to build an app that displays the top ranked UFC fighters in each weight class,  which you’ll choose with the picker.  This is what it will look like when finished.

gif image here

Let’s set up the storyboard first.  It will be a simple UIPickerView that transitions to a tableview that displays the results we select.

image here

Next, I set up the enum to include all the UFC weight classes.  Then create and array    using dot notation and autocomplete since that’s one of the great benefits we get from setting up enum.  We’ll use the array to set up the picker view options.  

image here

Code the picker view

image

Grab the data from a plist to display in the tableView.