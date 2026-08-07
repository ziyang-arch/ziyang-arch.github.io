---
title: "PCCL: Energy-Efficient LLM Training with Power-Aware Collective Communication"
date: 2026-08-05
weight: 3
tags: [NCCL, DVFS, Energy Efficiency, LLM Training]
summary: "A power-aware collective communication library that applies per-operation GPU DVFS, cutting collective energy by ~27% and end-to-end LLM training energy by 17.3% with negligible throughput impact."
---

## Overview

Bandwidth-bound collectives (all-reduce, all-gather, reduce-scatter) dominate communication time in distributed LLM training — yet their performance is largely **insensitive to GPU core frequency**. Running them at boost clocks burns power for no throughput benefit. **PCCL** (Power-aware Collective Communication Library, ICCD 2024) exploits this property directly inside the communication library.

## Design

PCCL extends NCCL to apply **per-operation DVFS**: it lowers GPU frequency when entering bandwidth-bound collective operations and restores it for compute phases, transparently to the training workload. No model or framework changes are required.

## Results

- ~**27%** reduction in collective communication energy.
- **17.3%** reduction in end-to-end LLM training energy.
- Negligible impact on training throughput.

## Links

- Paper: [PCCL (ICCD 2024)](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=hKWh7p4AAAAJ&citation_for_view=hKWh7p4AAAAJ:9yKSN-GCB0IC)
