---
title: "NIXT: Observability of Collective Communication in Large Model Training"
date: 2026-08-06
weight: 2
tags: [NCCL, Collective Communication, Observability, Distributed Training]
summary: "A NCCL Inspector eXporter Tool that turns high-volume NCCL profiling streams into actionable insights, deployed on Nemotron-4 pretraining at up to 2,048 H100 GPUs."
---

## Overview

Collective communication is a first-class citizen in large model training — and one of the hardest things to observe at scale. **NIXT** (NCCL Inspector eXporter Tool), built during my NVIDIA internships, is a profiler-export pipeline that converts the high-volume profiling stream from NCCL Inspector into readily accessible analysis and actionable insights for collective-communication performance.

## What NIXT Provides

- Per-collective, per-rank visibility into communication behavior (operation mix, message sizes, bandwidth, timing) with low overhead.
- A real-time telemetry path: NCCL Inspector → Prometheus exporter → Grafana dashboards, enabling live monitoring of large GPU clusters.
- Analysis techniques to attribute performance variation across ranks and to root-cause stragglers and communication anomalies.

## Case Study: Nemotron-4 Pretraining

Applied to Nemotron-4 LLM pretraining on an NVIDIA H100 cluster scaling up to **2,048 GPUs**, NIXT characterized how communication phases shift with ML parallelism and GPU scale, attributed performance variation across ranks, and performed root-cause analysis of stragglers.

## Links

- Paper: [arXiv:2608.01449](https://arxiv.org/abs/2608.01449) — to appear at **IISWC 2026**
- NVIDIA blog: [Enhancing Communication Observability of AI Workloads with NCCL Inspector](https://developer.nvidia.com/blog/enhancing-communication-observability-of-ai-workloads-with-nccl-inspector/)
- NVIDIA blog: [Real-Time Performance Monitoring and Faster Debugging with NCCL Inspector and Prometheus](https://developer.nvidia.com/blog/real-time-performance-monitoring-and-faster-debugging-with-nccl-inspector-and-prometheus/)
