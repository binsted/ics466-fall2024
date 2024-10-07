---
morea_id: inclass-dart-practice-2
morea_type: reading
title: "Dart Practice 2"
published: false
morea_summary: "Simple programming problems in Dart, part 2"
morea_sort_order: 10
morea_labels: 
---

# Dart Practice, Part 2

Divide into groups of 2. 

While everyone will use their own DartPad to complete these example exercises, you should work with your partner to write every line. Make it collaborative!

While ChatGPT can write the code for you in an instant, you are not being graded on the correctness of your solution or how quickly you can finish. In fact, you're not being graded at all.

Instead, the goal of this exercise is to get more fluent with writing Dart code by, well, actually writing Dart code.  It's the process, not the product, that counts today.

## 1. Set up DartPad

In the previous class period, you created an ICSCourse class with a enumerated type called CourseType that partitions the courses into a set of distinct types.

First, retrieve this DartPad (or else get a copy from a group member).

Second, each person should create a new DartPad and copy that code into it. 

## 2. Create ICSCourseDB

Third, add a new class to the bottom of the DartPad called ICSCourseDB. This class represents a collection of ICSCourses. It takes a list of ICSCourses in its constructor. It also includes a method called addICSCourse() that allows you to add additional courses to the collection after it's been created.  For example:

```dart
ICSCourse ics111 = ICSCourse(111);
ICSCourse ics691 = ICSCourse(691);
ICSCourseDB icsCourseDB = ICSCourseDB(courses: [ics111]);
icsCourseDB.addCourse(ics691);
print(icsCourseDB);
```

Could result in output like this:
```dart
<ICSCourseDB [<ICSCourse 111 CourseType.intro []>, <ICSCourse 691 CourseType.advanced []>]>
```

## 3. Create icsCoursesWithType

Fourth, implement a method in the ICSCourseDB class called icsCoursesWithType. This method takes a CourseType value, and returns a list of all the ICSCourse instances that are associated with that CourseType.

So, for example:

```dart
ICSCourse ics111 = ICSCourse(111);
ICSCourse ics691 = ICSCourse(691);
ICSCourseDB icsCourseDB = ICSCourseDB(courses: [ics111, ics691]);
List<ICSCourse> intros = icsCourseDB.coursesWithType(CourseType.intro);
print(intros);
```
would print something like this:

```dart
[<ICSCourse 111 CourseType.intro []>]
```
## 4. Create badICSCourses

Fifth, implement a method in ICSCourseDB called badICSCourses. This function returns a list of ICSCourses that are "bad" (according to some criteria of your own choosing based on the CourseType). 

So, for example:

```dart
ICSCourse ics111 = ICSCourse(111);
ICSCourse ics691 = ICSCourse(691);
ICSCourseDB icsCourseDB = ICSCourseDB(courses: [ics111, ics691]);
print(icsCourseDB.badICSCourses());
```

Might result in this output:

```dart
[]
```

In other words, for my implementation, there were no bad courses!

## 5. Save your DartPad as a GitHub gist

Once you've finished this exercise, it is convenient to save it for future reference.  This involves:

1. Create a public gist at GitHub.
2. Copy the code from your DartPad into the gist, and save it.

## 6. Raise your hands when you're finished.

Please let me know when your group is finished.
