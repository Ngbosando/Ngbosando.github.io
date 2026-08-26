---
layout: post
order: 3
title: Additive-manufactured acoustic absorber
description: Multiphysics modelling of a controlled porous microstructure to identify transport parameters, study acoustic absorption and guide geometry before additive manufacturing.
skills: [COMSOL Multiphysics, SolidWorks, Homogenisation, Parametric design, Additive manufacturing, Analytical / numerical comparison]
permalink: /projects/acoustic-absorber/
---

## Context
At **MSME laboratory**, the objective was to design and manufacture a granular acoustic material whose absorption behaviour could be predicted. A JCAL-type macroscopic description requires transport parameters obtained from the microstructure.

The work links **cell-scale geometry → transport parameters → predicted acoustic absorption → geometry choice before manufacturing**.

## Numerical characterisation
For one reference geometry at porosity 0.46, the identified parameters included tortuosity 1.42, thermal permeability 5.81×10⁻⁹ m², viscous permeability 2.26×10⁻⁹ m², thermal characteristic length 288.30 µm and viscous characteristic length 202.62 µm.

## Reformulation
The viscostatic cell problem could not be implemented directly in the PDE module in the form initially derived. I returned to the **momentum conservation equation** and reformulated the problem in a form that could be solved numerically in COMSOL. The result was then checked against analytical estimates and known trends with porosity.

## Parametric design
For the reference case, the predicted absorption reaches approximately **0.92 around 2.5 kHz** for a 1 mm cell and 25 mm layer. Increasing thickness shifts the absorption peak toward lower frequencies.

## Manufacturing preparation
SolidWorks geometries were prepared and exported as STL files for additive manufacturing.
