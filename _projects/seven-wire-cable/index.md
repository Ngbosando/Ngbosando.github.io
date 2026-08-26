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

## Objective
Reduce the computational cost of the 3D reference model while retaining the dispersion branches required for vibration analysis.

<figure>
  <img src="{{ '/assets/images/cable-3d.svg' | relative_url }}" alt="Three-dimensional seven-wire cable model">
  <figcaption>Detailed seven-wire geometry used as the starting point for the reference finite-element model.</figcaption>
</figure>

## Model hierarchy
<div class="pipeline"><div><b>3D finite-element model</b><small>approximately 39,700 DOF<br>Helical geometry and inter-wire contacts.</small></div><div><b>FE-WFEM-GBMS</b><small>approximately 680 DOF<br>Reduction of the periodic finite-element cell.</small></div><div><b>Beam-spring model</b><small>42 DOF<br>Wires represented by beams and contacts by springs.</small></div></div>

## Validation
The reduced formulations are compared with the 3D reference through dispersion curves and convergence studies. The model is refined only when the comparison identifies a significant discrepancy.

## Result
The three levels provide different compromises between fidelity and computation time. The beam-spring model is used for rapid exploration, while FE-WFEM-GBMS provides the reduced reference used to control the deviation from the detailed 3D model.
