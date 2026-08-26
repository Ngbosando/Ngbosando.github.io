---
layout: post
order: 3
title: Acoustic absorber for additive manufacturing
description: Multiphysics modelling of a controlled porous microstructure to identify transport parameters, predict acoustic absorption and guide geometry before additive manufacturing.
skills: [COMSOL Multiphysics, SolidWorks, Homogenisation, Parametric design, Additive manufacturing, Analytical / numerical comparison]
main-image: /assets/images/msme-thermal.svg
permalink: /projects/acoustic-absorber/
---

## Context
At the **MSME Laboratory**, the objective was to design and manufacture a controlled porous acoustic material whose absorption behaviour could be predicted from its microstructure.

<figure>
  <img src="{{ '/assets/images/msme-thermal.svg' | relative_url }}" alt="COMSOL thermal transport simulation of porous microstructure">
  <figcaption>Cell-scale COMSOL model used to identify transport properties before acoustic prediction and manufacturing.</figcaption>
</figure>

## Numerical model
The workflow links **microstructure → transport parameters → acoustic absorption → geometry choice**. Transport properties are obtained numerically from the representative cell and introduced into the macroscopic acoustic model.

## Reformulation
The initial viscostatic formulation could not be implemented directly in COMSOL. I returned to the momentum conservation equation and reformulated the problem in a numerically solvable form, then compared the results with analytical estimates.

## Parametric design
For the reference case, the predicted absorption reaches approximately **0.92 around 2.5 kHz** for a 1 mm cell and a 25 mm layer. Increasing the layer thickness shifts the absorption peak toward lower frequencies.

## Manufacturing preparation
The geometries were prepared in SolidWorks and exported as STL files for additive manufacturing.
