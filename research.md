---
layout: page
title: Research
permalink: /research/
---

We develop and apply numerical and analytical methods to understand strongly correlated electron systems. Our work spans algorithm development, mathematical foundations, and physical applications.

---

## Quantum Impurity Solvers

Quantum impurity models describe a small interacting quantum system — typically a single correlated atom or molecule — coupled to a non-interacting bath. They arise as auxiliary problems in dynamical mean-field theory and its cluster extensions, and as models of quantum dots and magnetic impurities in metals. We develop continuous-time quantum Monte Carlo (CT-QMC) algorithms, which stochastically sample Feynman diagrams in imaginary time, and tensor-train solvers, which represent the impurity Green's function as a low-rank tensor network. These methods enable numerically exact solutions across a wide range of temperatures, interaction strengths, and bath geometries.

1. [Continuous-time Monte Carlo methods for quantum impurity models](https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.83.349) — *Rev. Mod. Phys.* 83, 349 (2011)
2. [Continuous-time auxiliary field Monte Carlo for quantum impurity models](https://doi.org/10.1209/0295-5075/82/57003) — *EPL* 82, 57003 (2008)
3. [Tensor train continuous time solver for quantum impurity models](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.107.245135) — *Phys. Rev. B* 107, 245135 (2023)
4. [Taming the dynamical sign problem in real-time evolution of quantum many-body problems](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.115.266802) — *Phys. Rev. Lett.* 115, 266802 (2015)

---

## Compressed Representations and Analytic Continuation

Green's functions and self-energies in quantum many-body theory are smooth functions whose structure is constrained by analyticity, causality, and spectral positivity. We exploit these mathematical properties to develop compact representations — including pole representations, Chebyshev polynomial expansions, and the intermediate representation (IR) basis — that compress imaginary-time and Matsubara-frequency data by orders of magnitude. We also develop algorithms for analytic continuation, which extracts real-frequency spectral information from noisy imaginary-time data, using pole-based methods, semidefinite programming, and Nevanlinna theory.

1. [Minimal pole representation and controlled analytic continuation of Matsubara response functions](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.110.035154) — *Phys. Rev. B* 110, 035154 (2024)
2. [Minimal pole representation and analytic continuation of matrix-valued correlation functions](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.110.235131) — *Phys. Rev. B* 110, 235131 (2024)
3. [Nevanlinna Analytical Continuation](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.126.056402) — *Phys. Rev. Lett.* 126, 056402 (2021)
4. [Chebyshev polynomial representation of imaginary time response functions](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.98.075127) — *Phys. Rev. B* 98, 075127 (2018)

---

## Mathematical Properties of Green's Functions

Green's functions encode the full many-body physics of a quantum system and satisfy a rich set of mathematical constraints — analyticity, Kramers-Kronig relations, sum rules, and Lehmann representations. Understanding these properties is essential for designing numerically stable algorithms and for interpreting physical results. We study the mathematical structure of single- and two-particle Green's functions, develop diagrammatic frameworks based on discrete pole representations, and analyze denoising and projection methods that enforce known spectral constraints on noisy numerical data.

1. [Feynman diagrammatics based on discrete pole representations](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.110.075158) — *Phys. Rev. B* 110, 075158 (2024)
2. [Denoising of imaginary time response functions with Hankel projections](https://journals.aps.org/prresearch/abstract/10.1103/PhysRevResearch.6.L032042) — *Phys. Rev. Research* 6, L032042 (2024)
3. [Robust analytic continuation of Green's functions via projection, pole estimation, and semidefinite relaxation](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.107.075151) — *Phys. Rev. B* 107, 075151 (2023)

---

## Quantum Computing

Whether quantum computers will outperform classical methods for quantum many-body simulation remains an open question. We develop algorithms at the interface of classical and quantum computing, including methods that use quantum hardware to solve impurity problems and approaches that combine quantum circuit ansätze with classical diagrammatic techniques. A central focus is on rigorously understanding when and whether quantum algorithms offer a genuine advantage over state-of-the-art classical methods.

1. [Quantum-centric Supercomputing for Materials Science: A Perspective on Challenges and Future Directions](https://doi.org/10.1016/j.future.2024.04.060) — *Future Generation Computer Systems* 160 (2024)
2. [Denoising and Extension of Response Functions in the Time Domain](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.132.160403) — *Phys. Rev. Lett.* 132, 160403 (2024)

---

## Realistic Electronic Structure Methods

Ab initio simulations of real materials require treating both weak and strong electronic correlations on equal footing. In collaboration with the Zgid group, we develop self-consistent many-body perturbation theory methods for solids, as well as embedding approaches such as self-energy embedding theory (SEET) that treat a correlated subspace exactly while describing the rest at a perturbative level. These methods are implemented in the Green software framework.

1. [Finite Temperature Quantum Embedding Theories for Correlated Systems](https://iopscience.iop.org/article/10.1088/1367-2630/aa5d34) — *New J. Phys.* 19, 023047 (2017)
2. [Green/WeakCoupling: Implementation of fully self-consistent finite-temperature many-body perturbation theory](https://www.sciencedirect.com/science/article/pii/S0010465524003035) — *Comput. Phys. Commun.* (2024)

---

## Open Source Software

See the [Software](/software/) page for codes developed by the group.
