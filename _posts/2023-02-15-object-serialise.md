---
layout: post
title: Serialise Objects in Python
author: Tim Cargan
date: 2023-02-15
tags: life
categories: Snippet
type: Code
short: True
---
I Often have data stored in python objects that aren't dataframes.
Think config objects.
Saving and loading these data objects to and from disk is often very helpful.
The easiest way to save an arbitrary object is to use `pickel`, however you almost always shouldn't.
It is a security nightmare and in the worst case can lead to arbitrary code execution.
A safer alternative is to serialize the data:

{% highlight javascript linnos %}   
import json
s = json.dumps(dict_object) 

dict_obj = json.loads(s)
 {% endhighlight %}

 There are also `dumb` and `load` that work directly with files and not string objects.

 I have also recently come across [pyserde](https://yukinarit.github.io/pyserde/api/serde.html). 
 A super cool library that allows the serialisation of `dataclass` objects.


