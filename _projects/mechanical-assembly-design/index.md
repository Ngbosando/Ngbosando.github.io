---
layout: post
order: 1
title: Mechanical assembly design
description: Generation, screening, CAD definition and mechanical verification of shaft-pulley-bearing assemblies.
skills: [Mechanical design, CAD automation, Tolerancing, Structural sizing / FEM, Rotating dynamics]
main-image: /assets/images/assembly-exploded.png
permalink: /projects/mechanical-assembly-design/
---

<div class="project-intro"><b>Objective</b><span>Generate mechanical architectures, reject infeasible designs, then verify the retained concepts through CAD and mechanical analysis.</span></div>

## 1. Generate and screen architectures

The grammar defines the possible shaft, pulley, bearing, housing and retention combinations. A randomized traversal samples the design space, then progressively removes concepts that fail analytical or dynamic requirements.

<div class="pipeline">
  <div><b>Grammar</b><small>314,928 possible<br>14,624 sampled</small></div>
  <div><b>Analytical screening</b><small>2,266 feasible<br>2,000 after Campbell</small></div>
  <div><b>CAD + FEM</b><small>1,935 solved<br>1,654 accepted</small></div>
  <div><b>Selection</b><small>51 Pareto solutions<br>9 final architectures</small></div>
</div>

<div class="figure-pair">
  <figure class="technical-figure">
    <a href="{{ '/assets/images/design-space.png' | relative_url }}"><img src="{{ '/assets/images/design-space.png' | relative_url }}" alt="Mechanical assembly design space"></a>
    <figcaption>Design-space view used to compare the admissible candidates. Mass, cost and unbalance are optimisation objectives; resonance margin is used as a feasibility threshold.</figcaption>
  </figure>

  <figure class="technical-figure">
    <a href="{{ '/assets/images/design-selection.png' | relative_url }}"><img src="{{ '/assets/images/design-selection.png' | relative_url }}" alt="Selected mechanical assembly concepts"></a>
    <figcaption>Final inspection of retained concepts with their generated geometry and validation results.</figcaption>
  </figure>
</div>

## 2. From architecture to mechanical definition

ASM_C229583 is used as a stable reference design while the screening criteria and reduced models are checked. The selected architecture is then rebuilt as an assembly and translated into manufacturable part geometry.

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/assembly-exploded.png' | relative_url }}"><img src="{{ '/assets/images/assembly-exploded.png' | relative_url }}" alt="Exploded view of ASM_C229583"></a>
  <figcaption>Exploded assembly used to check component sequence, interfaces and axial retention.</figcaption>
</figure>

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/shaft-drawing.png' | relative_url }}"><img src="{{ '/assets/images/shaft-drawing.png' | relative_url }}" alt="Manufacturing drawing of ASM_C229583 shaft"></a>
  <figcaption>Shaft manufacturing drawing used to define functional diameters, lengths and fits.</figcaption>
</figure>

## 3. Mechanical verification

The reference assembly is then checked against the 3,000 rpm operating requirement. The Campbell diagram gives the speed ceiling; FRF and fatigue checks are used to confirm the dynamic and structural behaviour.

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/campbell-c229583.png' | relative_url }}"><img src="{{ '/assets/images/campbell-c229583.png' | relative_url }}" alt="Campbell diagram for ASM_C229583"></a>
  <figcaption>Campbell diagram. Required operating speed: 3,000 rpm. Calculated speed ceiling: 4,936 rpm.</figcaption>
</figure>

<div class="figure-pair">
  <figure class="technical-figure">
    <a href="{{ '/assets/images/frf-c229583.png' | relative_url }}"><img src="{{ '/assets/images/frf-c229583.png' | relative_url }}" alt="Frequency response of ASM_C229583"></a>
    <figcaption>Frequency-response check of the retained assembly.</figcaption>
  </figure>

  <figure class="technical-figure">
    <a href="{{ '/assets/images/haigh-c229583.png' | relative_url }}"><img src="{{ '/assets/images/haigh-c229583.png' | relative_url }}" alt="Haigh fatigue diagram for ASM_C229583"></a>
    <figcaption>Haigh diagram used for shaft fatigue verification.</figcaption>
  </figure>
</div>

<div class="metric-strip">
  <div><b>4,936 rpm</b><span>speed ceiling</span></div>
  <div><b>362,904 h</b><span>bearing life</span></div>
  <div><b>10.58</b><span>fatigue factor</span></div>
  <div><b>0.0313 mm</b><span>shaft deflection</span></div>
</div>

## 4. Design decision

ASM_C229583 remains a reference witness rather than the final optimum. After screening and Pareto selection, ASM_C288079 reaches **0.469 kg and €416**, compared with **0.775 kg and €423** for the reference, corresponding to a **39.5% mass reduction** at similar cost.
