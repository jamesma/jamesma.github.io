---
layout: post
title: Another Project - Purdue Maps
---

After my internship at Amazon, I became even more comfortable with Eclipse IDE and Java programming so I decided to make some Android Apps to enhance my OOP skills. Browsing through Google Play's directory of apps led to me believe there is a shortage (and a need) of a Purdue campus finder very much like the one that is available on [iOS][]. So, I present to you [Purdue Maps][]:

![Purdue Maps Screenshot](/assets/images/android_purdue_maps.jpg "Purdue Maps Screenshot")

If you're a Purdue CS student like me, you might be wondering how I've managed to create a database of campus locations as there isn't really one made available "publicly". I started my search from [Purdue's campus map][] and wondered if the Google Maps overlay and geo-coordinates are somehow obtained from a database. I digged deeper into the website's JavaScript files using Google Chrome developer tools and I discovered this gem:

![JavaScript Screenshot](/assets/images/android_purdue_maps_how.jpg "JavaScript Screenshot")

Very interesting! So I navigated to that [address][] and found myself looking at an XML file of campus locations with their abbreviations, geo-coordinates and street addresses! What comes next is rather easy, I converted the XML contents into an SQLite database and included it into my Android app to be accessed through custom search suggestion functionality. I didn't create a web service to serve the data as I didn't see the need to overcomplicate things when it is just a small database of locations. I hope you enjoy the app!

[iOS]: 					http://itunes.apple.com/us/app/purdue/id371741254?mt=8 						"Purdue iOS app"
[Purdue Maps]: 			http://play.google.com/store/apps/details?id=com.jamesma.purdue.maps 		"Purdue Maps"
[Purdue's campus map]: 	http://www.purdue.edu/campus_map/											"Purdue campus map"	
[address]:				http://www.purdue.edu/campus_map/xml/MarkersAll5.xml 						"Jackpot"