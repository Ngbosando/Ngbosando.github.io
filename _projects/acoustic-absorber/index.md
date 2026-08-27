---
layout: post
order: 3
title: Absorbeur acoustique poreux
description: Homogénéisation, calcul des propriétés de transport et prédiction de l’absorption avant fabrication additive.
skills: [COMSOL Multiphysics, SolidWorks, Homogénéisation, Acoustique, Fabrication additive]
main-image: /assets/images/msme-thermal.png
permalink: /projects/acoustic-absorber/
---

<div class="project-intro"><b>Objectif :</b><span>Concevoir un absorbeur sonore granulaire dont le comportement acoustique peut être prédit avant fabrication. La microstructure est caractérisée à l’échelle locale, puis ses propriétés de transport alimentent un modèle acoustique macroscopique pour orienter la géométrie à fabriquer.</span></div>

## 1. De la microstructure à l’absorption

La démarche relie directement la géométrie poreuse aux performances acoustiques. Les problèmes de cellule sont d’abord formulés par homogénéisation, puis résolus sous COMSOL pour identifier les propriétés de transport nécessaires au modèle JCAL.

<div class="pipeline">
  <div><b>Homogénéisation</b><small>problèmes de cellule<br>basse et haute fréquence</small></div>
  <div><b>COMSOL</b><small>thermostatique<br>tortuosité et viscostatique</small></div>
  <div><b>Transport</b><small>perméabilités, tortuosité<br>longueurs caractéristiques</small></div>
  <div><b>JCAL</b><small>coefficient d’absorption<br>et fréquence du maximum</small></div>
</div>

<figure class="figure-wide technical-figure single-figure">
  <a href="{{ '/assets/images/msme-thermal.png' | relative_url }}"><img src="{{ '/assets/images/msme-thermal.png' | relative_url }}" alt="Champ thermostatique calculé sur la cellule périodique"></a>
  <figcaption>Champ thermostatique calculé sur la cellule périodique utilisée pour identifier les propriétés de transport.</figcaption>
</figure>

## 2. Reformulation et résolution du problème viscostatique

La formulation viscostatique ne pouvait pas être implantée directement dans le module EDP utilisé. Le problème a donc été réécrit à partir de l’équation de conservation de la quantité de mouvement afin d’obtenir une forme directement résoluble sous COMSOL.

<div class="result-line"><b>Choix de modélisation</b><span>Reformuler le problème au lieu de changer de méthode afin de conserver la chaîne d’homogénéisation prévue et les grandeurs de transport recherchées.</span></div>

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

Les paramètres issus de COMSOL sont comparés aux estimations analytiques disponibles dans la littérature. Les perméabilités restent en bon accord sur une large plage, tandis que certaines approximations analytiques se dégradent lorsque la porosité diminue.

<div class="metric-strip">
  <div><b>0,46</b><span>porosité</span></div>
  <div><b>1,42</b><span>tortuosité</span></div>
  <div><b>5,81 × 10⁻⁹ m²</b><span>perméabilité thermique</span></div>
  <div><b>2,26 × 10⁻⁹ m²</b><span>perméabilité visqueuse</span></div>
</div>

## 4. Étude paramétrique avant fabrication

Une fois les propriétés de transport identifiées, le modèle acoustique permet d’étudier l’effet des paramètres géométriques avant de fabriquer un prototype. La taille de cellule agit sur le niveau et la fréquence d’absorption, tandis que l’augmentation de l’épaisseur déplace le maximum vers les basses fréquences.

<div class="figure-pair equal-figures">
  <figure class="technical-figure">
    <a href="{{ '/assets/images/msme-size.png' | relative_url }}"><img src="{{ '/assets/images/msme-size.png' | relative_url }}" alt="Influence de la taille de cellule sur l’absorption acoustique"></a>
    <figcaption>Influence de la taille de cellule sur le niveau et la fréquence d’absorption.</figcaption>
  </figure>

  <figure class="technical-figure">
    <a href="{{ '/assets/images/msme-thickness.png' | relative_url }}"><img src="{{ '/assets/images/msme-thickness.png' | relative_url }}" alt="Influence de l’épaisseur sur l’absorption acoustique"></a>
    <figcaption>Influence de l’épaisseur : déplacement du maximum d’absorption vers les basses fréquences.</figcaption>
  </figure>
</div>

## 5. Résultat et choix de conception

Pour le cas de référence, avec une taille de cellule de **1 mm** et une couche de **25 mm**, le modèle prédit un coefficient d’absorption maximal d’environ **0,92 autour de 2,5 kHz**. L’étude paramétrique sert ensuite à sélectionner la géométrie à préparer sous SolidWorks et à exporter en STL pour fabrication additive.

<div class="result-line"><b>Cas de référence</b><span>l = 1 mm · L = 25 mm · α ≈ 0,92 à 2,5 kHz</span></div>
