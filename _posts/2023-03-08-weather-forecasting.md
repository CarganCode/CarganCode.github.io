---
layout: post
head-short: true
title: Weather Forecasting
description: watching clouds transform across the sky
head-img: /images/tree.jpg
author: Timothy R. Cargan
date: 2023-03-08
tags: forecasting 
categories: PhD forecasting
type: code
---

If the tag-line of this post doesn't make any sense then you might not be up to speed of the current trend in deep learning, the _transformer_.
I have been aware of the transformer architecture for a while now. 
I spend time at work exploring LLMs like bart, T5, and like everyone else have seen the impressive GPT-3 demo from openAI.
So, over christmas I decided it was time to dig into the detail and truly get upto speed.


The original use case of the transformers is for NLP, in the [original paper](https://arxiv.org/abs/1706.03762) it was used for sequence to sequence machine translation.
However, I'm not an NLP expert.
I also know transformers are data hungry and I have easy access to a lot of satellite imagery (about 300GB).
Fundamentally, the attention / transformer architecture just deals with sequences and there have been work to use them for images e.g ViT.
So why not use them to try and do weather forecasts?

<video autoplay muted loop style="display: block;margin-left: auto;margin-right: auto;">
  <source src="/images/blog/weather_forecast/demo.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<!--more-->

### FULL REPORT COMING SOON...

<!-- ## The Architecture


## My Use Case
So two key take aways. The raw transformer is sequence invariant (the order of the inputs doesn't matter)
Take the raw satiate images
apply an expanded vision transformer to predict the next chunks

## Code
To do this project needed I needed to do two things. 
1) Write the code to pre-process and load the weather data
2) Make a transformer model

### Loading the data
Going into this project I assumed it would

## Concision
Overall this work seemed like fairly promising direction. 
It would integrate well with the work from in my PhD and potentially lead to a nice next chapter.
As is typical, Microsoft [published](https://microsoft.github.io/ClimaX/) a paper doing something very similar but with more compute and data than I ever could do. 

### References -->


---
### Technolgies used:

##### Python, JAX, TensorStore