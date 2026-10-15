---
title: "Linear Spin Wave Theory"
description: "Open-source Python library for linear spin-wave theory (LSWT) — spin-system definitions, solvers, and observables for magnon spectra on 2D lattices."
categories: [Projects]
icon: fas fa-wave-square
tags: ["Linear Spin Wave Theory", "Magnon Spectra", "Holstein-Primakoff"]
link: "https://github.com/sungmin-park-dev/Linear-Spin-Wave-Theory"
github_repo: "sungmin-park-dev/Linear-Spin-Wave-Theory"
permalink: /projects/linear-spin-wave-theory/
order: 6
status: in-progress
project_type: software
published: false
---

## Overview

Open-source Python library for linear spin-wave theory (LSWT): defines spin
systems on a lattice, builds and diagonalizes the LSWT Hamiltonian, and
computes magnon spectra and their quantum corrections. Generalized out of
the spin-wave component of the
[Spin Supersolid in Triangular Lattice](/projects/spin-wave-theory/)
project into a reusable package — still alpha and under validation ahead of
a public release.

## Design

- Separates system definition (`SpinSystem`), solving (`LSWTSolver`,
  `SpinOptimizer`), results (`SolverResult`), observables, and
  visualization into independent layers.
- Exchange-matrix support for Heisenberg, XXZ, spin-orbit coupling,
  Dzyaloshinskii-Moriya, and Kitaev interactions, alongside a dedicated
  NBCP (Na₂BaCo(PO₄)₂) exchange matrix.
- Keeps backward compatibility with the legacy dictionary-based input
  format from earlier in the project.

## Status

- `SpinSystem`, `LSWTSolver`, `SpinOptimizer`, and `SolverResult` are
  implemented, along with spin-arrangement visualization.
- Thermodynamic, topological, and correlation-function observables exist
  as modules but aren't yet wired into a high-level solver interface.
- Its main validation case reproduces LSWT results for Na₂BaCo(PO₄)₂,
  checked against Woodland et al., *Physical Review B* 112, 104413 (2025)
  and Gao et al., *npj Quantum Materials* 7, 89 (2022).

## Links

- [Repository](https://github.com/sungmin-park-dev/Linear-Spin-Wave-Theory)
