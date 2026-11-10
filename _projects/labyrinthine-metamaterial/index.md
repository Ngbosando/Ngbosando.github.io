---
layout: post
order: 4
title: Métamatériau labyrinthique & Vibroacoustique
description: Modélisation de cellules labyrinthiques en PMMA et photopolymère, maillages périodiques 2D/3D, dispersion de Bloch-Floquet et étude de transmission.
skills: [ANSYS Workbench / APDL, Python, Gmsh OCC, Bloch-Floquet, Calcul éléments finis, Vibroacoustique]
main-image: /assets/images/PMMA%20from%20unit%20cell.png
permalink: /projects/labyrinthine-metamaterial/
---

<div class="project-intro"><b>Objectif :</b><span>Étudier la propagation des ondes dans des structures labyrinthiques, depuis la génération paramétrique d'une cellule jusqu'à l'analyse de dispersion et de transmission. Le travail porte sur deux matériaux, le PMMA et un photopolymère, avec des modèles 2D et des géométries extrudées.</span></div>

## 1. Conception des structures labyrinthiques

La cellule de base possède une période de **50 mm**. Ses canaux concentriques et ses jonctions imposent un trajet de propagation allongé au sein d'une géométrie compacte. Deux configurations ont été modélisées en CAO pour étudier leur comportement mécanique et vibroacoustique.

<div class="metric-strip">
  <div><b>50 mm</b><span>Période de la cellule</span></div>
  <div><b>2</b><span>Matériaux étudiés</span></div>
  <div><b>2D / 3D</b><span>Configurations EF</span></div>
  <div><b>ANSYS</b><span>Calcul modal et APDL</span></div>
</div>

<div class="figure-pair equal-figures">
  <figure class="technical-figure">
    <a href="{{ '/assets/images/Labyrinthine%20metamaterial%20PMMA%20BP%20siemen%20Nx.png' | relative_url }}"><img src="{{ '/assets/images/Labyrinthine%20metamaterial%20PMMA%20BP%20siemen%20Nx.png' | relative_url }}" alt="Assemblage de cellules labyrinthiques en PMMA conçu avec Siemens NX"></a>
    <figcaption>Configuration PMMA et assemblage de cellules sous Siemens NX.</figcaption>
  </figure>
  <figure class="technical-figure">
    <a href="{{ '/assets/images/Labyrinthine%20metamaterial%20Photopolymer%20metamaterial%20structure%20Fusion%20360.png' | relative_url }}"><img src="{{ '/assets/images/Labyrinthine%20metamaterial%20Photopolymer%20metamaterial%20structure%20Fusion%20360.png' | relative_url }}" alt="Structure labyrinthique photopolymère conçue avec Fusion 360"></a>
    <figcaption>Configuration photopolymère et empilement de cellules sous Fusion 360.</figcaption>
  </figure>
</div>

<figure class="figure-wide technical-figure single-figure">
  <a href="{{ '/assets/images/PMMA%20from%20unit%20cell.png' | relative_url }}"><img src="{{ '/assets/images/PMMA%20from%20unit%20cell.png' | relative_url }}" alt="Vue détaillée d'une cellule labyrinthique extrudée et de ses canaux concentriques"></a>
  <figcaption>Détail de la géométrie labyrinthique extrudée, à partir de la cellule de base.</figcaption>
</figure>

## 2. Géométrie paramétrique et maillage

Un script **Python / Gmsh OCC** génère les canaux, les jonctions, les zones solides et les maillages. Il prend en charge des modèles 2D et 3D, identifie les frontières périodiques et exporte les maillages au format <code>.inp</code> pour leur exploitation dans ANSYS.

<div class="pipeline">
  <div><b>Gmsh OCC</b><small>géométrie paramétrique<br>de la cellule</small></div>
  <div><b>Maillage EF</b><small>2D et 3D<br>frontières identifiées</small></div>
  <div><b>ANSYS / APDL</b><small>conditions périodiques<br>Bloch-Floquet</small></div>
  <div><b>Résultats</b><small>courbes de dispersion<br>et transmission</small></div>
</div>

<div class="result-line"><b>Code source</b><span><a href="https://github.com/Ngbosando/Projects/blob/main/Labyrinthine_metamaterial/Laby.py" target="_blank" rel="noopener noreferrer">Génération de la géométrie et du maillage avec Python / Gmsh</a></span></div>

## 3. Dispersion de Bloch-Floquet

Des conditions de périodicité sont imposées aux frontières opposées de la cellule. Les scripts **ANSYS APDL** représentent les composantes réelle et imaginaire du déplacement par duplication du modèle, puis appliquent les équations de contrainte correspondant au nombre d'onde. Les fréquences propres sont extraites à chaque pas pour construire les courbes de dispersion.

<div class="figure-pair equal-figures">
  <figure class="technical-figure">
    <a href="{{ '/assets/images/PMMA_dispersion_plot.png' | relative_url }}"><img src="{{ '/assets/images/PMMA_dispersion_plot.png' | relative_url }}" alt="Courbes de dispersion du métamatériau en PMMA en déformation plane 2D"></a>
    <figcaption>PMMA : dispersion calculée en déformation plane (2D).</figcaption>
  </figure>
  <figure class="technical-figure">
    <a href="{{ '/assets/images/photopolymer_dispersion_plot.png' | relative_url }}"><img src="{{ '/assets/images/photopolymer_dispersion_plot.png' | relative_url }}" alt="Courbes de dispersion du métamatériau photopolymère en déformation plane 2D"></a>
    <figcaption>Photopolymère : dispersion calculée en déformation plane (2D).</figcaption>
  </figure>
</div>

<figure class="figure-wide technical-figure single-figure">
  <a href="{{ '/assets/images/3D_PMMA_dispersion_plot.png' | relative_url }}"><img src="{{ '/assets/images/3D_PMMA_dispersion_plot.png' | relative_url }}" alt="Dispersion du métamatériau PMMA calculée avec un modèle extrudé 2,5D"></a>
  <figcaption>Extension au modèle extrudé (2,5D) : courbes de dispersion du PMMA.</figcaption>
</figure>

<div class="result-line"><b>Implémentation APDL</b><span><a href="{{ '/assets/images/2D%20Ansys%20Floquet%20BC%20WORK.txt' | relative_url }}">Script des conditions de Floquet 2D</a> · <a href="{{ '/assets/images/3D%20Ansys%20Floquet%20BC%20work.txt' | relative_url }}">Script pour le modèle 3D</a></span></div>

## 4. Transmission et couplage vibroacoustique

Une étude de transmission sur un quart de guide compare trois configurations numériques : **sans air**, **air fermé** et **air ouvert**. La figure ci-dessous présente ces réponses calculées par une approche de réduction de modèle **GBMS (Craig-Bampton et L-CC)** avec les mêmes conditions de guidage.

<figure class="figure-wide technical-figure single-figure">
  <a href="{{ '/assets/images/transmission_trois_cas.png' | relative_url }}"><img src="{{ '/assets/images/transmission_trois_cas.png' | relative_url }}" alt="Comparaison des transmissions dans un quart de guide sans air, avec air fermé et avec air ouvert"></a>
  <figcaption>Comparaison numérique de transmission de 0 à 2 kHz, suivant la prise en compte de l'air.</figcaption>
</figure>

<div class="result-line"><b>Travail en cours</b><span>Confrontation des modèles de dispersion et de transmission, et mise en place de la chaîne de calcul acoustique couplée dans ANSYS Workbench / Mechanical. Les résultats présentés sont numériques et ne constituent pas une validation expérimentale.</span></div>

Le projet s'appuie notamment sur l'article de Hermann et al. (2024), *Design and experimental validation of a finite-size labyrinthine metamaterial for vibro-acoustics*, comme référence de modélisation. <a href="{{ '/assets/images/Labyrinthine%20metamaterial%20from%20unit%20cell.pdf' | relative_url }}">Voir la vue de la structure (PDF)</a>.
