---
morea_id: inclass-dart-practice
morea_type: reading
title: "Dart Practice"
published: false
morea_summary: "Simple programming problems in Dart"
morea_sort_order: 10
morea_labels: 
---

# Dart Practice, Part 1

Divide into groups of 2. 

While everyone will use their own DartPad to complete these example exercises, you should work with your partner to write every line. Make it collaborative!

While ChatGPT can write the code for you in an instant, you are not being graded on the correctness of your solution or how quickly you can finish. In fact, you're not being graded at all. 

Instead, the goal of this exercise is to get more fluent with writing Dart code by, well, actually writing Dart code.  It's the process, not the product, that counts today.

## Birthday cake

### 1. Birthday cake: Basic implementation

Create a class that represents a birthday cake. A birthday cake is created with a cake ingredient (carrot or flour), and a frosting (chocolate, vanilla). 
After a cake instance is created, it is possible to add an inscription ("Happy Birthday to Philip"). 

Hint: you can create this class in a null-safe fashion (i.e. no need to use the "?").

After you've created the class, write some code to exercise it. For example:

```dart
BirthdayCake cake = BirthdayCake(ingredient: "carrot", frosting: "chocolate");
cake.inscription = "Happy Birthday to Philip";
print(cake);
```

Ideally, this should print out something like:

```
<BirthdayCake (carrot, chocolate, Happy Birthday to Philip)>
```

### 2. Birthday cake: Calculate the price

Now, add a method to calculate the price of the cake that is derived from the chosen ingredient, frosting, and inscription. Then incorporate it into the string that is printed for a cake instance. For example:

```dart
BirthdayCake cake = BirthdayCake(ingredient: "carrot", frosting: "chocolate");
cake.inscription = "Happy Birthday to Philip";
print(cake);
  
cake = BirthdayCake(ingredient: "flour", frosting: "chocolate");
print(cake);
```

Would print out something like:

```
<BirthdayCake (carrot, chocolate, Happy Birthday to Philip, 18.00)>
<BirthdayCake (flour, chocolate, , 7.00)>
```

### 3. Birthday cake: Save as a public gist

Once you've finished this exercise, it is convenient to know how to save it for future reference.  This involves:

1. Create a public gist at GitHub.
2. Copy the code from your DartPad into the gist, and save it.

Now you can retrieve your code in DartPad using `dartpad.dev/?id=GISTID`.

For more details, see [How to create DartPad Examples from GitHub Gists](https://codewithandrea.com/tips/create-dartpad-from-github-gist/).

### 4. Birthday cake: Let me see your work

Once you and your partner have completed this exercise, raise your hands so I can check your work before your proceed on to the next step.

## ICSCourse

Let's switch to a different topic, ICS Courses.  You'll do this in a new DartPad. 

### 5. ICSCourse: Basic

Create a class that represents an ICS Course.  Each Course instance is created with a number (i.e. 111, 211, 466, 691).

Create an [enum](https://dart.dev/language#enums) to represent the course "type" called CourseType. Make up your own types. For example, "intro, advanced".  Or "easy, difficult, hard, brainfreeze".  Or "fun, boring, horrible".  

Create a method in your class called getType() which returns one of the CourseType enum values based upon the number.  Make sure that all possible integers return a type. Also, make sure that there is at least one course associated with all possible CourseType enum values.

After you've created this class, write some code to exercise it. For example:

```dart
ICSCourse ics111 = ICSCourse(111);
print(ics111.getType());
ICSCourse ics691 = ICSCourse(691);
print(ics691.getType());
```

This could print out (for example):

```dart
CourseType.intro
CourseType.advanced
```

### 6. ICSCourse: Support prerequisites

Add a field to your ICSCourse class that is a list of ICSCourses that represent prerequisities.  Prerequisites must have a number less than the number associated with the current course.  Provide a method called `setPrerequisites()`  that takes a list of ICSCourse instances, and sets the prerequisities field (if they are valid) or throws an error (if they aren't).  For example:

```html
ICSCourse ics111 = ICSCourse(111);
ICSCourse ics691 = ICSCourse(691);
ics691.setPrerequisites([ics111]);
print(ics691);
```

Might print something like:

```
<ICSCourse 691 CourseType.advanced [<ICSCourse 111 CourseType.intro []>]>
```

Whereas this:

```
ICSCourse ics111 = ICSCourse(111);
ICSCourse ics691 = ICSCourse(691);
ics111.setPrerequisites([ics691]);
print(ics691);
```


Would print something like:

```dart
Uncaught Error: Invalid argument(s): Invalid prereq.
```

### 7. ICSCourse: Save as a public gist

As before, please create a new gist to save your completed Dart exercise.


### 8. ICSCourse: Let me see your work

As before, raise your hands when you've completed this so I can check your work.


## End of class

At the end of the class period, each group will have an opportunity to present their course type definition. Karma points will be awarded to the most amusing type definitions.
