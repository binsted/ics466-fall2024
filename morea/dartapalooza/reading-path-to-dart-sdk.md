---
morea_id: reading-path-to-dart-sdk
morea_type: reading
title: "How to find the Dart SDK path"
published: True
morea_summary: "IntelliJ wants this path. Here's how to find it (on MacOS)"
morea_sort_order: 10
morea_labels: 
---

# How to find the Dart SDK path

When you open your first Dart file in IntelliJ, it may ask for the path to the Dart SDK.

On MacOS, you should be able  'brew info dart' to get the path. In my case, it was: /opt/homebrew/opt/dart/libexec

Add that to the preferences pane for Dart, enable it for your project, you should be good to go.
