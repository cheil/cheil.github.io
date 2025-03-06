---
title: Announcing IsoME
description: IsoME: Streamlining High-Precision Eliashberg Calculations
background:
  img: "../../../assets/theme/images/IsoME_flowchart_v1.png"
  by: Eva Kogler
author: Christoph Heil
# tags: []
comments: true
---

We are thrilled to announce the release of **IsoME**, our new Julia package designed to make high-precision superconductivity calculations both accessible and efficient. IsoME unifies multiple approximation schemes under one roof, enabling researchers to seamlessly transition from quick estimates with semi-empirical formulas to rigorous ab initio analyses based on isotropic Migdal-Eliashberg theory.

## What is IsoME?

IsoME offers a versatile framework that covers a wide range of superconductivity calculations:
- **Semi-Empirical Methods:** Quickly estimate the critical temperature (Tc) using the McMillan-Allen-Dynes formula and its machine learning-enhanced variant.
- **Ab Initio Calculations:** Dive deep with the full Migdal-Eliashberg approach—whether using the constant DOS (cDOS) or the more refined variable DOS (vDOS) methods, with the option to include static Coulomb interactions.
- **Automatic Tc Search Mode:** Designed for high-throughput workflows, IsoME can automatically determine Tc without the need for manual temperature specification.

These features make IsoME an ideal tool for both detailed theoretical investigations and rapid material screenings.

## Why Try IsoME?

Superconductivity research demands a careful balance between computational efficiency and accuracy. With IsoME, you benefit from:
- **Flexibility:** Use the level of theory that best suits your research needs, from rapid estimations to fully ab initio calculations.
- **User-Friendly Integration:** IsoME works out-of-the-box with popular DFT/DFPT and GW codes like Quantum Espresso, EPW, and BerkeleyGW.
- **High-Throughput Capability:** Its dedicated Tc search mode and streamlined workflow enable large-scale screenings with minimal fuss.

## Getting Started is Easy

With Julia's package manager, installing and using IsoME is straightforward. Here’s a quick example to kick off your calculations:

```julia
using IsoME

# Define your input arguments
inp = arguments(
  a2f_file = "path-to-your-α2F-data",
  outdir  = "path-to-output-directory"
)

# Run the Eliashberg solver
EliashbergSolver(inp)
```

This simple snippet sets you on the path to exploring superconducting properties with first-principles precision!

## Dive Into the Details

Our accompanying preprint provides an in-depth description of IsoME’s methodology, benchmark tests, and application examples. It showcases how IsoME successfully bridges the gap between computational efficiency and ab initio accuracy in superconductivity research.  
[Read the preprint on arXiv:2503.03559](https://arxiv.org/abs/2503.03559).

## Download and Contribute

IsoME is available at multiple platforms:
- **JuliaHub:** [https://juliahub.com/ui/Packages/General/IsoME](https://juliahub.com/ui/Packages/General/IsoME)
- **GitHub:** [https://github.com/cheil/IsoME.jl](https://github.com/cheil/IsoME.jl)
- **Zenodo:** [DOI:10.5281/zenodo.14967551](https://zenodo.org/records/14967551)

We invite you to download the code, try it out, and join us in refining this tool. Your feedback, contributions, and suggestions are highly welcome!

## Join the Conversation

Stay connected for future updates and share your experiences with IsoME. Together, we can push the boundaries of computational materials science and make breakthrough discoveries in superconductivity research.

Happy computing!

**Christoph Heil**

<img src="../../../assets/theme/images/IsoME_flowchart_v1.png" width="1000"/>
