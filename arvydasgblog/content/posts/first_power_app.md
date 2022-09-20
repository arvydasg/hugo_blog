---
title: "Microsoft Inventorization Power App"
date: 2022-08-27
cover:
    image: powerapp.png
    alt: 'pkc powerapp different screens'
    caption: 'power app demo'
tags: ["microsoft", "pkc", "software"]
categories: ["projects"]
---

# The problem

Many odd, but necessary jobs appear in PKC on a daily basis. This
Saturday I have worked on Inventorization solution for PKC. Since I
got the responsibility to manage invoices of purchased IT items, I
also noticed that there is no system whatsoever of where/when/how many
things arrive to our IT office or how many we hand out to users or
production or how many are being sent to other sites.

And then once in a while someone from Finances asks me: Who this
computer belongs to? What inv.nr sticker does it have? Who has this
phone, what are the phone numbers that PKC uses and SO ON.

I basically never have the answers, because there was no documentation.

Even a simple excel sheet with all this info written would have been
better than a stack of paper sheets with user info that PKC collected
over 5 or so years.

# The solution

## First attempt

I have been looking for a solution for almost a week. My first attempt
was this - [Check in / out Google Sheets](https://www.youtube.com/watch?v=0PtnVvrVTCY&ab_channel=TheMobileSalesEngineer), it worked quite well, I was
about to present it to my Manager, but after 50scans I have figured
out that it's a paid app. Nope. On a closer look - it was quite
clumpsy to use.

## Second attempt

Okay, now I thought I found what I need. This excelent example that
uses forms - [Google QR Inventory](https://www.youtube.com/watch?v=cdqEB78cHpw&ab_channel=RandyBennett) I was sure will solve my problem, I
just need to tweak it a little. I tweaked, I weaked.. 3 days, I keep
tweaking.. it is too confusing with all these sheets that get
created... + I keep updating my excel data sheet and I don't see how
this could work.. I need another solution.

## Third and Final attempt

### License

I am glad I did not give up after all this work. I was obsessed with a
solution, no matter where I went I was googling about this
inventorization app. I then found [Google Apps
Script](https://developers.google.com/apps-script) thought okay, maybe
I should look into that... then I came up [Microsoft Power
Apps](https://powerapps.microsoft.com/en-us/) and thought wait, is it
included in my E3 license? Went to PKC o365 admin panel, found myself,
assigned a the proper license and I can now start playing with Power
apps.

### Extremely intuitive

I was shocked that one can create web and phone apps with Wordpress
like interface. Many videos on YouTube of how it can be done... I have
found one that resembled my case and followed it. Build Cloud
Inventory Management App using power apps and SharePoint. 24hours of
intense tweaking and redoing and I have finally made my app. It was
quite simple and intuitive...

* Now I can SCAN new inv.nr as well as serial numbers and add new
  items AS SOON AS they arrive to our office.
* Whenever me or my colleague is handing out equipment from IT
  warehouse - they will scan the TTR number and fill out the info to
  whom, when the item will be given.
* All of the information will be tracked in google list and achieved
  on our IT Team sharepoint, so whenever anyone from financses or my
  manager needs to review anything - they will be able to comfortably.
  
## Conclusion

At first I wasn't so happy doing "IT warehouse worker" job... after
all I am here to get IT experience, now warehouse experience... BUT I
found a way how I can implement my knowledge and my drive for learning
new things and automating/making processes easier in this situation. I
will continue doing the inventorization part of work, but now with an
app that I have made. :)
