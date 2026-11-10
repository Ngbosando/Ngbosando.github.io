---
layout: post
order: 4
title: Métamatériau labyrinthique & Vibroacoustique
description: "Étude d’une géométrie labyrinthique adaptée : CAO, maillage 2D/3D, dispersion de Bloch-Floquet et transmission vibroacoustique."
skills: [Siemens NX, Fusion 360, ANSYS Workbench / APDL, Gmsh, HomoLib / GBMS, Bloch-Floquet, Vibroacoustique]
main-image: /assets/images/Labyrinthine%20metamaterial%20PMMA%20BP%20siemen%20Nx.png
show_hero_image: true
permalink: /projects/labyrinthine-metamaterial/
---

<div class="project-intro"><b>Objectif :</b><span>Étudier la propagation des ondes dans des structures labyrinthiques à partir de géométries CAO, de calculs de dispersion et de réponses de transmission. Le travail distingue les cellules en PMMA et en photopolymère, ainsi qu'une géométrie adaptée pour l'étude vibroacoustique.</span></div>

## 1. Conception des structures labyrinthiques

La cellule de base possède une période de **50 mm**. Ses canaux concentriques et ses jonctions imposent un trajet de propagation allongé au sein d'une géométrie compacte. Deux configurations ont été modélisées en CAO sous **Siemens NX et Fusion 360** pour étudier leur comportement mécanique et vibroacoustique.

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

<figure class="figure-wide technical-figure single-figure labyrinth-2d-figure">
  <a href="{{ '/assets/images/Laby%202D.jpg' | relative_url }}"><img src="{{ '/assets/images/Laby%202D.jpg' | relative_url }}" alt="Vue de la cellule élémentaire labyrinthique 2D en PMMA"></a>
  <figcaption>Géométrie de la cellule labyrinthique 2D en PMMA.</figcaption>
</figure>

## 2. Géométrie et maillage

Les géométries CAO sont préparées au format **STEP**, puis discrétisées pour les études de dispersion 2D et les modèles de transmission 3D. Le maillage du quart de structure et des domaines d'air est préparé sous **Gmsh**, avec identification des interfaces fluide-structure, puis exporté au format <code>.inp</code> pour ANSYS.

<div class="pipeline">
  <div><b>CAO / STEP</b><small>Siemens NX<br>et Fusion 360</small></div>
  <div><b>Gmsh</b><small>maillages EF<br>et interfaces FSI</small></div>
  <div><b>ANSYS / APDL</b><small>dispersion<br>Bloch-Floquet</small></div>
  <div><b>HomoLib / ANSYS</b><small>transmission<br>avec et sans air</small></div>
</div>

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

<div class="metric-strip">
  <div><b>1 512 Hz</b><span>Bande interdite PMMA 2D : 725–2 237 Hz</span></div>
  <div><b>1 030 Hz</b><span>Bande interdite photopolymère 2D : 492–1 522 Hz</span></div>
</div>

<div class="result-line"><b>Implémentation APDL</b><span><a href="{{ '/assets/images/2D%20Ansys%20Floquet%20BC%20WORK.txt' | relative_url }}">Script des conditions de Floquet 2D</a> · <a href="{{ '/assets/images/3D%20Ansys%20Floquet%20BC%20work.txt' | relative_url }}">Script pour le modèle 3D</a></span></div>

## 4. Transmission et couplage vibroacoustique

Une étude de transmission sur un quart de guide compare trois configurations numériques : **sans air**, **air fermé** et **air ouvert**. Les réponses sont calculées par réduction de modèle **GBMS (Craig-Bampton et L-CC)**, sur une géométrie adaptée de celle étudiée par Hermann et al. (2024), avec les mêmes conditions de guidage entre les trois cas.

<div class="result-line"><b>Propriétés physiques</b><span>• <b>PMMA :</b> E = 3,14 GPa ; ν = 0,36 ; ρ = 1 230 kg/m³ ; η = 0,04.<br>• <b>Photopolymère :</b> E = 1,49 GPa ; ν = 0,42 ; ρ = 1 210 kg/m³ ; η = 0,10.<br>• <b>Air :</b> ρ = 1,2043 kg/m³ ; c = 343 m/s dans HomoLib ; acoustique compressible linéaire sans écoulement moyen ni pertes visco-thermiques.<br>Les facteurs de perte η s'appliquent aux réponses harmoniques ; les calculs de dispersion 2D sont non amortis.</span></div>

<figure class="figure-wide technical-figure single-figure">
  <a href="{{ '/assets/images/transmission_trois_cas.png' | relative_url }}"><img src="{{ '/assets/images/transmission_trois_cas.png' | relative_url }}" alt="Comparaison des transmissions dans un quart de guide sans air, avec air fermé et avec air ouvert"></a>
  <figcaption>Transmission mécanique de 0 à 2 kHz : structure seule, cavité d'air fermée et air ouvert.</figcaption>
</figure>

<div class="result-line"><b>Géométrie adaptée</b><span>Les plaques de l'étude sont plus larges et la cavité diffère de la configuration de référence de Hermann et al. Les transmissions <b>sans air</b> et <b>air fermé</b> sont ici plus proches que dans l'article.</span></div>

## 5. Comparaison numérique avec ANSYS

Pour contrôler les résultats, les réponses de transmission calculées avec **HomoLib / GBMS** ont été confrontées à des résultats de référence **ANSYS** sur le même quart de guide. Deux cas sont documentés : une structure sans air et une configuration avec air ouvert.

<figure class="figure-wide technical-figure single-figure">
  <a href="{{ '/assets/images/comparaison_cas%20pur%20strucure_ansys_homolib_reference_complete.png' | relative_url }}"><img src="{{ '/assets/images/comparaison_cas%20pur%20strucure_ansys_homolib_reference_complete.png' | relative_url }}" alt="Comparaison de transmission du cas sans air entre ANSYS, la méthode GBMS et HomoLib, avec détail autour du minimum"></a>
  <figcaption><b>Structure seule :</b> superposition de la référence ANSYS, de la GBMS initiale et des calculs HomoLib, avec un agrandissement de la zone de forte atténuation.</figcaption>
</figure>

<figure class="figure-wide technical-figure single-figure">
  <a href="{{ '/assets/images/comparaison_open.png' | relative_url }}"><img src="{{ '/assets/images/comparaison_open.png' | relative_url }}" alt="Comparaison de transmission pour le cas air ouvert entre HomoLib et ANSYS, avec courbe des écarts"></a>
  <figcaption><b>Air ouvert :</b> comparaison des transmissions HomoLib et ANSYS sur 98 fréquences communes et courbe des écarts en décibels.</figcaption>
</figure>

<div class="metric-strip">
  <div><b>148 202 → 490</b><span>DDL solides → coordonnées GBMS, base initiale du quart guidé</span></div>
  <div><b>98</b><span>Fréquences communes, air ouvert</span></div>
  <div><b>1,77 dB</b><span>Écart RMS inter-solveurs, cause à clarifier</span></div>
</div>

<div class="result-line"><b>Interprétation</b><span>Le cas structurel montre une bonne concordance. Pour l'air ouvert, l'écart RMS de 1,77 dB sur les fréquences communes ne peut pas être attribué d'emblée à la troncature GBMS : les contrôles disponibles entre modèle réduit et calcul complet ne suffisent pas à confirmer cette cause. La définition des réponses, les interfaces fluide-structure et les conditions de rayonnement restent à confronter entre HomoLib et ANSYS.</span></div>

<div class="result-line"><b>Travail en cours</b><span>Il reste à calculer les courbes de dispersion avec couplage fluide-structure, puis à les comparer aux courbes sans fluide pour évaluer l'influence de l'air sur la propagation des ondes et les bandes d'atténuation.</span></div>

L'[article de Hermann et al. (2024)](https://pmc.ncbi.nlm.nih.gov/articles/PMC11391290/), *Design and experimental validation of a finite-size labyrinthine metamaterial for vibro-acoustics*, fournit les propriétés matériaux et les bandes interdites de référence. L'étude présentée utilise une **géométrie adaptée**, et non une reproduction à l'identique.
