---
layout: post
title: "Alt-U Day One Recap"
date: 2016-09-12
author: Doug Harper
tags: [Alt-U, iOS, Swift]
published: true
---

It's been a couple weeks since I attended [Five Pack Creative's Alt-U iOS Journeyman](http://www.fivepackcreative.com/ios-journeyman/ "Alt-U iOS Journeyman") course and I want to revisit some of the material and keep it fresh in my mind.  Writing it down helps me more than just reading over it.  

## Alt-U Day One

We started off talking about what it takes to move from an apprentice iOS Developer to a journeyman... the ability to take an idea and turn it into an app.  Tons of changes can happen along the way so the best way to handle all the change is through  an agile/iterative process:

- Define requirements 
- Develop to the requirments - breaks down big tasks to small pieces
- Deliver what you develop
- Communicate clearly and gather feedback
- Use feedback to generate additional requirements 

This is called an iteration and can be repeated as needed until you decide the product is ready to ship.  To add some predictability to the process you introduce SCRUM: 

- **Story** or User Story (requirements) - describes a feature or expectation of functionality. Keep it small.
- **Acceptance Criteria** - important part of any good story, details exactly what is needed (tested) for the story to be completed.
- **Epic** - a story that is too large to work on.
- **Backlog** - a list of stories for a project, should probably be prioritized.
- **Sprint** - prioritize backlog stories are added to a sprint, which is a well defined period of time.
- **Points** - arbitrary team measurement of the story's difficulty.  Points are used to determine the amount of work a team is likely to complete.  Does not necessarily equate to hours of days.
* **Velocity** - measures points over time to help business plan a release date.

Start writing stories from what can be seen (design, description, etc...), talk about assumptions to get a clear picture of what to develop. Set up a sprint that includes some functionality, deliver it, start the feeback loop and repeat until you have a completed product.

Next we reviewed and discussed Git version control.  Everyone in the class had a good enough working knowledge so we didn't go into great detail, but we spent some time covering the pro's and con's of using rebase.  FivePackCreative uses BitBucket and Tower for version control, but I was using the Source Control built into Xcode without issue.  

> Tip - Stashes are useful for new ideas that may not be implemented at the current time, but worth saving for the future

## Flickr Feed Project

We started building a photo viewing project to implement all the topics we're covering.  Jerry took time to walk us through the first part, of what turned out to be an awesome app, using SCRUM methodology.  We set up a collection view and went to town covering a lot of ground:

- Autolayout - autosizing cells
- Type Alias
- Helper functions
- Segue identifier enums and how to implement them. 
- GCD - Grand Central Dispatch
- Guard lets - used often, much more than if-let

### Autolayout Lab - Autosizing Cells in Collection View

Set up a CollectionViewController and create a UICollectionViewController class for it.  I also created a custom UICollectionViewCell class where I set up IBOutlets for my content.  Make sure to set these classes correctly on the Storyboard.  Next, add constraints and make sure the dynamic items (text label) are constrained to all sides of the cell - **that's the key**.  Finally, add in estimatedItemSize in ViewDidLoad to trigger autosizing -> 

    guard let cvl = collectionViewLayout as? UICollectionViewFlowLayout else {return print("nothing happening")}
    cvl.estimatedItemSize = CGSize(width: 100, height: 100)

I also practiced using a guard here, adding in a custom error message is one of the big advantages over the if-let syntax. As noted, I noticed Jerry and Chris used guard statements often throughout the course - more than other tutorials I've seen.   These autosizing cells are great and this is just a starting point for building some cool layouts. 

### GCD 

I began this topic with zero knowledge and a little intrepidation, because it seemed complicated.  The work we did in the playground was very helpful in understanding the theory and application.  Although it can get complicated in certain situations, generally it's not difficult.  

iOS has global queues that execute every task, which you can use directly.   Always update UI (main thread) from background thread.  Not doing so can cause unpredictable errors that are difficult to deal with. 

     extension Photo {
        class func getAllPhotos() {
            DispatchQueue.global(qos: .userInitiated).async {
                go get photo data
            }
            DispatchQueue.main.async {
				completion(photos, nil)
			}
        }
    }

#### You can create your own Queue's:

1.  Specify a label, which will become useful when debugging.
2.  Serial is the default value, but you can specify concurrent
	- **Serial** is one job at a time.
	- **Concurrent** is multiple jobs at a time.
	 

			let myQueue = DispatchQueue(label: "com.myCustomLabel", qos: .userInitiated, attributes: [.serial], autoreleaseFrequency: .inherit)

Now we can dispatch work asynchronously or synchronously:

1.  **Asynchronously** - sends work to be done and continues on - does not wait for result.
2.  **Synchronously** - waits for work to complete before continuing (be careful here)
 
		myQueue.async
		myQueue.snyc

### Enum for Segue.identifier

We set up an enum for segue identifiers when you need to have multiple segues from an object.  I am currently working on a project (Mobius Sales App) where this makes a lot of sense.  

	private enum SegueIdentifier: String {
		case goToMyDetailViewController
	}

Now use a switch in prepareForSegue.  May seem like extra work at first, but if you may be expanding it could save time and it looks pretty cool.

	override func prepare(for segue: UIStoryboardSegue, sender: Any?) {
		guard let identifier = segue.identifier else { return }
		guard let segueIdentifier = SegueIdentifier(rawValue: identifier) else { return }
		
		switch segueIdentifier {
		case .goToMyDetailViewController:
			let controller = segue.destination as! MyDetailViewController
			let cell = sender as! PhotoCell
			controller.photoToShow = cell.photo
		}
	}



### Tips in Day One
- `PlaygroundPage.current.needsIndefiniteExecution = true` keeps the page executing. This allows code to run when it depends on something else happening, because the playground may stop executing before our code runs.
- `PlaygroundPage.current.finishExecution()` stops the execution.
-  Git Stashes are useful for new ideas that may not be implemented at the current time, but worth saving for the future.

