---
layout: post
title: 108 Emergency Services Hackathon Experience
tagline: Our Experience at 108 Emergency Services Hackathon in IIT Madras.
visible: 0
category: Hackathons
tags: [hackathons]
date: 2016-12-30
customjs:
 - /assets/js/gifAnimation.js
 - /assets/js/post/108Hackathon.js
---
#  108 Emergency Services Hackathon Experience

Participating in 108 Emergency Services Hackathon was a very nice experience for us and winning the competition makes it even better. So we decided to share our experience with everyone.

-----------------------

## What is 108 Hackathon?

It was a hackathon specially organized by TNHSP and IIT Madras. The aim of this hackathon was to come up with solutions that leverage the capabilities of a smart phone and integrate them with 108 emergency call center to decrease the response times.
It was held at IIT Madras on 17th and 18th December, 2016.
You can further read about it at [108 Hackathon's Website](https://www.108hackathon.in/)

## Our Experience

### What we did?
We made two android apps, one for the user requiring emergency and another for the ambulance driver. Also we made an online dashboard to be used by the 108 emergency call center to view the emergency request made in real time and process them.

##### User App
In this we implemented a 108 dial listener so that whenever the user dials 108, a service gets started in the background which fetches the location using inbuilt GPS and sends it to our sever via internet or sms (if no internet).
Also it contained a one time signup screen for registering user details on our server.
<div class="row" markdown="1">![Screenshots](/assets/images/posts_images/108hackathon/userapp_1/1.png){: id="userapp_gif_1" style=" width:250px; margin-left:0; margin-right:20px;"}![Screenshots](/assets/images/posts_images/108hackathon/userapp_2/1.png){: id="userapp_gif_2" style=" width:250px; margin-right:0;"}
{: style="text-align:center;"}
</div>

##### Server
It was based on [Node.js](https://nodejs.org/en/) and for database we choose [Firebase Realtime Database](https://firebase.google.com/docs/database/). It hosted both the api as well as the dashboard and was deployed online using heroku services.
On the server after receiving a new request from the user's app, it searches through our database in the users city for the nearest ambulance driver using google's [Distance Matrix Api](https://developers.google.com/maps/documentation/distance-matrix/intro).
Once the driver is found a sms is sent to the driver's mobile along with the info of the user requesting emergency. Meanwhile the user is also sent a sms containing the details about the driver and his ETA to reach him which is then parsed and automatically displayed on the user's app.



##### Driver App
This app implemented a sms listener, which triggers on receiving any sms from our server. It then shows an activity containing a map with users location and other details. The driver can navigate through the location using google maps api.

![Screenshots](/assets/images/posts_images/108hackathon/driverapp/1.png){: id="driverapp_gif" style=" width:250px; margin-left:0; margin-right:0;"}
{: style="text-align:center;"}

##### Dashboard
It used simple html, css and js and contained the following elements:

* List of recent requests
* Map containing location of all drivers and users
* Graph showing no. of requests made in recent hours
* Two pie charts showing city wise ratio of users and drivers.

**To view dashboard [click here](https://dashboard108.herokuapp.com)**

[![Screenshots](/assets/images/posts_images/108hackathon/dashboard/1.png){: id="dashboard_gif" style="margin-left:0; margin-right:0;"}](https://dashboard108.herokuapp.com)
{: style="text-align:center;"}

### Languages used
* Java for Android
* Node.Js
* Javascript
* Html
* Css

### What we learned?
1. OTP verification
2. Firebase Authentication and Database
3. Sms listener and sender
4. Android service and Intent Filters
5. Constructing a Dashboard
6. Sms to http request implementation
7. Working with google maps api
	* Geocoding and reverse geocoding
	* Distance Matrix Api

### What we got?

We bagged 4th position in the Hackathon and **won a cash prize of Rs. 10,000** along with mementos and certificates of commendation. Along with these we had an amazing experience of working in a team for more than 24 hours straight.


**You can check our submission [here.](https://github.com/rahulbabbar1/108/)**
