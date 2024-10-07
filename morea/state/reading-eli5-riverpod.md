---
morea_id: reading-eli5-riverpod
morea_type: reading
title: "Explain Like I'm Five: Riverpod"
published: True
morea_summary: "Riverpod is simply a way of declaring 'super smart global variables'."
morea_sort_order: 10
morea_labels:
  - State
---

# Explain Like I'm Five: Riverpod

Explanations of Riverpod often involve lots of complicated jargon: "dependency injection", "reactivity", "prop drilling", etc. And, to be frank, there's a bit of a learning curve involved in learning how to set up Riverpod and access its capabilities. For folks just starting with Riverpod, the logistics of *how* to use it can distract you from *why* you're using it. Let's fix that.

Riverpod, in a nutshell, is a way to declare and manipulate "Super Powered Global Variables". I assume that, as a five year old, you already know what a global variable is---it's a variable that can be accessed from anywhere in your program. In the case of Riverpod Global Variables, they are actually only "almost" global. In general, they can be accessed from within any Widget, so in the case of Flutter applications, that's pretty much the same as "global".

So, given that we know what a global variable is, what makes the Riverpod version "super powered"?  To answer that, let's look at some Flutter pseudocode.

```dart
Widget build(BuildContext context) {
  List<Something> somethings = SomethingDB.getSomethings();
  return ListView(
           children: somethings.map((something) => ViewSomething(something));
           
}
```

The above code represents a situation that occurs all the time in Flutter. You have a Widget that displays a list of things. You need to get that list of things from someplace else in your program. So, you need to access a global variable! And in the above code, that's exactly what we do: we access the globally accessible variable `getSomethings` declared in the `SomethingDB` class.  (Technically, we invoke the function bound to the getSomethings variable to obtain a value to bind to the `somethings` local variable.)

So, that's all well and good, and works great as long as `getSomething` is accessing a list or value or anything that is never going to change for the life of the program. If you have a global variable that never changes for the life of your program, such as a variable that returns a string with your name as the author of the program, then there's no reason to use a Riverpod Global Variable, because its super powers are of no help in this situation.

But in many cases, you are going to need global variables which access values that *change* during the execution of your program. 

Let's look again at the above code.  What if the value returned by `SomethingDB.getSomethings()` might change during the execution of the program? What if it might change *while that widget is currently displayed*?  Now we are in trouble! Let's say we're building an app with a screen that a student keeps open in order to notify them when anyone in the class asks a question about their homework. We could try to write it just like the above code:

```dart
Widget build(BuildContext context) {
  List<Message> messages = MessageDB.getMessages();
  return ListView(
           children: messages.map((messages) => ViewMessage(message));
           
}
```

Here we have a global variable `MessageDB.getMessages` that gets the most recent set of messages from some sort of shared database. The problem is that once this screen is displayed, it won't get updated if a new message is put into the database. We could try to fix it like this:

```dart
Widget build(BuildContext context) {
  while (true) {
    List<Message> messages = MessageDB.getMessages();
    return ListView(
             children: messages.map((messages) => ViewMessage(message));
  }           
}
```

But that "solution" won't even work: we're creating an infinite loop in our program.

<div class="alert alert-success" role="alert" markdown="1">
<i class="fa-regular fa-rocket fa-xl"></i> **Riverpod Super Power #1: Reactivity**

A Riverpod Global Variable can watch a data source and rebuild a screen automatically whenever the data source changes.
</div>
 
Riverpod enables you to have your screen update automatically when new messages arrive by making tiny changes to your original code:

```dart
Widget build(BuildContext context, WidgetRef ref) {
  List<Message> messages = ref.watch(messagesProvider);
  return ListView(
           children: messages.map((messages) => ViewMessage(message));
           
}
```

This code has just two changes. First, the build method defines a second parameter `ref`. Second, that ref parameter is used to "watch" a Riverpod global variable called `messagesProvider`.  That `messagesProvider` variable will be declared in such a way that it returns the messages in the MessageDB (but we won't show that code here).

What's super cool is that this Riverpod `messagesProvider` variable can be written to monitor the database, and when the list of messages changes, it can tell Flutter to re-run this build method so that this screen will be updated with the latest message list, even if the user doesn't touch their app!

If Riverpod accomplished nothing else, this first Super Power might be enough to convince you to use it. But there are a few more Super Powers to mention.

<div class="alert alert-success" role="alert" markdown="1">
<i class="fa-regular fa-rocket fa-xl"></i> **Riverpod Super Power #2: Caching**

A Riverpod Global Variable doesn't necessarily re-compute its value each time it's accessed.
</div>

Let's say that you're doing your homework, and bouncing back and forth between the screen that displays the messages from your class, and other screens where you are actually doing your homework.

If your build method contains a line of code like `MessagesDB.getMessages()`, then each time you switch back to that screen, it needs to be built, which means the database would need to be called to get the messages, even if you just displayed that screen a minute or so ago and nothing's changed. 

This is not only wasteful, it can potentially cost you real money!  Some databases like Firestore charge you based upon the number of times data is read from (and/or written to) the database.  Depending upon how many users you have and how many messages you are displaying, a "non-super powered" implementation could increase how much you pay each month for the database.

Once again, a Riverpod Global Variable comes to rescue. When your build method replaces `MessagesDB.getMessages()` with `ref.watch(messageProvider)`, the `messageProvider` Riverpod Global Variable can "cache" the data that it computed the last time you called it, and return that instead of requesting data from the database again. This can not only save you money, but can also enable the screen to build much more quickly.

I don't have to show you any new code for this feature, because caching comes automatically with Riverpod Global Variables. (There are lots of mechanisms to control caching if you need them.)

<div class="alert alert-success" role="alert" markdown="1">
<i class="fa-regular fa-rocket fa-xl"></i> **Riverpod Super Power #3: AsyncValue**

When requesting data from external services, a Riverpod Global Variable provides an easy way to handle the three possible situations: loading, error, or data. 
</div>

The pain and potential of mobile apps is their ability to mash up data from internet sites that publish an "API", i.e. a way to request and receive data. Let's start with the potential. Perhaps your app needs to know the current weather: there's an API for that! Perhaps your app needs to find recipes: there's an API for that!  Perhaps your app suggests good recipes depending upon the current weather: just combine those two APIs!

Now let's turn to the pain. The problem with using APIs (and this includes back end databases) is that when you request data from an internet site, it takes an unpredictable amount of time for the site to give you back the data, and it might not even give you back data the data you requested. Perhaps the network glitched, or their site was down, or whatever. In general, whenever your users take an action that results in an API call, you need to keep your users updated about the status, which can be one of three situations:

1. **Loading**. Your app has made the request, and is waiting for a response. You generally want to show a spinning ball or some other animated graphic to let the user that your app hasn't died, it's just waiting.
2. **Error**.  Something went wrong and you're not going to be able to complete the request.
3. **Data**. You got the data back, and now your app can proceed and display whatever you want based on the data you requested and have now received.

The third Super Power of Riverpod Global Variables is their support for handling these situations using a class called `AsyncValue`. There is a [great article](https://codewithandrea.com/articles/flutter-use-async-value-not-future-stream-builder/) by Andrea Bizzotti that explains this super power in detail, so I am just going to show you two code snippets that illustrate the difference between handling this situation in regular Flutter vs. Riverpod's `AsyncValue`.

From Andrea's article, here's the kinds of shenanigans you have to go through if you're not using Riverpod:

```dart
StreamBuilder<Item>(
  stream: getItem(),
  builder: (context, snapshot) {
    if (snapshot.connectionState == ConnectionState.waiting) {
      // handle loading
      return const Center(child: CircularProgressIndicator());
    } else if (snapshot.hasData) {
      // handle data
      final item = snapshot.data!;
      return ListTile(
        title: Text(item.title),
        subtitle: Text(item.description),
      );
    } else if (snapshot.hasError) {
      // handle error (note: snapshot.error has type [Object?])
      final error = snapshot.error!;
      return Text(error.toString());
    } else {
      // uh, oh, what goes here?
      return Text('Some error occurred - welp!');
    }
  },
);
```

Yikes!  In contrast, here's the kind of code you can write using a Riverpod Global Variable (where our previous `messagesProvider` has been changed to return an `AsyncValue`): 

```dart
  Widget build(BuildContext context, WidgetRef ref) {
    final AsyncValue asyncValue = ref.watch(messagesProvider);
    return asyncValue.when(
      data: (messages) => ListView(
          children: messages.map((messages) => ViewMessage(message));
      loading: () => const Center(child: CircularProgressIndicator()),
      error: (e, st) => Center(child: Text(e.toString())),
    );
  }
```

Now our user interface will tell the user exactly what the situation is while doing a request, and because we're "watching" `messagesProvider` the UI will rebuild automatically whenever the situation changes (from loading to data or whatever).

BTW, Andrea Bizzotti has written a bunch of great courses and articles about Flutter, Riverpod, and more. For example, check out his tutorials at <https://codewithandrea.com/tutorials/>. 

<div class="alert alert-success" role="alert" markdown="1">
<i class="fa-regular fa-rocket fa-xl"></i> **Riverpod Super Power #4: Testing**

A Riverpod Global Variable makes it easy to "mock" a call to a database (or any other external service) during testing. 
</div>

At some point you might want to test your app.  During testing, connecting to a backend database (or any external API) is not desirable for several reasons:

1. Setting up a backend database and initializing its contents is usually time-consuming and complicated.
2. Accessing a backend database can really slow your tests down, making you less likely to run them. 
3. Some external APIs don't return the same thing each time for a given request, so are hard to use in testing. (For example, an API that returns the "current weather".)

Once again, Riverpod comes to the rescue by allowing you to override the implementation of any provider. Recall that you generally wrap your top-level widget in a Riverpod `ProviderScope` widget so that your widgets can access your Riverpod Global variables as follows:

```dart
void main() {
  runApp(
    ProviderScope(
      child: MyApp(),
    ),
  );
}
```

During testing, if you want to (for example) provide a mock implementation of the `messagesProvider` Riverpod Global Variable, you can easily do it as follows:

```dart
testWidgets('override messagesProvider', (tester) async {
  await tester.pumpWidget(
    ProviderScope(
      overrides: [
        messagesProvider.overrideWithValue(FakeMessages())
      ],
      child: MyApp(),
    ),
  );
});
```
As you can see, it's very easy to write a test in which you've instructed the testing framework to use a different implementation for a Riverpod Global Variable than the one you use in your production code.

#### Conclusions 

So, now that you understand the four major Super Powers of Riverpod Global Variables, should you take the time to learn and use Riverpod? After all, there are other Flutter packages for "state management" that seem to do a lot of what Riverpod can do. And sometimes they appear less complicated to use.

Trying to be as objective as possible, here is my answer:  while some packages can do some of what Riverpod can do in a somewhat simpler way, no package (currently) can do all of what Riverpod can do, as elegantly as Riverpod does it.

Therefore, if you want to "future proof" your application as much as possible, invest the time to learn Riverpod. If you don't, and if some other approach seems less complicated to you, then try that one out instead! You can always come back to Riverpod later if the other way doesn't work out for you. 
