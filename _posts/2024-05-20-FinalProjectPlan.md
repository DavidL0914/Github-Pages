---
toc: false
comments: true
layout: post
title: Final Project Planning
courses: { csp: {week: 33} }
description: David and Brandon's plan for final project (Algorithm project)
type: hacks
---

### Overall Idea
* My feature on the CPT was a forum on our cooking website. The forum allowed users to post text for other users to see. This allowed users to share their favorite recipes or questions they have on certain foods/recipes they are looking at on our website. 
* I plan on adding a feature where users can upvote posts. The most up-voted post shows up at the top of the forum for a week - represents post of the week!
  * Every week the upvotes reset (prevents cluttering) to make way for a new most upvoted message of the week

### Loops/Iteration:
* Each time a user upvotes a message, the system records this action and updates the message's upvote count
  * This involves iterating through user actions to identify which message to update
* The algorithm iterates over the messages to locate the one that has been upvoted
  * For each upvoted message, the system increments its upvote count by one.
  * This demonstrates iteration as the system processes each user upvote action and updates the relevant message.

### Sorting/Big O:
* After updating upvote counts, the system gathers all messages and their respective upvote counts into a list
* The algorithm sorts the list of messages based on the upvote counts in descending order
    * This sorting step rearranges the messages so that those with the highest upvotes appear at the top
    * Sorting involves iterating through the list of messages to compare upvote counts and arrange them accordingly

### Example
![img](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQj9__vdk-YRtp8L-WACkN6Yi0wboXHuR1YwO-raODW4w&s)
![img](https://assets-global.website-files.com/5e5e26b553a5521191e73140/61b7dd8d6e6e58fdd8c55827_upvote_software.jpg)