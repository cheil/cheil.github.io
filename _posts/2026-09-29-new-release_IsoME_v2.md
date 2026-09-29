---
title: IsoME v2.0.0 released
description: Eliashberg equations solved directly on the real-frequency axis
background:
  img: "../../../assets/theme/images/realaxis_ME.png"
  by: Alejandro Simon
author: Christoph Heil
comments: true
---

We are happy to announce the release of **IsoME v2.0.0**, the largest update to our Julia package for high-precision Eliashberg calculations since its first release. The headline addition is a second solver, `RealAxisSolver()`, which solves the finite-temperature isotropic Migdal-Eliashberg equations *directly on the real-frequency axis*—no analytic continuation required. Get it from [GitHub](https://github.com/cheil/IsoME.jl), or simply `Pkg.add("IsoME")`.

## Why the real axis?

Almost every quantity an experiment actually measures on a superconductor—tunneling spectra, optical conductivity, quasiparticle lifetimes—is a real-frequency quantity. The Migdal-Eliashberg equations, however, are conventionally solved on the imaginary (Matsubara) axis and then analytically continued. That continuation is an ill-conditioned inverse problem: it amplifies numerical noise, smears out spectral structure, and becomes increasingly unstable at low temperatures—exactly where the physics is most interesting.

`RealAxisSolver()` removes that step. It returns the complex gap function &Delta;(&omega;) and renormalization function *Z*(&omega;) on a real-frequency grid, retaining the fine spectral structure inherited from &alpha;&sup2;*F*(&omega;) that analytic continuation irretrievably loses, and it remains numerically stable from millikelvin temperatures up to above *T*<sub>c</sub>.

Crucially, the real-axis solver keeps the full energy dependence of the electronic density of states—something most real-axis implementations give up in favour of a constant density of states. All three approximation levels familiar from the Matsubara solver are available on the real axis:

- **cDOS+&mu;** — constant density of states with the Morel-Anderson pseudopotential
- **vDOS+&mu;** — full-bandwidth variable density of states with the Morel-Anderson pseudopotential
- **vDOS+W** — full-bandwidth with the *ab initio* screened Coulomb interaction *W*(&epsilon;,&epsilon;&prime;)

Keeping the full bandwidth matters. For H<sub>3</sub>S, whose van Hove singularity at the Fermi level makes the electronic structure strongly particle-hole asymmetric, the full-bandwidth real-axis solution gives a zero-temperature gap of 2&Delta; &asymp; 60 meV, close to recent tunneling measurements, while the constant density of states approximation overshoots at 75 meV.

## Fast enough to use in a loop

A direct real-axis solution has historically been considered expensive. The key algorithmic ingredient in IsoME v2.0.0 is a reformulation of the integral kernel *K*(&omega;,&omega;&prime;) that reduces the cost from the conventional O(*N*&sup2;) to O(*N*). High-resolution solutions therefore converge in milliseconds in the cDOS case and in minutes with the full variable density of states—on a standard laptop.

That speed is what turns the real-axis solver from a curiosity into a building block. Updating the full Migdal-Eliashberg solution at every time step of a kinetic-equation simulation would be hopeless with imaginary-axis methods and analytic continuation; with a linear-scaling real-axis solver it becomes routine. This is precisely what underpins our recent work on the non-equilibrium response of driven superconductors: the *ab initio* framework for [ultrafast dynamics and light-induced superconductivity](https://arxiv.org/abs/2603.18182), including our account of photo-induced superconductivity in K<sub>3</sub>C<sub>60</sub>, and the [modeling of single-photon detection in superconducting nanowire detectors and qubits](https://journals.aps.org/prb/abstract/10.1103/3m2k-mzr6) carried out with the group of [Prof. Karl Berggren](https://qnn-rle.mit.edu/) at MIT.

The methodology behind the solver is described in detail in [arXiv:2603.18199](https://arxiv.org/abs/2603.18199).

## Using it

Both solvers share the same `arguments` interface, so switching between them is a one-line change:

```julia
using IsoME

inp = arguments(
  a2f_file = "path-to-your-α2F-data",
  outdir   = "path-to-output-directory"
)

EliashbergSolver(inp)   # Matsubara axis: fast and robust, ideal for Tc searches
RealAxisSolver(inp)     # real axis: spectral quantities without analytic continuation
```

The Matsubara solver is unchanged in spirit and remains the right tool for critical-temperature searches and high-throughput screening, where its automatic *T*<sub>c</sub> search mode does the work for you. Reach for the real-axis solver when you need real-frequency self-energy components—and be prepared to treat grids and cutoffs with a little more care. Runnable examples for both are included in `test/Nb/examples.jl`.

**A note for existing users:** v2.0.0 is a major version and contains breaking changes. If you are upgrading from the 1.x series, please have a look at the [documentation](https://cheil.github.io/IsoME.jl/) before rerunning old input scripts.

## Get the code

- **GitHub:** [github.com/cheil/IsoME.jl](https://github.com/cheil/IsoME.jl)
- **JuliaHub:** [juliahub.com/ui/Packages/General/IsoME](https://juliahub.com/ui/Packages/General/IsoME)
- **Documentation:** [cheil.github.io/IsoME.jl](https://cheil.github.io/IsoME.jl/)
- **Zenodo:** [DOI:10.5281/zenodo.22964731](https://doi.org/10.5281/zenodo.22964731)

If you use IsoME, please cite the package paper, [*IsoME: Streamlining High-Precision Eliashberg Calculations*, Comput. Phys. Commun. **315**, 109720 (2025)](https://doi.org/10.1016/j.cpc.2025.109720), and, when using the real-axis solver, [arXiv:2603.18199](https://arxiv.org/abs/2603.18199). BibTeX entries for both are in `CITATION.bib`.

As always, we would be glad to hear how it works for you. Bug reports, feature requests, and contributions are very welcome on the [issue tracker](https://github.com/cheil/IsoME.jl/issues).

Happy computing!

**Christoph Heil**

<img src="../../../assets/theme/images/realaxis_ME.png" width="1000"/>
