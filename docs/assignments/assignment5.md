---
title: Assignment 5
layout: doc
---

# Assignment 5: Frontend Design and Implementation
16 October 2024

## Heuristic Evaluation
### Usability criteria:
- Discoverability
    - The interface does a good job here since its buttons are easy to understand and their actions should be familiar from other apps. For example, the like button is very familiar, the arrows to switch posts are self-intuitive, the report button is labeled, clicking on your profile pic takes you to your profile, clicking the home icon takes you to the home page, and the plus button makes a new post. One thing that could be improved is removing the arrows and just allowing users to scroll through posts since that’s probably how they would expect to operate the interface. Another thing is the “Likes” menu option on the profile page might not be very clear in that it is clickable, so we could potentially make it more button-like.
- Efficiency
    - One place that does a good job here is the report button. The core value of the app is safety, so it makes sense for the report function to be just one click away which is why it’s displayed right next to every post. This might sacrifice consistency a little bit since most apps have the report option hidden behind a menu, but it’s a good tradeoff to make since it ties into the intentions of the app. On top of this, clicking the report button pops up a report menu, and the submit button for that is in the same spot, so users can quickly submit an empty report if they feel no additional information is needed. 

### Physical heuristics:
- Gestalt principles
    - The comments and like button of an associated post are placed very close together which makes sense for them to be grouped. The comments label is also placed inside of its box as the heading which is another good grouping to have. The following and follower counts are placed directly underneath their labels, so it’s easy to associate those things together. 
- Accelerators
    - One shortcut provided for users is the ability to see all of their liked posts in one place by simply toggling to the “Likes” menu option on their profile page. I’m not sure if there are many other opportunities to apply this in the app, but it would be nice if the search bar had autocompletion for accounts. That might be a little hard to implement, so I’m not sure if that will be added in this project, but it will be considered for sure.

### Linguistic level:
- Speak a user’s language
    - Some places where this is done well is the report button is very understandable in what it does and instructions are very simple where they are provided, such as on the make a post screen for the image and caption and on the report menu. On the make a post screen, we could make the instructions more concise and less fun which I think would better follow this heuristic, but I think this is a moment where we want to trade that off because the app is about safety and is more geared towards younger audiences, so I think a more playful tone is a good thing here.
- Consistency
    - I touched on this in discoverability, but it does use similar interface designs as other apps, such as the like button icon, the profile page is pretty recognizable, and the way to navigate between the home and profile page is fairly common. One place to improve on here, as said earlier, is allowing users to scroll through posts instead of clicking a button. By using consistent icons and buttons from other apps, we sacrifice Fitt’s Law a little bit since they’re mostly just small buttons on the edges of the screen like the profile picture icon. We could make that specific button take up the entire corner of the screen to make it easier to click.

## Frontend Code Repo
https://github.com/gjaap21/safespace-frontend/tree/main

## Deployed Service
https://vercel.com/gjaap21s-projects/safespace-frontend

https://safespace-frontend-one.vercel.app

https://safespace-frontend-eiusededr-gjaap21s-projects.vercel.app

Admin account for you guys to use when testing: user=gjaap, pass=secret123
