---
title: New preprint announcement  
description: First-principles framework for ultrafast dynamics and light-induced superconductivity in conventional superconductors
background:  
  img: "../../../assets/theme/images/ultrafast_Fig1.png"  
  by: Alejandro Simon  
author: Christoph Heil  
comments: true  
---

We are delighted to announce the simultaneous submission of two closely linked preprints to arXiv, representing
a major joint effort between our group at Graz University of Technology and our collaborators at MIT's Research
Laboratory of Electronics.

The first, [Ultrafast dynamics and light-induced superconductivity from first principles](https://arxiv.org/abs/2603.18182),
develops a predictive *ab initio* framework for the nonequilibrium response of optically driven superconductors.
The second, [Fast Real-Axis Eliashberg Calculations: Full-bandwidth solutions beyond the constant density of
states approximation](https://arxiv.org/abs/2603.18199), provides the critical methodological engine that makes
the first possible. Together, these works open a new chapter in the first-principles description of conventional
superconductors driven far from equilibrium.

---

### The methodological foundation: solving Migdal-Eliashberg theory directly on the real-frequency axis

Nearly all experimentally accessible properties of a superconductor, such as tunneling spectra, optical
conductivity, and quasiparticle lifetimes, are real-frequency quantities. Yet the Migdal-Eliashberg equations,
the gold standard for *ab initio* strong-coupling superconductivity, are almost universally solved on the
imaginary-frequency (Matsubara) axis and then analytically continued to real frequencies. Analytic continuation
is an ill-conditioned inverse problem that amplifies numerical errors, blurs spectral features, and becomes
increasingly unstable at low temperatures, precisely where the physics is most interesting.

In [arXiv:2603.18199](https://arxiv.org/abs/2603.18199), we bypass this bottleneck entirely. We present a
practical and efficient scheme to solve the finite-temperature Migdal-Eliashberg equations *directly* on the
real-frequency axis, while retaining the full energy dependence of the electronic density of states. Most
existing real-axis implementations sacrifice this in favour of a constant density of states approximation.
A key algorithmic contribution is a reformulation of the integral kernel K(&omega;,&omega;') that reduces the
computational cost from the conventional O(N<sup>2</sup>) to O(N), enabling high-resolution solutions to
converge in milliseconds (in the constant density of states case) to minutes (with the full variable density of states)
on a standard laptop.

We demonstrate the importance of going beyond the constant density of states approximation on H<sub>3</sub>S,
the archetypal high-*T*<sub>c</sub> hydride. H<sub>3</sub>S hosts a prominent van Hove singularity near the
Fermi level that induces strong particle-hole asymmetry. Our full-bandwidth real-axis solution yields a
zero-temperature superconducting gap of 2&Delta; &asymp; 60 meV, in close agreement with recent tunneling
measurements, while the constant density of states approximation overshoots at 75 meV. The direct
real-frequency solutions also display fine spectral structure inherited from &alpha;<sup>2</sup>F(&omega;) that
is irretrievably lost in analytically continued results, and they remain numerically stable across the entire
temperature range from millikelvin to above *T*<sub>c</sub>.

---

### The physics: ultrafast dynamics and photo-induced superconductivity from first principles

Armed with this fast real-axis solver, [arXiv:2603.18182](https://arxiv.org/abs/2603.18182) constructs the
first fully self-consistent, first-principles framework for the nonequilibrium response of conventional
superconductors to ultrafast optical excitation. The approach couples a set of kinetic equations for the
quasiparticle distribution f(E,t) and the phonon distribution n(&omega;,t), an extension of the
Chang-Scalapino equations to the strong-coupling regime, solved self-consistently with the Migdal-Eliashberg
equations on the real-frequency axis. All material-specific inputs, including the Eliashberg spectral function
&alpha;<sup>2</sup>F(&omega;) and the phonon density of states, are computed from density functional (perturbation)
theory. The optical response of the driven film is then obtained from the time-dependent complex conductivity
via a Kubo formula, and the Maxwell equations are solved to yield the differential reflectance
&Delta;R/R<sub>0</sub> and differential transmission &minus;&Delta;T/T<sub>0</sub> for direct comparison
with pump-probe experiments.

We validate the framework quantitatively on two conventional superconductors that could hardly be more
different: Pb at ambient pressure, with its soft phonon spectrum and modest coupling, and LaH<sub>10</sub>
at 165 GPa, where superconductivity is driven by stiff hydrogen vibrations and reaches *T*<sub>c</sub> &asymp; 250 K.
For Pb, the temperature-dependent amplitude and recovery time of &minus;&Delta;T/T<sub>0</sub> agree
quantitatively with experiments. For LaH<sub>10</sub>, the model captures the multi-timescale relaxation
dynamics and the onset of a phonon bottleneck at higher fluences. This cross-material consistency across
vastly different phonon energy scales and coupling strengths confirms the robustness of the approach.

---

### Explaining and predicting photo-induced superconductivity

With validation in hand, we turn to the problem that has captivated the community for over a decade:
*photo-induced superconductivity*. In the alkali-doped fulleride K<sub>3</sub>C<sub>60</sub>, mid-infrared
pump pulses at 170 meV have been reported to induce signatures of superconductivity at temperatures far above
the equilibrium *T*<sub>c,0</sub> &asymp; 20 K, but the underlying mechanism has remained controversial.

Our calculations, using electron-phonon inputs computed with FHI-aims, reproduce a prominent peak in
&alpha;<sup>2</sup>F(&omega;) at 170 meV, precisely the energy targeted by the pump in the experiments.
Replicating the experimental conditions, we obtain a transient photo-induced gap &Delta;<sub>0</sub>(t) > 0
at temperatures well above *T*<sub>c,0</sub>, persisting briefly after the pump is switched off. This
photo-induced state emerges entirely within the framework of conventional electron-phonon-mediated
superconductivity. Resonant excitation of quasiparticles to energies matching the peak in
&alpha;<sup>2</sup>F(&omega;) depletes the gap-edge population and enhances pairing, in close analogy to the
long-known enhancement of superconductivity under microwave irradiation. The mechanism is therefore not exotic;
it is a natural consequence of the phonon spectrum.

Crucially, this analysis reveals a general design principle. Materials with prominent high-frequency structure
in &alpha;<sup>2</sup>F(&omega;) are candidate systems for photo-induced superconductivity. Guided by this
insight, we identify calcium-intercalated graphite, CaC<sub>6</sub>, as a promising new candidate and predict
a photo-induced gap response comparable to that of K<sub>3</sub>C<sub>60</sub> when pumped resonantly at its
characteristic phonon frequency, a prediction that is directly testable with existing ultrafast spectroscopy
equipment.

---

These two works are deeply intertwined. The fast real-axis Eliashberg solver is not merely a convenience for
the nonequilibrium calculations; it is a necessity. Updating the full Migdal-Eliashberg solution at each time
step of the kinetic equations would be prohibitive with traditional imaginary-axis methods that require analytic
continuation. Our linear-scaling real-axis approach reduces this to a tractable computation, transforming a
formally intractable problem into a practical tool for materials prediction.

We believe these results establish a new baseline for the theoretical study of driven superconductors, and we
look forward to seeing how the community applies and extends this framework, particularly toward the long-standing
goal of light-enhanced or even room-temperature superconductivity.

Check out the preprints at [arXiv:2603.18182](https://arxiv.org/abs/2603.18182) and
[arXiv:2603.18199](https://arxiv.org/abs/2603.18199).

<img src="../../../assets/theme/images/ultrafast_Fig1.png" width="1000"/>