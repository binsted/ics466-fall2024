---
title: "1. Make your App"
published: true
morea_id: experience-mockup-phase-1
morea_summary: "Create an app that illustrates some of the goals for your app"
morea_type: experience
# morea_start_date: "2024-10-06"
morea_sort_order: 1
morea_labels:
- Optional

---

# 1. Improve your app

## Task

It's time to stop simply following someone else's tutorial and begin writing your own Flutter code! For this task, your group will create an initial working version of your FTW app. The goals of this task are to:

* Improve your ability to write Dart code
* Improve your ability to implement Flutter widgets to create a UI
* Get more comfortable writing a Flutter app using IntelliJ idea
* Evaluate and improve your team process
* Start developing your project's public interface

<div class="alert alert-warning" role="alert" markdown="1">
<i class="fa-solid fa-circle-exclamation fa-xl"></i> **Slow going ahead!**
<hr/>
If you are like me, you are going to find this task to take much longer than expected. Figuring out every little thing, from how to pass arguments, to how to map over a list, is going to require looking up examples.  

My recommendation is that you work a little on this every single day. Think of it like you want to run a marathon but have never jogged more than a half mile before. You have to swap in this task consistently---every day for an hour or so if possible---and just grind it out.

The good news is that within a week, your comfort level with implementing new pages and UI elements will increase radically.

This is also a moment to evaluate your group process: are you communicating? are you helping each other out?  
</div>

### An Example: The AGC mockup app

To get a sense for what you're aiming for, please check out [Phase I Flutter Mockup of the Agile Garden Club app](https://github.com/philipmjohnson/flutter_agc_mockup_1_f23).  You can see that this mockup has:

* A signin and signup page, and about nine interior pages (Home, Gardens, Chapters, Outcomes, Seeds, Members, and Discussions).  
* A "Drawer" which pulls out from the left side and provides navigation to all of the top-level pages. 
* Only a few pages that are actually fleshed out with UI elements.  The remainder contain a textual description with documentation on what the page should accomplish.

Feel free to clone this repo and run it locally to see how it works. 

### Phase 1 app: the code

The Phase I AGC app has a fairly "standard" mobile app structure. This may or may not be appropriate for your FTW app.  

To get started with your app, one person should create a public repo in your project's organization called something like "app", clone it to your laptop, then use the flutter create command to generate the initial counter app. Then commit this code to the main branch. 

Once that initial code base is present, group members can start making branches to work on assigned tasks.

If you want to look at a different UI approach, you can download the [Wondrous](https://flutter.gskinner.com/wonderous/).

Third, if you are thinking about designing a serious game, then you might be interested in the [Flutter Casual Games Toolkit](https://flutter.dev/games).

Set as your goal to implement around a half dozen "pages" or "screens" that start to reveal the organization and features of your app. (The signup and signin screens don't really count!)  

You don't need to have any kind of back-end database for this mockup. Just hard-code the data directly into the source code for each page. If you want to show multiple "items", then just copy and paste the code and edit each copy slightly. 

### The project site

You should also get started implementing the project website, which will provide the public face of your project. To do this, create a second repo in your organization called `<organization>.github.io`, where `<organization>` is the name of your GitHub organization.  

The simplest way to implement this site is to create a top-level file called `index.md` that contains all of your documentation. Then use [GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages) to publish your documentation. 

If you want to invest more time and energy into the public face of your project, you could use a free documentation generator like [Docusaurus](https://docusaurus.io/). But this is not necessary for this class.

Regardless of which path you choose, your Phase 1 project documentation site should include the following:

* Motivation. This section explains why the project exists. What problem(s) is it hoping to address?

* Goals.  What are the desired capabilities of the technology? How can someone know if the project is helping to address the problem(s)?

* Usage.  This section provides an overview of the current status of the technology associated with the project. It should include screenshots for all implemented screens of the app.  Provide descriptive text with each screenshot and build a narrative. (This section will get progressively more detailed with each release of your app.) 

* Installation. This section should provide a link to the repo containing your code, and instructions on how to install and run it. (At this point, it's basically just download and invoke `flutter run`. Later, when there is a backend database, these instructions will become more complicated. Some projects may also need people to obtain API keys if you are using third party services such as Google Maps or weather services.)  Note that your repo, at this point, should be public. 

* Development status. This section should provide a link to your Project Board. 

* About us.  This section should introduce all of the team members. 

## Submission Instructions

No submission required.
