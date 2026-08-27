---
layout: post
order: 2
title: Seven-wire cable model reduction
description: Comparison of detailed and reduced formulations for faster vibration and wave-propagation studies.
skills: [ANSYS Workbench / APDL, Structural dynamics, Contact mechanics, WFEM / GBMS, Model reduction]
main-image: /assets/images/cable-3d.svg
permalink: /projects/seven-wire-cable/
---

<div class="project-intro"><b>Objective</b><span>Reduce computation cost while preserving the dynamic behaviour required for dispersion analysis.</span></div>

## Reference model
<figure class="figure-wide technical-figure"><img src="{{ '/assets/images/cable-3d.svg' | relative_url }}" alt="Three-dimensional seven-wire cable model"><figcaption>Detailed seven-wire geometry.</figcaption></figure>

## Reduced model
<figure class="figure-wide technical-figure"><img src="{{ '/assets/images/cable-beam-spring-user.jpg' | relative_url }}" alt="Seven-wire beam-spring model"><figcaption>42-DOF beam-spring representation.</figcaption></figure>

## Dispersion
<figure class="figure-wide technical-figure"><img src="{{ '/assets/images/cable-dispersion.webp' | relative_url }}" alt="Seven-wire dispersion results"><figcaption>Dispersion branches used to compare model formulations.</figcaption></figure>

## Energy velocity
<figure class="figure-wide technical-figure"><img src="{{ '/assets/images/cable-energy.webp' | relative_url }}" alt="Energy velocity comparison"><figcaption>Energy velocity comparison between reduced formulations and the finite-element reference.</figcaption></figure>

## Relative error
<figure class="figure-wide technical-figure"><img src="{{ '/assets/images/cable-error.webp' | relative_url }}" alt="Relative error"><figcaption>Relative error used to quantify the effect of model reduction.</figcaption></figure>

## Computation time
<figure class="figure-wide technical-figure"><img src="{{ '/assets/images/cable-time.webp' | relative_url }}" alt="Computation time"><figcaption>Beam-spring SAFE, beam-spring WFEM and FE-WFEM-GBMS.</figcaption></figure>

<div class="result-line"><b>Result</b><span>approximately 39,700 to 680 to 42 DOF; approximately 2,022 s to 6.3 s to 0.6 s.</span></div>
