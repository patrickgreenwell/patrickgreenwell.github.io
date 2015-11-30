---
layout: post
title: Importing GTFS into a MongoDb
categories: [Transportation, Coding]
tags: [Transit,MongoDb,GTFS,mongoimport, Transportation, Planning]
published: False

---

Recently I've taken an interest in expanding my knowledge of transportation planning along with regional and city planning.   One of the main tools used by many agencies is the [GTFS] File.  This is a collection of an Transit Agency or Agencies routes, their stops, the trips they take and when they stop at specific stops.  It also optionally includes [GeoJSON] of the route's  shape on a map.  This file is how Google knows that you need to take the 1 Bus down Mass Ave to get where you're going when you select the transit option.  This file is difficult to maintain as it is essentially a zip file(compressed archive) of CSV files that don't have any hard links between the keys between the different files.  

One way you can manage this is by using Excel.  Which many agencies do when they've got a small amount of routes.  Once you get up past a few routes then you need to have some dedicated software to manage and plan the routes and the stops and the stop_times and so on.  If you're wanting to do analysis on any big agency's [transit feed][MBTA] you'll quickly find out excel doesn't really hold up.  Have you ever tried working with an excel file that's 1.9GB?

An easy way to do some analysis is to use a database of some sort, You could go with a traditional SQL database but I'd rather get going quickly and have the option to save things as JSON objects.  For that I'm going to use [mongoDB], a document database that stores items a [BSON] with some extra base datatypes not present in standard JSON.  Mongo is quick, supports atomic operations and can handle quite a large set of documents in various collections.    



[GTFS]:https://developers.google.com/transit/gtfs/reference?hl=en
[GeoJSON]:http://geojson.org/
[MBTA]:https://www.mbta.com/