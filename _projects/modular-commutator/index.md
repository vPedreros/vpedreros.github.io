---
title: "Modular Commutator and Chiral Topological Order"
description: "Uncovering the geometric additivity of the modular commutator."
categories: [Projects]
icon: fas fa-calculator
tags: ["Entanglement Bootstrap", "Chiral Topological Order", "Free Fermion"]
link: "https://journals.aps.org/prb/abstract/10.1103/PhysRevB.111.075167"
paper: "PRB 111, 075167 (2025)"
permalink: /projects/modular-commutator/
order: 1
status: completed
project_type: physics
published: false
---

## Overview

Implementation and numerical study of the modular commutator, an
entanglement-based diagnostic for chiral topological order in
two-dimensional gapped quantum phases. This project underlies
["Geometric additivity of the modular commutator for multipartite
entanglement"](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.111.075167),
published with Isaac H. Kim and Eun-Gook Moon in *Physical Review B* 111,
075167 (2025).

## Motivation

The modular commutator detects chirality directly from a many-body ground
state's entanglement structure, without relying on edge-mode counting or an
explicit measurement of Hall conductance. It was originally defined for
tripartite entanglement; extending it to multipartite regions raises a
natural question — does the quantity compose additively across
geometrically separated regions, and what does that additivity reveal about
the underlying topological data of the phase?

## Method

- Defines the modular commutator from the modular Hamiltonians of a ground
  state's reduced density matrices, and proves it decomposes additively
  over a partition with multiple tri-junctions — the commutator of a
  coarser region reduces to a sum of commutators over simplified regions,
  plus a residual term that vanishes for invertible (non-anyonic) states.
- Applies the additivity formula to "pizza" partitions of both the bulk and
  the physical edge, deriving closed-form multiples of the chiral central
  charge for different tri-junction arrangements, plus a complementary
  identity for incomplete junctions that extracts a half-quantized value at
  smaller subsystem sizes.
- Verifies the additivity numerically on the Haldane model on a honeycomb
  lattice, computing the modular commutator directly from ground-state
  correlation functions across its topological phase transitions.

## Results

- Confirms geometric additivity for invertible states: each complete
  tri-junction contributes (π/3)c₋, so a bulk pizza partition gives twice
  the single-tri-junction value while the corresponding physical-edge
  partition gives twice the value with the opposite sign — even though the
  edge modular Hamiltonians involved act on disconnected intervals.
- Generalizes this to a single relation, where a "geometric integer"
  characterizing the tri-junction arrangement sets the multiple of the
  chiral central charge on both the bulk and the edge.
- Numerically reproduces these predictions on the Haldane model to high
  precision away from its critical points, unchanged under added on-site
  disorder, and finds qualitatively consistent higher geometric integers on
  a π-flux square-lattice model.

## Links

- [Geometric additivity of the modular commutator for multipartite entanglement](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.111.075167) — *Physical Review B* 111, 075167 (2025)
