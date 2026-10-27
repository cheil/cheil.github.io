---
title: Welcome Carina Schmid  
description: New master's student joins the group
#background:  
#  img: "../../../assets/theme/images/hydrides_banner.png"  
#  by: Christoph Heil  
author: Christoph Heil  
comments: true  
---
We are delighted to welcome **Carina Schmid** to the group as a master's student.

Carina's project is part of our [FWF project on superconductivity in alloys](/blog/2025/new-project-alloyssc/). There, we model disordered alloys with the extended generalized quasichemical approximation (EGQCA), which treats an alloy as a statistical ensemble of atomic configurations rather than a single idealized ordered structure. Getting that ensemble right means computing the energetics of a large number of configurations. The number of configurations grows rapidly as we move from binary to ternary alloys, and doing all of this with density-functional theory quickly becomes the bottleneck.

This is where machine-learned interatomic potentials come in, and Carina will find out which kind is best suited for the job. On one side are bespoke **moment tensor potentials (MTPs)**, trained from scratch on DFT data for the specific alloy system. On the other side are **universal potentials**, pre-trained on large materials databases and then fine-tuned to the system at hand. **Ephemeral data-derived potentials (EDDPs)** are a third candidate we may also put to the test. The central question is how accuracy, transferability, and the cost of generating training data trade off against each other, and what that means for the reliability of the EGQCA predictions built on top of them.

Her work ties in closely with that of [Luka Wibmer](/blog/2026/new-phd/), who is developing and applying the EGQCA framework in the same project. A fast and trustworthy route to configurational energetics should let us tackle alloy systems that are currently out of reach.

Carina joined the group in October 2026, and we are looking forward to working with her.

Welcome, Carina!
