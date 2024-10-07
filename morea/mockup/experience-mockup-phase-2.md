---
title: "2. Make your App"
published: true
morea_id: experience-mockup-phase-2
morea_summary: "Create a data model for your app"
morea_type: experience
# morea_start_date: "2024-10-06"
morea_sort_order: 1
morea_labels:
- Optional

---

# 2. Make your app

## Task

Since all of the data in your Phase 1 app was hard-coded into the source code for each page, it would be unwieldy to manipulate a significant amount of data in your UI. For the Phase 2 app, you will fix this by creating an internal "data model" in your application. So, the goals of this experience are: 

* Improve your ability to write Dart code
* Improve your ability to implement Flutter widgets to create a UI
* Get more comfortable writing a Flutter app using IntelliJ idea
* Evaluate and improve your team process

Notice that these goals are still exactly the same as Phase 1!  The creation of a data model doesn't require you to learn anything significantly new, but it does enable you to more easily create realistic looking pages and thus better understand what your app should do.

### An Example: The Phase 2 AGC app

To get a sense for what you're aiming for, please check out [Phase 2 Flutter Mockup of the Agile Garden Club app](https://github.com/philipmjohnson/flutter_agc_mockup_2).  The major new features of this app include:

* A `data_model` directory that contains five files: `chapter_db.dart`, `garden_db.dart`, `help_db.dart`, `news_db.dart`, and `user_db.dart`.   Each of these files implement a "table" (if you come from an SQL background in databases) or a "collection" (if you come from a noSQL background in databases).
* Each "db" file contains a class that represents a single entity in the data model (i.e. "row" or "document"), plus a class that encapsulates access to each entity and defines several of them. Finally, each "db" file creates a singleton instance of the encapsulating class, which is used by all clients to access individual entities and display them in the UI.  
* Every entity has an "id" field which is assigned a unique ID.  Entities refer to each other via IDs. 
* The pages in the application no longer hard-wire data into the source code. Instead, they access entity data from the data model and display this data.
* There are some additional pages in this mockup. For example, there is now a "help" page associated with several of the main pages that is accessed via a help icon in the upper right corner.  This is to illustrate that you should not only create a data model during Phase 2, but you should also continue to develop your UI.
* The `user_db.dart` file defines a variable called `currentUserID`.  This specifies the currently logged in user. You can change the value of this variable and restart the app to simulate what the UI would look like for different users.

Feel free to clone this repo and run it locally to see how it works. 

### Your app: the code

You do not need to create a new repo for this stage. Just continue with your original repo. You should find that creating a data model will help you to better understand your application and its information architecture.   

You still don't need your application to be "interactive"; there is no ability to add or edit information.

An important advance in your Phase 2 is that the screens should be populated with realistic data.  Now that you have a backend "database", you should put effort into figuring out what the app would display under production conditions, and populate your database accordingly. 

### The project site

If you did a great job on your project site, then the only updates to this site will be to include screenshots of any new pages you've implemented since then. 

## Submission Instructions

No submission required.