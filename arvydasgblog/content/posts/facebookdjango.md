---
title: "Facebook automation with Django"
date: 2022-02-05T17:03:29+03:00
cover:
    image: facebookdjango.gif
    alt: 'facebook automation with Django'
    caption: 'facebook automation with Django'
tags: ["django", "automation", "openpyxl", "pillow", "pyAutoGUI", "webdev", "software"]
categories: [""]
---

A short [demo video](https://www.veed.io/view/c32a9c68-e5c3-48be-939e-b3121bc8d8f9) of how it works. 

[Github repository](https://github.com/arvydasg/facebook_django).

# What is it for

A recently started smoothie drink powder business that is testing
itself out in the field. Instead of purchasing ads on facebook, the
client first wanted to post their content to various facebook groups
to see the engagement. Over time this tasks proved to be too tedious,
since it requires a lot of manual clicking.

I have decided to help them out by creating this automation bot that
posts to various facebook groups by itself, with client needing to
click only a few clicks. There were various facebook bots on the
internet, but you had to pay fro those. It was interesting for me to
see if I can create something like it myself.

# How it works

All the user need is a link to the facebook post and a call to action
message. He then needs to input these two into the browser window and
click start. Application does the rest. Taking the data from the
groups file, going through each and every one of them and posting the
choosen content (link, ad description and a call to action message).
Leave it running, come back after a white - inspect the terminal
windows - see how many successful group posts this app has done.

# Cons

There are a few cons of using this script.

* You can not really use the computer while it runs since it occupies
  your mouse and you shouldn't be clicking on other windows while it
  is running. You can run this script while you are having a break,
  step away from your computer for 15min or so and come back with
  having your post shared to 30 or so groups.
  
* Your facebook account gets restricted. Often. If you are posting to
  too many groups at a time. 20 or so is fine, but more than that (in
  one sitting) and you are risking to get a temporary ban by facebook.

# What to fix

* if the script breaks - take a screenshot of the whole screen (easier
  to debug what happened)
* when the script finishes posting to one group - take a screenshot
  (easier to track the activity)
* If group has pending posts - stop the for loop, run next group
* Rebuild facebook_django app with modules
