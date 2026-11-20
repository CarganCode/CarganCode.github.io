---
layout: post
title: Serialise Objects in Python
author: Tim Cargan
date: 2023-02-15
tags: python
categories: Snippet
type: code
short: True
---
I often have data stored in Python objects that aren't DataFrames,
such as config objects.
Saving and loading these objects to and from disk is frequently useful.
The simplest way to save an arbitrary Python object is `pickle`, however in most cases you should avoid it.
It is a security hazard and in the worst case can lead to arbitrary code execution when loading untrusted data.
A safer alternative is to serialise structured data explicitly:

```python
import json
s = json.dumps(dict_object)
dict_obj = json.loads(s)
```

There are also `dump` and `load` functions that operate directly on file handles rather than strings.

For typed dataclasses, [pyserde](https://yukinarit.github.io/pyserde/api/serde.html) is also a clean library for serialising and deserialising `dataclass` objects.
