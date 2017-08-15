---
layout: post
title: Google Maps Android API v2
tagline: Integration of Google Maps with your app
visible: 1
category: Google Maps API V2
tags: [Google Maps API]
---

## Integration of Google Maps with your app

Now that most of you are done with basic task in the challenge, it's time to score the bonus points . You need to show the location data that you received from the user on the map. Alternatively, you can just open the map, let the user pinpoint the location and save the latitude & longitude of that location. So how to accomplish this ? 
Google provides via Google play a library for using Google Maps in your application.

First of all, let's see what an API is -

> API, an abbreviation of application program interface, is a set of
> routines, protocols, and tools for building software applications. The
> API specifies how software components should interact and are used
> when programming graphical user interface (GUI) components.

Before delving into the implementation details we need to make sure we have the appropriate SDKs installed to connect to Google Play Services and get the API key for Google Maps.

#### 1. Installing Required SDK Components

Under the Extras section in the Android SDK Manager , check if you have installed the following packages. If not , then download them.

 - Google Play Services
 - Google Repository
 
![Required Installations](https://lh4.googleusercontent.com/ASho7RHs3RAAibw4As8phhw2jWtj76grIj7y0SFRcec=s0 "RequiredInstallations.png")

#### 2. Setting Up Google Play Services

Once these packages have been installed, we must add the Google Play Services dependency to our projects build.gradle file. Open up the build.gradle file present within the module directory.
Under the dependencies section add the latest version of the google-play-services library. At the time of writing, this is 6.1.71. You can find out the latest version number of the plugin, as well as many others [here](http://gradleplease.appspot.com/)

    dependencies {
	    compile fileTree(dir: 'libs', include:['*.jar'])
	    compile 'com.google.android.gms:play-services:6.1.71'
    }

#### 3. Creating an API key for the app

 - Navigate to [https://console.developers.google.com/project](https://console.developers.google.com/project). Click on "Create Project". Enter the project name and id of your choice.
 
 ![CreateProject](https://lh4.googleusercontent.com/QSNYokre-9cx3Aq5IvqcI65XRidKOavzhV5sdvJ-uzQ=s0 "CreateProject.png")
 -  Click on the "APIs & auth" menu on the left, and from the submenu select APIs. From the list of APIs that appear, scroll down and ensure that Google Maps Android API v2 is set to “On”.
 
 ![SetOnGoogleMapsAPIv2](https://lh4.googleusercontent.com/8_bob1D13HM-0M0achMCxxRLysbt3hzKz4QtFxkSgmI=s0 "SetOnGoogleMapsAPIv2.png")
 
 - Now under the same menu on the left, select “Credentials” . Under the Public API access heading, click "Create New Key", and then "Android Key".
 
 ![CreateNewKey](https://lh3.googleusercontent.com/4VGgwQH1LbPsKhLlERSDAan_9lzSX7f-ScQoxpvj4oM=s0 "CreateNewKey.png")
 - Run the following command in your command prompt to generate your developer certificates SHA1 fingerprint key:
 
##### For Windows Users
        keytool -list -v -keystore "%USERPROFILE%\.android\debug.keystore" -alias androiddebugkey -storepass android -keypass android

##### For Mac OS or Linux Users
        keytool -list -v -keystore ~/.android/debug.keystore -alias androiddebugkey -storepass android -keypass android

  
Take your SHA1 key, and append the apps package name to the end of it, separated by a semicolon. Paste this into the textbox and click Create. 
	
![AddSHA1Key](https://lh5.googleusercontent.com/Kg3E1jIFPblpxs1zBTs7lVMfFac-cPYeFCPDGqjpGFo=s0 "AddSHA1Key.jpg")

- You’ll see an API generated and displayed on the page. Copy the android api key to your clipboard.

![ReqAPIKey](https://lh4.googleusercontent.com/CK2PqCteAaUxNkGnnS7SFZ7xfZHrpsYxUbRVNFd-Vo8=s0 "ReqAPIKey.jpg")

#### 4. Adding the API key in our app

In your project, open up AndroidManifest.xml. Just before the </application> tag add the following lines of code.

    <meta-data 
	    android:name="com.google.android.gms.version" 
		android:value=
		"@integer/google_play_services_version" 
	/>
    <meta-data
	   android:name="com.google.android.maps.v2.API_KEY"
	   android:value="enter_your_api_key" 
	/>

#### 5. Adding a few Permissions

Now we need to specify the permissions that our app needs. In order to use mapping functionality, we need to add the following permissions:

    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
    <uses-permission android:name="com.google.android.providers.gsf.permission.READ_GSERVICES" />
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />

## Google Maps Components

### [The map object](https://developers.google.com/maps/documentation/android/map)

The key class when working with a map object is the GoogleMap class. GoogleMap models the map object within your application. Within your UI, a map will be represented by either a MapFragment or MapView object.

### [MapFragment](https://developer.android.com/reference/com/google/android/gms/maps/MapFragment.html)

MapFragment, a subclass of the Android Fragment class, allows you to place a map in an Android fragment. MapFragment objects act as containers for the map, and provide access to the GoogleMap object.

Unlike a View, a Fragment represents a behavior or a portion of user interface in an activity. Refer to the Android documentation on Fragments to learn more.

### [Mapview](http://developer.android.com/reference/com/google/android/gms/maps/MapView.html)
MapView, a subclass of the Android View class, allows you to place a map in an Android View.  Much like a MapFragment, the MapView acts as a container for the map, exposing core map functionality through the GoogleMap object.

Users of this class must forward all the activity life cycle methods - such as `onCreate()`, `onDestroy()`, `onResume()`, and `onPause()` - to the corresponding methods in the MapView class.

### [Marker](https://developer.android.com/reference/com/google/android/gms/maps/model/Marker.html)
Markers identify locations on the map. The default marker uses a standard icon, common to the Google Maps look and feel. It's possible to change the icon's color, image or anchor point via the API.
 Markers are objects of type Marker, and are added to the map with the [`googleMap.addMarker(markerOptions)`](http://developer.android.com/reference/com/google/android/gms/maps/GoogleMap.html#addMarker(com.google.android.gms.maps.model.MarkerOptions)) method.
 
## Implementation Specifics

Using the below code snippets, try to complete the task.

### Adding a Map to the view

Open the xml file for the activity in which you want to view the map.
Just after the basic layout opening tag add the following code.

    <fragment
        android:id="@+id/map"
        android:name=
	       "com.google.android.gms.maps.MapFragment"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
    />

### Initialising the Map

Declare a [GoogleMap](https://developer.android.com/reference/com/google/android/gms/maps/GoogleMap.html) object.

    private GoogleMap googleMap ;

Now in the OnCreate( ) method of the activity, use the below code to initialise the GoogleMap instance.

    googleMap = ((MapFragment) getFragmentManager()
    .findFragmentById(R.id.map)).getMap();


### Setting a listener on Map Click

Remember to save the data for the clicked location. This also needs to be done in the OnCreate( ) method of the activity.

    googleMap.setOnMapClickListener(new OnMapClickListener() {
             @Override
            public void onMapClick(LatLng latLng) {
				 // add the code for saving the data 
				 // and displaying a marker
            }
        });

### Adding a Marker

The marker is added on the location whose latitude and location are x and y respectively.

    googleMap.addMarker(new MarkerOptions()
                            .position(new LatLng(x, y))
                            .title("Marker")
                            .draggable(true)

## Changing Map Type

A map's type governs the overall representation of the map. 
The Google Maps Android API offers four types of maps, as well as an option to have no map at all:

 - **Normal** : Typical road map. Roads, some man-made features, and important natural features such as rivers are shown. Road and feature labels are also visible.
 - **Hybrid** : Satellite photograph data with road maps added. Road and feature labels are also visible.
 - **Satellite** : Satellite photograph data. Road and feature labels are not visible.
 - **Terrain** : Topographic data. The map includes colors, contour lines and labels, and perspective shading. Some roads and labels are also visible.
 - **None** : No tiles. The map will be rendered as an empty grid with no tiles loaded.

 ![MapTypes](https://lh5.googleusercontent.com/3RcPnvhno5u3hNLdB3VUgMfMOq1FESP4ztLquP5bxdY=s0 "MapTypes.jpg")

The map type can be changed by using the [`googleMap.setMapType()`](http://developer.android.com/reference/com/google/android/gms/maps/GoogleMap.html#setMapType(int)) method.
Here the `googleMap` is an instance of GoogleMap class.

    googleMap.setMapType(GoogleMap.MAP_TYPE_NORMAL);
    googleMap.setMapType(GoogleMap.MAP_TYPE_HYBRID);
    googleMap.setMapType(GoogleMap.MAP_TYPE_SATELLITE);
    googleMap.setMapType(GoogleMap.MAP_TYPE_TERRAIN);
    googleMap.setMapType(GoogleMap.MAP_TYPE_NONE);

## Conclusion

This completes our discussion on Google Maps Android API v2 . Feel free to post any sort of doubts in the comments below or on our Facebook Group. 
For more resources and detailed explanation you can always refer to the following links:

 - [Vogella](http://www.vogella.com/tutorials/AndroidGoogleMaps/article.html)
 - [Android Hive](http://www.androidhive.info/2013/08/android-working-with-google-maps-v2/)
 - [Google Developers](https://developers.google.com/maps/documentation/android/)
