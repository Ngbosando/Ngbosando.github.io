---
layout: post
order: 1
title: Mechanical assembly design
description: Generation, screening, CAD definition and mechanical verification of shaft-pulley-bearing assemblies.
skills: [Mechanical design, CAD automation, Tolerancing, Structural sizing / FEM, Rotating dynamics]
main-image: /assets/images/assembly-exploded.svg
permalink: /projects/mechanical-assembly-design/
---

<div class="project-intro"><b>Objective</b><span>Explore several assembly architectures, eliminate infeasible concepts and retain mechanically valid designs.</span></div>

## Design space

<figure class="figure-wide">
  <img src="{{ '/assets/images/design-space.svg' | relative_url }}" alt="Assembly design space in MetaExplorer">
  <figcaption>Generated architectures compared by mass, cost, unbalance and resonance margin.</figcaption>
</figure>

<div class="metric-strip"><div><b>314,928</b><span>possible combinations</span></div><div><b>14,624</b><span>sampled</span></div><div><b>1,654</b><span>accepted after FE</span></div><div><b>9</b><span>final architectures</span></div></div>

## Screening

<div class="pipeline"><div><b>Analytical checks</b><small>Tolerance chain, kinematics, strength, bearing life, bolting, thermal growth, fatigue.</small></div><div><b>Campbell pre-screen</b><small>2,266 → 2,000 candidates.</small></div><div><b>CAD + FE</b><small>2,000 → 1,935 solved → 1,654 accepted.</small></div><div><b>Pareto selection</b><small>1,654 → 51 → 9 designs.</small></div></div>

## Assembly definition

<figure class="figure-wide">
  <img src="{{ '/assets/images/assembly-exploded.svg' | relative_url }}" alt="Exploded view of the reference mechanical assembly">
  <figcaption>Reference assembly ASM_C229583: shaft, pulley, bearings, housings and base.</figcaption>
</figure>

<div class="project-intro"><b>Checks</b><span>Functional interfaces, bearing life, fatigue, shaft deflection and rotating-speed margin.</span></div>

<div class="result-line"><b>Result</b><span>Reference: 0.775 kg, €423. A retained alternative reaches 0.469 kg and €416.</span></div>
