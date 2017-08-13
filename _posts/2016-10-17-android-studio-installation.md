---
layout: post
title: Android Studio Installation
tagline: Android Studio 2.2 setup instructions
visible: 1
category: Android Studio Installation
tags: [androidstudio,setup,installation]
---

Hey there! For Android app development, you first need a development environment for which you have two choices :

- **ANDROID STUDIO** based on Intellij IDEA platform recommended by Google and any other sane person for android development
- **ECLLIPSE** (Google officially declared it to be obsolete for android development).

We will focus on _Android Studio_.

-------------------------------


System Requirements
-------------------------------

Building apps with **Android Studio** has following requirements:

>**Windows:**

> - Microsoft Windows 10/8/7/Vista (32- or 64-bit)
> - 2 GB RAM minimum while 4 GB RAM is recommended (mostly for running emulator for android)
> - 400 MB hard disk space
> - At least 1 GB for Android SDK, emulator system images, and caches(don’t bother)
> - 1280 x 800 minimum screen resolution
> - Java Development Kit (JDK) 7or above
> - Optional for accelerated emulator(skip if you are a beginner): Intel® processor with support for Intel® VT-x, Intel® EM64T (Intel® 64), and Execute Disable (XD) Bit functionality

>**Mac OS X:**

> - Mac® OS X® 10.8.5 or higher, up to 10.9 (Mavericks)
> - 2 GB RAM minimum, 4 GB RAM recommended (mostly for running emulator for android)
> - 400 MB hard disk space
> - At least 1 GB for Android SDK, emulator system images, and caches(don’t bother)
> - 1280 x 800 minimum screen resolution
> - Java Runtime Environment (JRE) 6
> - Java Development Kit (JDK) 7
> - Optional for accelerated emulator(skip if you are a beginner): Intel® processor with support for Intel® VT-x, Intel® EM64T (Intel® 64), and Execute Disable (XD) Bit functionality

Getting Started
-------------------
**<i class="icon-check"></i> Setting up Java environment**
This is the most crucial part for a beginner with less or no knowledge about programming. We will focus on windows, if you have any other OS, you can contact us.

Go to [Java download page](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html "Java Download page")

![](https://1.bp.blogspot.com/-2Ib224wr9x8/Vt03JmlhRSI/AAAAAAAACJQ/6QgGur4_FVc/s1600/Java7.jpg "java7")

Download and install the latest version of JDK matching your system specification.

Now go to the path where Java is installed and copy the path Address as shown in image

![enter image description here](https://lh3.googleusercontent.com/-Ahc6i6-NnsQ/WAHJaZI1qrI/AAAAAAAADy0/oWmSaWmuVA8P1krypKNxcQZGztyygPB1wCLcB/s0/Screenshot+from+2016-10-05+17-02-26.png "Java")

Go to Control Panel -> System and Security

![enter image description here](https://2.bp.blogspot.com/-4CsTyKnooOw/UR-UvnYNGII/AAAAAAAAAho/Jd5U5dc4DsM/s640/windows8_control_panel.JPG "control panel")

Go to System -> Advanced System settings

![enter image description here](https://1.bp.blogspot.com/-WcYq7RTdUZA/UR-U1PYDucI/AAAAAAAAAiI/hKk6nxhqaoY/s640/windows8_system_and_security.JPG "system")

![enter image description here](https://2.bp.blogspot.com/-FBQMKviDa0g/UR-U08B-_eI/AAAAAAAAAiE/x1Jrxi1r77w/s640/windows8_system.JPG "advsettings")

Under Advanced tab, click Environment Variables

![enter image description here](https://4.bp.blogspot.com/-taR8pvDqBkA/UR-U10dSNqI/AAAAAAAAAiY/sh4FP0DULuE/s640/windows8_system_properties.JPG "env box")

Click on New.. and give a random variable name, in variable value, paste the path address that you copied earlier.

![enter image description here](https://4.bp.blogspot.com/-Ld9O3cM65P8/UR-U0ENQYoI/AAAAAAAAAhw/z2I9qNF0-3g/s640/windows8_java_path_settings.JPG "final")

You can ensure that your effort is valid by typing "javac -version"(without quotes) in command prompt. If you get a version, you have successfully set-up Java environment variable and you are good to go.


#### <i class="icon-check"></i>Android Studio Installation

This is an easy and cliche installation without any fuss. All you have to do is go [here](http://developer.android.com/sdk/index.html "here") and click on download.

![android studio](https://4.bp.blogspot.com/-tvKjoFGqi3Q/Vt03Jlfgw0I/AAAAAAAACJU/wPEBdl06AN0/s1600/AndroidStudio.jpg "studio")

You can keep all default settings in the Installation wizard and once installation is done, you will be prompted to install Android SDK which is itself a cake walk.
![android sdk](https://lh3.googleusercontent.com/-FeeBvpav4eo/WAHP_ZJhciI/AAAAAAAADzM/KbnVOTqa_kY7GLcH2UduIGQqZvDO6HPbACLcB/s0/Screenshot+from+2016-10-05+17-11-48.png "sdk")


*If you face any problem you can contact us at [Chat](http://mdg.sdslabs.co/chat)*
