---
morea_id: reading-customizations-intellij
morea_type: reading
title: "IntelliJ shortcuts and customizations for Flutter"
published: True
morea_summary: "Tips and tricks for improving Flutter development in IntelliJ"
morea_sort_order: 10
morea_labels: 
---
# IntelliJ customizations for Flutter

## Keyboard shortcuts

Here are several articles that discuss useful keyboard bindings to speed up Flutter app development in IntelliJ. Note that "Android Studio" is just IntelliJ with a specific set of plugins, so all of these apply if you are using IntelliJ Ultimate. 

There's some redundancy but I think each article has some unique recommendations:

* [IntelliJ/Android Studio Shortcuts for Flutter Development](https://codewithandrea.com/articles/intellij-keyboard-shortcuts-flutter-development/)
* [Flutter IDE Shortcuts for Faster Development](https://medium.com/flutter-community/flutter-ide-shortcuts-for-faster-development-2ef45c51085b)
* [11 Tips to improve your Flutter Development Productivity in Android Studio](https://www.syncfusion.com/blogs/post/11-tips-to-improve-your-flutter-development-productivity-in-android-studio.aspx) 

## Customizations

### Enable terminal

Enable Terminal in Preferences/Plugins, as it is disabled by default. Then the terminal icon appears in bottom of screen.  This provides an in-IDE terminal which defaults to the project directory location. Very useful.

### Disable "Apply official Kotlin Style" popup

IntelliJ has an annoying habit of popping up a notification to ask if you want to apply the official Kotlin style when you open a new Flutter project.  To get rid of this, go to Preferences/Appearance and Behavior/Notifications, find "Kotlin official code style available" and set the Popup type: to "No popup".

### Enable format code and optimize imports on save

Go to Settings-Languages and Frameworks-Flutter, and enable:
* Format code on save
* organize imports on save

### Allow directory creation within lib folder

By default IntelliJ does not provide a "Create directory" option inside the lib/ folder, which is horrible. To fix this, go to File - Project Structure - Module. Then click the lib/ directory and unmark it as sources. 

More information at: <https://github.com/flutter/flutter-intellij/issues/2539>

## Tips

### Always use relative imports within the lib directory.

Let's say you are developing an app named 'foo' and you need to import a file from another directory. You could use "absolute" import as follows:

```
import 'package:foo/app/home/models/bar.dart';
```

Instead, use a "relative" import:

```
import '../../models/bar.dart';
```



### Don't hand-format code

Don't adopt a personal style for code formatting. Instead, use Option-Command-L to format the code according to the "official" guidelines. It might not be exactly the way you prefer (it isn't for me), but you won't spend time on formatting, and the official approach is good enough.

Besides, your code will be formatted automatically on save anyway.
