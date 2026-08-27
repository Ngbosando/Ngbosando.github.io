---
layout: post
order: 2
title: Réduction de modèle d’un câble à 7 torons
description: Comparaison de formulations détaillées et réduites pour accélérer l’étude vibratoire et la propagation des ondes.
skills: [ANSYS Workbench / APDL, Dynamique des structures, Mécanique du contact, WFEM / GBMS, Réduction de modèles]
main-image: /assets/images/cable-beam-spring-user.jpg
permalink: /projects/seven-wire-cable/
---

<div class="project-intro"><b>Objectif</b><span>Réduire le coût de calcul tout en conservant le comportement dynamique nécessaire à l’analyse des courbes de dispersion.</span></div>

## Modèle poutres-ressorts
<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/cable-beam-spring-user.jpg' | relative_url }}"><img src="{{ '/assets/images/cable-beam-spring-user.jpg' | relative_url }}" alt="Modèle poutres-ressorts du câble à 7 torons"></a>
  <figcaption>Modèle poutres-ressorts du câble à 7 torons utilisé pendant le stage.</figcaption>
</figure>

## Dispersion
<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/cable-dispersion.webp' | relative_url }}"><img src="{{ '/assets/images/cable-dispersion.webp' | relative_url }}" alt="Résultats de dispersion du câble à 7 torons"></a>
  <figcaption>Branches de dispersion utilisées pour comparer les différentes formulations.</figcaption>
</figure>

## Vitesse d’énergie
<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/cable-energy.webp' | relative_url }}"><img src="{{ '/assets/images/cable-energy.webp' | relative_url }}" alt="Comparaison de la vitesse d’énergie"></a>
  <figcaption>Comparaison de la vitesse d’énergie entre les formulations réduites et la référence éléments finis.</figcaption>
</figure>

## Erreur relative
<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/cable-error.webp' | relative_url }}"><img src="{{ '/assets/images/cable-error.webp' | relative_url }}" alt="Erreur relative"></a>
  <figcaption>Erreur relative par rapport à la référence réduite FE-WFEM-GBMS.</figcaption>
</figure>

## Temps de calcul
<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/cable-time.webp' | relative_url }}"><img src="{{ '/assets/images/cable-time.webp' | relative_url }}" alt="Temps de calcul"></a>
  <figcaption>Comparaison Beam-Spring SAFE, Beam-Spring WFEM et FE-WFEM-GBMS.</figcaption>
</figure>

<div class="result-line"><b>Résultat</b><span>environ 39 700 vers 680 puis 42 DDL ; environ 2 022 s vers 6,3 s puis 0,6 s.</span></div>
