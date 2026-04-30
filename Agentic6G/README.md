Official repository for the paper:
**"6G Needs Agents: Toward Agentic AI-Native Networks for Autonomous Intelligence"**

---

## 📌 Overview

This repository provides the **code, experimental setup, and results** for evaluating Large Language Model (LLM)-based agents in next-generation 6G systems.

We introduce a novel paradigm:

> **Agentic AI-Native 6G**, where LLM-based agents operate as reasoning entities within a semantic control plane layered above deterministic 3GPP infrastructure.

Unlike traditional optimization-centric AI approaches, this work focuses on:
- Intent-aware reasoning
- Multi-agent coordination
- Tool-augmented decision-making
- Deployment across the **device–edge–core continuum**

---

## 🧠 Key Contributions

- 🏗️ **Four-layer Agentic 6G Architecture**
  - Deterministic Infrastructure
  - Semantic Abstraction
  - Agentic Reasoning
  - Distributed Multi-Agent Fabric

- 🤖 **LLM-based Agent Framework**
  - Multi-step reasoning (Perceive → Plan → Act → Reflect)
  - Tool invocation and orchestration
  - Policy- and trust-aware decision making

- 📊 **6G-Bench Evaluation Pipeline**
  - Domain-specific benchmark for agentic decision-making
  - 30 task categories (intent, slicing, trust, orchestration, etc.)

- ⚖️ **System-Level Trade-off Analysis**
  - Accuracy vs latency vs throughput vs memory
  - Impact of quantization (Q4, Q8, etc.)

- 🌐 **Heterogeneous Deployment Insight**
  - No single model satisfies all constraints
  - Necessity of device–edge–core distribution

---

## 🧱 Repository Structure

```
.
├── data/                     # Benchmark data and processed episodes
├── prompts/                  # Prompt templates for 6G-Bench
├── scripts/                  # Experiment scripts and utilities
│   ├── run_inference.py

├── models/                   # Model configs (Ollama / llama.cpp)
├── results/                  # Raw and processed results
│   ├── accuracy/
│   ├── latency_throughput_memory/

├── figures/                  # Plots and paper figures
├── config/                   # Experiment configurations
└── README.md
```

---

## ⚙️ Setup

### 1. Clone the repository

```bash
git clone https://github.com/your-username/agentic-6g.git
cd agentic-6g
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Install Ollama and models

Follow: https://ollama.com/

Example:
```bash
ollama pull qwen:7b
ollama pull gemma:4b
```

---

## 🚀 Running Experiments

### Run inference on 6G-Bench

```bash
python scripts/run_inference.py \
  --model qwen3.6:27b \
  --quantization q4 \
  --dataset data/6gbench.json
```

### Evaluate results

```bash
python scripts/evaluate.py \
  --predictions results/output.json \
  --ground_truth data/labels.json
```

### Compute metrics

```bash
python scripts/metrics.py
```

---

## 📊 Metrics

We evaluate both **reasoning performance** and **system efficiency**:

### Task-level metrics
- Accuracy
- Per-task accuracy
- Pass@k

### System-level metrics
- Latency (cold / warm)
- Throughput (tokens/sec)
- Memory usage (VRAM)

---

## 📈 Results

Key findings:

- Large models (e.g., Qwen, LFM) achieve highest reasoning performance
- Quantization effects are **non-uniform** across models
- Smaller models benefit from stochastic reasoning (pass@k)
- **No single model satisfies all constraints**

👉 This motivates **heterogeneous deployment across device–edge–core**.

---

## 🤖 Supported Models

- DeepSeek-R1
- Gemma 3
- Granite 4
- LLaMA 3.2
- Qwen 3.x
- Nemotron
- SmolLM
- LFM (MoE models)

Quantization formats:
- Q4
- Q4_K_M
- Q8

---

## 🧪 Experimental Environment

- **Framework**: Ollama + llama.cpp
- **Orchestration**: OpenClaw
- **Hardware**: NVIDIA L40S (46GB VRAM)
- **Inference**: Local (no API)

---

## 🔁 Agentic Pipeline

The evaluation pipeline follows:

```
Perceive → Plan → Act → Reflect
```

- Perceive: Parse context and telemetry
- Plan: Decompose intent into tasks
- Act: Invoke tools / APIs
- Reflect: Validate outputs and adjust

---

## 🔐 Reproducibility

- Deterministic evaluation (T = 0)
- Fixed seeds per task
- Standardized prompt templates
- Logged runtime metrics

---

## 📄 Citation

If you use this work, please cite:

```
@article{ferrag2026agentic6g,
  title={6G Needs Agents: Toward Agentic AI-Native Networks for Autonomous Intelligence},
  author={Ferrag, Mohamed Amine and others},
  year={2026}
}
```

---

## 🤝 Contributing

Contributions are welcome!

- Open issues for bugs or suggestions
- Submit pull requests for improvements
- Add new models or benchmarks

---

## 📬 Contact

Mohamed Amine Ferrag  
📧 mohamed.ferrag@uaeu.ac.ae

---

## ⭐ Acknowledgements

- 6G-Bench benchmark
- Ollama & llama.cpp
- OpenClaw orchestration framework

---

## 📢 License

This project is licensed under the MIT License.

---

## 🚀 Vision

This repository aims to support research toward:

> **Self-reasoning, intent-aware, and autonomous 6G networks powered by distributed AI agents.**

---

