---
layout: post
title: Bugs bugs bugs everywhere!
date: 2014-08-07T14:13:42.000Z
tags: autoCrat, Code, Bugs
categories: autoCrat
type: code
---

As you may or may not know, I wright/ maintain the somewhat popular Google Drive add-on autoCrat. We just passed 13,000 users however more importantly, about 2 weeks about I published my biggest update to date. It has a new sleeker look and feel, new functionality and (in theory) is faster at merging docs. The trouble is for the last two weeks autoCrat has been plagued with bugs I've never seen in testing.   

<!--more-->   

The issues range in size from small UI bugs that are annoying but don't break anything right up to issues that make it unusable. Some are easy to recreate, others are impossible. Some are caused by silly things, forgetting to invert a boolean, some are much more nuanced.   
   
 A great example of this is zero index arrays. All the merge data read from the Google sheets is a zero index array. However when interacting with the sheet directly, e.g `sheet.getLastRow() `, the sheet is 1 indexed. Coming from java and other *normal* programing languages zero index arrays are what I'm used too, 1 indexed not so much. Normally I would just grin and bear, the trouble is I have to translate 1 index arrays to 0 indexed and vice versa. But still there is another layer of complexity as the zero index arrays used to store the merge data don't include the headers whereas when interacting with the sheets they are.   
   
 Here is a great example of where i tripped up, looking back it's trivial but when I first saw its effects trust me when I say it wasn't. I re-wrote at least 3 functions before I realized what was causing it.

{% highlight javascript linnos %}   
 function calcRowsLeft(){   
    var sheet = SpreadsheetApp.getSheet;   
    var sheetData = getAllData(sheet)   
    var header = merge.name + '-' + Strings.stat.stat   
   
       lastRow = 0;   
       while (sheetData[lastRow][header] != null){   
          lastRow++   
       }   
   
    //This is where i messed up, I was only subtracting 1 not 2   
    return (lastRow + 2) //Offset for header AND zero index   
 }   
   
 {% endhighlight %}

These kinds of bugs are tricky but not impossible to fix, once you know what you are looking for its just a bit of thinking (on second thought maybe it is, who likes thinking?). The hard ones are when you don't even know what you are looking for. Multiple people report something as not working so, like the good developer inside us would do, I test but it works fine. I ask for a more detailed bug report, something more than "Its not working! FIX IT!" but still I can not recreate the error, what am I supposed to do?!? I can't mark it as WON'T FIX since I can't even prove it exists. If I tell them its just one of the mystery of the matrix i doubt they will be happy, I don't want unhappy people with my email address.   
   
 And so we end with a quote:   
   
 >"Logic errors are the bane of my existence!" - me, just now.
  
