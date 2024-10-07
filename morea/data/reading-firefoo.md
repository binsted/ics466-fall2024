---
morea_id: reading-firefoo
morea_type: reading
title: "Initializing your Firestore database with Firefoo"
published: True
morea_summary: "Firefoo is a GUI client for Firebase Firestore that simplifies database initialization from JSON files. "
morea_sort_order: 10
morea_labels: 
 - Firestore
---

# Initializing your Firestore database with Firefoo

During mockup development, it is common for your data model to evolve significantly as you discover new requirements for your domain.  You might add, delete, or rename collections, as well as add, delete, or rename the fields associated with the documents in any particular collection. 

To facilitate this evolution, it is nice to be able to:

1. Create sample collections and documents in JSON format that illustrate your data model with realistic examples.

2. Be able to initialize your Firestore database with your sample data model, and re-initialize your database with a revised version of your sample data after you evolve it in some way. 

Firebase has a browser-based [console](https://console.firebase.google.com/u/0/) which makes it easy to delete individual documents and even entire collections.  What it does not have, however, is a simple way to upload a JSON file to initialize the contents of a collection.

It turns out that there is a third-party tool, [Firefoo](https://firefoo.app/), which does have this capability.  

For this class, you will be able to use Firefoo to do this initialization. (Licensing information will be provided separately.)

The following set of screens illustrate how you can use Firefoo to upload data. 

### Add your Firebase project

The first step is to connect your desktop Firefoo client to your Firebase project. When you've completed this process, you'll see something like the following screen:

{% include medium-img.html url="reading-firefoo-01.png" %}

### Add your first collection

Now define a collection according to your application's data model. Right-click on the project and select "Add Collection":

{% include medium-img.html url="reading-firefoo-02.png" %}

The Add Collection dialog box will come up.  Type in the name of your collection. In this case, we will define a collection called "chapters":

{% include medium-img.html url="reading-firefoo-03.png" %}

Firefoo will create that collection by adding a default document. This is because NoSQL databases require that for a collection to exist, there must be a document inside it:

{% include medium-img.html url="reading-firefoo-04.png" %}

### Add your example documents to the collection

Next, click on the "Import Documents" icon:

{% include medium-img.html url="reading-firefoo-05.png" %}

This will pop up a dialog box allowing you to select a data file containing JSON data in the appropriate format for that collection:

{% include medium-img.html url="reading-firefoo-06.png" %}

I am selecting the `assets/initialData/chapters.json` file. 

Note that, by default, the upload process will result in associating a randomly generated documentID to each document.  

{% include medium-img.html url="reading-firefoo-07.png" %}

In my case, I don't want that: I want the documentID associated with each document to be taken from the `id` field:


{% include medium-img.html url="reading-firefoo-08.png" %}

Now I press "Import", and get the following dialog box that shows the progress of the upload. In general, it takes only a few seconds:

{% include medium-img.html url="reading-firefoo-09.png" %}

When the process completes, you can return to the main screen. Unfortunately, it looks like nothing has changed!

This is because the application does not automatically refresh the contents of the screen. So, just hit the "Run" button:

{% include medium-img.html url="reading-firefoo-10.png" %}

Now you can see the newly imported Chapter documents. (In this case, there are only two):

{% include medium-img.html url="reading-firefoo-11.png" %}

### Get rid of the default document

The last thing to do is to get rid of the default document. You can do this in either Firefoo or from the Firebase console.  To do it from Firefoo, which is more convenient because, well, you're using it right now, just right click on the default document, and select "Delete document":

{% include medium-img.html url="reading-firefoo-12.png" %}

### Maintaining data model consistency

Part of the fun of mockup development is the ability to easily refine and improve your data model as you learn about the domain.  In our approach to application development, you must keep three distinct representations of the data model in a consistent format in order for everything to work ok.  These representations are:

1.  The `@freezed` class in the data directory that defines the class whose instances correspond to the documents in Firestore.  The first step in evolving the data model is to make changes to the fields or other aspects of these classes, then run `flutter pub run build_runner build` to regenerate the corresponding `.freezed.dart` and `.g.dart` classes.

2. The sample data JSON files, typically in the `assets/initialData` directory. If you're like me, for each of the `@freezed` classes, I have a file in this directory with an array of JSON objects representing examples of this data model object. If you change the data model, you need to edit the corresponding example data file to be consistent. The AGC Mockup illustrates how to test that your sample JSON files are consistent with your mockup at system startup time. 

3. The data in Firebase.  The last representation of the data model is the set of collections and documents in Firebase.  Each time you evolve the data model, you will normally delete a collecion in Firebase (using either Firebase Console or Firefoo), and then upload the JSON file of example data to re-initialize the collection (using Firefoo).
