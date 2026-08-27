---
layout: post
order: 2
title: Seven-wire cable model reduction
description: Comparison of detailed and reduced formulations for faster vibration and wave-propagation studies.
skills: [ANSYS Workbench / APDL, Structural dynamics, Contact mechanics, WFEM / GBMS, Model reduction]
main-image: /assets/images/cable-beam-spring-user.jpg
permalink: /projects/seven-wire-cable/
---

<div class="project-intro"><b>Objective</b><span>Reduce computation cost while preserving the dynamic behaviour required for dispersion analysis.</span></div>

## Beam-spring model
<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/cable-beam-spring-user.jpg' | relative_url }}"><img src="{{ '/assets/images/cable-beam-spring-user.jpg' | relative_url }}" alt="Seven-wire beam-spring model"></a>
  <figcaption>Seven-wire beam-spring model used during the internship.</figcaption>
</figure>

## Dispersion
<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/cable-dispersion.webp' | relative_url }}"><img src="{{ '/assets/images/cable-dispersion.webp' | relative_url }}" alt="Seven-wire dispersion results"></a>
  <figcaption>Dispersion branches used to compare model formulations.</figcaption>
</figure>

## Energy velocity
<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/cable-energy.webp' | relative_url }}"><img src="{{ '/assets/images/cable-energy.webp' | relative_url }}" alt="Energy velocity comparison"></a>
  <figcaption>Energy velocity comparison between reduced formulations and the finite-element reference.</figcaption>
</figure>

## Relative error
<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/cable-error.webp' | relative_url }}"><img src="{{ '/assets/images/cable-error.webp' | relative_url }}" alt="Relative error"></a>
  <figcaption>Relative error against the FE-WFEM reduced GBMS reference.</figcaption>
</figure>

## Computation time
<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/cable-time.webp' | relative_url }}"><img src="{{ '/assets/images/cable-time.webp' | relative_url }}" alt="Computation time"></a>
  <figcaption>Beam-spring SAFE, beam-spring WFEM and FE-WFEM-GBMS.</figcaption>
</figure>

<div class="result-line"><b>Result</b><span>approximately 39,700 to 680 to 42 DOF; approximately 2,022 s to 6.3 s to 0.6 s.</span></div>
