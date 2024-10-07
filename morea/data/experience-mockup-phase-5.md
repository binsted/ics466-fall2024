---
title: "4. Make Your App"
published: true
morea_id: experience-mockup-phase-5
morea_summary: "Create a Firebase backend for your app"
morea_type: experience
# morea_start_date: "2024-10-06"
morea_sort_order: 1
morea_labels:
- Optional
---

# 4. Make your app

## Task

For this task, you will make your mockup less like a mockup and more like an "alpha" version of your application by connecting it to a Firestore backend. 

To accomplish this, you will need to do the following:

* Create a Firebase project for your app, and install the Firebase dependencies. You might find the [Firestore Setup Cheat Sheet](reading-firestore-setup-cheat-sheet.html) to be useful.
* Create an "authorization workflow" so that only authenticated users can access data. You might find the [Flutter Firebase Auth Example](https://philipmjohnson.org/flutter_firebase_auth_example/api/index.html) system to be useful. 
* Use Freezed to create data model classes.
* Store and retrieve data using Firebase. 
* Initialize your database using Firefoo.

One issue you will confront is how to deal with the "sample" data you have been using to enable your mockup to exhibit a realistic look and feel. Here's how I did it.

1. I created entity classes using Freezed for each data model item.
2. I created a json file in the assets/initialData folder containing sample data in json format.
3. I created a function to read the json file and generate entity instances from them. This checked to see that my Freezed definition and my json files were consistent. Almost every one of them initially failed this test!
4. Once I had json files that could be used to correctly generate my Freezed entities, I used FireFoo to create collections in Firebase and create a set of documents corresponding to those json file. 

Now my mockup Firebase database is initialized with data that can be represented locally using my Freezed data entity classes. 

### An Example: The Phase 5 AGC mockup app

To get a sense for what you're aiming for, please check out [Phase 5 Flutter Mockup of the Agile Garden Club app](https://github.com/philipmjohnson/flutter_agc_mockup_5).  


## Submission Instructions

No submission required.
