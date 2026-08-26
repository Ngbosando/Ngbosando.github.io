---
layout: post
order: 1
title: Mechanical assembly design and selection
description: Deterministic generation, screening and mechanical verification of shaft-pulley-bearing assemblies.
skills: [Mechanical design, CAD automation, Tolerancing, Structural sizing / FEM, Rotating dynamics, Design space exploration]
main-image: /assets/images/assembly-exploded.svg
permalink: /projects/mechanical-assembly-design/
---

## Context
The study concerns a belt-drive assembly built from a **shaft, pulley, two bearings, housings and a base**. The objective is to compare admissible mechanical architectures while keeping the design process deterministic and traceable.

<figure class="wide-figure">
  <img src="{{ '/assets/images/assembly-exploded.svg' | relative_url }}" alt="Exploded mechanical assembly drawing">
  <figcaption>Reference assembly ASM_C229583.</figcaption>
</figure>

## Generation and screening
The shape grammar records the rule sequence used to generate each architecture. A randomized traversal samples the design space before analytical checks, CAD generation and finite-element verification.

<div class="pipeline"><div><b>Analytical feasibility</b><small>14,624 → 2,266</small></div><div><b>Campbell screening</b><small>2,266 → 2,000</small></div><div><b>CAD and FEM</b><small>2,000 → 1,935 solved → 1,654 accepted</small></div><div><b>Selection</b><small>1,654 → 51 Pareto → 9 final architectures</small></div></div>

## Exploration and selection
<figure class="wide-figure">
  <img src="{{ '/assets/images/design-space.svg' | relative_url }}" alt="MetaExplorer assembly design space">
  <figcaption>Mass, cost, unbalance and resonance margin are inspected together with the generated geometries.</figcaption>
</figure>

## Axial tolerance chain
<figure class="wide-figure">
  <img src="{{ '/assets/images/tolerance-chain.svg' | relative_url }}" alt="Axial tolerance chain of the reference shaft assembly">
  <figcaption>Worst-case reserved tolerance: 0.840 mm. Remaining axial margin: 41.41 mm.</figcaption>
</figure>

## Mechanical verification
For reference candidate ASM_C229583, the calculated speed ceiling is **4,936 rpm** for a 3,000 rpm requirement. Bearing life, shaft deflection and fatigue are checked as feasibility constraints before the design is retained.

## Result
The reference design weighs 0.775 kg and costs €423. Candidate ASM_C288079 reaches **0.469 kg and €416**, corresponding to **39.5% lower mass and 1.6% lower cost** than the reference.
