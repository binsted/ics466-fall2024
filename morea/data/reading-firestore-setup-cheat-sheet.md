---
morea_id: reading-firestore-setup-cheat-sheet
morea_type: reading
title: "Firestore Setup Cheat Sheet"
published: True
morea_summary: "Minimal steps to setup Cloud Firestore for a new Flutter app"
morea_sort_order: 10
morea_labels: 
 - Firestore
---

# Firestore Setup Cheat Sheet

When you are just starting with Firestore, you should read and follow the instructions in the [Get to know Firebase for Flutter](https://firebase.google.com/codelabs/firebase-get-to-know-flutter#3) codelab, specifically steps 3 and 4.  These instructions include some one-time setup actions, such as installing the Firebase CLI.

Once you have successfully configured a Flutter app to work with Firestore, you might find it a bit faster to refer to this page, which detail the minimal steps to create a database with Email authentication.  There are just three steps:

## 1. Create the Firebase project

Go to the [Firebase Console](https://console.firebase.google.com/u/0/).

Click the "+" button to add a new project.

Enable (or not) Google Analytics.

In the Project Overview Pane, expand the Build menu, and click *Authentication > Get Started > Sign-in method > Email/Password > Enable > Save*.

Also in the Build menu, click *Cloud Firestore > Create database*.

Select *Start in Test mode*.

Click *Next* and select the database location.


## 2. Add libraries to your project

In the top-level directory of your project, run:

```
flutter pub add firebase_core firebase_auth cloud_firestore firebase_ui_auth
```

## 3. Configure your project

Also in the top-level directory, run:

```
flutterfire configure
```

This runs a configuration script that ultimately produces a `firebase_options.dart` file in your project.

Note that [API keys for Firebase are different from typical API keys](https://firebase.google.com/docs/projects/api-keys#api-keys-for-firebase-are-different) and thus the firebase_options.dart file can be committed to GitHub.
