---
layout: post
title: Droid Wars - Problem 2
tagline: Application development Challenge.
visible: 0
category: Droid Wars
tags: [recruitments]
date: 2015-12-22 20:00
---

### **Car Pooling**

With the pollution in Delhi continuously on the rise, the metropolitan gears up to try odd-even strategy for vehicles to curb pollution from the coming year. Though the motive behind this is large and noble, but is bound to create confusions and anarchy. The residents of Delhi need a system which is efficient and ensures lesser confusion and serves the purpose. The Delhi government needs you to create **"Hitch My Ride"**, which fits in the requirements the city needs. Your task is to create a prototype of this app, which the government will integrate with their servers and put it in action. The app will let the people hitch a ride with a car that has the same destination as theirs. The citizens just need to add a record of them going from one place to another along with their basic details, and someone who can ride along the way will contact them. Your app should have the following screens :

- **Main Screen**: The home screen should consist of two buttons, "Add Record" and "Display Records". Clicking on "Add Record" opens up a screen to create a new record for a commuter and clicking on "Display Records" opens a list of details about records of commuters stored.

- **Add Record**: This screen is displayed when the user clicks on "Add Record" button. It is meant for anybody to add a record for their traveling from one location to another. It should display a form to fill up the details. Inclusion of these fields is mandatory: 
  - Name, Gender, Age, Contact Information of the commuter.
  - Preferred Gender (Which gender are you comfortable to travel along - Male Youth, Female Youth, Senior Citizens, implement a set of checkboxes)
  - Source and Destination (Select place from two separate drop down menus: Chandni Chowk, Connaught Place, Defense Colony, Hauz Khas, Mehrauli, Nizamuddin, Sarojini Nagar, Tilak Nagar, etc.)
  - Date and Time of Journey.
  - "Save Details" button.
  
- **Display Records**: This screen is displayed when the user clicks on "Display Records" button. It should display a list of records stored about the commuters in the mobile so far, which people would view to find a ride for them. Each item of list will show basic details of the commuter. Clicking on any item will open up complete details of the commuter.

- **Commuter Details**: This screen is displayed when the user clicks on any item from the list of commuters. It should display the complete information stored in the database about the commuter.

### **Bonus Points**

  - Elegant User Interface, particularly Material UI.
  - If cards in the list have different background colours according to the commuter being male, female youth or senior citizen.
  - If the commuter can upload his/her image which can be stored and displayed.
  - If there are validations at various fields in “Add record”, such as checking whether age is a number, whether source and destination are different, and if not followed, an alert is displayed in a suitable manner.
  - Usage of special input fields pertaining to time-date and age, rather than simple text field.
  - Any other tweak or feature which adds to the utility of the app as per your creativity.
