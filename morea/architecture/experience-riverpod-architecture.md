---
title: "1. Refactor your app"
published: true
morea_id: experience-riverpod-architecture
morea_summary: "Refactor your app to use the Riverpod project structure"
morea_type: experience
morea_sort_order: 1
morea_labels:
morea_labels:
  - Optional

---

# 1. Adapt your app to the Riverpod Architecture

## Task

For this experience, please begin by carefully reading all of the Readings associated with this module. This will give you an excellent overview of architectural considerations for mobile apps in general and Flutter apps in particular. The author presents a particular architecture, which he calls the "Riverpod Architecture".

To begin this process, the goal of this experience is to refactor your code base to conform to the structure presented in [Flutter Project Structure: Feature-first or layer first](https://codewithandrea.com/articles/flutter-project-structure/). 

What you'll notice is that the current AGC mockups (for example) basically implement a "layer-first" project structure.  Presuming you followed this example, then your FTW app does as well. 

So, you'll want to change your app architecture to "feature first". (If you somehow followed a feature-first strategy to begin with, then you'll not have much to do for this experience!)

## Example: AGC Mockup (Phase 4)

For an example of how this might look, see [Flutter AGC Mockup 4](https://github.com/philipmjohnson/flutter_agc_mockup_4_f23). This app is functionally equivalent to Mockup 3, but the lib/ directory has been reorganized. Here's an excerpt illustrating the basic structure:

```
lib/
  app.dart
  main.dart
  features/
    authentication/
    chapter/
    common/
    :
    user/
      data/
        user_providers.dart
      domain/
        user_db.dart
      presentation/
        user_avatar.dart
        user_card_view.dart
        users_view.dart
```

The basic idea is:
  * Most of the code is now organized into "features".
  * Features often correspond according to entities in the data model. There is also a feature called "common", for UI elements that aren't really features and occur in many places (in this app, the only "common" element is drawer.dart).
  * Each feature can have one or more of the following subdirectories:
    * A `data/` directory (containing the Provider declaration), 
    * A `domain/` directory (containing the DB and entity classes), and 
    * A `presentation/` directory (containing the various UI widgets associated with the feature)
  * There is no `repository/` layer, since we don't yet have a backend database.
  * There is also no `application` layer, since we do not need to multiple service paths to any entity.
  * Notice that the presentation layer accesses the data layer (i.e. the Riverpod providers) in order to obtain access to entities in the domain layer. 


You will find the IntelliJ IDEA "Move File" command under the refactor menu to be very useful in this process! I suggest you only move file at a time. 

In most cases, you are simply moving a file into a different directory. The exception is the Riverpod Provider declarations: they need to be extracted from the "DB" file and put into their own file in the data/ directory.

There is an annoying tendancy of Flutter to not let you create new subdirectories within the lib/ directory. To fix this, see [this stackoverflow answer](https://github.com/flutter/flutter-intellij/issues/2539#issuecomment-894648191).

## Hints on how to do this

This is a difficult task to decompose into subtasks and accomplish in parallel.  Instead, I suggest you:

* Decide upon a two hour block of time for the entire team to get together;
* Before this meeting time, everyone should have completed whatever task they are currently working on and have merged the results into main. 
* By the meeting time, the main branch should be working and (relatively) error free.
* By the meeting time, everyone should have read through the readings so they understand what needs to happen.
* At the start of the meeting, order pizza and drinks or whatever. Make it fun.
* Appoint someone as the "driver" who will do the typing, and who will start refactoring the code into a new set of directories according to the advice of the "viewers". The driver shouldn't have to think--they should just do whatever the rest of the group tells them to do. Maybe switch out the "driver" every 15-30 minutes so everyone gets a turn. (If you want to work at your own laptop, then just commit the intermediate results to main so you can transfer the code snapshot over to your laptop easily.
* At the end of the meeting, the system should be running the same way it was before, but now the code is reorganized. You should have also eaten all the pizza.

## Submission Instructions

No submission required.
