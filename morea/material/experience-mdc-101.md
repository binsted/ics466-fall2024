---
title: "1. MDC Basics"
published: true
morea_id: experience-mdc-101
morea_summary: "Build a login page using several of MDC Flutter's components."
morea_type: experience
# morea_start_date: "2024-10-06"
morea_sort_order: 1
morea_labels:
  - Codelab
  - Optional
---

# MDC Basics

## Task

For this task, you will go through the [MDC-101 Flutter: Material Components (MDC) Basics](https://codelabs.developers.google.com/codelabs/mdc-101-flutter#0) Codelab.

There are a couple of modifications you need to make to the Codelab instructions for this class.

### Step 2: Set up your Flutter development environment

For this step, please create a private repo called "flutter_shrine" and clone it to your laptop. (Add a README file to make this process easier.) This repo will hold the code as you incrementally build the Shrine app during the four MDC tutorials.

You should already have Dart, Flutter, etc installed.

Make me a collaborator on that repo so I can view your work.

### Step 3: Download the codelab starter app

For this step, download the initial codebase for this tutorial as a zip file, extract it, then copy the contents of the "mdc_100_series" directory into your flutter_shrine directory. 

Next, open your flutter_shrine directory in IntelliJ IDEA. Then open the lib/main.dart file.

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-exclamation fa-xl"></i> **Notes**
<hr/>
* IntelliJ might ask if you want to open this project as a Dart project. Confirm.

* Next, invoke "Tools / Flutter / Flutter Pub Get" to install the library dependencies. In my case, IntelliJ wanted me to specify the location of the Flutter SDK.  I clicked on the pull-down menu and selected the lone entry. Not sure why IntelliJ couldn't figure that out by itself.
</div>

At the conclusion of this, you should be able to open the main.dart file, run the project in the simulator, and display the initial screen of the Shrine app (a logo plus the text "Shrine"). 

Once you can run the project from within IntelliJ, you are ready to continue with the Codelab.

### Codelab hints

Early on, the linter will want you to make the TextFields "const". If you do that, then you will run into errors later. So maybe ignore that recommendation at the beginning.

## Submission Instructions

No submission required.
