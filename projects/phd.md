---
layout: page
title: Ph.D.
description: Code name Zephyrus
head-img: '/images/wheel.jpg'
head-short: true
---

## Ph.D. [Code name zephyrus]

As of Nov 2021, a good place to go to see updates is my [zephyrus-public git repo](https://github.com/TimCargan/zephyrus-public).
Unfortunately as if yet I can't publish the raw data, so running the code yourself is a bit hard, but this is something we are working on (reproducible results are a must).


I have code named my Ph.D. project, at least the first part, Zephyrus, after one of the Greek gods.
My dissertation was focused on forecasting solar irradiance using satellite imagery and this is where we are starting the Ph.D. from.
Our plan is to enhance the model and add rigour to the experimental framework used in my dissertation.
From there we plan to use agent based optimisation to see what kind of impact adding batteries would have (have a look at my agents project for UG for an idea of what that means).


Currently the bulk of the machine learning modelling is done in TensorFlow.
I make heavy use of TFDS to load the data in, however a lot of the initial processing is done in the cloud in spark.
Over the years I have hit many tech issues around spark and images, it has gotten better but there can still be issues (OOM issues are the worst).
We recently added a new data source EUMetSat and have hit many issues processing their raw data.
It turns out raw satellite data is big and all the tools are very old and not well suited to distributed frameworks like spark :'(.


---

#### Technologies Used:

##### Python, TensorFlow, Spark
