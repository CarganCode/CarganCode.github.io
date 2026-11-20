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

If the tag-line of this post doesn't make sense then you might not be up to speed on the _transformer_.
I have been aware of the transformer architecture for a while now.
I spend time at work exploring LLMs like BART and T5, and like everyone else have seen GPT-3 demos from OpenAI.
So, over Christmas I decided it was time to dig into the detail and properly get up to speed.


The original use case for transformers was NLP; in the [original paper](https://arxiv.org/abs/1706.03762) it was used for sequence-to-sequence machine translation.
However, I'm not an NLP expert.
I also know transformers are data-hungry and I have access to a lot of satellite imagery (around 300 GB).
Fundamentally, attention operates over sequences, and there has been substantial work applying transformers to images, such as ViT.
So why not test them on short-term satellite cloud forecasting?

<video autoplay muted loop style="display: block;margin-left: auto;margin-right: auto;">
  <source src="/images/blog/weather_forecast/demo.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<!--more-->

## Follow-up in PhD Research

This experiment was an exploratory prototype predicting future satellite frames directly with vision/sequence transformers. For my main PhD forecasting work, we shifted focus to multi-site solar irradiance forecasting using multimodal Encoder-Decoder Transformers combining EUMETSAT SEVIRI satellite imagery with ground meteorological observations.

That work was published in *Applied Intelligence* (2024): [*Local-global methods for generalised solar irradiance forecasting*](https://link.springer.com/article/10.1007/s10489-024-05273-9) (DOI: `10.1007/s10489-024-05273-9`), with experiment code at [local-global-solar](https://github.com/TimCargan/local-global-solar) and the satellite ingestion tooling at [eumetsat-downloader](https://github.com/TimCargan/eumetsat-downloader).

---
#### Technologies Used

##### Python, JAX, Flax, TensorStore, EUMETSAT SEVIRI imagery
