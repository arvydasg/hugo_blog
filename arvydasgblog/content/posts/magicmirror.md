---
title: "Magicmirror on Raspberry Pi"
date: 2022-07-12T21:45:39+03:00
cover:
    image: magicmirror.png
    alt: 'First MagicMirror Setup'
    caption: 'magic mirror screen'
tags: ["javascript", "node.js", "raspberrypi", "software"]
categories: ["projects"]
---

# The idea

Found an unused raspberry pi at work. Was wondering what it would be like to use
it for something useful... One of the projects I liked was
"[MagicMirror](https://www.google.com/search?q=magic+mirror+raspberry+pi&tbm=isch&ved=2ahUKEwjZtNr6mur5AhXO_CoKHaYoChQQ2-cCegQIABAA&oq=magic+mirror+raspber&gs_lcp=CgNpbWcQARgAMgUIABCABDIFCAAQgAQyBQgAEIAEMgYIABAeEAUyBggAEB4QCDIECAAQGDIECAAQGDIECAAQGDIECAAQGDIECAAQGDoECAAQQ1C7B1jYEGD_FmgAcAB4AIABVIgBsAWSAQE5mAEAoAEBqgELZ3dzLXdpei1pbWfAAQE&sclient=img&ei=B7oLY5mVJc75qwGm0aigAQ&bih=945&biw=1680)".

What you need:
* Raspberry pi
* Free monitor

Follow a well written tutorial([I watched something like this I
think](https://www.youtube.com/watch?v=OYlloiaBINo&ab_channel=BreakItYourself))
and make it work to your liking.

In case you wonder where to get modules for your MagicMirror -
[check](https://github.com/MichMich/MagicMirror/wiki/3rd-Party-Modules).

Some modules are outdated, so keep that in mind if something does not
work. (like Spanish word of the day in my case. It worked for a month
or so at first).

This setup barely uses any electricity(if your monitor is not super
old), so I would say its quite convenient. We constantly keep an eye
on it.

# Current setup

![magic mirror google calendar](/magicmirror2.png)

Currently displaying google calendar and some other relevant
information. Displaying one google calendar that I use together with
my family members so we are all up to date with the upcoming events.

# Future Ideas

One day I want to learn how to work with API's so I can pull my weight
data from "Google Fit" and display in MagicMirror. 

Or... I could scrape cvbankas.lt and make MagicMirror display all the job
adds that contained word "Python" in it. 

I have many ideas like such :)
