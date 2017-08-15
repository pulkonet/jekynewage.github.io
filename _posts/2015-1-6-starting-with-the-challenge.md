---
layout: post
title: Starting with the challenge
tagline:  Setting up the development environment
visible: 1
category: Droid Wars
tags: [recruitments]
---

## Installation of Android Studio

Android Studio is a latest and most widely accepted IDE designed by Google itself and quickly replacing Eclipse which was used earlier. If you want to develop apps in android then it is highly recommended to use Android Studio instead of Eclipse. Details for download and usage of android studio can be found [here] as well as in the following video:

<center> <iframe width="560" height="315" src="//www.youtube.com/embed/zEsDwzjPJ5c" frameborder="0" allowfullscreen="allowfullscreen"> </iframe> </center>
 
 
## Quick Start

A typical native android application is written using XML for the frontend (the User Interface) and JAVA for the backend.

### JAVA

All the programming part in android development is done using JAVA. Although its a great advantage, if you know a thing or two about programming in Java, but even if you know any object oriented programming language, then it will not be much difficult to relate to the concepts used during development. 
     
Those who are familiar with other programming languages like C,C++ etc might need to understand a few concepts of JAVA which are not so commonly used in C and C++. Some of them have been mentioned here:

* Basic understanding of OOP concepts - classes,  functions, meaning of public/private/protected, inheritance etc.
* Use of interfaces
* Types of identifiers such as static, abstract, final etc.

### XML

This is used to build the app's user interface. All user interface elements in an Android app are built using View and ViewGroup objects. A View is an object that draws something on the screen that the user can interact with. A ViewGroup is an object that holds other View (and ViewGroup) objects in order to define the layout of the interface.
	
The Android developer kit provides an elegant and easy-to-use graphic interface to work with these components and avoid XML, and thus as a beginner, you can directly use this for your app. But as you move on, working with XML provides greater control over the design of the elements.
	
Here is a list of basic UI elements which are used very often while developing android apps :
*  [TextView] :  Displays text to the user and optionally allows them to edit it.
* [EditText] : EditText is a thin veneer over TextView that configures itself to be editable. 
*  [Button] : A button consists of text or an icon (or both text and an icon) that communicates what action occurs when the user touches it.
*  [Spinner] : Select one value from a set. In the default state, a spinner shows its currently selected value.
* [ListView] : ListView is a view group that displays a list of scrollable items. 
* [ImageView] : Displays an arbitrary image, such as an icon. The ImageView class can load images from various sources

	Now the first task as a part of your problem statement is to develop a form wherein you take the details of a new criminal as input. First of all, you will need a layout(Relative or Linear) to place the rest of the elements in it. Then you can use the EditText element to input his name, address, area in which he lives, and other information. TextView can be used to indicate these fields to the user corresponding to these EditTexts. Explore other elements as well and see if you can ask for more information using them.  Finally have a submit and a clear button to store the record and clear the form respectively.

### Running the app
	  
An android application can run either on your device or in the emulator that comes bundled with the SDK. Since the emulators can be slow, it is always recommended to use an actual device. [This] link contains detailed explanation for setting up your device/emulator for testing.
	
<br>
So that's it from our side in this blog. In case of any problem you can visit the official android website, which has a huge documentation on almost every topic related to developing Android Studio, including Tools, downloadable Material, Designs, APIs ,etc. You can also post your doubts on this blog or in our [facebook group] 

We will soon be back with the next blog in the android development series. Till then goodbye and happy coding !
	  
	  
[here]:http://developer.android.com/tools/studio/index.html
[facebook group]:http://fb.com/groups/sdsmobiledevelopment
[TextView]:http://developer.android.com/reference/android/widget/TextView.html
[EditText]:http://developer.android.com/guide/topics/ui/controls/text.html
[Button]:http://developer.android.com/guide/topics/ui/controls/button.html
[Spinner]:http://developer.android.com/guide/topics/ui/controls/spinner.html
[ListView]:http://developer.android.com/guide/topics/ui/layout/listview.html
[ImageView]:http://developer.android.com/reference/android/widget/ImageView.html
[This]:http://developer.android.com/training/basics/firstapp/running-app.html
