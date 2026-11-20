---
layout: page
title: chemise
description: Open-source training framework for Flax models in JAX
head-img: '/images/graph.jpg'
head-short: true
---

`chemise` is an open-source training framework for [Flax](https://github.com/google/flax) models built on [JAX](https://github.com/google/jax), available on [GitHub](https://github.com/TimCargan/chemise).

---

## Motivation

Unlike PyTorch Lightning or Keras, Flax intentionally leaves the training loop to the user. In research codebases spanning multiple architectures and datasets, re-implementing boilerplate for step updates, device sharding, checkpointing, and metric aggregation quickly becomes repetitive and error-prone. `chemise` began as a thin wrapper to factor out this training-loop scaffolding while preserving JAX's functional semantics and XLA compilation behaviour.

---

## Capabilities

* **Structured training loops**: Provides a clean, Keras-like fit/evaluate workflow around Flax modules without hiding JAX transformations.
* **Multi-GPU parallelism**: Supports data and model parallelism across multiple GPUs using JAX primitives.
* **Experiment state & logging**: Built-in checkpoint management and structured metric logging across training and validation epochs.
* **Dataset integration**: Supports streaming data pipelines via `tensorflow_datasets` alongside in-memory datasets.

---

## Usage in Research

`chemise` served as the shared training layer across my doctoral forecasting and deep learning experiments, keeping model definitions cleanly separated from distributed training, logging, and checkpointing infrastructure.

---

#### Technologies Used

##### Python, JAX, Flax, Optax, Orbax
