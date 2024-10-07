---
morea_id: reading-flutter-coding-tips
morea_type: reading
title: "Flutter coding standards"
published: True
morea_summary: "Initial tips for Flutter coding standards"
morea_sort_order: 10
morea_labels: 
---

#Flutter coding standards

Here is an initial set of best practices that I recommend as you get started doing Flutter development. More to come!

## Always use relative imports within the lib directory.

Let's say you are developing an app named 'foo' and you need to import a file from another directory. You could use "absolute" import as follows:

```
import 'package:foo/app/home/models/bar.dart';
```

Instead, use a "relative" import:

```
import '../../models/bar.dart';
```

One reason to do this is because much of the code you will develop during this class is intended to create for you a personal library of code that illustrates various behaviors and practices of use to you in future Flutter development (such as your final project). By using relative imports, you will be able to more easily "cut and paste" code from your personal library into your future projects.


## Don't hand-format code

Don't adopt a personal style for code formatting. Instead, use Option-Command-L (in IntelliJ) to format the code according to the "official" guidelines. It might not be exactly the way you prefer (it isn't for me), but you won't spend time on formatting, and the official approach is good enough.

Besides, if you are following my recommendations, your code will be formatted automatically on save anyway (in IntelliJ).
