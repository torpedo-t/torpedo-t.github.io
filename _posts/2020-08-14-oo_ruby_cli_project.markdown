---
layout: post
title:      "OO Ruby CLI Project"
date:       2020-08-14 11:55:41 -0400
permalink:  oo_ruby_cli_project
---

**A Gem's Creation**

Every journey is simultaneously a beginning and an ending: I left my old life behind and began a journey to find a new me! A journey filled with new rules to follow, and an entirely new language to comprehend. A journey that has taken me half way around the globe, without ever leaving my house.

In fact, this journey of mine, lead me straight to Japan (the birthplace of Ruby). Where none other than Yukihiro Matsumoto created this interpreted, high-level, general purpose programming language, that was designed and developed in the mid 1990's, with the capability to analyze data, prototype, and prove concepts. 

My task was to familiarize myself with this programming language enough to develop my own CLI Gem. A gem that could be used by anyone around the world (as long as they are english-literate). 

My CLI Gem is a program that scrapes data from (https://www.artic.edu/exhibitions) The Art Institute of Chicago's Exhibition's URL. And, with this Gem, I am able to display every current Exhibition at The Art Institute of Chicago (in a short, concise list) with a single command. And, i'm also able to view the entire description of any Exhibition (of my choice), with another single command. So, if you enjoy Art Exhibitions, I definitely recommend checking this out!

My program is based on the following problem and solution:

* Problem: The Art Institute of Chicago's website takes too long to scroll through, and most users would like the process simplified. They don't want to scroll incessantly to see all of the exhibitions. And, they also don't want to load and re-load a new webpage every time they want to learn more about an exhibiton. 

* Solution: Allow user's to view all of the exhibitions in a short, easy to read list; with the ability to punch in one key-command to learn more (view the exhibition's description).

Features Include:

* Scraping HTML via Nokogiri.
* Creating and saving Exhibition objects with :Name, & :Link attributes.
* Viewing every current Exhibition, that The Art Institute of Chicago has to offer, with the click of a button.
* Viewing the Exhibition's description by entering it's index within the list (1, 2, 5, etc.).
* Viewing menu options: 1) View the list of Exhibitions again. 2) Exit program.

This project came with many challenges, and there was no shortage of difficulties to overcome. Following are the biggest challenges, that I personally faced, and how I overcame them:

Scraping data from multiple URL's within one method:

My `Exhibition` class has many `Exhibition` object's, and each and every `Exhibition` object has it's own unique, and distinct URL (where the `Exhibition's` description is located). This was particularly tricky for me, until I began initializing each `Exhibition` object with a `:link` attribute. This was necessary for my program, because I needed a way to grab and present the correct description (based on the user's input). So, to do this, I had to scrape the `Exhibition's` `"href"` attribute (the URL) in the initial scrape. I did this by iterating through all of the Exhibition blocks within the webpage and setting my `@link` instance variable (which is none other than the :`link` attribute associated with each and every instance of my `Exhibition` class) equal to `e["href"]`, which essentially is just an argument of my iteration (`e`) going through and grabbing the associated URL, and appointing that URL, as that `Exhibition's` `:link` attribute. It was necessary that I do this, because after scraping every `Exhibition's` `:name`, and `:link` and creating every `Exhibition` object, I needed a way to pass in the desired `:link `associated with the chosen `Exhibition`, and this just happened to be the best way (I knew) to solve my problem.

Making the program user friendly:

My `CLI` class was in charge of instructing the user on how to use the program. It's duty was to provide quick, and simple instructions, that anyone could follow, for a user-friendly experience. The goal was to reduce the amount of reading and writing, that the user was responsible for, while still providing them with all the necessary information. To do this, I used a method defined as `list_current_exhibitions`, where I utilize my `@current_exhibitions` instance variable (which was set equal to the entire array of Exhibition objects aka `Exhibition.all`) to iterate through each `Exhibition`, to print out the Exhibition's index (within the array), and it's` :name` attribute. By doing this, the user can quickly associate which `Exhibition`, they want to learn more about, with the number directly to the left of it. Now, the user can simply input "1" or "2" and my program will grab the description to the desired `Exhibiton`. This removes any typo's or any other human related errors from the process.

All in all, I learned a ton from by researching and overcoming the many obstacles, that I faced along the way. And, I anxiously await the new set of obstacles, that will present themselves next!


























