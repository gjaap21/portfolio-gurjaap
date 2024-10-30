---
title: Blog 1 - TA Review Session Lecture
layout: doc
---

# Using Specific Error Messages at Scale 
## Spooky story for Halloween about the horrors of bugs at scale

During the TA’s recap, they touched on the fact that a lot of people didn’t use specific error messages or extend the errors that were already provided in the code. I realized that I only made a few specific error messages myself, even though I thought I had already learned this lesson, so I decided to share my experience with using more specific error messages, especially at larger scales, as an example for how this can be a really useful concept.

This last summer I interned at Amazon, and their codebase was huge, with a lot of connected parts. Even after looking through what I thought was most of the relevant code for my project, I still wasn’t fully aware of where most things were to be honest. As I started working, I had bug after bug after bug, and almost every single error message was completely useless because they were all basically the same message. The team I was working with was still a fairly new organization, so they were more focused on getting functionality done than putting super useful error messages. If I wanted to figure out where an error was coming from for any front-end code I was changing, I had to “Inspect Element” and then either go into the “Networks” tab and figure out why certain calls weren’t working, like if there was something wrong with the request itself or the back-end API’s, or put breakpoints everywhere, like actually EVERYWHERE because most of the time, the errors would be in how my code interacted with other pieces of code and not in my code itself, to figure out what was going wrong. If it isn’t clear already, this took years off my life. If there had been more specific error messages in each part of the code, I could’ve easily searched the codebase for that error message and found the problem area instantly, and it would’ve saved a whole lot of time.

It can be difficult to see why you need to put really specific error messages when you’re working on a smaller project like this, but when it gets to a larger scale, it becomes waaay more important, so it’s good to start practicing now. Looking back at my code for this project, I realize that I have become the villain with very few specific error messages :/
