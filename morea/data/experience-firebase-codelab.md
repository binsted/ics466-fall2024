---
title: "1. Experience the Firebase Codelab"
published: true
morea_id: experience-firebase-codelab
morea_summary: "Learn how to use Firebase with Flutter."
morea_type: experience
morea_sort_order: 1
morea_labels:
  - Codelab
  - Optional
---

# 1. Experience the Firebase Codelab

## Task

For this experience, you will go through the [Get to know Firebase for Flutter](https://firebase.google.com/codelabs/firebase-get-to-know-flutter#0) Codelab and create a sample app for your personal library that documents this experience. 

The Codelab starts by having you clone the Flutter codelabs repo. Then, it directs you to work in this directory, editing the files to incrementally build the working application. For this experience, we want you to instead create a GitHub repo containing your work, and this requires a few modifications to the Codelab instructions.

## Modifications to the Codelab workflow

### Steps 1 and 2: Get the sample code

First, instead of doing all of the work in the flutter Codelabs repo, you will create your own personal repo to hold your work:

1. Create a new private GitHub repo called "flutter\_firebase\_codelab".
2. Clone this repo to your computer.
3. Instead of running `git clone` to obtain Flutter codelabs repo, go to <https://github.com/flutter/codelabs>, click the green "Code" button, and select "Download zip".
4. Unzip the codelabs-main.zip file, find the firebase-get-to-know-flutter/step_02 subdirectory, and copy it into your flutter\_firebase\_codelab directory. (Be sure to copy the *contents* of the step_02 directory, not the directory itself!).
5. Run this code in the simulator to ensure that it works correctly.
6. Edit the "Firebase Meetup" string in the HomePage widget to include your initials. For example, "Firebase Meetup (PJ)". This helps you test that your installation is successful, and also verifies that you have done the codelab yourself.  

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Heads Up**
<hr/>

The analysis_options.yml file in your project consists of this line:

```
include: ../../analysis_options.yaml
```

Unfortunately, since you've copied the project files out of their original location, this line does not resolve correctly. To fix it, just find the analysis_options.yml file from the top level of the zip file and copy it into your project, overwriting this file.  

</div>

### Step 3: Create the Firebase Project

This step involves creation and configuration of a Firebase project. You can follow those instructions as written.

It took me a while to get the Firebase CLI installed correctly. On MacOS, I needed to add `$HOME/.pub-cache/bin` to my PATH (not `$HOME/flutter/.pub-cache/bin` as specified in the instructions).

### Step 4: Configure Firebase

Follow these instructions to install packages and create the firebase_options.dart file in your project.

You can skip the section "Configure MacOS".

I suggest that you commit and push your changes to your project at this point in the codelab, so that you have a working version to return to in case you run into problems below.

### Step 5: Add RSVP functionality

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Glitch 1: queryParameters not defined**
<hr/>

As you copy the code, you might find an error on the following line indicating that "queryParameters" is not defined.

```
final arguments = state.queryParameters;
```

This field variable was removed in go_router 10.0.0 (see [Migration Guide](https://docs.google.com/document/d/1vjupshmFJtfGSOppZxp7Tzkq7dotcLxCcpdluuNYe1o/edit?resourcekey=0-aS66t4OcDTjJW50s-veSzQ))

As suggested in the Migration Guide, I ran `dart fix --apply` and the error was removed.
</div>

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Glitch 2: Podfile out of date**
<hr/>

When I tried to run the code on the iOS simulator after making the changes in this section, I got a "podfile out of date" error.  As suggested in the error message, I ran "pod repo update" inside the ios/ directory which fixed things. 
</div>

Once you get to the end of this section and verify that your app handles authentication correctly, commit your working code to GitHub as a checkpoint. 

### Steps 6-10

I was able to follow the instructions and complete the codelab without any additional shenanigans.

I suggest you commit your code at the completion of each step just to provide a working place to return to.

## Submission Instructions

Submission not required.
