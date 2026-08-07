---
title: "Energy-Efficient Cooling Systems for Datacenters"
date: 2026-08-04
weight: 4
tags: [Datacenter Cooling, Warm Water Cooling, Green Computing, Edge Computing]
summary: "A line of work on warm-water cooling for cloud and edge datacenters — fine-grained cooling control, thermal energy harvesting, and component-level cooling for heterogeneous hardware."
---

## Overview

Before working on GPU power management, I spent my undergraduate research years at HUST on the other side of the energy equation: **cooling**. Cooling accounts for a large fraction of datacenter energy overhead, and warm-water cooling — running coolant at higher temperatures than traditional chilled-water systems — opens opportunities to cut that overhead dramatically and even recycle the captured heat.

## Main Works

- **Fine-grained warm water cooling for improving datacenter economy** (ISCA 2019) — instead of treating cooling as a facility-level knob, this work controls warm-water cooling at fine granularity to match server-level heat generation, improving datacenter economy without sacrificing reliability.

- **Heat to power: thermal energy harvesting and recycling for warm water-cooled datacenters** (ISCA 2020) — warm water leaving the servers carries usable thermal energy; this work harvests and recycles it, turning waste heat into a resource for the datacenter.

- **CoolEdge: hotspot-relievable warm water cooling for energy-efficient edge datacenters** (ASPLOS 2022) — edge datacenters pack heterogeneous hardware into constrained spaces, creating hotspots; CoolEdge relieves them with warm-water cooling designed for edge deployment.

- **Cooling as You Wish: component-level cooling for heterogeneous edge datacenters** (IEEE Transactions on Computers, 2026) — extends cooling control down to individual components, matching cooling capacity to the heterogeneous thermal profiles of edge hardware.

## Links

- Full publication list on [Google Scholar](https://scholar.google.com/citations?user=hKWh7p4AAAAJ&hl=en)
