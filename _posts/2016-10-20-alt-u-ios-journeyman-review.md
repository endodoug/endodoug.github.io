---
layout: post
title: "Alt-U iOS Journeyman Recap"
date: 2016-10-20
author: Doug Harper
tags: [Alt-U, iOS, Swift]
published: false
---
![Alt-U](/images/Alt-U-Desk.jpg "Learning iOS and Swift at Alt-U")

It’s been almost 2 months since I attended [Alt-U’s iOS Journeyman Course](http://www.fivepackcreative.com/ios-journeyman/ "Alt-U Journeyman Bootcamp") and I’d like to take some time to write down a few thoughts about it. 

I’m self-taught, primarily studying Apple Documentation and [Ray Wenderlich](https://www.raywenderlich.com "RayWenderlich.com") tutorials.  I’ve been curious about bootcamps but nothing seemed to make sense in my current situation.  Fortunately, this opportunity presented itself and I was able to take advantage of it.  

The Journeyman course is *“designed for experienced programmers and iOS developers looking to go to the next level with iOS development and the Swift programming language,”* which is exactly where I was.  Turns out… some of the content was an insightful review, while other parts were difficult for me.  All in all, I’d say the curriculum was a great mix.

We had 3 instructors for a class of 8 students.  Niles Musgrave, Jerry Beers and Chris Griffith, all seasoned developers, were a great source of information and kept things moving along smoothly. As a group, we ran into couple bugs (Xcode 8 beta) which provided the unintended benefit of seeing how pros went about problem-solving.  A powerful teaching technique they utilized was Chris live coding, while Jerry pointed out details on the screen or taking trips down various rabbit holes.  For me it, it added extra insight and kept the focus on what we were doing - I often go code-blind when learning new material.

![Alt-U Instructors](/images/Alt-U-Instructors.jpg "Alt-U Instructors")

The process of transforming an idea into an app was an important big-picture focus of the Journeyman course.  I already had my own workable way of using GitHub and Trello, so it was comforting to see experienced programmers using similar methods.  One of my biggest takeaways was another big-picture sort of thing… overall app structure.  I’ve done tutorials and looked into tons of project files, but never get to see the how’s & why’s a certain file is implemented - everything is usually in the file navigator ready to go.  Jerry and Chris did a great job of explaining the thought process of each step as we moved along.

The course project was a Flickr Feed, it’s awesome, which required us to integrate some of the latest iOS 10 features.  I’m not going to rehash the all the coding, here're my [Alt-U Day One](http://endodoug.github.io/blog/alt-u-day-one "Alt-U Day One") notes to give you an idea.  You’ll see we covered a lot of ground, but I felt everything was discussed thoroughly and we mixed a couple labs.

Flickr Feed Day One Topics:

- Autolayout - auto sizing cells
- Type Alias
- Helper functions
- Segue identifier enums and how to implement them.
- GCD - Grand Central Dispatch
- Guard lets - used often, much more than if-let

GCD/Concurrency was covered thoroughly, we spent a lot of time learning/discussing/coding in a playground.  It’s a complicated topic and I’ve always been a little intimidated by GCD, but Jerry did an excellent job with the playground - it is crystal clear and will never leave my desktop. Our Flickr Feed project gave us several opportunities to implement what we learned here, in fact, we used it 4 out of the 5 days. 

Over the 5 days, I must have had 20 A-ha moments.  I immediately implemented 3 things I learned into a current project being developed for a local business: 

- Using a SafariViewController - saved me a lot of time.
- State Restoration - makes the app much more user-friendly.
- Constraint animations - added some cool points.

I should have come armed with more questions from apps I previously worked on.  There was plenty of opportunities to get help one-on-one with the instructors, who were more than happy to help us with our current projects *e.g. Jerry explained how an unwind segue would work for a particular situation in one of my apps and detailed why it was the best solution.* 

It was great to meet the other students, hear their stories and discuss iOS development.  In fact, this is a huge benefit Alt-U has over online courses.  It's motivating and inspiring to see other developers excited about learning iOS/Swift. 


