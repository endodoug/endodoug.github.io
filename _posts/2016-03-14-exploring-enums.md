---
layout: post
title: "Exploring Enums in Swift"
date: 2016-03-14
author: Doug Harper
tags: [Tutorials, Swift, Enums, Dictionary]
published: true
---
I'm learning enums in Swift are very powerful.  When I first started studying Swift, I blew by enums, just enough to recognize the syntax and get a general idea about how to use them.  As I learn more, it's obvious that enums are a great tool to be used in more situations than I imagined. 

## Using an Enum as a Dictionary

Dot notation and code completion in Xcode makes enums very convenient when creating dictionary keys. Xcode automatically assigns a String to each member (case) if you don't specify one. I used a string literal for `case LightHeavyweight = "Light Heavyweight"` for spacing between the words, it also makes a great example.  First, I set up my enum...


    enum WeightClass: String  [
      case Flyweight
      case Bantamweight
      case Featherweight
      case Lightweight
      case Welterweight
      case Middleweight
      case LightHeavyweight = "Light Heavyweight"
      case Heavyweight
    ]


Next, I created an array of dictionaries using my WeightClass enum as the key for the values. 

    let mmaWeightClasses: [[WeightClass: Int]] = [
      [.Flyweight: 125],
      [.Bantamweight: 135],
      [.Featherweight: 145],
      [.Lightweight: 155],
      [.Welterweight: 170],
      [.Middleweight: 185],
      [.LightHeavyweight: 205],
      [.Heavyweight: 265]
    ]

Finally, I [loop through(Swift way)](https://www.hackingwithswift.com/swift2-2?utm_campaign=This%2BWeek%2Bin%2BSwift&utm_medium=web&utm_source=This_Week_in_Swift_78) the dictionary and print out the results using the `.rawValue` & `.lowercaseString` to return the string literals and format them.

    for fighter in mmaWeightClasses {
        for (weightClass, value) in fighter {
           print( "\(value) lbs is the maximum weight for \(weightClass.rawValue.lowercaseString)s.")
        }
    }
   
~~~~~~~    
125 lbs is the maximum weight for flyweights
135 lbs is the maximum weight for bantamweights
145 lbs is the maximum weight for featherweights
155 lbs is the maximum weight for lightweights
170 lbs is the maximum weight for welterweights
185 lbs is the maximum weight for middleweights
205 lbs is the maximum weight for light heavyweights
265 lbs is the maximum weight for heavyweights
~~~~~~~

## Extensions and Protocols

You can add some versatility be creating a another enum this time with associated values.  

        enum UFCWeightClass {
            case Named(WeightClass)
            case Weight(Int)
        }
        
Then add an extension to conform to the `CustomStringConvertible` which uses a computed property to print out an string.

        extension UFCWeightClass: CustomStringConvertible {
            var description: String {
            switch self {
            case .Named(let weightClassName):
            return weightClassName.rawValue
            case .Weight(let pounds):
            return String(pounds)
                }
            }
        }
        
        print(UFCWeightClass.Weight(125))
        print(UFCWeightClass.Named(.LightHeavyweight))

~~~~~~~
125
light heavyweight
~~~~~~~

Why not add one more extension with an initializer to cover cases where we need to include a catchweight bout.

        extension UFCWeightClass {
            init(catchweight: Int) {
            self = .Weight(catchweight)
            }
        }

~~~~~~~
let catchweight = UFCWeightClass.init(catchweight: 160)
print(catchweight)
~~~~~~~
