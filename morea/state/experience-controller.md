---
title: "1. Implement a simple controller"
published: true
morea_id: experience-controller
morea_summary: "Read about controllers, and then assess your understanding by creating a simple app"
morea_type: experience
# morea_start_date: "2024-10-06"
morea_sort_order: 1
morea_labels:
- Optional

---

# 1. Implement a simple controller

## Task

The Controller is a foundational design pattern in Flutter, and so it is important that you have a good understanding of it.  Fortunately, it's not a hard concept to understand and use once you get the hang of it. 

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **What is the "Controller" design pattern?**
<hr/>

In Flutter, what I'm calling the "Controller" design pattern is actually a combination of two general design patterns:

1. The ["publish-subscribe" design pattern](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern). This is a design pattern in which one component can add a "listener" function to another component which will be invoked when an appropriate event occurs in the latter component. Flutter provides direct support for the publish-subscribe design pattern through the [ChangeNotifier](https://api.flutter.dev/flutter/foundation/ChangeNotifier-class.html) class.

2. The ["model-view-controller" (MVC) design pattern](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller). This is a design pattern in which the user interface ("view") reflects the state of an underlying database ("model") through an intermediary (the "controller"). 

In Flutter, the "C" in "MVC" has been generalized---you will often want to implement an "intermediary" between not just models and views but between any two kinds of widgets. And the design of this intermediary involves the publish-subscribe design pattern. 

</div>

This experience consists of two tasks. When you're done, you will hopefully have a good understanding of the Controller design pattern.

## 1. Review an existing controller app example

First, carefully read [Create a controller for a custom widget](https://www.flutterclutter.dev/flutter/tutorials/create-a-controller-for-a-custom-widget/2021/2149/).  

The source code for this example is available on GitHub. Fork the repo, download it, and make sure you can run the code locally and understand it.

Now that you've got that code under your belt, you can deepen your understanding with the next task.

## 2. Implement a "Switch Color Controller" app

For this step, start by reading [Write a controller on Flutter](https://jimmyleo.medium.com/write-a-controller-on-flutter-73286731a113).  The good news is that this example is much less complicated than the example in step 1. The even better news is that there is no sample GitHub repo for this example, only the snippets in the article. So, for this step, implement a GitHub repo with a fully functional Flutter app based on these snippets. 

The basic steps are as follows:

1. Create a private GitHub repo called "flutter_switch_color_controller" and clone it to your computer.
2. In the parent directory of that directory, run `flutter create --no-overwrite flutter_switch_color_controller`.  This will produce the Flutter app skeleton at the top level of your GitHub repo.
3. Open that directory in IntelliJ.
4. Open the iOS simulator (on MacOS), then run the template code and see it in the simulator (iPhone 14 Pro Max). This just verifies that the template runs correctly.
5. Starting with the snippets of code from the above article, create an app with: (a) a title bar containing your initials; (b) a colored box; and (c) a button that, when pushed, changes the color of the box.

A few notes on the implementation:

* The code in the article has a couple of minor bugs. They are easy to fix. 
* To help your understanding, make sure the "parent widget" (i.e., MyHomePage) is stateless. The default Flutter app creates a Stateful MyHomePage widget. Note that you can use option-return in IntelliJ and select "Convert to stateless" to make this change automatically!
* Here's how to obtain a random color: `Colors.primaries[Random().nextInt(Colors.primaries.length)])`.

## Submission Instructions

No submission required.
