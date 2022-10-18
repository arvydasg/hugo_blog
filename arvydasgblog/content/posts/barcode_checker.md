---
title: "Barcode_checker"
date: 2022-10-03T21:58:49+03:00
cover:
    image: barcodu_checkeriukas.png
    alt: 'Barcode checker'
    caption: 'Barcode checker'
tags: ["pkc", "VBA", "automation", "scripting"]
categories: ["projects"]
---

# A complaint 

PKC group has received a complaint regarding one process due to
which nonconformity appeared in some products.

I was asked to make something so ensure the nonconformity in the
process does not repeat.

# Estonian code

I ended up looking through 12 years old
[VBA](https://learn.microsoft.com/en-us/dotnet/visual-basic/) code which had no
documentation, most of the code was in Estonian and it's the developer
did not want to touch his code anymore.

I took the challenge, read through the code, saw the connections,
googled a lot and finally added my own pieces of code to get the
desired outcome. I have added a few barcodes to necessary places.

# Created a whole app with a language I have never worked before

I then created a
[VBA](https://learn.microsoft.com/en-us/dotnet/visual-basic/) app to
scan those barcodes with and instructed the shift leaders as well as
other employers to use the app. 

This app was implemented in 3 departments in Panevezys site, there are
plans of launching it in other sites in Lithuania as well.

The barcodes scanned with the app had to be made available for Quality
personel to check. I have created a shell script that runs at 13:00 on
a daily basis and copies the needed file from the user machine to a
location on the server so it can be accesssed.

# Conclusion

During this project I went from not knowing anything about VBA to
coding a fully functional app wiht it that is now used on a daily
basis and helps to prevent future nonconformities that can be made by
packing departments all around PKC.
