---
layout: post
title: Starting out with Meteor.js
categories: ["coding"]
tags: ["Coding","Meteor","Heroku","Git"]
published: True

---

As someone who has mainly worked in the same stack the last 6 years (C#, Asp.net, SQL Server) diving into something new is pretty exciting.  Other than toying around with a few of the MVC libraries in Javascript, I've not really with much outside of the Microsoft Stack.  With the new .net stuff coming down the pipe, WebAPI, ASPvNext, OWIN and the Katana project, I thought I'd take a look to see what else was available out there.  I've always found one of the cool ways to discover new tech is to look to what tech people in hackathons are using.  One such project I chanced upon is [MBTA Ninja](https://www.Mbta.ninja), it's a hackathon project built over a weekend at [Code Accross Boston].  Users Report issues with MBTA subway lines that are then shared with all users in real time.  The app is built ontop of Meteor.js which itself sits upon Node.js.  

## First experiences
After cloning the repo for the MBTA Ninja I followed along on how to get Meteor setup on my windows box.  This was no easy task and led to about 3 hours trying to get a vagrant box setup that would run the project and then allow me to edit files on the host machine so I could edit in whatever text editor I wanted.  Luckily the folks at meteor must have felt my pain because they had a native install of meteor for windows as a release candidate.  

## The Native Windows version

This was much simpler to run on my machine.

I simply:
* [Installed meteor](https://www.meteor.com/install)
* Cloned the repo `git clone https://github.com/patrickgreenwell/mbta-ninja`
* Told meteor to update all packages to make them compatible with the Windows Release candidate `meteor update --release WINDOWS-PREVIEW@0.3.0` (which it helpfully told me the exact command when I tried to run the project the first time)
* Told meteor to run the project via `meteor run`

After that the app stared right up and ran on localhost:3000. Meteor runs a MongoDb as it's backing store, while it also allows you to access those collections from the client side code.  Giving you the lean app that you've wanted, allowing you to only transfer the data needed to render the views. 

The best thing is though you can go in and start modifying files on you local drive and meteor listens for file changes, the second it does it goes ahead and rebuilds your site.  

## Package Management and more

Meteor has it's own package management site called [Atmosphere](https://atmospherejs.com/).  It allows you easily to add packages to the project that you'll use throughout, it's quite simple and meteor itself serves as the all in one compiler, package manager, and deployer(if you want to deploy to a subdomain at meteor.com)  Adding a pacakage is as simple as `meteor add {packagname}`.  I find this to be almost as useful as the NuGet Package Manager or npm for Node, the best part about it over NuGet I've seen is that it handles the version dependency on packages with ease.  If you've ever tried to switch a .net project from one framework version to another and then deal with the packages.config file for NuGet you know what I'm talking about.

## Conclusion

Overall i'm really liking Meteor so far, it seems to have a good number of packages out there [Restivus](https://atmospherejs.com/nimble/restivus),[SyncCronJob](https://atmospherejs.com/percolate/synced-cron),[IronRouter](https://atmospherejs.com/iron/router) for the server side stuff.  While I haven't delved too much into the Template system they've built out for the UI, it looks like it's pretty hand[lebars]y.  I might do some more on walking through developing something in Meteor from the get go if I can think up a good idea.  They've got some handy tutorials on the Meteor.js site and it seems like it covers most all of the bases.  All in all I think Meteor's got a lot of good strengths for building out webapps quickly and efficently, and with Mongo Serving as the backing store on it, it should scale pretty well.  
