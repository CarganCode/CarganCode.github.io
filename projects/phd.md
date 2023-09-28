---
layout: page
title: Ph.D.
description: Code name Zephyrus
head-img: '/images/wheel.jpg'
head-short: true
---
<div class="type"> 
    {% include icons/pencil_circle.svg %}
</div>
---

My PhD is titled “Real World Solar Energy Power Prediction and Use Optimisation,” and focuses on developing and applying novel forecasting, planning and optimisation techniques for use with renewable energy.
As renewables become a major source of energy, forecasting production and optimising energy use is key to grid stability. The rollout of; smart meters, domestic energy production, connected appliances, and battery technology present optimisation challenges/ opportunities not only on the commercial scale but at a household level. The amount of data being produced requires novel optimisation and ML techniques that work with existing big data paradigms.


## Phase 1

Code named Zephyrus, after one of the Greek gods of wind.
My dissertation was focused on forecasting solar irradiance using satellite imagery and this is where we are starting the Ph.D. from.
Our plan is to enhance the model and add rigour to the experimental framework used in my dissertation.
The bulk of the machine learning modelling was done using FLAX/JAX.
I made heavy use of TFDS to load the data in, however a fair bit of the pre-processing for the weather data was done in the cloud using spark.

Over the years I have hit many tech issues around spark and images.
After switching to using data from EUMetSat these issues compounded when trying to load and processing their raw data.
It turns out raw satellite data is big and all the tools are very old and not well suited to distributed frameworks like spark.
To deal with that I wrote a [library](https://github.com/TimCargan/eumetsat-downloader) to download and process the raw data on our SLURM cluster.

Our paper “Local-Global Methods for Generalised Solar Irradiance Forecasting,” developed generalised methods to forecast irradiance for locations with minimal historic data is currently under review. 
Leveraging both weather and satellite data, our deep learning model was able to produce forecasts for any location. 
We showed our model generalises well even to locations with no historical data or sensors at the location of interest
A good place to go to see updates is my [zephyrus-public git repo](https://github.com/TimCargan/zephyrus-public).
Unfortunately as of yet I can't publish the raw data, so running the code yourself is a bit hard, but this is something we are working on (reproducible results are a must).


## Phase 2

Code name tulip, since it stated in the spring.
I am currently exploring the intersection of forecasting and optimisation using decision-focused learning. 
The goal is to learn models that have prediction errors that cause a minimal effect on downstream optimization problems such as scheduling. 
Our aim is to use DFL to build models that minimise the total carbon intensity of energy used in the setting of homes with both solar and batteries installed.

---

#### Technologies Used:

##### Python, TensorFlow, Spark
