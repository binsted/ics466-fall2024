---
title: "5. Building layouts; Adding Interactivity"
published: true
morea_id: experience-flutter-building-layouts-adding-interactivity
morea_summary: "Build a Campground app to learn about layout and interactivity."
morea_type: experience
morea_sort_order: 1
morea_labels:
  - Tutorial
  - Optional
---

# Building layouts; Adding Interactivity

<div class="alert alert-success" role="alert" markdown="1">
<i class="fa-solid fa-circle-check fa-xl"></i> **Questions? We have answers.**

If you run into problems while doing this codelab, please post to the #codelab-questions channel in Discord.
</div>

## Task

This task involves going through two tutorials in sequence: [Building Layouts](https://docs.flutter.dev/development/ui/layout/tutorial) followed by [Adding Interactivity](https://docs.flutter.dev/development/ui/interactive).

At the conclusion, you will have built an app called "Campground" that looks like this:

![](https://github.com/philipmjohnson/flutter_example_screenshots/raw/main/README-campground-screenshot.png)

Note that this looks just like the tutorial page, except that the title has been changed to "Campground" and there is a new Text widget at the bottom to indicate authorship (i.e. "Developed by: Philip Johnson"). You will substitute your own name when you build this widget.

### Part 1: Building Layouts

For this experience, start with the following steps to initialize your development environment:

1. Create a private GitHub repository called "flutter_campground". 
2. Make me a collaborator so I can view your work.
3. Clone it to your laptop.
4. In the parent directory of that directory, run `flutter create --no-overwrite flutter_campground`.  This will produce the Flutter app skeleton at the top level of your GitHub repo.
5. Open that directory in IntelliJ.
6. Open the iOS or Android Simulator, then run the template code and see it in the simulator.

Now that you've established a working codebase and development environment, proceed with the [Building Layouts](https://docs.flutter.dev/development/ui/layout/tutorial) tutorial.

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-exclamation fa-xl"></i> **Notes**
<hr/>

Step 0:
* The default app created by "flutter create" is no longer exactly like the one in the tutorial. Just work around it.

Step 1:
* This is a good illustration of how to decompose a page mockup into its component rows and columns.

Step 2:
* At the conclusion of this step, you can now delete the StatefulWidget (MyHomePage) from main.dart.
* If you haven't figured it out already, command-option-L (reformat code) is a very useful key binding.

Step 5:
* Useful info on how to add an Image.

</div>

When you've finished this part, commit your code to GitHub.

### Part 2: Adding Interactivity

Now move on to the second tutorial, [Adding interactivity](https://docs.flutter.dev/development/ui/interactive).

After updating the app to include a StatefulWidget, there are some sections about "Managing State".  These sections are well worth reading, but you do not have to implement that code.

At the conclusion of this step, commit your changes to GitHub.

## Submission Instructions

No submission required.