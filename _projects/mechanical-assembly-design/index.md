---
layout: post
order: 1
title: Mechanical assembly design
description: Generation, screening, CAD definition and mechanical verification of shaft-pulley-bearing assemblies.
skills: [Mechanical design, CAD automation, Tolerancing, Structural sizing / FEM, Rotating dynamics]
main-image: /assets/images/assembly-exploded.svg
permalink: /projects/mechanical-assembly-design/
---

<div class="project-intro"><b>Objective</b><span>Explore assembly architectures, eliminate infeasible concepts and retain mechanically valid designs.</span></div>

## Design space

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/design-space.svg' | relative_url }}"><img src="{{ '/assets/images/design-space.svg' | relative_url }}" alt="Assembly design space in MetaExplorer"></a>
  <figcaption>Design space: mass, cost, unbalance and resonance margin.</figcaption>
</figure>

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/design-selection.webp' | relative_url }}"><img src="{{ '/assets/images/design-selection.webp' | relative_url }}" alt="MetaExplorer selected assembly concepts"></a>
  <figcaption>Concept selection with generated assembly geometries.</figcaption>
</figure>

<div class="metric-strip"><div><b>314,928</b><span>possible combinations</span></div><div><b>14,624</b><span>sampled</span></div><div><b>1,654</b><span>accepted after FE</span></div><div><b>9</b><span>final architectures</span></div></div>

## Assembly definition

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/assembly-exploded.svg' | relative_url }}"><img src="{{ '/assets/images/assembly-exploded.svg' | relative_url }}" alt="Exploded view of reference assembly ASM_C229583"></a>
  <figcaption>Reference assembly ASM_C229583.</figcaption>
</figure>

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/shaft-drawing.webp' | relative_url }}"><img src="{{ '/assets/images/shaft-drawing.webp' | relative_url }}" alt="Manufacturing drawing of shaft ASM_C229583"></a>
  <figcaption>Shaft definition and functional fits.</figcaption>
</figure>

## Dynamic verification

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/campbell.webp' | relative_url }}"><img src="{{ '/assets/images/campbell.webp' | relative_url }}" alt="Campbell diagram for ASM_C229583"></a>
  <figcaption>Campbell diagram for ASM_C229583. Required operating speed: 3,000 rpm. Calculated speed ceiling: approximately 4,936 rpm.</figcaption>
</figure>

<div class="result-line"><b>Result</b><span>Reference: 0.775 kg, €423. A retained alternative reaches 0.469 kg and €416.</span></div>
