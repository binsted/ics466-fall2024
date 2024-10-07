---
title: "3. Make your Phase 3 App "
published: true
morea_id: experience-riverpod-mockup
morea_summary: "Update your mockup to use Riverpod for application state"
morea_type: experience
# morea_start_date: "2024-10-06"
morea_sort_order: 1
morea_labels:
- Optional

---

# 3. Make your App

## Task

Now that you have a little experience with Riverpod, let's push forward and start using it in your own application.  

There are three parts to this process:

1. Convert your current mockup to use Riverpod Providers to control access to your data model.
2. Implement a couple of interactive features so that application state can change will running the app.  You can decide for yourself what aspects of state you want to manage. Here are some suggestions:
  * Define some users, and "login" to the appropriate user when their email address is supplied in the login page. The application state thus includes the currently logged in user.
  * Create a page that allows you to add a new entity to your data model. 
  * Create a page that allows you to edit an existing entity in your data model.
3. Convert Settings to use Riverpod. (See below for details.)

If you are adding or updating data model entities, you'll need to learn how to create Forms. See the readings for Form documentation links. You might also find the [AGC Mockup Phase 3](https://github.com/philipmjohnson/flutter_agc_mockup_3_f23) app to be useful. 

Note that if you encounter a [CircularDependencyError](https://pub.dev/documentation/riverpod/latest/riverpod/CircularDependencyError-class.html), it's because you have inadvertently created a dependency loop in your data model. For example, data model X accesses the provider for data model Y that accesses the provider for data model Z that accesses the provider for data model X.  If this happens, you need to reorganize the structure of your data models so that this loop is no longer present.

## An Example: The AGC Phase 3 mockup app

To get a sense for what you're aiming for, please check out [Phase 3 Flutter Mockup of the Agile Garden Club app](https://github.com/philipmjohnson/flutter_agc_mockup_3_f23).  The major new features of this app include:

* All collections (i.e. the "DB" classes) in the data model are made available to the app as Riverpod Providers. This means that all of the StatelessWidgets are converted to ConsumerWidgets (and StatefulWidgets are converted to StatefulConsumerWidgets). Then a `ref.watch` function is used to obtain the DB instances and retrieve their contents.
* The ability to add and edit garden data using the Add Garden and Edit Garden pages. This provides example code to illustrate how to modularize form fields and buttons to facilitate reuse. It also makes the code much easier to read and understand, IMHO.
* The ability to login as any defined user by entering their email. The password field is not checked, you can leave it blank. The signin page updates the currentUserID Riverpod provider with the email of the defined user for access by the rest of the app. If you enter an email that is not associated with a defined user, the UI will let you know and not let you proceed to the Home Page.

Feel free to clone the Phase 3 mockup and run it locally to see how it works.

## Test your understanding: convert Settings to Riverpod

In addition to implementing some interactive features, your Phase 3 mockup must convert the Settings implementation from "Controller-based" to Riverpod.  Recall that the Settings page allows the user to switch between Light and Dark mode. This implementation was originally part of the "Scaffold" starter template, which didn't include any state management system. Now that we know about Riverpod, we can simplify the implementation of Settings. 

This should only take you a few minutes to accomplish, and will help reinforce your understanding of Riverpod and state management. Here are some hints:

* Use currentUserIDProvider in the AGC Phase 3 mockup as a model for how to use Riverpod to manage a new state variable called, say, currentThemeMode.
* Create a Provider that stores a single state variable (currentThemeMode).
* Update main.dart and app.dart to no longer reference SettingsController etc
* Change MyApp to be a ConsumerWidget and ref.watch the currentThemeMode provider to set the themeMode.
* Get rid of the AnimatedWidget wrapping the MaterialApp in app.dart. It is no longer needed.
* Update settings_view.dart to read the ThemeMode provider state value to get the current ThemeMode, and update the state value when it changes.
* Delete settings_controller.dart and setttings_service.dart as no longer necessary.
* Test that you can set the dark and light themes and they change appropriately.
* Notice that the app is now simpler: there is no need for a Controller or for an AnimatedBuilder

The AGC Phase 3 mockup example does not include this revision so that you cannot simply copy-and-paste the solution!

## Getting started with your Phase 3 mockup

You do not need to create a new repo for Phase 3. Just continue with your original repo. 

## Submission Instructions

No submission required.