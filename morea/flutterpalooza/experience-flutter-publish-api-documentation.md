---
title: "3. Publish API documentation"
published: false
morea_id: experience-flutter-publish-api-documentation
morea_summary: "Learn how to create a public GitHub page that documents your Flutter app "
morea_type: experience
morea_sort_order: 1
morea_labels:
---

# Publish API documentation

## Task

Notes:
* https://pub.dev/documentation/gh_pages/latest/
* https://dart.dev/tools/dart-doc
* Note that "dart doc" takes almost a minute to run.
* https://dart.dev/guides/language/effective-dart/documentation#doc-comments
* pub global activate gh_pages
* Add export PATH="$PATH":"$HOME/flutter/.pub-cache/bin" to your profile
* flutter pub gh_pages doc
* Documentation is available at: https://philipmjohnson.org/flutter_startup_namer/api/
* Note that top-level page is the README.md file, followed by all libraries.
* Write documentation strings, see: https://dart.dev/guides/language/effective-dart/documentation#doc-comments
* Note you can put square braces around any Dart class name and "dart doc" will make it into a hyperlink. Sweet!

* Add some sort of signature to each sample app
* Rename the widgets when useful
* Add public and private doc comment strings.
* Delete the test directory because the template test does not work on this example.
* Explain use of flutter_screenshots repo for private repo API publishing.

* Generate documentation and commit your startup_namer project's documentation to github.
* Example: https://philipmjohnson.org/flutter_startup_namer/api/index.html

## Submission Instructions

No submission required.
