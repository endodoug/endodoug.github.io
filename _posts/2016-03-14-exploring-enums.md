---
layout: post
title: "Exploring Enums in Swift"
date: 2016-03-14
author: Doug Harper
tags: [Tutorials, Swift, Enums, Dictionary]
published: true
---
I'm learning Enums in Swift are very powerful.  When I first started studying Swift, I blew by enums, just enough to recognize the syntax and get a general idea about how to use them.  As I learn more, it's obvious that enums are a great tool to be used in more situations than I imagined. 

## Using an Enum as a Dictionary

Dot notation and code completion in Xcode makes enums very convenient when creating dictionary keys.  First, I set up my enum...


    enum WeightClasses: String  [
      case Flyweight
      case Bantamweight
      case Featherweight
      case Lightweight
      case Welterweight
      case Middleweight
      case LightHeavyweight = "Light Heavyweight"
      case Heavyweight
    ]

I used a string literal for `case LightHeavyweight = "Light Heavyweight"` for spacing between the words.

Next, I created an array of dictionaries using my WeightClasses enum as the key for the values. 

    let mmaWeightClasses: [[WeightClasses: Int]] = [
      [.Flyweight: 125],
      [.Bantamweight: 135],
      [.Featherweight: 145],
      [.Lightweight: 155],
      [.Welterweight: 170],
      [.Middleweight: 185],
      [.LightHeavyweight: 205],
      [.Heavyweight: 265]
    ]

Finally, I [loop through(Swift way)](https://www.hackingwithswift.com/swift2-2?utm_campaign=This%2BWeek%2Bin%2BSwift&utm_medium=web&utm_source=This_Week_in_Swift_78) the dictionary and print out something useful.

    for fighter in mmaWeightClasses {
        for (weightClass, value) in fighter {
           print( "\(value) lbs is the maximum weight for \(weightClass.rawValue.lowercaseString)s")
        }
    }
    
![enum console image](/images/enum-console.png "weight classes")
