---
layout: post
order: 2
title: Seven-wire cable model reduction
description: Progressive modelling of a seven-wire strand from a detailed finite-element model to reduced WFEM/GBMS and beam-spring formulations for fast dispersion studies.
skills: [ANSYS Workbench / APDL, Contact mechanics, Structural dynamics, WFEM / SAFE / GBMS, Model reduction, Validation]
main-image: /assets/images/cable-3d.jpg
permalink: /projects/seven-wire-cable/
---

## Context
During my final-year internship at **Inria / POMA**, I studied elastic-wave propagation and vibration transmission in transport cables. The reference three-dimensional finite-element model represents the **seven wires and their contact interactions**.

## Objective
Reduce computational cost while retaining the dispersion branches required for vibration analysis.

## Model hierarchy
<div class="pipeline"><div><b>3D finite elements</b><small>39,744 DOF<br>Helical geometry and wire-to-wire contacts. Reference model.</small></div><div><b>FE-WFEM-GBMS</b><small>680 DOF<br>Reduced periodic cell.</small></div><div><b>Beam-spring model</b><small>42 DOF<br>Wires represented by beams and contacts by springs.</small></div></div>

## Validation
The reduced formulations were compared with the detailed model through dispersion and convergence studies. The beam-spring model was used for rapid pre-analysis, while the reduced finite-element formulation was retained to control the deviation from the 3D reference model.
