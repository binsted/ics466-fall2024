---
title: "3. Experience Freezed"
published: true
morea_id: experience-freezed
morea_summary: "Modify the starter template to use Freezed"
morea_type: experience
# morea_start_date: "2024-10-06"
morea_sort_order: 1
morea_labels:
- Optional
---

# 3. Experience Freezed

## Overview

In Dart and Flutter, appropriate manipulation of data entities involves ensuring that they implement an "abstract data type" (ADT). In practical terms, it means that:
* Each instance should be immutable,
* There should be a correctly written `hashCode()` and `==` operators for instances.
* There should be a `copyWith()` method so that instances can be cloned. 
* There should be methods to convert an instance to JSON format (i.e. serialize), and create an instance from a JSON object (de-serialize). (This is necessary for storing instances in a database such as Firestore.) 

Implementing all of this manually is a hassle, and generally requires dozens to hundreds of lines of boilerplate code which is easy to get wrong and can create very subtle bugs. 

The Flutter "industry standard" for creating abstract data types is [Freezed](https://pub.dev/packages/freezed). It is a code generation facility, where you provide a kind of "top-level specification" of your data entity, run a command line script, and the Freezed package generates all of the code necessary for make your entity a true ADT.

There is a very small learning curve associated with Freezed, but it's really not very complicated and the results are definitely worth the investment in time to learn it. 

In this experience, you will read up on Freezed and then test your understanding by porting a couple of data types to use Freezed. 

## Tasks

### Background readings

To begin, please read all of the Readings in this module labeled "Freezed". You should also download and run the [Flutter_Riverpod_Freezed](https://github.com/philipmjohnson/flutter_riverpod_freezed) sample app, which provides working samples of the use of Freezed to create data model entities. (It also illustrates how to use Dio to retrieve data from an external API, which is pretty sweet.)

Once you feel somewhat comfortable with Freezed, it's time to test your understanding.

### Update the Starter Architecture's Entry and Job to use Freezed

In the last experience, you made a personal fork of the `starter_architecture_flutter_firebase` repo.

For this experience, please create a branch in your fork called "freezed", and then update the code for the Entry and Job data model classes to use Freezed rather than Equatable.

Here are some tips:

* You will have to install the Freezed packages. See <https://pub.dev/packages/freezed#install>.   Note that you may get incompatible version errors when running `pub get`. To fix that, you have to change some of the riverpod-related package version specifications in pubspec.yml from something like `^2.5.1` (which basically pins to version to 2.5) to something like `">=2.5.1"` (which says *any* version greater than 2.5. Note the use of quotation marks!)

* You will see references to Dart language constructs such as `mixin`. As always, if you come across an unfamiliar language construct, take a second and look it up! 

* The classes to convert are Entry and Job.

* You can use the Firestore Database console to see that your Freezed versions are storing and retrieving the same data format as the original version using Equatable.


## Submission Instructions

No submission required.