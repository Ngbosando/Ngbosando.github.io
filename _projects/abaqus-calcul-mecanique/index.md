---
layout: post
order: 5
title: Calcul mécanique & études non linéaires sous Abaqus
description: "Études par éléments finis de poutres et treillis, flexion et torsion, grandes transformations, contact-frottement et mécanique de la rupture."
skills: [Abaqus/CAE, Éléments finis, RDM, Non-linéarité géométrique, Contact & frottement, Rupture & endommagement]
permalink: /projects/abaqus-calcul-mecanique/
---

<div class="project-intro"><b>Objectif :</b><span>Étudier différentes réponses de structures mécaniques sous Abaqus, du modèle élémentaire vérifiable analytiquement aux comportements non linéaires avec contact et endommagement. Les travaux portent sur la construction des modèles, le choix des formulations, la convergence et l'interprétation des résultats.</span></div>

## 1. Poutres, treillis et éléments ressort

Modélisation de structures avec des éléments **Truss, Beam et Spring** : définition des matériaux, des sections, des conditions aux limites et des chargements, puis construction du maillage. L'étude compare les efforts internes et les déplacements obtenus aux prévisions de la résistance des matériaux.

<div class="pipeline">
  <div><b>Prétraitement</b><small>géométrie, matériaux<br>et sections</small></div>
  <div><b>Éléments EF</b><small>Truss, Beam<br>et Spring</small></div>
  <div><b>Résolution</b><small>conditions aux limites<br>et chargements</small></div>
  <div><b>Contrôle</b><small>S11, U et RF<br>extraction XY Data</small></div>
</div>

L'exploitation des résultats utilise notamment les **contraintes S11**, les déplacements **U**, les réactions d'appui **RF** et les historiques **XY Data** pour comparer les modèles et vérifier l'équilibre des efforts.

## 2. Petites et grandes transformations

Comparaison de calculs en petites transformations et en grandes transformations par activation de **NLGEOM**. Les études portent sur l'influence de la cinématique retenue, de la densité du maillage et de l'incrémentation sur la réponse et la convergence du calcul.

<div class="result-line"><b>Points examinés</b><span>Écart entre réponses linéaires et géométriquement non linéaires ; sensibilité au raffinement du maillage ; influence du pas d'incrémentation sur la stabilité et la convergence.</span></div>

## 3. Flexion 2D et torsion 3D

Deux familles de problèmes servent à confronter la simulation éléments finis à une solution analytique :

- **Flexion 2D :** modélisation en contraintes planes avec chargement distribué défini par un <i>Analytical Field</i> ; analyse des contraintes et des déplacements.
- **Torsion 3D :** définition d'un repère cylindrique et application d'une traction tangentielle `tθ` via un <i>Analytical Field</i> ; comparaison du champ de contraintes et de la réponse mécanique aux relations analytiques.

<div class="result-line"><b>Vérification</b><span>Contrôle des conditions aux limites, des champs de sollicitation et de la cohérence des résultats EF avec les solutions de référence.</span></div>

## 4. Contact et frottement

Études de contact avec pression normale de type **Hard Contact** et frottement de **Coulomb**. Comparaison des discrétisations **Surface-to-Surface** et **Node-to-Surface**, ainsi que des formulations de contrainte **Penalty** et **Lagrange Multiplier**.

<div class="pipeline">
  <div><b>Interfaces</b><small>surfaces de contact<br>et frottement</small></div>
  <div><b>Formulations</b><small>Penalty / Lagrange<br>Surface / Node</small></div>
  <div><b>Résultats</b><small>forces de contact CFT<br>et réactions RF</small></div>
  <div><b>Comparaison</b><small>courbes force–déplacement<br>et référence</small></div>
</div>

Le post-traitement exploite les **forces de contact CFT** et les courbes **force–déplacement**, afin d'étudier l'effet de la formulation du contact et de confronter les réponses aux références disponibles.

## 5. Rupture et endommagement

Exploration de différentes approches de propagation de fissure et de dégradation de matériau :

- **VCCT et approche cohésive :** prise en compte de l'énergie de rupture et des interfaces susceptibles de se séparer.
- **X-FEM :** étude des conditions de discrétisation et de maillage associées à la représentation des fissures.
- **Endommagement :** suivi de la variable **SDEG**, des critères énergétiques de rupture et, selon le modèle, de la suppression d'éléments.

<div class="result-line"><b>Apport des études</b><span>Mise en relation du phénomène physique, de la formulation numérique, des paramètres de résolution et des grandeurs exploitables pour interpréter les résultats de calcul.</span></div>

Ces cas réunissent des méthodes de **calcul statique et non linéaire**, de **vérification analytique** et d'**analyse de contact/rupture**. Les résultats détaillés et les figures de simulation pourront être ajoutés progressivement.
