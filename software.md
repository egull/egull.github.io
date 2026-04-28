---
layout: page
title: Software
permalink: /software/
---

We develop open source software for quantum many-body calculations. All codes are freely available.

---

## Green

Green is a C++ framework for self-consistent finite-temperature many-body perturbation theory for molecules and periodic solids. It implements the GW and GF2 approximations using Gaussian basis sets and supports coupling to extended dynamical mean-field theory (EDMFT). The code is designed for high-performance computing environments and targets ab initio electronic structure of real materials.

- Paper: [Green/WeakCoupling: Implementation of fully self-consistent finite-temperature many-body perturbation theory for molecules and solids](https://www.sciencedirect.com/science/article/pii/S0010465524003035), *Comput. Phys. Commun.* (2024)
- Repository: [github.com/Green-Phys/green-mbpt](https://github.com/Green-Phys/green-mbpt)

---

## ALPS

ALPS (Algorithms and Libraries for Physics Simulations) is a broad open-source software project providing standardized, well-tested implementations of numerical algorithms for strongly correlated quantum lattice models. It includes quantum Monte Carlo, exact diagonalization, DMRG, and DMFT solvers for spin, bosonic, and fermionic systems.

- Website: [alps.comp-phys.org](https://alps.comp-phys.org/)
- Repository: [github.com/ALPSim/ALPS](https://github.com/ALPSim/ALPS)

---

## ALPSCore

ALPSCore is the modular core library extracted from the ALPS project, providing reusable scientific computing components for quantum physics simulations. It offers Monte Carlo frameworks, Green's function utilities, statistical accumulators, parameter handling, and HDF5 I/O as independent C++ modules with Python bindings.

- Repository: [github.com/ALPSCore/ALPSCore](https://github.com/ALPSCore/ALPSCore)
