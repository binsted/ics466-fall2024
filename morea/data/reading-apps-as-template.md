---
morea_id: reading-apps-as-template
morea_type: reading
title: "Using an app repo as a template"
published: True
morea_summary: "How to create a new application from a pre-existing codebase "
morea_sort_order: 10
morea_labels:
---

# Using an app repo as a template

Sometimes you might want to create a new app using a pre-existing codebase.  When the app connects to a Firebase database, this is a little bit complicated.  If you simply copy the old code, you will be referencing the old app name in various places, which creates strange behavior.


Here are the steps that I've found necessary when trying to create a new app based off of a pre-existing app:

1. Bring up the repo you wish to use a template in a browser, click on the "Code" button, and download a copy of the files from the main branch as a zip file.

2. Create your new repository in GitHub, and clone it to your local computer.

3. Use the `flutter create <appname> --overwrite` command to create a new Flutter app skeleton in your new repo.  Crucially, this skeleton will contain subdirectories referencing your new app name.

4. Copy the pubspec.yaml file from the expanded .zip file.  **Edit the name field to your new app name.**

5. Create the Firestore database. You can follow the [Firestore Setup Cheat Sheet](https://courses.ics.hawaii.edu/mobile-application-development/morea/data/reading-firestore-setup-cheat-sheet.html).

6. Initialize the Firestore database with sample data if desired. For further information, see these [instructions for uploading data to Firestore with Firefoo](https://courses.ics.hawaii.edu/mobile-application-development/morea/data/reading-firefoo.html).

7. Copy the `lib/` and `assets/` directories and the `analysis_options.yaml` file from the expanded .zip file into your new repo. Check for any compiler errors with this code and fix if necessary. Run Dart Analysis and fix any errors.

7. Run `flutterfire configure`.  See [FlutterFire CLI instructions](https://firebase.google.com/docs/flutter/setup?platform=ios#install-cli-tools) for details on how to run this command.

8. You should now be able to run the code in the simulator.  You'll need to re-register any users since you're using a fresh database, but if you uploaded sample data, it should appear. 
