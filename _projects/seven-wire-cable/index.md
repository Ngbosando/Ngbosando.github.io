---
layout: post
order: 2
title: Seven-wire cable model reduction
description: Progressive modelling of a stranded cable from a detailed finite-element representation to reduced WFEM/GBMS and beam-spring models for fast dispersion studies.
skills: [ANSYS Workbench / APDL, Contact mechanics, Structural dynamics, WFEM / SAFE / GBMS, Model reduction, Validation]
main-image: /assets/images/cable-3d.jpg
permalink: /projects/seven-wire-cable/
---

## Context
During my final-year internship at **Inria / POMA**, I studied elastic-wave propagation and vibration transmission in transport cables. The initial three-dimensional finite-element model includes the seven strands and contact interactions between wires.

The objective was to **reduce computational cost while retaining the dispersion branches required for vibration analysis**.

## Model hierarchy
<div class="pipeline"><div><b>3D finite elements</b><small>39,744 DOF<br>Detailed strand geometry and contacts. Reference model.</small></div><div><b>FE-WFEM-GBMS</b><small>680 DOF<br>Reduced periodic cell.</small></div><div><b>Beam-spring model</b><small>42 DOF<br>Wires represented by beams and contacts by springs.</small></div><div><b>Use</b><small>Fast dispersion pre-analysis with reduced FE control.</small></div></div>

## Model improvement
The beam-spring formulation was not accepted from visual agreement alone. Convergence studies were used to identify which parameters affected dispersion and to refine the model only where comparison with the higher-fidelity formulation showed a meaningful discrepancy.
