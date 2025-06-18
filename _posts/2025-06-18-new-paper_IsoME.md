---
title: IsoME Publication
description: IsoME - Streamlining High-Precision Eliashberg Calculations
background:
  img: "../../../assets/theme/images/IsoME_flowchart_v1.png"
  by: Eva Kogler
author: Christoph Heil
# tags: []
comments: true
---

We’re happy to announce that our **IsoME** paper has been published in [*Computer Physics Communications* (Vol 315, 109720, 2025)](https://doi.org/10.1016/j.cpc.2025.109720). The article is open-access and documents the full capabilities, performance, and use cases of IsoME for high-precision superconductivity calculations.

## What is IsoME?

IsoME is a Julia-based tool designed to streamline superconductivity calculations across a wide range of approximation levels:

- **Semi-Empirical Methods:** Quickly estimate critical temperatures (*T*<sub>c</sub>) using the McMillan–Allen-Dynes formula and its machine learning extension.
- **Ab Initio Approaches:** Perform fully self-consistent isotropic Migdal-Eliashberg calculations, either with constant DOS (cDOS) or variable DOS (vDOS), including optional static Coulomb corrections.
- **Automatic Tc Search Mode:** Automatically finds *T*<sub>c</sub> without manual temperature input—ideal for high-throughput workflows.

## Why Use IsoME?

IsoME brings together flexibility and ease of use:

- **Unified Framework:** Cover a full range of superconducting models in one package.
- **Interoperability:** Compatible with standard DFT/DFPT and GW outputs (e.g., from Quantum Espresso, EPW, BerkeleyGW).
- **Efficient Workflows:** Run ab initio Eliashberg calculations on a workstation in minutes.

## Quick Start Example

IsoME is easy to install and run:

```julia
using IsoME

inp = arguments(
  a2f_file = "path-to-your-α2F-data",
  outdir  = "path-to-output-directory"
)

EliashbergSolver(inp)
```

## Learn More

The published article includes benchmarks, methodology details, and usage examples:  
[https://doi.org/10.1016/j.cpc.2025.109720](https://doi.org/10.1016/j.cpc.2025.109720)

## Get the Code

- **JuliaHub:** [https://juliahub.com/ui/Packages/General/IsoME](https://juliahub.com/ui/Packages/General/IsoME)  
- **GitHub:** [https://github.com/cheil/IsoME.jl](https://github.com/cheil/IsoME.jl)  
- **Zenodo:** [https://zenodo.org/records/14967551](https://zenodo.org/records/14967551)

**Christoph Heil**

<img src="../../../assets/theme/images/IsoME_flowchart_v1.png" width="1000"/>
