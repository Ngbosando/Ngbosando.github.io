---
layout: post
order: 2
title: Seven-wire cable model reduction
description: Comparison of detailed and reduced formulations for faster vibration and wave-propagation studies.
skills: [ANSYS Workbench / APDL, Structural dynamics, Contact mechanics, WFEM / GBMS, Model reduction]
main-image: /assets/images/cable-3d.svg
permalink: /projects/seven-wire-cable/
---

<div class="project-intro"><b>Objective</b><span>Reduce computation cost while preserving the dynamic behaviour required for dispersion analysis.</span></div>

## Reference model

<figure class="figure-wide">
  <img src="{{ '/assets/images/cable-3d.svg' | relative_url }}" alt="Three-dimensional seven-wire cable model">
  <figcaption>Detailed helical geometry and inter-wire contacts.</figcaption>
</figure>

## Reduced model

<figure class="figure-wide">
  <img src="{{ '/assets/images/cable-beam-spring.svg' | relative_url }}" alt="Seven-wire beam-spring model">
  <figcaption>42-DOF beam-spring representation: wires as beams, contacts as springs.</figcaption>
</figure>

## Model reduction

<figure class="figure-wide">
  <img src="{{ '/assets/images/cable-computation-time.svg' | relative_url }}" alt="Computation time comparison for the three cable models">
  <figcaption>Detailed 3D FE → FE-WFEM-GBMS → beam-spring.</figcaption>
</figure>

<div class="result-line"><b>Result</b><span>≈39,700 → ≈680 → 42 DOF, with computation time reduced from ≈2,022 s to ≈6.3 s and ≈0.6 s.</span></div>
