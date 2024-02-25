---
toc: false
comments: true
layout: post
title: CSP Final Review
description: Reflecting With Written Review on CPT Project
courses: { csp: {week: 23} }
type: tangibles
---

## Overview
This review contains:
* My code for main features
* Preparation of key features before coding
* How my features maps to College Board requirements for the CPT project
* Pull request(s)
* Code commits to prove my work

## CPT Project Plans:
* Create a cookbook site with easy to access ingredients and recipes
  * Easy to search for specific recipes and formatted nicely
* User/Login system for unique accounts with Admin system
* Forum where users can post their own favorite ingredients to inspire others
* Customizable user settings

## My contributions:
* Created landing page to site
* Created forum (blogging feature) for users to write posts about their favorite recipes for other users to see
<br>

* **Frontend Code:**
![submitImage](https://github.com/DavidL0914/student/assets/67357222/6e0612f2-dea7-4515-8231-cb0dea7c1705)
* submitImage function - handles submission of image data to the backend using the Fetch API: includes error handling and updates the UI accordingly.
<br>

* **Frontend Code:**
![fetchImages](https://github.com/DavidL0914/student/assets/67357222/32a0b75c-9b3a-4dd6-9ae0-bac0a7f3fcd1)
* fetchImages function - retrieves and displays recipes posted by other users, including both their usernames and post's content.
<br>

* **Frontend Code:**
![deletePost](https://github.com/DavidL0914/student/assets/67357222/2760418f-65cb-44c1-9942-8acb2a9c26a9)
* deletePost function - sends a request to the backend to delete the specified post (only works if logged in as correct user)
<br>

* **Backend code**
![Backend](https://github.com/DavidL0914/student/assets/67357222/1f437050-5826-4235-b3cd-59f0b311c16c)
* Setting up backend to run all the code above on frontend

## Preparation of code before coding
**Issues/Initial Planning:**
[Issues Link](https://github.com/DavidL0914/frontcasts/issues/2)
<br>

**UI Design**
![UI](https://github.com/DavidL0914/student/assets/67357222/b468976e-6f90-40e8-a0a0-883ae6e6d2e9)

## How my features match CB CPT requirements
**CB requirements bolded**
* **Instructions for input from the user (user actions)**
  * My blogging feature addresses this as users can create and delete posts for other users to see
* **Use of at least one list (or other collection type) to represent a collection of data that is stored and used to manage program complexity and help fulfill the program’s purpose.**
  * In my feature, the post data is collected in a SQLite database. The user's post information is stored in JSON which is a collection of data that keeps track of what users post. This helps manage the program's complexity and allows for the blogging feature and lets users share their recipes which thus fulfills the program's purpose.
  * ![JSON data](https://github.com/DavidL0914/student/assets/67357222/12c2f7b3-c0ff-4aee-ae37-fdea552a2d39)
* **The data abstraction must make the program easier to develop or easier to maintain.**
  * The images and explanations I gave above when describing my feature shows how our program can easily capture user's posts and store them which makes them easy to maintain as well as pull up for other users to see. 
* **At least one procedure that contributes to the program’s intended purpose, where you have defined: the procedure’s name, the return type , one or more parameters**
  * I created a blogging feature which uses Fetch to return information from our database. We fetch our data from an endpoint I created in the backend as shown in the images above.
* **An algorithm that includes sequencing, selection, and iteration that is in the body of the selected procedure**
  * The submitImage function includes sequencing for handling image submission. It also uses conditional statements for selection, checking to make sure the submitted posts are not empty.
* **Calls to your student-developed procedure**
  * The submitImage function is called when the submit button is clicked.
* **Instructions for output based on input.**
  * User input is obtained as users write their posts and submit it. The website displays error messages if the input is empty or if there is an issue with the submission. Successful submission also results in successful messages and changes the UI.

## Pull Requests:
Since I own the repository, I decided to go on my alt account to make some changes and then submit a pull request to the main repo. [Link to pull request](https://github.com/DavidL0914/frontcasts/commit/a3a3feafd56995d567859c85c8184580b6f7a67e)

## Code Commits:
* [Frontend Commits Link](https://github.com/DavidL0914/frontcasts/commits?author=DavidL0914)
* [Backend Commits Link](https://github.com/DavidL0914/backcasts/commits?author=DavidL0914)

<br>

**Graph showing recent commits**
![Graph](https://github.com/DavidL0914/student/assets/67357222/31d669a0-52ec-4647-82cc-3077e824cf92)