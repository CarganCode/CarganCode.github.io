---
layout: page
title: autoCrat
description: yes, the first 'a' is supposed to be lower case
head-img: '/images/ts.jpg'
---

##autoCrat

autoCrat is a Google Sheets Add-on used by over 80,000 people worldwide as a document merge utility for Google Drive. Originally build by Andrew Stillman, as a Sheets Script, for New Visions for public schools. The Add-on version was completely rebuilt from the ground by me in the spring of 2014. I worked as part of the pre-release group of developers to be one of the first add-ons available in the store. 

Some of the issues that had to be dealt with:

- Relatively slow read time from the spreadsheet. I had to implement a caching system 

- If the user had a lot of documents to merge the add-on needed to find a way not to timeout.  Each merge ended up being its own server call since it was relatively safe to assume 1 document wouldn’t take more than 5 minuets

- Ensuring the rate limit of document creation was never exceeded. In an effort to speed up the merge multiple server calls were made at once to try and reduce the overall time it took to merge all the documents. (This proved to be unstable and the current version of autocrat doesn’t use this technique) 

---

####Technologys Uses:

#####Google Apps Script, Java Script, HTML + CSS
