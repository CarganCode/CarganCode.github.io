---
layout: page
title: PhD Research
description: Learning to Predict for Optimisation
head-img: '/images/wheel.jpg'
head-short: true
---

* **Title**: *Learning to Predict for Optimisation: from Predict-then-Optimise to Predict-and-Optimise*
* **Institution**: School of Computer Science, University of Nottingham (Computational Optimisation and Learning Lab)
* **Status**: Thesis submitted October 2026; viva January 2027 (EPSRC studentship)
* **Supervisors**: Dr Isaac Triguero and Prof Dario Landa-Silva

---

## Overview

Decision-making pipelines classically separate parameter prediction from downstream optimisation. In this two-stage Predict-then-Optimise (PtO) setup, an upstream model is trained against symmetric statistical losses such as mean squared error (MSE), then passed to a solver that has no visibility into prediction uncertainty. Even small statistical errors can cause disproportionate decision regret and constraint violations.

This thesis traces the progression from decoupled PtO baselines through surrogate decision-focused learning to an integrated Predict-and-Optimise formulation, in which learned neural combinatorial solvers serve directly as differentiable task-gradient operators.

---

## 1. Multi-Site Solar Irradiance Forecasting

The first stage examines the predictive foundation of decoupled PtO pipelines under locality bottlenecks, data scarcity, and sensor failures across distributed solar installations:

* **Global cross-learning**: Unified Global models exploit spatial data symmetries across sites, consistently outperforming isolated per-site Local models while reducing performance variance across locations.
* **Cold-start and outage resilience**: Evaluated Global Plant Holdout (GPH) to test generalisation to unseen locations with no local historical data, and formulated Global Plant k-Near (GPkN) to sustain forecasts during telemetry outages via proximal telemetry substitution.
* **Multimodal architectures**: Built Encoder-Decoder Transformers fusing multi-spectral EUMETSAT SEVIRI satellite imagery with ground meteorological features, supported by a custom [EUMETSAT downloader](https://github.com/TimCargan/eumetsat-downloader) for SLURM preprocessing.

While these baselines establish accurate and resilient statistical forecasts, minimising predictive error alone does not prevent downstream constraint violations, motivating end-to-end decision-focused methods. Published in *Applied Intelligence* (2024) with code at [local-global-solar](https://github.com/TimCargan/local-global-solar).

---

## 2. Surrogate Decision-Focused Learning

The second stage investigates Decision-Focused Learning (DFL) via differentiable surrogate loss models (LODL), bridging predictors and non-differentiable optimisation solvers:

* **Evolutionary directed perturbations**: To reduce the high cost of per-instance solver queries during surrogate fitting, I proposed an evolutionary directed-perturbation strategy that concentrates samples near decision boundaries, reaching surrogate convergence with up to 4x fewer solver evaluations on a solar-plus-battery dispatch task ([IJCNN 2025](https://ieeexplore.ieee.org/document/11227956), [directed-perturbations](https://github.com/TimCargan/directed-perturbations)).
* **Cross-domain sensitivity study**: An expanded evaluation across domains showed acute hyperparameter fragility in surrogate-based DFL. Crucially, internal training diagnostics (such as surrogate fit quality and predictor task loss) fail to reliably track downstream decision quality, forcing candidate selection to rely on direct validation against expensive solvers.
* **Applied energy storage collaboration**: Contributed to follow-on work combining decision-focused learning with automated feature engineering for energy storage optimisation (*Expert Systems with Applications*, 2026).

---

## 3. Neural Combinatorial Optimisation Policies as Task-Gradient Operators

The final stage transitions to an integrated Predict-and-Optimise framework implemented from scratch in JAX and Flax, using RL-trained Neural Combinatorial Optimisation (NCO) policies as reusable task-gradient operators:

* **JAX/Flax RL training stack**: Implemented policy-gradient training (PPO and GRPO-style advantages, GAE, Winner-Takes-All multi-policy populations, and self-distillation) for transformer-based knapsack and CVRP solvers. Profiled XLA dispatch and GPU memory throughout to run parallel multi-policy rollouts efficiently inside a single GPU's memory.
* **Score-function gradients without solver calls**: By routing RL score-function gradients through the learned NCO policy back into the upstream predictor, the predictor internalises downstream constraint sensitivities without calling an external solver during training.
* **Visual Knapsack (Image-KS) under uncertainty**: Under deterministic constraints, DFL offers minimal gain over MSE; under uncertain constraints, the Predict-and-Optimise predictor learns to trade marginal item value to cut constraint violations from 34.9% to 14.3%. In addition, the sequential construction order of the neural solver acts as a priority heuristic, recovering over half of the gap to an optimal repack when solutions are truncated at constraint boundaries.
* **Cross-solver transfer (ETETS)**: Within an End-to-End Two Step protocol, predictors trained through the neural policy transfer positively to an exact classical solver (OR-Tools), reducing violations from 45.9% to 23.0% with lower decision regret than two-stage regression (0.1201 vs 0.1313). Adding an auxiliary MSE regulariser anchors parameter scale and cuts OR-Tools violations further to 3.7%, while pairing the predictor with the learned neural policy achieves even stronger feasibility. Pre-training the neural solver on clean instances stabilises co-training.

---

## Publications

1. T. R. Cargan, D. Landa-Silva, and I. Triguero, *"Directed perturbations for efficient learning of surrogate losses"*, in *International Joint Conference on Neural Networks (IJCNN)*, 2025. [DOI: 10.1109/IJCNN64981.2025.11227956](https://ieeexplore.ieee.org/document/11227956)
2. T. R. Cargan, D. Landa-Silva, and I. Triguero, *"Local-global methods for generalised solar irradiance forecasting"*, *Applied Intelligence*, 2024. [DOI: 10.1007/s10489-024-05273-9](https://link.springer.com/article/10.1007/s10489-024-05273-9)
3. N. Alkhulaifi, I. G. Dogan, T. R. Cargan, A. L. Bowler, D. Pekaslan, N. J. Watson, and I. Triguero, *"Decision-focused learning enhanced by automated feature engineering for energy storage optimisation"*, *Expert Systems with Applications*, vol. 302, p. 130554, 2026. [DOI: 10.1016/j.eswa.2025.130554](https://doi.org/10.1016/j.eswa.2025.130554)

---

#### Core Stack

##### Python, JAX, Flax, Optax, Orbax, CVXPY, OR-Tools, Apache Spark, SLURM, XLA profiling
