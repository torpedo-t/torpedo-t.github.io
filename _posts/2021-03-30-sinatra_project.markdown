---
layout: post
title:      "Sinatra Project"
date:       2021-03-30 14:24:50 -0400
permalink:  sinatra_project
---


**Videoshare**

During covid-19 lockdown's everyone could use a bit of nostalgia. The term encompasses a longing for affection of the past, typically for a period or place with happy personal associations. Videoshare can help supplement this sensation. 

To bring this vision to reality, I used Sinatra to create a way to quickly upload, edit, delete your own videos, while also being able to view other users' videos. My program consists of two models- users, and videos, with the latter belonging to the former. A user can essentially have many videos.

![](https://imgur.com/2XTY3ss)

The user begins by signing up (if they don't already have an account) or logging in (if they have an account). If they're signing up, they must fill in each field (email, username, password). If they leave any field blank, they'll be taken back to the signup page. The same applies for logging in, they must fill in a valid username and password to proceed. The user's password gets secured via the bcrypt gem. The signup and login function was straightforward thanks to this gem for streamlining the process.

![](https://imgur.com/7ItyN0Z)
![](https://imgur.com/3Qk6t0l)

Once the user signs up or logs in, they will be directed to the home page:

![](https://imgur.com/orl3SEn)

From here a user can share a video by clicking on the link 'share video'. This will bring the user to a page where they can give their video a name and category property. Once they have filled in both fields, they simply click on the share video button and they will be brought to the newly uploaded video's show page.

![](https://imgur.com/SsO8gfy)

Once the user has rendered this view, they can edit/delete this video from the server, go back to the home page for browsing, log out to end the session.

![](https://imgur.com/p9WN4rd)
