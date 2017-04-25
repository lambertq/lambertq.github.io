---
layout: post
title:  "CSC 497B: Finding Success" 
date:   2017-03-02 16:00:00 -0500
categories: mario
---

## [](#header-2) I Have a Working Inventory!

It took me a few weeks, but I was able to bring together an inventory system that I am proud of. The problems that I was facing before, all seem so simple now that I have worked past them.

The first of these previous issues concerns the ability to have the items be draggable within the UI inside of the game. In order to create the system, I had to create a canvas object within the gameworld in Unity. The canvas object has a child panel object that stores each of the inventory slots. Which in turn will store the items held within those slots. This hierarchy is shown below.

![Concept-Art](/assets/images/menuheirarchy.png)

All of this is to say that the items that are held at the very bottom of this hierarchy need to be movable between each slot. To achieve this, I have added in a drag and drop system that dynamically changes this hierarchy based on which objects are in what inventory slot. 

The trick that held me back, was that I could get the inventory to visually update, but the hierarchy would refuse to update with the movement of the image. It took 3 weeks, but I was able to find a solution to this problem and its in one line of code: 


```c#
// C# code with syntax highlighting.
ExecuteEvents.ExecuteHierarchy<IHasChanged>(gameObject,null, (x,y) => x.HasChanged ());
```

While I do not fully understand this line of code, I do understand that it allows for me to have a fully updating hierarchy upon moving an image between all of the inventory slots. 

Every one of my attempts at getting this inventory system were close to working, I just needed the hierarchy to update. I can't believe that I finally got a working feature! I can finally move forward!
