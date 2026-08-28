---
layout: post
order: 2
title: Réduction de modèle d’un toron à 7 brins
description: Réduction progressive d’un modèle éléments finis de câble hélicoïdal pour accélérer l’analyse de dispersion et de transmission vibratoire.
skills: [ANSYS Workbench / APDL, Dynamique des structures, Mécanique du contact, WFEM / GBMS, Réduction de modèles, Python, MATLAB]
main-image: /assets/images/cable-3d.png
permalink: /projects/seven-wire-cable/
---

<div class="project-intro"><b>Objectif :</b><span>Exploiter des sous-structures et des modèles réduits pour obtenir rapidement les indicateurs de dispersion d’un toron à 7 brins hélicoïdaux, tout en conservant la fidélité dynamique requise pour comparer les formulations de calcul.</span></div>

## 1. Problème étudié

L'étude porte sur la propagation d’ondes élastiques et la transmission vibratoire dans des câbles de transport. Le point de départ est un modèle éléments finis 3D détaillé du toron à 7 brins (intégration de la géométrie hélicoïdale et des contacts non linéaires inter-brins). Bien que très précis, ce modèle initial reste trop coûteux pour multiplier les analyses paramétriques de dispersion.

<div class="figure-pair equal-figures">
  <figure class="technical-figure">
    <a href="{{ '/assets/images/cable-3d.png' | relative_url }}"><img src="{{ '/assets/images/cable-3d.png' | relative_url }}" alt="Modèle tridimensionnel du câble à 7 brins"></a>
    <figcaption>Modèle 3D éléments finis du toron à 7 brins hélicoïdaux avec contacts inter-brins.</figcaption>
  </figure>

  <figure class="technical-figure">
    <a href="{{ '/assets/images/cable-beam-spring.jpg' | relative_url }}"><img src="{{ '/assets/images/cable-beam-spring.jpg' | relative_url }}" alt="Modèle poutres-ressorts du câble à 7 brins"></a>
    <figcaption>Modèle lattice beam-spring obtenu après simplification de la formulation initiale.</figcaption>
  </figure>
</div>

## 2. Réduction progressive du modèle

La démarche s'appuie sur une hiérarchie de modèles de complexité décroissante. Chaque niveau sert de référence au suivant, permettant de contrôler la perte d’information dynamique et la précision des fréquences calculées.

<div class="pipeline">
  <div><b>Modèle EF initial</b><small>≈ 40 000 DDL<br>géométrie 3D et contacts</small></div>
  <div><b>FE-WFEM-GBMS</b><small>676 DDL<br>238 + 238 frontière, 200 internes</small></div>
  <div><b>Lattice beam-spring</b><small>42 DDL<br>lecture rapide de la dispersion</small></div>
  <div><b>Validation</b><small>dispersion, erreur relative<br>et temps de calcul</small></div>
</div>

## 3. Validation par les courbes de dispersion

Les branches de dispersion constituent l’indicateur principal pour comparer les formulations. Les scripts de post-traitement (Python / MATLAB) permettent de suivre les erreurs relatives et les décalages de pics entre le modèle de référence et les formulations réduites.

<div class="figure-pair equal-figures">
  <figure class="technical-figure">
    <a href="{{ '/assets/images/parallel7_dispersion.png' | relative_url }}"><img src="{{ '/assets/images/parallel7_dispersion.png' | relative_url }}" alt="Courbes de dispersion du modèle de câble à 7 brins"></a>
    <figcaption>Courbes de dispersion utilisées pour comparer les formulations du câble à 7 brins.</figcaption>
  </figure>

  <figure class="technical-figure">
    <a href="{{ '/assets/images/twisted7_probe_dispersion.png' | relative_url }}"><img src="{{ '/assets/images/twisted7_probe_dispersion.png' | relative_url }}" alt="Dispersion du câble hélicoïdal à 7 brins"></a>
    <figcaption>Vérification de la dispersion sur la géométrie hélicoïdale du toron.</figcaption>
  </figure>
</div>

<figure class="figure-wide technical-figure single-figure">
  <a href="{{ '/assets/images/beam_spring_wfem_fe_relative_error.png' | relative_url }}"><img src="{{ '/assets/images/beam_spring_wfem_fe_relative_error.png' | relative_url }}" alt="Erreur relative entre modèles réduits et référence éléments finis"></a>
  <figcaption>Erreur relative entre les formulations beam-spring, WFEM et la référence éléments finis réduite.</figcaption>
</figure>

## 4. Gain en coût de calcul

La hiérarchisation des modèles permet d'adapter l'effort numérique au besoin industriel :
* **Référence FE-WFEM-GBMS** (676 DDL) pour le contrôle de précision de référence[cite: 1].
* **Beam-spring WFEM / SAFE** (42 DDL) pour la pré-analyse et l'exploration rapide de la dispersion en quelques fractions de seconde[cite: 1].

<figure class="figure-wide technical-figure single-figure">
  <a href="{{ '/assets/images/cable-time.png' | relative_url }}"><img src="{{ '/assets/images/cable-time.png' | relative_url }}" alt="Comparaison des temps de calcul des modèles du câble"></a>
  <figcaption>Temps de calcul mesurés pour un balayage de dispersion : 0,8 s (beam-spring SAFE), 2,4 s (beam-spring WFEM) et 940 s (référence FE-WFEM-GBMS).</figcaption>
</figure>

<div class="metric-strip">
  <div><b>≈ 40 000</b><span>DDL du modèle EF initial</span></div>
  <div><b>676</b><span>DDL après FE-WFEM-GBMS</span></div>
  <div><b>42</b><span>DDL du modèle beam-spring</span></div>
  <div><b>< 1 s</b><span>Pré-analyse beam-spring</span></div>
</div>

## 5. Résultat

La méthodologie mise en place fournit une stratégie de sous-structuration efficace : elle permet de sélectionner à la volée le niveau de réduction adapté au besoin de calcul (analyse exploratoire rapide ou validation fine), évitant le recours systématique au modèle éléments finis complet le plus coûteux[cite: 1].
