---
title: "DATE-serve: Energy-Efficient Multimodal Inference Serving"
date: 2026-08-07
weight: 1
aliases: ["/research/tri-serve/"]
tags: [Multimodal LLM, Inference Serving, GPU Power Management, Energy Efficiency]
summary: "A serving system that coordinates workload-aware GPU power management across the multimodal (Thinker/Talker/Vocoder) pipeline to cut serving energy with negligible latency impact. Accepted at ICCD 2026."
---

## Overview

Multimodal LLM serving (e.g., Qwen2.5-Omni) runs a pipeline of heterogeneous stages — a **Thinker** (LLM reasoning), a **Talker** (speech token generation), and a **Vocoder** (waveform synthesis) — each with very different compute characteristics. Serving them on GPUs with default power management wastes substantial energy: GPUs auto-boost to peak clocks even when a stage is memory-bound, stalled on upstream dependencies, or thermally constrained.

## Key Observations

DATE-serve orchestrates **D**ependency, **A**rithmetic intensity, and **T**hermal awareness — the three inefficiency sources it identifies in multimodal serving pipelines:

- **Dependency stalls** — downstream stages idle at high power while waiting for upstream outputs.
- **Arithmetic-intensity mismatch** — auto-boost drives clocks far beyond what memory-bound phases can use, burning power without improving latency.
- **Thermal throttling** — sustained peak clocks erode thermal headroom, causing throttling that hurts tail latency at the worst time.

## Design

DATE-serve coordinates DVFS decisions *across* the pipeline rather than per-GPU in isolation: it sets each stage's frequency based on its workload phase, its position in the dependency chain, and the available thermal headroom, keeping end-to-end latency (TTFT/TPOT and audio real-time factor) within SLO while eliminating wasted boost energy.

## Results

On Qwen2.5-Omni serving workloads, DATE-serve reduces serving energy by double-digit percentages with negligible latency impact compared to default auto-boost operation.

## Publication

- **"DATE-serve: Orchestrating Dependency, Arithmetic Intensity, and Thermal-awareness for Energy-Efficient Multimodal Inference"** — accepted at **ICCD 2026** (regular paper). To appear.
- Preprint (earlier version, as *Tri-serve*): [arXiv:2606.29629](https://arxiv.org/abs/2606.29629)
