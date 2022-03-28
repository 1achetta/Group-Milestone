Group Project App: Unit 9 - Group Project App: Design Part 2
===

# Munchies

## Table of Contents
1. [Overview](#Overview)
1. [Product Spec](#Product-Spec)
1. [Wireframes](#Wireframes)
2. [Schema](#Schema)

## Overview

### Description
Memebers: Qiaowen Fang, Roberto Hernandez, Steven Lerner.
An application for users to search places to eat, and it will provide a list of restaurants with ratings and menus based on the search.

### App Evaluation
[Evaluation of your app across the following attributes]
- **Catagory: Food and Service**
- **Mobile: Used on all android devices**
- **Story: Takes in a zip code and shows local restraunts and allows users to see ratings**
- **Market: The expected user is anyone above 16**
- **Habit: This app can be used everyday multible times a day to see where to eat**
- **Scope: Anyone, anywhere, because we search by zip code**



## Product Spec

### 1. User Stories (Required and Optional)

**Required Must-have Stories**

* [Required Stories]
* User should be able to search restaurants by zip code, city name, and cuisine.
* User should NOT have to log in, and the zip code should never be saved
* User should be able to click a restraunant and get a rating based on yelp/online
* User should see distance and most recent review of the restraunt as well an image

**Optional Nice-to-have Stories**

* [Stretch Stories]
* User profile should be customizable, with color and text and images
* User should have access to a profile where they can add a pic and name

### 2. Screen Archetypes

* [list first screen here]
   * [Search screen where the user just has to search by zip code, cuisine or city name]
   * ...
* [list second screen here]
   * [show local restaurants and recent reviews]
   * ...

### 3. Navigation

**Tab Navigation** (Tab to Screen)

* User enters search parameters on the search box which will show the user a list of restaurants.
* The user selects a restaurant and is shown the information regarding the selected restaurants.
* The user is able to post his/her rating the visited restaurants.

**Flow Navigation** (Screen to Screen)

* [search screen with zip code enter]
   * [then go to list of restraunts]
   * ...
* [show restraunts and pick any of them]
   * [show the rating and information of any selected restaurant]
   * [from this screen access the location of the restaurant in a map]
   * [user can leave a rating for the restaurant]

## Wireframes
[Add picture of your hand sketched wireframes in this section]
<img src="https://i.imgur.com/WudCliN.jpg" width=600>

### [BONUS] Digital Wireframes & Mockups
<img src="https://i.imgur.com/Aca4pJl.gif" width=600>

### [BONUS] Interactive Prototype
N/A

## Schema 

### Models

Search and results

| Property | Type | Description |
| -------- | -------- | -------- |
| searchVal     | string    | The value used by the user to search for restaurants can be zip code, city name, restaurant name, or cuisine   |
|objectdID|string|Id of the return restaurant (provided by the Yelp API)|
|imageR|file|Image of the Restaurant|
|titleR|string|Restaurant Name|
|addressR|string|Restaurant address|
|cuisineR|string|Restaurant cuisine|
|descriptionR|string|Restaurant description|
|ratingR|integer|Restaurant actual rating|



### Networking
List of network requests by screen

Example API call to get Restaurant List:

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
  
Request request = new Request.Builder()

  .url("https://api.yelp.com/v3/businesses/search?term=restaurants&categories=french&location=miami")
  
  .method("GET", null)
  
  .addHeader("Authorization", "Bearer API_KEY")
  
  .addHeader("API_KEY", "")
  .build();
  
Response response = client.newCall(request).execute();


•	Home Search Screen

*    Read/Get Query all restaurants that satisfy user search values. Shows Name, address, and rating.

•	RestaurantInfo Screen

* 	Read/Get Query information for a specific restaurant. Shows Name, address, description, rating.

•	Map Screen

* 	Read/Get Shows the location of the restaurant on a map with the option to get directions on google maps.

•	Reviews Screen

* 	Read/Get Query latest Reviews for a restaurant

- [Create basic snippets for each Parse network request]
- [OPTIONAL: List endpoints if using existing API such as Yelp

* Yelp’s Fusion API

    Base URL - https://www.yelp.com/developers/documentation/v3/get_started
    
    

| HTTP Verb | Endpoint | description |
| -------- | -------- | -------- |
| GET   | /search?term=restaurants&location=     | Get all restaurant on a specific location     |
|GET|/search?term=restaurants&location=&categories=|Get all restaurants at a specific location and category|
|GET|/businesses/restaurant-alias/reviews|Get reviews for a specific restaurant|


### MileStones
1. Login screen - user will be able to login and search local restaurants by zip code. 

2. Have a basic build with the zip code search and return restaurants that can be clicked on for more information.

3. Final build just needing to change layout so it is more user friendly.