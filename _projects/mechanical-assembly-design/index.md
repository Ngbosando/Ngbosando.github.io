---
layout: post
order: 1
title: Mechanical assembly design
description: Generation, screening, CAD definition and mechanical verification of shaft-pulley-bearing assemblies.
skills: [Mechanical design, CAD automation, Tolerancing, Structural sizing / FEM, Rotating dynamics]
main-image: /assets/images/assembly-exploded.png
permalink: /projects/mechanical-assembly-design/
---

<div class="project-intro"><b>Objective</b><span>Generate mechanical architectures, reject infeasible designs, and verify the retained concepts through CAD and mechanical analysis.</span></div>

## 1. Architecture generation and screening

The grammar generates shaft, pulley, bearing, housing and retention combinations. A randomized traversal samples this space, then analytical and dynamic checks progressively remove infeasible concepts.

<div class="pipeline">
  <div><b>Grammar</b><small>314,928 possible<br>14,624 sampled</small></div>
  <div><b>Analytical screening</b><small>2,266 feasible<br>2,000 after Campbell</small></div>
  <div><b>CAD + FEM</b><small>1,935 solved<br>1,654 accepted</small></div>
  <div><b>Selection</b><small>51 Pareto solutions<br>9 final architectures</small></div>
</div>

<div class="figure-pair">
  <figure class="technical-figure">
    <a href="{{ '/assets/images/design-space.png' | relative_url }}"><img src="{{ '/assets/images/design-space.png' | relative_url }}" alt="Mechanical assembly design space"></a>
    <figcaption>Design-space comparison of admissible candidates.</figcaption>
  </figure>

  <figure class="technical-figure">
    <a href="{{ '/assets/images/design-selection.png' | relative_url }}"><img src="{{ '/assets/images/design-selection.png' | relative_url }}" alt="Selected mechanical assembly concepts"></a>
    <figcaption>Inspection of retained concepts with geometry and validation results.</figcaption>
  </figure>
</div>

<p class="section-note">Mass, cost and unbalance are optimisation objectives. Resonance margin is treated as a feasibility threshold.</p>

## 2. Mechanical definition

ASM_C229583 is retained as a stable reference while the screening criteria and reduced models are checked. The architecture is then rebuilt as an assembly and translated into manufacturable part geometry.

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/assembly-exploded.png' | relative_url }}"><img src="{{ '/assets/images/assembly-exploded.png' | relative_url }}" alt="Exploded view of ASM_C229583"></a>
  <figcaption>Exploded assembly used to check component sequence, interfaces and axial retention.</figcaption>
</figure>

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/shaft-drawing.png' | relative_url }}"><img src="{{ '/assets/images/shaft-drawing.png' | relative_url }}" alt="Manufacturing drawing of ASM_C229583 shaft"></a>
  <figcaption>Shaft drawing used to define functional diameters, lengths and fits.</figcaption>
</figure>

## 3. Mechanical verification

The reference assembly is checked against the 3,000 rpm operating requirement. Dynamic response and shaft fatigue are then verified before the design is retained.

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/campbell-c229583.png' | relative_url }}"><img src="{{ '/assets/images/campbell-c229583.png' | relative_url }}" alt="Campbell diagram for ASM_C229583"></a>
  <figcaption>Campbell verification with a calculated speed ceiling of 4,936 rpm.</figcaption>
</figure>

<div class="figure-pair">
  <figure class="technical-figure">
    <a href="{{ '/assets/images/frf-c229583.png' | relative_url }}"><img src="{{ '/assets/images/frf-c229583.png' | relative_url }}" alt="Frequency response of ASM_C229583"></a>
    <figcaption>Frequency-response verification of the reference assembly.</figcaption>
  </figure>

  <figure class="technical-figure">
    <a href="{{ '/assets/images/haigh-c229583.png' | relative_url }}"><img src="{{ '/assets/images/haigh-c229583.png' | relative_url }}" alt="Haigh fatigue diagram for ASM_C229583"></a>
    <figcaption>Haigh fatigue verification of the shaft.</figcaption>
  </figure>
</div>

<div class="metric-strip">
  <div><b>4,936 rpm</b><span>speed ceiling</span></div>
  <div><b>362,904 h</b><span>bearing life</span></div>
  <div><b>10.58</b><span>fatigue factor</span></div>
  <div><b>0.0313 mm</b><span>shaft deflection</span></div>
</div>

## 4. Design decision

ASM_C229583 is used as a reference witness rather than as the final optimum. After screening and Pareto selection, ASM_C288079 reaches **0.469 kg and €416**, compared with **0.775 kg and €423** for the reference, corresponding to a **39.5% mass reduction** at similar cost.
