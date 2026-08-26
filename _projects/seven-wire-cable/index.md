---
layout: post
order: 2
title: Seven-wire cable model reduction
description: Comparison of three modelling levels for a seven-wire stranded cable, from a detailed 3D finite-element reference to reduced formulations for faster dispersion studies.
skills: [ANSYS Workbench / APDL, Contact mechanics, Structural dynamics, WFEM / SAFE / GBMS, Model reduction, Validation]
permalink: /projects/seven-wire-cable/
---

## Context
During my final-year internship at **Inria**, in collaboration with **POMA**, I studied elastic-wave propagation and vibration transmission in seven-wire stranded cables.

## Objective
Reduce the computational cost of the 3D reference model while retaining the dispersion branches required for vibration analysis.

## Model hierarchy
<div class="pipeline"><div><b>3D finite-element model</b><small>approximately 39,700 DOF<br>Helical geometry and inter-wire contacts. Reference model.</small></div><div><b>FE-WFEM-GBMS</b><small>approximately 680 DOF<br>Reduction of the periodic finite-element cell.</small></div><div><b>Beam-spring model</b><small>42 DOF<br>Wires represented by beams and contacts by springs.</small></div></div>

## Validation
The reduced formulations were compared with the 3D reference through dispersion curves and convergence studies. The model was refined only when the comparison identified a significant discrepancy.

## Use of each model
The beam-spring formulation is used for rapid exploration. FE-WFEM-GBMS provides the higher-fidelity reduced reference used to control the deviation from the detailed 3D model.

Industrial POMA calculation and experimental data are confidential and are therefore not reproduced in this portfolio.
