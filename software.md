---
layout: page
title: Software
permalink: /software/
---

We develop open source software for quantum many-body calculations. All codes are freely available.

---

## Green

[![Green logo](https://green-phys.org/logo/rosetta.webp){: style="height:60px; float:right; margin:0 0 1em 1.5em;"}](https://green-phys.org)

Green is a C++ framework for self-consistent finite-temperature many-body perturbation theory for molecules and periodic solids. It implements the GW and GF2 approximations using Gaussian basis sets and supports coupling to extended dynamical mean-field theory (EDMFT). The code is designed for high-performance computing environments and targets ab initio electronic structure of real materials.

- Paper: [Green/WeakCoupling: Implementation of fully self-consistent finite-temperature many-body perturbation theory for molecules and solids](https://www.sciencedirect.com/science/article/pii/S0010465524003035), *Comput. Phys. Commun.* (2024)
- Repository: [github.com/Green-Phys/green-mbpt](https://github.com/Green-Phys/green-mbpt)

---

## H-NESSi

H-NESSi (Hierarchical Non-Equilibrium Systems Simulation) is an open-source C++ package for simulating strongly correlated quantum systems far from equilibrium. It solves the Kadanoff-Baym equations using hierarchical low-rank compression of the two-time Green's function, combined with the discrete Lehmann representation and high-order time-stepping schemes. MPI and OpenMP parallelization enable large-scale simulations of driven superconductors, multiorbital systems, and the nonequilibrium Hubbard model that are otherwise computationally prohibitive.

- Paper: [H-NESSi: The Hierarchical Non-Equilibrium Systems Simulation package](https://arxiv.org/abs/2604.05319) (2026, preprint)
- Repository: [github.com/KBE-hodlr/H-NESSi](https://github.com/KBE-hodlr/H-NESSi)

---

## MiniPole

MiniPole is a Python package implementing the matrix-valued Minimal Pole Method (MPM) for analytic continuation of Green's functions and self-energies. Given noisy Matsubara or real-frequency data, it recovers spectral functions via compact pole representations, with variants supporting discrete Lehmann representation coefficients and real-frequency fitting. It is available on PyPI and is part of the Green software ecosystem.

- Papers: [Minimal pole representation and controlled analytic continuation of Matsubara response functions](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.110.035154) — *Phys. Rev. B* 110, 035154 (2024); [Minimal pole representation and analytic continuation of matrix-valued correlation functions](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.110.235131) — *Phys. Rev. B* 110, 235131 (2024)
- Repository: [github.com/Green-Phys/MiniPole](https://github.com/Green-Phys/MiniPole)

---

## ALPS

[![ALPS logo](https://alps.comp-phys.org/logo/alps.png){: style="height:60px; float:right; margin:0 0 1em 1.5em;"}](https://alps.comp-phys.org)

ALPS (Algorithms and Libraries for Physics Simulations) is a broad open-source software project providing standardized, well-tested implementations of numerical algorithms for strongly correlated quantum lattice models. It includes quantum Monte Carlo, exact diagonalization, DMRG, and DMFT solvers for spin, bosonic, and fermionic systems.

- Website: [alps.comp-phys.org](https://alps.comp-phys.org/)
- Repository: [github.com/ALPSim/ALPS](https://github.com/ALPSim/ALPS)

---

## ALPSCore

[![ALPSCore logo](https://avatars.githubusercontent.com/u/7558003?v=4){: style="height:60px; float:right; margin:0 0 1em 1.5em;"}](https://github.com/ALPSCore/ALPSCore)

ALPSCore is the modular core library extracted from the ALPS project, providing reusable scientific computing components for quantum physics simulations. It offers Monte Carlo frameworks, Green's function utilities, statistical accumulators, parameter handling, and HDF5 I/O as independent C++ modules with Python bindings.

- Repository: [github.com/ALPSCore/ALPSCore](https://github.com/ALPSCore/ALPSCore)
