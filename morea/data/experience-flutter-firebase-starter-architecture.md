---
title: "2. Experience the Flutter Firebase Starter Architecture"
published: true
morea_id: experience-flutter-firebase-starter-architecture
morea_summary: "Install and run the Flutter Firebase starter template"
morea_type: experience
morea_sort_order: 1
morea_labels:
- Optional
---

# 2. Experience the Flutter Firebase Starter Architecture

## Overview

For this experience, you will read through the [Starter architecture for Flutter and Firebase apps using Riverpod](https://codewithandrea.com/videos/starter-architecture-flutter-firebase/) tutorial, then download and run the template. 

### Install the sample system

Please start by making a fork of <https://github.com/bizz84/starter_architecture_flutter_firebase>, then downloading your copy to your computer.

Next, delete the top-level .firebaserc file. This file specifies that the firebase project associated with this app must be named "starter-architecture-flutter". Or, don't delete it, and make sure you name your firebase project "starter-architecture-flutter" in the next step. 

Next, create a cloud firestore project. Follow the instructions in Steps 3 and 4 of [Get to know Firebase for Flutter codelab](https://firebase.google.com/codelabs/firebase-get-to-know-flutter). You will end up with a Firestore database in 
"test mode" (which allows anyone to read or write from it), and an automatically generated firebase_options.dart file added to your project.

Now you should be able to build and run your fork. Check that you can add two news Jobs and several new entries on various dates so that you understand how data is represented and displayed.

### Do a walkthrough

Now, starting with the main.dart file, read through the source code to get an understanding of how the application works. Here are some questions to answer:

1. main.dart uses `UncontrolledProviderScope`. In a sentence or two, explain why? (For more information, see [Flutter Riverpod: How to Register a Listener during App Startup](https://codewithandrea.com/articles/riverpod-initialize-listener-app-startup/). 

2. The app puts all the code except main.dart inside the src/ directory. Is this is a good idea? Why or why not?

3. This app provides an example of using [go_router](https://pub.dev/packages/go_router). While you are not required to use go_router in this class, it is currently the "best practice" routing package for Flutter. You can start tracing the go_router code in app.dart to see a simple but realistic example. Do you think you want to use go_router in your own app? Why or why not?

4. There are four "Features": authentication, entries, jobs, and onboarding. For the purposes of this walkthough, just look at the "jobs" feature. What is the UI interaction that results in a job getting deleted?

## Submission Instructions

No submission required.
