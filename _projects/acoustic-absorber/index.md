---
layout: post
order: 3
title: Absorbeur acoustique poreux & Multiphysique
description: Homogénéisation micro/macro, résolution EDP sous COMSOL et prédiction de l’absorption avant fabrication additive.
skills: [COMSOL Multiphysics, SolidWorks, Homogénéisation, Modèle JCAL, MATLAB, Impression 3D / STL]
main-image: /assets/images/msme-thermal.png
permalink: /projects/acoustic-absorber/
---

<div class="project-intro"><b>Objectif :</b><span>Concevoir un absorbeur sonore microstructuré dont le comportement acoustique est prédit avant fabrication. La microstructure est caractérisée par homogénéisation à l’échelle locale, puis ses propriétés de transport alimentent un modèle macroscopique JCAL pour guider la conception CAO et la fabrication additive.</span></div>

## 1. De la microstructure à l’absorption

La démarche relie directement la géométrie poreuse aux performances acoustiques globales. Les problèmes de cellule sont d’abord formulés par homogénéisation, puis résolus sous COMSOL pour identifier les propriétés de transport nécessaires au modèle fluide équivalent (JCAL).

<div class="pipeline">
  <div><b>Homogénéisation</b><small>problèmes de cellule<br>basse et haute fréquence</small></div>
  <div><b>COMSOL</b><small>thermostatique<br>tortuosité et viscostatique</small></div>
  <div><b>Transport</b><small>perméabilités, tortuosité<br>longueurs caractéristiques</small></div>
  <div><b>Modèle JCAL</b><small>coefficient d’absorption<br>et fréquence du maximum</small></div>
</div>

<figure class="figure-wide technical-figure single-figure">
  <a href="{{ '/assets/images/msme-thermal.png' | relative_url }}"><img src="{{ '/assets/images/msme-thermal.png' | relative_url }}" alt="Champ thermostatique calculé sur la cellule périodique"></a>
  <figcaption>Champ thermostatique calculé sur la cellule périodique utilisée pour identifier la perméabilité thermique.</figcaption>
</figure>

## 2. Reformulation et résolution du problème viscostatique

La formulation viscostatique ne pouvait pas être implantée directement dans le module EDP standard de COMSOL. Le problème a donc été réécrit à partir de la conservation de la quantité de mouvement afin d’obtenir une forme variationnelle directement résoluble.

<div class="result-line"><b>Choix de modélisation</b><span>Reformulation théorique du problème au lieu d'un changement de méthode, afin de conserver la chaîne d’homogénéisation prévue et la précision des grandeurs de transport.</span></div>

<div class="figure-pair equal-figures">
  <figure class="technical-figure">
    <a href="{{ '/assets/images/pression.jpeg' | relative_url }}"><img src="{{ '/assets/images/pression.jpeg' | relative_url }}" alt="Champ de pression obtenu après résolution sous COMSOL"></a>
    <figcaption>Champ de pression obtenu après résolution du problème de cellule sous COMSOL.</figcaption>
  </figure>

  <figure class="technical-figure">
    <a href="{{ '/assets/images/vts.jpeg' | relative_url }}"><img src="{{ '/assets/images/vts.jpeg' | relative_url }}" alt="Champ de vitesse obtenu après résolution sous COMSOL"></a>
    <figcaption>Champ de vitesse obtenu après résolution du problème viscostatique sous COMSOL.</figcaption>
  </figure>
</div>

## 3. Contrôle des propriétés de transport

Les paramètres extraits sous COMSOL sont comparés aux estimations analytiques de la littérature. Ils permettent de valider les propriétés physiques du milieu poreux sur la plage de porosité ciblée.

<div class="metric-strip">
  <div><b>0,46</b><span>Porosité (φ)</span></div>
  <div><b>1,42</b><span>Tortuosité (α∞)</span></div>
  <div><b>5,81 × 10⁻⁹ m²</b><span>Perméabilité thermique (k'₀)</span></div>
  <div><b>2,26 × 10⁻⁹ m²</b><span>Perméabilité visqueuse (k₀)</span></div>
</div>

## 4. Étude paramétrique avant fabrication CAO

Une fois les propriétés de transport identifiées, le modèle acoustique permet d’étudier l’effet des paramètres géométriques avant de concevoir le prototype physique. La taille de cellule agit sur l'amplitude du pic d’absorption, tandis que l’épaisseur de la couche déplace le maximum vers les basses fréquences.

<div class="figure-pair equal-figures">
  <figure class="technical-figure">
    <a href="{{ '/assets/images/msme-size.png' | relative_url }}"><img src="{{ '/assets/images/msme-size.png' | relative_url }}" alt="Influence de la taille de cellule sur l’absorption acoustique"></a>
    <figcaption>Influence de la taille de cellule sur le niveau et la fréquence d’absorption.</figcaption>
  </figure>

  <figure class="technical-figure">
    <a href="{{ '/assets/images/msme-thickness.png' | relative_url }}"><img src="{{ '/assets/images/msme-thickness.png' | relative_url }}" alt="Influence de l’épaisseur sur l’absorption acoustique"></a>
    <figcaption>Influence de l’épaisseur : déplacement du pic d’absorption vers les basses fréquences.</figcaption>
  </figure>
</div>

## 5. Résultat et orientation CAO / Impression 3D

Pour le cas de référence (taille de cellule de **1 mm** et épaisseur de **25 mm**), le modèle prédit un coefficient d’absorption maximal de **α ≈ 0,92 autour de 2,5 kHz**. L’étude paramétrique sert ensuite à orienter la modélisation 3D sous SolidWorks et l'export des fichiers STL pour la fabrication d'échantillons par impression 3D.

<div class="result-line"><b>Configuration retenue</b><span>l = 1 mm · L = 25 mm · α ≈ 0,92 à 2,5 kHz (fichiers STL générés sous SolidWorks)</span></div>
