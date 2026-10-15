---
title: "Spin Supersolid in Triangular Lattice"
description: "Studying spin supersolid stability against spin-orbit-induced exchange anisotropy, with possible application to candidate materials such as Na₂BaCo(PO₄)₂."
categories: [Projects]
icon: fas fa-atom
tags: ["Na₂BaCo(PO₄)₂", "Spin Wave Theory", "Holstein-Primakoff", "Magnon Spectra"]
link: "https://arxiv.org/abs/2601.20963"
paper: "arXiv:2601.20963 (2026)"
permalink: /projects/spin-wave-theory/
order: 2
status: planned
project_type: physics
published: false
sitemap: false
---

## Overview

Studies the spin supersolid phase of the triangular-lattice antiferromagnet
Na₂BaCo(PO₄)₂, combining spin-wave theory, tensor-network methods, and
renormalization-group analysis to trace its stability against spin-orbit
coupling and thermal fluctuations — the subject of ["Spin-orbit-induced
Instability and Finite-Temperature Stabilization of a Triangular-lattice
Supersolid"](https://arxiv.org/abs/2601.20963) (arXiv:2601.20963, 2026).

The code behind this splits into two parts: analysis scripts specific to
this paper's tensor-network and renormalization-group calculations, and the
spin-wave-theory core, which was generalized beyond this one result and
published separately as a reusable package (see Links).

## Motivation

Spin-orbit coupling (SOC) is usually assumed negligible in
Na₂BaCo(PO₄)₂, but symmetry says otherwise: any nonzero SOC breaks the
continuous spin symmetry that supersolid order depends on, opening a gap
in its low-energy excitations. This raises the central question — to
what extent can supersolidity survive symmetry-allowed SOC, and what new
phases emerge as it grows?

## Method: Spin-Wave Component

- Start from a bilinear spin exchange Hamiltonian on a given lattice and
  magnetic structure, with the classical ground-state order fixed per
  exchange configuration.
- Expand around that order with a Holstein-Primakoff transformation to get a
  bosonic Hamiltonian, then diagonalize it in momentum space with a
  Bogoliubov (BdG) transformation to obtain the magnon band structure.
- Layer solvers for exchange-parameter optimization and ground-state energy
  on top of the diagonalization core.

## Method: Tensor-Network Component

- Infinite density-matrix renormalization group (iDMRG) on an infinite
  Y-type cylinder maps the zero-temperature ground-state phase diagram
  across the exchange-anisotropy parameter planes.
- Identifies five phases without spin-orbit terms — three spin-supersolid
  phases (Y, V, Ψ) alongside an up-up-down plateau and a polarized phase —
  and tracks how growing spin-orbit coupling collapses the three-sublattice
  orders into modified magnetic unit cells, including stripe phases and,
  at larger coupling, a quantum skyrmion lattice identified by its scalar
  spin chirality.

## Method: Renormalization-Group Component

- Maps the spin-orbit-induced pseudo-Goldstone gap onto a discrete
  ground-state anisotropy — sixfold for the Y and Ψ phases, threefold for
  the V phase — and builds an effective classical Hamiltonian for each.
- A standard two-dimensional Kosterlitz-Thouless RG analysis on the
  anisotropy coupling shows the sixfold term becomes irrelevant above a
  threshold temperature, while the threefold term stays relevant at every
  temperature.

## Results

- Confirms the spin-orbit-induced pseudo-Goldstone gap directly via
  spin-wave theory, and reproduces the Y and V ground states found by
  iDMRG (linear spin-wave theory alone does not capture the Ψ phase,
  attributed to quantum fluctuations beyond linear order).
- Shows that the Y and Ψ phases regain a finite-temperature
  spin-supersolid window, bounded above by a
  Berezinskii-Kosterlitz-Thouless transition, once the sixfold anisotropy
  becomes RG-irrelevant — a stability window invisible to a
  zero-temperature analysis.
- Shows the V phase cannot support any finite-temperature supersolid once
  spin-orbit coupling is present, since its threefold anisotropy never
  becomes RG-irrelevant.
- Offers an explanation for the giant magnetocaloric effect observed in
  Na₂BaCo(PO₄)₂: the finite-temperature restoration of coherence keeps the
  entropy-enhancing soft modes active even though spin-orbit coupling is
  not negligible.

## Links

- [Spin-orbit-induced Instability and Finite-Temperature Stabilization of a Triangular-lattice Supersolid](https://arxiv.org/abs/2601.20963) — arXiv:2601.20963 (2026)
- [Linear-Spin-Wave-Theory](https://github.com/sungmin-park-dev/Linear-Spin-Wave-Theory) — Python package for linear spin wave theory (LSWT) computation, generalized from this project's spin-wave component
