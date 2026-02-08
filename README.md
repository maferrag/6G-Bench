# 6G-Bench
**An Open Benchmark for Semantic Communication and Network-Level Reasoning in AI-Native 6G Networks**

**Research paper** : https://arxiv.org/pdf/...

👉 If you are looking to evaluate your LLM model using our benchmark, please feel free to contact us at 📩 mohamed.ferrag@uaeu.ac.ae / mohamed.amine.ferrag@gmail.com


## Overview
**6G-Bench** is an open, standardized benchmark for evaluating **semantic communication** and **network-level reasoning** capabilities of foundation models in **AI-native 6G networks**.

Unlike existing telecom benchmarks that emphasize isolated tasks, factual knowledge, or numeric optimization, 6G-Bench focuses on **decision-making over meaning-bearing abstractions**, including:
- network intents and policies,
- slicing and resource management,
- trust, security, and SLA awareness,
- multi-agent coordination and agentic control,
- distributed intelligence and emerging 6G use cases.

The benchmark is grounded in **ongoing 6G standardization activities** (3GPP, IETF, ETSI, ITU-T, O-RAN Alliance) and evaluates whether foundation models can act as **semantic reasoning layers above standardized network functions**.

---

## Key Contributions
- **Standardization-aligned task taxonomy**  
  30 decision-making tasks (T1–T30) organized into five capability categories derived from 6G and AI-agent standardization efforts.

- **Network-level semantic reasoning under uncertainty**  
  Tasks require multi-step reasoning over intent, policy, trust, and future consequences using worst-case regret minimization.

- **Large-scale and high-difficulty benchmark**  
  - 113,475 source scenarios  
  - 10,000 very-hard MCQs generated  
  - 3,722 expert-validated MCQs released for evaluation

- **Rigorous validation pipeline**  
  Automated structural checks combined with human expert review to ensure semantic correctness and uniqueness.

- **Comprehensive model evaluation**  
  Evaluation of 22 state-of-the-art foundation models spanning dense and MoE architectures, open-weight and proprietary systems, and short- to long-context designs.

---

## Capability Categories
6G-Bench defines five standardization-aligned capability groups:

1. **Intent & Policy Reasoning**  
   Intent feasibility assessment, conflict resolution, intent drift detection, and conservative decision-making under uncertainty.

2. **Network Slicing & Resource Management**  
   Slice selection and switching, compute placement, graceful degradation, SLA violation prediction, and energy-aware decisions.

3. **Trust, Security & SLA Awareness**  
   Trust-aware offloading, agent identity and onboarding, third-party exposure control, and automated security response.

4. **AI-Native Networking & Agentic Control**  
   Agent interoperability, agent-to-agent communication, lifecycle management, and network-knowledge RAG decisions.

5. **Distributed Intelligence & Emerging 6G Use Cases**  
   Federated learning orchestration, ISAC decisioning, digital twins, disaster response, and immersive services.

---

## Problem Formulation
Each benchmark instance represents a **semantic decision under uncertainty**.

Given a truncated multi-turn trajectory capturing:
- mission or service intent,
- 6G network state (latency, throughput, packet loss, edge-compute load),
- policy and SLA constraints,
- agent operational context,

The model must select the action that **minimizes worst-case future regret** over a finite horizon.

All questions are **multiple-choice (A–D)** but require:
- multi-step quantitative reasoning,
- uncertainty-aware projection,
- policy and trust constraint evaluation,
- comparison of future consequences.

---
## Benchmark Design

The overall benchmark design and pipeline are illustrated below:

![6G-Bench Benchmark Design Pipeline](Figures/6G_Bench_benchmark_design.png)

The pipeline consists of:
1. **Standardization Collection and Task Extraction**  
2. **Semantic State and Action Abstraction**  
3. **Network-Level Semantic Reasoning & Task Conditioning**  
4. **Dataset Validation (Automated + Human-in-the-Loop)**  
5. **Evaluation & Metrics**

### Task Coverage

The distribution of questions across capability categories and individual tasks is shown below:

![Questions per Capability Category](Figures/6g_bench_questions_per_category_colored.svg)

![Questions per Task (T1–T30)](Figures/6g_bench_questions_per_task_colored.svg)


---

## Evaluation Protocol
6G-Bench provides a unified and reproducible evaluation methodology:

- **Deterministic pass@1 accuracy**
- **Per-task accuracy** (T1–T30)
- **Group-level accuracy** (five capability categories)
- **Selective pass@k accuracy** for reasoning-intensive tasks

Models are evaluated using **task-conditioned prompts** and must return a structured response:

```json
{"answer": "..."}
```
---

## Supported Use Cases

6G-Bench supports:

- benchmarking foundation models for **AI-native 6G research**,

- training and fine-tuning **6G-specialized reasoning models**,

- evaluation of **intent-based networking and agentic control**,

- analysis of **trust-, safety-, and SLA-critical AI decisions**,

- open and reproducible **6G standardization research**.



## Network Conditions in 6G-Bench

6G-Bench emphasizes **worst-case and degraded regimes** for latency, throughput, packet loss, and edge-compute load.

### Regime Distributions

![Latency Regimes](Figures/6gbench_latency_regimes.svg)
![Throughput Regimes](Figures/6gbench_throughput_regimes.svg)
![Edge-Compute Load Regimes](Figures/6gbench_edge_load_regimes.svg)

### Extremal Network Metrics

![Distribution of Per-Question Maximum Network Metrics](Figures/6gbench_metric_boxplots.svg)

These plots highlight that many questions are instantiated under severe latency, edge-load, and reliability stress, aligning the benchmark with deployment-relevant 6G conditions.

---

## Models Evaluated

We evaluate a diverse suite of contemporary foundation models, spanning dense and Mixture-of-Experts architectures, short- and long-context designs, and both open-weight and proprietary systems.

![Models Evaluated on 6G-Bench](Figures/Models_evaluated.jpg)

---

## Results

### Overall pass@k Performance

![Overall pass@k and pass@1 Accuracy](Figures/results.jpg)

### pass@1 Accuracy by Model Scale

To better understand scaling behavior, we report pass@1 (single-shot accuracy) for different parameter regimes:

- **Large Models**

  ![pass@1 – Large Models](Figures/6g_bench_pass1_large_models.svg)

- **Medium Models**

  ![pass@1 – Medium Models](Figures/6g_bench_pass1_medium_models.svg)

- **Small Models**

  ![pass@1 – Small Models](Figures/6g_bench_pass1_small_models.svg)

- **Tiny Models**

  ![pass@1 – Tiny Models](Figures/6g_bench_pass1_tiny_models.svg)

These visualizations show that:
- Some **mid-scale models** can match or outperform larger models on deterministic pass@1.
- **Trust-, security-, and distributed-intelligence tasks** remain among the most challenging categories.

---
