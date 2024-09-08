---
title: "3. Iterable Collections"
published: true
morea_id: experience-dart-codelab-iterable-collections
morea_summary: "How to use collections that implement the Iterable class—for example List and Set"
morea_type: experience
morea_start_date: "2023-08-30T23:00"
morea_sort_order: 1
morea_labels:
  - Codelab
---

# Dart Codelab: Iterable Collections

<div class="alert alert-success" role="alert" markdown="1">
<i class="fa-solid fa-circle-check fa-xl"></i> **Questions? We have answers.**

If you run into problems while doing this codelab, please post to the #codelab-questions channel in Discord.
</div>

## Task

### 1. Work through the Dart Iterable Collections Code Lab

For this experience, please go through the [Iterable Collections](https://dart.dev/codelabs/iterables) codelab.

During the codelab, you should use the embedded DartPad environment to execute the examples. 

Take your time, don't rush, and make sure you understand every line of code and every sentence in this codelab! Do all of the requested coding! If you have questions or get stuck, post a message to our Discord server.

### 2. Create a GitHub repo with the Email program

When you are done with the codelab, please do the following:

1. Create a private GitHub repository called "dart-email".  (Add a README to make it easier to clone using GitHub Desktop.)
2. Make me a collaborator so I can view your work.
3. Clone it to your laptop.
4. Run "dart create email" to create a template Dart application. 
5. Edit the email application to include the (corrected) code from the bottom of the final section of this codelab to process email addresses ("Putting it all together").  
6. Note: the code lab is missing the isValidEmailAddress method. You can use:
```dart
bool isValidEmailAddress(EmailAddress email) {
  return email.address.contains('@');
}
```
7. Edit the main() method to create instances of your EmailAddress class and exercise the functions you implemented to verify that they work correctly.
8. Run your application within IntelliJ IDEA to check your output. 
9. Commit your changes when finished. (I like to add a top-level .gitignore and ignore the .idea directory.)

Creating this repo provides evidence that you worked on this codelab, and gives you more practice using IntelliJ IDEA for Dart application development, which will be useful soon.

## Submission Instructions

By the date and time listed in the Schedule page, please submit the URL to your GitHub repo in Laulima.

Don't forget to make me (philipmjohnson) a collaborator so I can view your work!
