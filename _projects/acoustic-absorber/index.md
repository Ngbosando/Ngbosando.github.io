---
layout: post
order: 3
title: Acoustic absorber for additive manufacturing
description: Multiphysics modelling of a controlled porous microstructure to identify transport parameters, predict acoustic absorption and guide geometry before additive manufacturing.
skills: [COMSOL Multiphysics, SolidWorks, Homogenisation, Parametric design, Additive manufacturing, Analytical / numerical comparison]
permalink: /projects/acoustic-absorber/
---

## Context
At the **MSME Laboratory**, the objective was to design and manufacture a controlled porous acoustic material whose absorption behaviour could be predicted. A JCAL-type macroscopic model requires transport parameters obtained from the microstructure.

The workflow links **cell-scale geometry → transport parameters → predicted acoustic absorption → geometry choice before manufacturing**.

## Numerical characterisation
For a reference geometry at porosity 0.46, the identified parameters included tortuosity 1.42, thermal permeability 5.81×10⁻⁹ m², viscous permeability 2.26×10⁻⁹ m², thermal characteristic length 288.30 µm and viscous characteristic length 202.62 µm.

## Reformulation
The viscostatic cell problem could not be implemented directly in COMSOL in the form initially derived. I returned to the **momentum conservation equation** and reformulated the problem in a numerically solvable form. The results were then compared with analytical estimates and expected trends with porosity.

## Parametric design
For the reference case, the predicted absorption reaches approximately **0.92 around 2.5 kHz** for a 1 mm cell and a 25 mm layer. Increasing the layer thickness shifts the absorption peak toward lower frequencies.

## Manufacturing preparation
The geometries were prepared in SolidWorks and exported as STL files for additive manufacturing.
