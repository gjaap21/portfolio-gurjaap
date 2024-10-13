---
title: Assignment 4
layout: doc
---

# Assignment 4: Backend Design and Implementation
3 October 2024

## Data Modeling
### Authenticating
- State 
    - registered: set User
    - username, password: registered → one String
### Sessioning [User]
- State
    - active: set Session
    - user: active → one User
### Posting [User]
- State
    - posts: set Post
    - user: posts → one User
    - content: posts → one Image
    - date: posts → one Date
### Friending [User]
- State
    - friends: set (User1, User2)
    - requests: User → set User
### Commenting [User, Item]
- State
    - comments: set Comment
    - user: comments → one User
    - item: comments → one Item
    - content: comments → one String
    - date: posts → one Date
### Liking [User, Item]
- State
    - likes: set Like
    - user: likes → one User
    - item: likes → one Item
### Reporting [Item]
- Purpose - users can notify administrators about inappropriate content on the app
- Operational Principle - after a user reports an item, and optionally provides additional information, administrators will see that item and address it
- State
    - reports: set Report
    - item: reports → one Item
    - info: reports → one String
- Actions
    - create (item: Item, info: String, out report: Report) - creates a report using item and optional information info provided by an anonymous user and adds it to reports
    - getReports (out uReports: set Report) - returns uReports, or all of the reports in reports state
    - address (report: Report, validity: Boolean) - removes report from reports and handles actions according to the value of validity
### Blurring [User, Item]
- Purpose - users can choose to blur certain items and change the blur intensity
- Operational Principle - item x will be blurred, if x is in filter, to a predefined degree until the user changes the intensity
- State
    - filters: User → set Item
    - intensity: filter → one Int
- Actions
    - system blur (item: Item, out blurItem: Item) - returns blurItem, a blurred version of item to the degree of a predefined standard if item is in filter
    - addFilter (user: User, filt: Item) - adds filt to user’s filters 
    - removeFilter (user: User, filt: Item) - removes filt from the user’s filters
    - changeIntensity (item: Item, intensity: Int, out blurItem: Item) - returns blurItem, a blurred version of item to the degree of a user-defined intensity
### Badging [User]
- Purpose - users can have badges displayed on their profile
- Operational Principle - once earned, a badge of the earned type will be displayed on the user’s profile until removed
- State
    - badges: User → set Badge
    - type: badges → one BadgeT
- Actions
    - give (user: User, type: BadgeT, out badge: Badge) - gives badge of type type to user
    - getBadges (user: User, out uBadges: set Badge) - returns uBadges, all the badges in badges associated to user
    - remove (user: User, badge: Badge) - removes user’s badge from badges

## App Definition
app SafeSpace

	include Authenticating
	include Sessioning [Authenticating.User]
	include Posting [Authenticating.User]
	include Commenting [Authenticating.User, Posting.Post]
	include Liking [Authenticating.User, Posting.Post]
	include Friending [Authenticating.User]
	include Reporting [Posting.Post]
	include Blurring [Authenticating.User, Posting.Post]
	include Badging [Authenticating.User]

## Abstract Data Diagram
![Abstract Data Diagram](../../assets/images/abstractDataDiagram.png)

## Design Reflection
One ambiguity I came across was what to store in the Likes collection. In my conceptual designs, 
I had just said that each Like should be mapped to a user and an item. However, there’s many 
different ways to do that. One option is just having one Likes collection where each doc has one 
user and one item. However, that could be pretty slow at scale, depending on the operations we need. 
I know that a very frequent operation will be loading the quantity of likes on a post, and a less 
requent operation will be gathering all of a user’s likes in one place. Based on these considerations,
I opted for two collections, userLikes and itemLikes. userLikes is just like the Likes collection 
mentioned above, and its primary use is getting all of a user’s likes while itemLikes is solely 
responsible for mapping an item to the number of likes it has, so that the frequent operation can be 
done quickly.

Another ambiguity was how to display posts. I didn’t dive too deep into it here since this is the 
backend, and this problem will be easier to tackle on the frontend, but in my conceptual design, I 
assumed that I could just have the Posting concept handle displaying the post. However, while working 
on it, I realized that posts require a lot more than just Posting, so I opted for not including a 
display function at all in Posting and handling it entirely in the synchronization. I have a 
Blurring concept that allows users to blur posts, and I made the decision not to store the blurred 
posts and just directly display them. I did this because I think they will be taking up a lot of 
unnecessary space since we can just easily re-blur later if we need to. By doing it this way, I can 
also display regular posts that don’t need blurring through the Blurring concept by setting it to 
an intensity of 0. This allows me to simplify my synchronization a little bit, so I opted for this route.

## Backend Code Repo
https://github.com/gjaap21/safespace-backend

## Deployed Service
https://safespace-backend.vercel.app
