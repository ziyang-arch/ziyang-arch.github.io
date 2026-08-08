---
title: "About me"
date: 2026-02-13
---
<img src="/pictures/profile_2026v3.jpg" alt="Profile photo" class="about_me-photo" />

My name is Ziyang Jia, a PhD student in Computer Science at UC Riverside, working on GPU systems for ML applications.
I'm interested in creating better ML systems, making them faster, more energy-efficient on new generation of hardware and new generation of applications.

In life, I'm a music lover and like to play Chopin and jazz on piano. As a tennis player, I like to play sets with 3.5-4.5 players. I often feel benefited from the music and sports even in other field of study or work.



---

## News

- 🎉 I will be joining Meta's AI System SW/HW co-design team as a research scientist intern in June!

---

## Research

My research centers on energy-efficient system software for large-scale ML — from GPU power management and communication observability up to datacenter cooling.

<a class="research-card" href="/research/tri-serve/">
<div class="research-card-title">Tri-serve <span class="arrow">→</span></div>
<p class="research-card-desc">An energy-efficient serving system for multimodal LLMs (e.g., Qwen2.5-Omni). It coordinates workload-aware GPU DVFS across the multimodal (Thinker/Talker/Vocoder) pipeline, jointly tackling dependency stalls, arithmetic-intensity mismatch under auto-boost, and thermal throttling to cut serving energy with negligible latency impact.</p>
</a>

<a class="research-card" href="/research/nixt/">
<div class="research-card-title">NIXT <span class="venue">(IISWC 2026)</span> <span class="arrow">→</span></div>
<p class="research-card-desc">A NCCL Inspector eXporter Tool built during my NVIDIA internships, enabling fine-grained observability of collective communication in large-model training at scale (deployed on Nemotron-4 pretraining with up to 2048 H100 GPUs). NVIDIA blog posts on NCCL Inspector and real-time monitoring with Prometheus are linked inside.</p>
</a>

<a class="research-card" href="/research/pccl/">
<div class="research-card-title">PCCL <span class="venue">(ICCD 2024)</span> <span class="arrow">→</span></div>
<p class="research-card-desc">A Power-aware Collective Communication Library that applies per-operation GPU DVFS, exploiting the frequency-insensitivity of bandwidth-bound collectives to reduce collective energy by ~27% and end-to-end LLM training energy by 17.3% with negligible throughput impact.</p>
</a>

<a class="research-card" href="/research/energy-efficient-cooling/">
<div class="research-card-title">Energy-efficient cooling systems <span class="arrow">→</span></div>
<p class="research-card-desc">My earlier research at HUST on improving datacenter economy with warm-water cooling, including fine-grained warm water cooling (ISCA 2019) and thermal energy harvesting/recycling for warm water-cooled datacenters (ISCA 2020), along with other works on cloud/edge datacenter energy optimization.</p>
</a>

---

## Education

### University of California, Riverside
**Ph.D. in Computer Science** | *Sept 2021 - 2026 (Expected)*
- Luckily Advised by [Dr. Daniel Wong](https://danielwong.org) and [Prof. Laxmi Bhuyan](https://www.cs.ucr.edu/~bhuyan/), we have been working on exploring improving the energy efficiency of LLM training and inference wokrload on multi-GPU systems. 


### Huazhong University of Science and Technology
**B.E. in Computer Science and Technology** | *Sept 2017 - June 2021*
- Academic Advisor: [Dr. Fangming Liu](https://fangmingliu.github.io/)
I'm grateful to be able to participate in a series of research in the lab and contribute my effort to the data center/edge energy/cooling optimization. This experience opened my eyes beyond classroom and looking forward to research world.
---

## Experience

### Meta
**Research Scientist Intern, GenAI** | *June 2026 - Nov 2026*

- Researching kernel-fusion opportunities in GenAI inference and developing a general performance model for kernel fusion targeting next-generation accelerators, to guide both software scheduling and hardware design decisions.

### NVIDIA
**System Software Engineer Intern** | *June 2024 - Sept 2024*, *June 2025 - Sept 2025*

- Participated in the prototyping, function developing, real-world deployment, use case analysis of [NCCL Inspector](https://developer.nvidia.com/blog/enhancing-communication-observability-of-ai-workloads-with-nccl-inspector/). 
- Published our discoveries in the paper ["NIXT: A NCCL Inspector Exporter Tool for Observability of Collective Communication in Large Model Training"](https://arxiv.org/abs/2608.01449), accepted at IISWC 2026.




### University of California, Riverside
**Graduate Research Assistant** | *Mar 2021 - Present*
- Profiled and benchmarked the performance and energy consumption of various LLMs (e.g., qwen-2.5-7b,) on the vLLM and vllm-omni engine to identify computational and power bottlenecks.
- Engineered novel power-management techniques by instrumenting the vLLM library, utilizing DVFS to optimize GPU power states during inference.
- Proposed an analysis technique (Interpretive Trace Analysis) to provide insights from idleness in distributed GPU workloads.
- Developed energy-saving techniques for LLM training on top of the NCCL collective communication library. This work led to [PCCL](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=hKWh7p4AAAAJ&citation_for_view=hKWh7p4AAAAJ:9yKSN-GCB0IC) (ICCD 2024), a power-aware collective communication library that applies per-operation DVFS to reduce training energy with negligible throughput impact, and was extended to multimodal inference serving in [Tri-serve](https://arxiv.org/abs/2606.29629), an energy-efficient serving system that coordinates DVFS across the multimodal pipeline.


**Teaching Assistant** | *July 2022 - Dec 2022*
- TA for PU Architecture and Linux Administration.

### Huazhong University of Science and Technology
**Undergraduate Researcher** | *Sept 2018 - June 2021*
- Research in efficiency and improvement of water-cooling systems in cloud/edge data centers.
- Participated in C-style language compiler competition: constructed front-end, AST, and back-end for RISC-V.
- Implemented a multicycle 5-stage pipeline CPU simulation in Logisim supporting MIPS ISA.


