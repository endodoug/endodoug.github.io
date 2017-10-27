---
layout: post
title: "Core Data Revisited"
date: 2017-10-26
author: Doug Harper
tags: [core data, swift]
published: true
---

Why revisit Core Data?  Early in my Swift/iOS learning I tackled Core Data and used it within MMA Quotes, but honestly... I didn't understand much of what was going on. I have a much better understanding of iOs now and jumped on an opportunity to go through Core Data again, which seems like good idea since it's an important part in so many apps.   

I'll be focusing on setting up Core Data on my own first and then working through the Xcode pre-baked version so I can contrast the two.  The typical use-case for Core Data Tutorials is always some kind of list, which is exactly what I'll be creating as a tableview.

## Data Model

The first step is a simple one.  Create a new Core Data > Data Model.  Then add an Entity & create an Attribute for the new Entity, pretty simple but that's a good start.  

![Core Data Entity & Attribute in Xcode](/images/coreDateEntityAttribute.png "Core Data Entity & Attribute in Xcode")

Xcode does a little work behind the scenes to create a couple hidden files that you are warned against altering.  These files/class are for the Entity and Attribute, so your work is done.  
<div class="note">
  <h5>Time Saving Tip</h5>
  <p>Now is a good time to do a project build and clean.  Repeat this tip often!</p>
</div>

## Saving to Core Data

This was way over my head the first time I was introduced to Core Data, but seems to make sense now.  I'm going to break it down to 3 steps, each with a few things to accomplish:

1. **Initialize the Core Data Stack**
 - create a `let persistentContainer = NSPersistentContainer(name: NSManagedObject)`.
 - load Persistent Stores `container.loadPersistentStores` -> the closure checks if stores are loaded correctly.
  
2. **Create an object to save**
 - create a context(sort of a scratchpad) `let context = persistentContainer.ViewContext`
 - create your object & insert into the context `let company = NSEntityDescription.insertNewObject(for EntityName: Entity, into: context)`
 - set the value you want save with the attribute key `company.setValue(nameTextField.text, forKey: "name")` 
  
3. **Save the Context**

       do {
        try context.save()
          } catch let saveErr {
            print("Failed to save company: ", saveErr)
            }
  
In most situations Intializing the Core Data Stack is done as a singleton in it's own file/class or within the AppDelegate.  When you chose to allow Xcode adding Core Data in your project, the stack will automatically be create at the bottom of the AppDelegate.

So far, I have just saved my object into Core Data. Next, I'll fetch it and do something with it.
  

