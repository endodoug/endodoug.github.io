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

![UFC Rankings Gif](/images/UFCRankings.gif "UFC Rankings")

## Set up the Storyboard

Let’s set up the storyboard first.  It's a simple table view (rankingsTableView) with a prototype cell sitting on top of my picker view (weightClasses).  I then embedded the view controller into a navigation controller and titled it UFC Rankings.   The last step is to make three connections

1. Set view controller as the rankingsTableView dataSource
2. Make an IBOutlet for the rankingsTableView -> `@IBOutlet weak var weightClasses: UIPickerView!` 
3. Make an IBOutlet for the weightClasses -> `@IBOutlet weak var rankingsTableView: UITableView!`

![UFC Rankings Storyboard Screenshot](/images/UFCRankingsStoryboard.png "UFC Rankings Storyboard Screenshot")

## Create an Enum and Array for the Picker View

Next, I set up the enum to include all the UFC weight classes.  Then create and array using dot notation and autocomplete since that’s one of the great benefits we get from setting up enum.  We’ll use the array to set up the picker view options in the next step.  

    enum WeightClasses: String {
        case Flyweight
        case Bantamweight
        case Featherweight
        case Lightweight
        case Welterweight
        case Middleweight
        case LightHeavyweight = "Light Heavyweight"
        case Heavyweight
    }
    
    let pickerDataArray: [String] = [
        WeightClasses.Flyweight.rawValue,
        WeightClasses.Bantamweight.rawValue,
        WeightClasses.Featherweight.rawValue,
        WeightClasses.Lightweight.rawValue,
        WeightClasses.Welterweight.rawValue,
        WeightClasses.Middleweight.rawValue,
        WeightClasses.LightHeavyweight.rawValue,
        WeightClasses.Heavyweight.rawValue
    ]


## Code the Picker View

Start off by creating a global variable to store the value we'll get when the picker row is selected.

`var pickerViewWeightClassSelection = WeightClasses.Flyweight.rawValue`

Now we need to conform to the UIPickerViewDataSource Protocol by extended the PickerViewController

    extension PickerViewController: UIPickerViewDataSource {
      func numberOfComponentsInPickerView(pickerView: UIPickerView) -> Int {
         return 1
      }
    
      func pickerView(pickerView: UIPickerView, numberOfRowsInComponent component: Int) -> Int {
          return pickerDataArray.count
      }
    }

The number of components is set to 1 and the number of rows is set to the count of the PickerDataArray.   Now the only thing left to do is populate the rankingsTableView with the data.  I added a FighterData.plist for this example, but it could easily come from url.  

Add another global variable to store the fighter data, I used an array.

`var fighterData = [String]()`

Now go to viewDidLoad() and load the plist data into the fighterData array

    let path = NSBundle.mainBundle().pathForResource("FighterData", ofType: "plist")
        let dict = NSDictionary(contentsOfFile: path!)
        
        fighterData = dict!.objectForKey(WeightClasses.Flyweight.rawValue) as! [String]


image

Grab the data from a plist to display in the tableView.
