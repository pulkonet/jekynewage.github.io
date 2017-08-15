---
layout: post
title: Installation
tagline: Android Studio Installation.
visible: 1
category: Introduction
tags: [intro]
---

## Why Develop For Android?##


With over **1 billion** Android devices already activated, Android represents an incredible opportunity for developers.
Android Studio is a latest and most widely accepted IDE designed by Google itself. If you want to develop apps in android then it is highly recommended to use Android Studio.

----------

## Quick Overview ##
A typical native android application is written using XML for the frontend (the User Interface) and JAVA for the backend.

----------
**JAVA**
All the programming part in android development is done using JAVA. Although it’s a great advantage, if you know a thing or two about programming in Java, but even if you know any object oriented programming language, then it will not be much difficult to relate to the concepts used during development. In short if you know C++ or C then also you are at peace.


----------
**XML**
This is used to build the app’s user interface. All user interface elements in an Android app are built using View and ViewGroup objects. It has drag and drop User Interface


----------
**Running the app**
An android application can run either on your device or in the emulator that comes bundled with the SDK. Since the emulators can be slow, it is always recommended to use an actual device. [This link](http://developer.android.com/intl/zh-cn/training/basics/firstapp/running-app.html) contains the detailed explanation for setting up your device/emulator for testing.


----------

# Installation of Android Studio#
------------------

JDK and JRE are essential for JAVA to run on your machine.

### For windows:

#### **Installing JAVA**
Follow [the link](http://www.oracle.com/technetwork/java/javase/downloads/index.html) and click Java Platform (JDK) 8u60 photograph. It redirects to a new page on which select Accept the license and download the version which is best suited with your machine.
After installing the JDK, you need to set the environment variable JAVA_HOME path and for that:

 - For this, right-click on the 'This PC' icon on your desktop and select 'Properties'. On the next screen that appears, go to 'Advanced system settings' item. On the 'System Properties' window that appears, select the 'Environment Variables' button. 
![System Properties](https://raw.githubusercontent.com/sdsmdg/sdsmdg.github.io/master/public/images/installation/system_properties.png?raw=true)
 - The 'Environment Variables' window will appear (see figure below). Click on the 'New...' button. 
![Environment Variables](https://raw.githubusercontent.com/sdsmdg/sdsmdg.github.io/master/public/images/installation/environment_variables.png?raw=true)
 - The 'New System Variable' window will appear (see the figure below). Enter 'JAVA_HOME' as the variable name and 'C:\Program Files\Java\jdk1.8.0_25' as the variable value. Then click the 'OK' button. 
![New System Variable](https://raw.githubusercontent.com/sdsmdg/sdsmdg.github.io/master/public/images/installation/new_system_variable.png?raw=true)
 - Scroll down the 'System variables' window until you see the 'Path' item, then click on it. Then click on the 'Edit...' button. The 'Edit System Variable' window will appear. 
![Edit System Variable](https://raw.githubusercontent.com/sdsmdg/sdsmdg.github.io/master/public/images/installation/edit_system_variable.png?raw=true)
 - Click anywhere in the 'Variable value' field and then press the End key on your PC. Then type the following into the field:

  ;C:\Program Files\Java\jdk1.8.0_25\bin\

*Do not forget the semi-colon at the start - they are used to separate each path item from one another. The completed screen will look something like this: 
![Edit system variable 2](https://raw.githubusercontent.com/sdsmdg/sdsmdg.github.io/master/public/images/installation/edit_system_variable2.png?raw=true)

 - For reference, one can visit [this link](http://ridz1ba.blogspot.in/2015/01/how-to-install-oracle-java-and-andoid.html) 

#### **Installing IDE**
------------------
• Go to [this link](http://developer.android.com/sdk/index.html) and select “Download Android Studio for Windows”.

• Check the “ I have read and agree with the above terms and conditions” box and Download Android Studio For Windows.

• Install studio after downloading.

• Open the Android Studio. A window similar to the below one would appear. Select configure in it.
![New Project](https://github.com/sdsmdg/sdsmdg.github.io/blob/master/public/images/installation/newproject.jpg?raw=true)

• Click on the SDK Manager icon (containing android and a downward sign).![Configure](https://github.com/sdsmdg/sdsmdg.github.io/blob/master/public/images/installation/configure.jpg?raw=true)


 Install the following packages
![SDK tools](https://github.com/sdsmdg/sdsmdg.github.io/blob/master/public/images/installation/SDKTools.jpg?raw=true)

### **For Linux Users :** 
**Installing JAVA**
• sudo apt-get update

• sudo apt-get install default-jre

• sudo apt-get install default-jdk

• sudo apt-get install oracle-java8-installer

• sudo update-alternatives --config java

• sudo vim /etc/environment – add JAVA_HOME="YOUR_PATH" {Your path is the path returned in previous command}.

• source /etc/environment

For reference one can [visit this link.](https://www.digitalocean.com/community/tutorials/how-to-install-java-on-ubuntu-with-apt-get)

If there is still some error, one could also refer [here](http://www.wikihow.com/Install-Oracle-Java-JDK-on-Ubuntu-Linux) 

#### **Installing IDE**
 -  [Follow this link](https://developer.android.com/sdk/index.html) -> select All Android Studio Packages -> Linux. This will start the download.
 -  Extract the file. In terminal type  :
		 cd /{Location where you extracted}/android-studio/bin
		sh studio.sh
		
 
• Open the Android Studio. A window similar to the below one would appear. Select configure in it.
![New Project](https://github.com/sdsmdg/sdsmdg.github.io/blob/master/public/images/installation/newproject.jpg?raw=true)

• Click on the SDK Manager icon (containing android and a downward sign).![Configure](https://github.com/sdsmdg/sdsmdg.github.io/blob/master/public/images/installation/configure.jpg?raw=true)


• Install the following packages
![SDK tools](https://github.com/sdsmdg/sdsmdg.github.io/blob/master/public/images/installation/SDKTools.jpg?raw=true)

### **Some Common errors:**
 - unable to access android sdk add-on list:
[http://stackoverflow.com/questions/29878370/android-studio-first-run-error](http://stackoverflow.com/questions/29878370/android-studio-first-run-error)
	1. Turn off the firewall.
	2. Run Studio again.
	3. Add android files to trusted files in your windows firewall and restart the firewall.
 - Your Android SDK is missing, out of date, or is missing templates. You can configure your SDK via Configure -> Project Defaults -> Project Structure -> SDKs: [http://stackoverflow.com/questions/26796724/your-android-sdk-is-missing-out-of-date-or-is-missing-templates](http://stackoverflow.com/questions/26796724/your-android-sdk-is-missing-out-of-date-or-is-missing-templates)
 - Unable to locate adb within SDK: [http://stackoverflow.com/questions/14421171/adb-error-on-android-sdk-using-linux-ubuntu-64-bit-12-10](http://stackoverflow.com/questions/14421171/adb-error-on-android-sdk-using-linux-ubuntu-64-bit-12-10), [http://stackoverflow.com/questions/27301960/unable-to-locate-adb-within-sdk](http://stackoverflow.com/questions/27301960/unable-to-locate-adb-within-sdk)

### **Links to kick start with developing Android apps**
[thenewboston](https://www.youtube.com/playlist?list=PL6gx4Cwl9DGBsvRxJJOzG4r4k_zLKrnxl) : Youtube channel to get you started.

**Some basic links to grasp a bit of more knowledge:**
[http://stackoverflow.com/questions/1906445/what-is-the-difference-between-jdk-and-jre](http://stackoverflow.com/questions/1906445/what-is-the-difference-between-jdk-and-jre)
 
[http://stackoverflow.com/questions/5102022/what-does-the-java-home-environment-variable-do](http://stackoverflow.com/questions/5102022/what-does-the-java-home-environment-variable-do)



