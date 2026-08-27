---
layout: post
order: 1
title: Mechanical assembly design
description: Generation, screening, CAD definition and mechanical verification of shaft-pulley-bearing assemblies.
skills: [Mechanical design, CAD automation, Tolerancing, Structural sizing / FEM, Rotating dynamics]
main-image: /assets/images/ASM_C229583.png
permalink: /projects/mechanical-assembly-design/
---

<div class="project-intro"><b>Objective</b><span>Explore assembly architectures, eliminate infeasible concepts and retain mechanically valid designs.</span></div>

## Design space

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/design-space.png' | relative_url }}"><img src="{{ '/assets/images/design-space.png' | relative_url }}" alt="Assembly design space"></a>
  <figcaption>Generated design space.</figcaption>
</figure>

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/design-selection.png' | relative_url }}"><img src="{{ '/assets/images/design-selection.png' | relative_url }}" alt="Design selection"></a>
  <figcaption>Selection of admissible architectures.</figcaption>
</figure>

<div class="metric-strip"><div><b>314,928</b><span>possible combinations</span></div><div><b>14,624</b><span>sampled</span></div><div><b>2,266</b><span>analytically feasible</span></div><div><b>2,000</b><span>sent to CAE</span></div><div><b>1,935</b><span>FE solved</span></div><div><b>1,654</b><span>accepted</span></div><div><b>51</b><span>Pareto non-dominated</span></div><div><b>9</b><span>final architectures</span></div></div>

## Retained reference

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/ASM_C229583.png' | relative_url }}"><img src="{{ '/assets/images/ASM_C229583.png' | relative_url }}" alt="ASM_C229583 retained assembly"></a>
  <figcaption>ASM_C229583, retained as a stable reference across the design sweeps.</figcaption>
</figure>

## Assembly definition

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/assembly-exploded.png' | relative_url }}"><img src="{{ '/assets/images/assembly-exploded.png' | relative_url }}" alt="Exploded view of ASM_C229583"></a>
  <figcaption>Exploded assembly view.</figcaption>
</figure>

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/shaft-drawing.png' | relative_url }}"><img src="{{ '/assets/images/shaft-drawing.png' | relative_url }}" alt="Manufacturing drawing of ASM_C229583 shaft"></a>
  <figcaption>Shaft manufacturing drawing and functional dimensions.</figcaption>
</figure>

## Mechanical verification

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/campbell-c229583.png' | relative_url }}"><img src="{{ '/assets/images/campbell-c229583.png' | relative_url }}" alt="Campbell diagram for ASM_C229583"></a>
  <figcaption>Campbell verification up to the required 3,000 rpm operating range.</figcaption>
</figure>

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/frf-c229583.png' | relative_url }}"><img src="{{ '/assets/images/frf-c229583.png' | relative_url }}" alt="Frequency response of ASM_C229583"></a>
  <figcaption>Frequency-response verification.</figcaption>
</figure>

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/haigh-c229583.png' | relative_url }}"><img src="{{ '/assets/images/haigh-c229583.png' | relative_url }}" alt="Haigh fatigue diagram for ASM_C229583"></a>
  <figcaption>Fatigue verification of the shaft.</figcaption>
</figure>

<div class="result-line"><b>Reference</b><span>ASM_C229583: 0.775 kg, €423, speed ceiling 4,936 rpm. The resolved front reaches 0.469 kg and €416 for ASM_C288079.</span></div>
