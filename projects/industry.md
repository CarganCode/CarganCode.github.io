---
layout: page
title: Industry Engineering
description: Enterprise Search, Evaluation Infrastructure & ML Systems
head-img: '/images/van.jpg'
head-short: true
---

Alongside my PhD, I have over seven years of part-time industry experience at Acora (formerly Elastacloud), progressing from Data and ML Engineering through to Tech Lead and Senior Data Scientist.

---

## Tech Lead & Senior Data Scientist, Enterprise Search (Jan 2025 - Present)

I lead a team of up to three data scientists developing, integrating, and evaluating LLM-powered enterprise search features, co-owning the technical roadmap with product leadership, running design and code reviews, and mentoring engineers (including coaching a junior data scientist to mid-level).

* **Shared Python SDK**: Architected and maintain the core Python SDK shared across both the production application and offline evaluation codebases, ensuring offline benchmarks and production services execute the same pipelines.
* **Agentic search migration**: Led the transition to an agentic architecture with tool calling, giving users conversational access across both structured and unstructured data sources.
* **Semantic caching**: Built a semantic cache for agentic conversations that cut LLM inference costs by over 30% while holding regression under 1% on our internal evaluation suite.

---

## LLM Evaluation Benchmark & Retrieval (June 2022 - Jan 2025)

* **1,000+ task evaluation benchmark**: Designed and built our internal LLM evaluation platform, covering the evaluation framework, ingestion pipeline, and a web application for team members to contribute tasks. With over 1,000 contributed tasks, it serves as a primary regression check whenever models, prompts, or retrieval pipelines change.
* **Adaptive RAG chunking**: Replaced fixed-window chunking with adaptive, context-aware chunking, improving retrieval recall@k by 15%.

---

## Earlier Production ML & Data Engineering (May 2019 - June 2022)

* **Anomaly detection**: Developed anomaly detection models that enabled an automotive manufacturer to release nearly £1m in warranty reserves.
* **Large-scale Spark ETL migration**: Migrated ETL workloads from SQL to Apache Spark (Scala), cutting runtime by over 20% on 100m+ daily transactions, and collaborated with QA teams on verification plans ensuring exact data parity for financial regulatory compliance.
* **Cloud delivery**: Delivered client-facing data and ML pipelines in Azure alongside internal applied research projects.

---

#### Technologies Used

##### Python, LLM Evaluation, Agentic Systems, RAG, Apache Spark, Scala, SQL, Azure, GCP, CI/CD
