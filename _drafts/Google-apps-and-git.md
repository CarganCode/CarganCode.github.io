---
layout: post
title:  "autoCrat bugs"
date:   2014-08-7 12:34:56
categories: code
---
As you may or may not know, I wright/ maintain the somewhat popular Google Drive add-on autoCrat. We just passed 13,000 users however more importantly, about 2 weeks about I published my biggest update to date. It has a new sleeker look and feel, new functionality and (in theory) is faster at merging docs. The trouble is for the last two weeks autoCrat has been plaged with bugs I've never seen in testing.

The issues range in size from small UI bugs that are annoying but don't brake anything right up to making it unusable. Some are easy to recreate, others are impossible. Some are cause by silly things (forgetting to invert a boolean) some are much more nuanced. 

A great example of this is zero index arrays. All the merge data read from the Google sheets is a zero index array. However when interacting with the sheet directly, e.g `sheet.getLastRow() `, the sheet is 1 indexed. Coming from java and other *normal* programing languages zero index arrays are good and make sense, 1 not so much. Normally it's something I would grim and bear, the trouble is you have to translate 1 index arrays to 0 indexed. But still there is another lay of complexity as the zero index arrays used to store the merge data don't include the headers whereas when interacting with the sheets they are.

These kinds of bugs are tricky but not impossible to fix once you know what you are looking for. The hard ones are when you don't even know what you are looking for. Multiple people report something as not working so you test, and it works fine. You ask for a more detailed bug report, something more than "Its not working! FIX IT!" Still you can't recreate the error, what are you supposed to do?!? These are people that rely on the tool, in some cases it makes them money