---
title: "2. Implement a simple use of Riverpod"
published: true
morea_id: experience-riverpod
morea_summary: "Update your simple controller to use Riverpod"
morea_type: experience
# morea_start_date: "2024-10-06"
morea_sort_order: 1
morea_labels:
- Optional

---

# 2. Implement a simple use of Riverpod

## Task

In the last experience, we "hand-rolled" a controller using Flutter's [ChangeNotifier](https://api.flutter.dev/flutter/foundation/ChangeNotifier-class.html) class. 

It turns out that the Controller design pattern is so useful and important that the Flutter community has built a variety of frameworks using Controller to support the more general concept of "state management".  There are over 40 [Flutter State Management packages](https://fluttergems.dev/state-management/), but in this course we will focus on one: [Riverpod](https://riverpod.dev/). 

Riverpod has a lot of features to support advanced state management issues, but fortunately you can go a long way with just a couple of simple features.  And, as you'll see, using Riverpod results in code that is more simple than the equivalent using a hand-rolled Controller class! 

This experience involves two tasks. 

## 1. Review state management readings

First, carefully review the state management readings:

  * [Introduction to state management](https://docs.flutter.dev/development/data-and-backend/state-mgmt/intro)
  * [Managing (widget) state](https://docs.flutter.dev/development/ui/interactive#managing-state)
  * [Stateless and stateful widgets](./reading-state-widgets-videos.html)
  * [Flutter Riverpod 2.0: The Ultimate Guide](https://codewithandrea.com/articles/flutter-state-management-riverpod/)

## 2. Update your "Switch Color Controller" app to Riverpod

For this step, you'll make a copy of your flutter_switch_color_controller app and update it to use Riverpod.  

The basic steps are as follows:

1. Create a private GitHub repo called "flutter_switch_color_controller_riverpod" and clone it to your computer.
2. In the parent directory of that directory, run `flutter create --no-overwrite flutter_switch_color_controller_riverpod`.  This will produce the Flutter app skeleton at the top level of your GitHub repo.
3. Open that directory in IntelliJ.
4. Open the iOS simulator (on MacOS), then run the template code and see it in the simulator (iPhone 14 Pro Max). This just verifies that the template runs correctly.
5. Copy the lib/ directory from your original Switch Color Controller app into your new repo, and restart the application. You should now see your original app running. 
6. Convert this app to use Riverpod rather than a hand-rolled Controller class.

## Hints

Here are some suggestions on how to do the conversion:

* Update the title to "Riverpod Color Controller (<your initials>)"
* Update your pubspec.yml to include the latest version of flutter_riverpod as a dependency.
* Wrap the app with ProviderScope.
* The MyHomePage widget should extend ConsumerWidget.
* Create a StateProvider to maintain the current color, updating when the button is pushed.
* "Watch" your StateProvider within MyHomePage's build method.
* Update your StateProvider's state variable with a new randomly generated color when the FloatingActionButton is pushed.
* Delete the Controller file and all references to it in your code, since you don't use it anymore.
* Change the ColorWidget from Stateful to Stateless.
* Update your code's documentation to reflect the new approach.

## Submission Instructions

No submission required.
