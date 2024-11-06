---
title: "Deploy your app"
published: true
morea_id: experience-deploy-your-app
morea_summary: "Deploy your app for initial evaluation by test users"
morea_type: experience
morea_sort_order: 1
morea_labels:
---

# Deploy your app

At this point, your mockup is almost certainly not functional enough for production use. Therefore, it is not appropriate for public distribution via the App Store or Play Store. However, it is still extremely useful at this point to evaluate your system on actual phones. So, in this module, you will deploy your app for testing using at least one of the following testing mechanisms:

* Apple's TestFlight (for iOS)
* Google's Play Store Console (for Android)
* Firebase App Distribution (for both iOS and Android)

Follow the official Flutter documentation for TestFlight or Play Store deployment (links in the readings). Unlike random blogs or videos, the official documentation should be up to date. 

For Firebase App Distribution, the reading provides links to both the official documentation and two selected Medium articles with more detail for Flutter.

## Hints for TestFlight

Here are some things Philip Johnson came across while deploying an app to iOS:

* If you want to deploy your app via TestFlight, you will need to pay $100 to Apple to join the Developer Program. If you don't want to do that, then you can just deploy to the Google Play Store or use Firebase App Distribution. 
* For the "SKU", just use the same string as for the Bundle ID.
* You might want to try building and running your system within XCode and resolving errors in your configuration file that way. 
* During his deployment process, the system returned a "provisioning error" which he eventually solved by physically connecting his iPhone to his Mac. More details [here](https://developer.apple.com/forums/thread/63957). The relevant comment: "... the answer was to plug-in my Apple device (in my case an iPhone), click on the drop-down at the very top of Xcode, to the right of the play, stop, and project name buttons, and select *my* device from the list. Then when I went back into the project details modal, it successfully completed the steps and linked my device."
* He followed the recommendation to download and install [Transporter](https://apps.apple.com/us/app/transporter/id1450874784) for uploading the *.ipa file to the Apple servers.


## Hints for Google Play Store

Please let me know if you find any useful hints.

## Hints for Firebase App Distribution

Please let me know if you find any useful hints.

