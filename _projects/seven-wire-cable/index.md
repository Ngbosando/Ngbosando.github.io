---
layout: post
order: 2
title: Seven-wire cable model reduction
description: Comparison of three modelling levels for a seven-wire stranded cable, from a detailed 3D finite-element reference to reduced formulations for faster dispersion studies.
skills: [ANSYS Workbench / APDL, Contact mechanics, Structural dynamics, WFEM / SAFE / GBMS, Model reduction, Validation]
main-image: /assets/images/cable-3d.svg
permalink: /projects/seven-wire-cable/
---

## Context
During my final-year internship at **Inria**, in collaboration with **POMA**, I studied elastic-wave propagation and vibration transmission in seven-wire stranded cables.

## Reference model
<figure class="wide-figure">
  <img src="{{ '/assets/images/cable-3d.svg' | relative_url }}" alt="Three-dimensional seven-wire cable model">
  <figcaption>Detailed helical geometry and inter-wire contacts used in the reference finite-element model.</figcaption>
</figure>

## Reduced beam-spring model
<figure class="wide-figure">
  <img src="{{ '/assets/images/cable-beam-spring-diagram.svg' | relative_url }}" alt="Seven-wire beam-spring reduced model">
  <figcaption>Each wire is represented by a beam and each contact by a spring.</figcaption>
</figure>

<div class="pipeline"><div><b>3D finite element</b><small>≈ 39,700 DOF</small></div><div><b>FE-WFEM-GBMS</b><small>≈ 680 DOF</small></div><div><b>Beam-spring</b><small>42 DOF</small></div></div>

## Computation time
<figure class="wide-figure">
  <img src="{{ '/assets/images/cable-timing.svg' | relative_url }}" alt="Computation time comparison between cable models">
  <figcaption>The model hierarchy is used to move from detailed verification to rapid exploration.</figcaption>
</figure>

## Validation
The reduced formulations are compared with the 3D reference through dispersion curves and convergence studies. FE-WFEM-GBMS is used to control the error introduced by the faster beam-spring formulation.
