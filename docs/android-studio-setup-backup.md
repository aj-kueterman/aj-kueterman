Download Android Studio
https://developer.android.com/studio

Grab the latest version, and make sure to choose the right one for the chip architecture of your mac (Intel or Apple Silicon/M-series).

Downloading will take a few minutes.

Clone the repo
Clone the Android banner repo here: https://github.com/krogertechnology/kroger-android

Downloading will take another few minutes.

Open Repo in Android Studio
Open Android studio, which will then require you to accept some terms and download some additional required components.

Once you get to the Open/New project dialog, choose open and open the kroger-android/DigitalCoupons  directory from the repo you just cloned.

At this point, you'll be waiting awhile for the project to sync and download its many, many dependencies. If you have issues with syncing, make sure you have the right JDK selected in Gradle settings inside Android Studio.

Create an Emulator
Use the Device Manager (usually an icon in your toolbar) to create a new Android emulator.

Choose a device with the little play icon in the 'Play Store' column
When picking an OS version, choose one of the latest OS versions (bigger numbers). You'll likely have to download first it by clicking the download icon.
Use the rest of the defaults and click Finish
Download Charles
https://www.charlesproxy.com/download/latest-release/

We'll use Charles Proxy to monitor traffic & connect to non prod environments.

Configure Charles for Android Emulator
Android Emulator Charles QuickStart

Run the app
At this point, your project should be done syncing and you should be able to Run the app with the Emulator as your destination. This will open the Emulator and launch the app when the build completes.

When this is done, you will also want to run the Mobile Service Selector client to the same emulator. This is an app for development/testing that will let us change environments & toggles.

Point the app to Stage with the MSS, then kill/launch the Kroger banner app again. Now you can Create an Account or Login in the Stage environment.

At this point you should have a working app that you can observe through Charles - congrats!

