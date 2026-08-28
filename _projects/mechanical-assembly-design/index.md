---
layout: post
order: 1
title: Conception générative & calcul d’un assemblage mécanique
description: Génération, filtrage analytique/EF, définition CAO et vérification dynamique d’assemblages arbre, poulie et roulements.
skills: [Conception mécanique, CAO & Tolérancement, Dimensionnement / FEM, Dynamique des rotors, Python, FreeCAD, Gmsh]
main-image: /assets/images/assembly-exploded.png
permalink: /projects/mechanical-assembly-design/
---

<div class="project-intro"><b>Objectif :</b><span>Développer un prototype de conception générative capable de générer, filtrer et vérifier automatiquement des architectures mécaniques (arbre-roulements-poulie), en couplant dimensionnement analytique, modélisation CAO et vérification éléments finis / dynamique.</span></div>

## 1. Génération et filtrage des architectures

Une grammaire de conception génère l’ensemble des combinaisons possibles (arrêts axiaux, montages de roulements, transmission du couple). Un algorithme d'exploration échantillonne cet espace, puis une succession de filtres analytiques et dynamiques élimine progressivement les concepts non admissibles.

<div class="pipeline">
  <div><b>Grammaire</b><small>314 928 possibles<br>14 624 échantillonnés</small></div>
  <div><b>Filtrage analytique</b><small>2 266 admissibles<br>2 000 après Campbell</small></div>
  <div><b>CAO + FEM</b><small>1 935 calculés<br>1 654 validés</small></div>
  <div><b>Sélection Pareto</b><small>51 solutions efficaces<br>9 architectures retenues</small></div>
</div>

<div class="figure-pair equal-figures">
  <figure class="technical-figure">
    <a href="{{ '/assets/images/design-space.png' | relative_url }}"><img src="{{ '/assets/images/design-space.png' | relative_url }}" alt="Espace de conception des assemblages mécaniques"></a>
    <figcaption>Comparaison des candidats admissibles dans l’espace de conception (Masse vs Coût vs Balourd).</figcaption>
  </figure>

  <figure class="technical-figure">
    <a href="{{ '/assets/images/design-selection.png' | relative_url }}"><img src="{{ '/assets/images/design-selection.png' | relative_url }}" alt="Sélection des concepts d’assemblage mécanique"></a>
    <figcaption>Examen des concepts retenus avec leur géométrie 3D et leurs résultats de validation.</figcaption>
  </figure>
</div>

<p class="section-note">La masse, le coût et le balourd constituent les objectifs d’optimisation multi-critères, sous contraintes de marge de résonance et de tenue mécanique.</p>

## 2. Définition mécanique & CAO

L’architecture de référence (`ASM_C229583`) est modélisée en assemblage CAO complet afin de valider la séquence de montage, le maintien axial et la mise en plan de fabrication (cotation fonctionnelle et chaînes de cotes).

<figure class="figure-wide technical-figure single-figure">
  <a href="{{ '/assets/images/assembly-exploded.png' | relative_url }}"><img src="{{ '/assets/images/assembly-exploded.png' | relative_url }}" alt="Vue éclatée de ASM_C229583"></a>
  <figcaption>Vue éclatée de l'assemblage : vérification des empilements, des interfaces paliers et du montage des roulements.</figcaption>
</figure>

<figure class="figure-wide technical-figure single-figure">
  <a href="{{ '/assets/images/shaft-drawing.png' | relative_url }}"><img src="{{ '/assets/images/shaft-drawing.png' | relative_url }}" alt="Plan de fabrication de l’arbre ASM_C229583"></a>
  <figcaption>Mise en plan de l’arbre de transmission : définitions des portées de roulement, tolérances géométriques et ajustements ISO.</figcaption>
</figure>

## 3. Vérification mécanique & Dynamique des rotors

L’assemblage est dimensionné pour une vitesse nominale de fonctionnement de 3 000 tr/min. La tenue mécanique est contrôlée par éléments finis et vérifications analytiques recoupées (fatigue, dynamique des rotors et durée de vie des roulements).

<figure class="figure-wide technical-figure single-figure">
  <a href="{{ '/assets/images/campbell-c229583.png' | relative_url }}"><img src="{{ '/assets/images/campbell-c229583.png' | relative_url }}" alt="Diagramme de Campbell de ASM_C229583"></a>
  <figcaption>Diagramme de Campbell : identification des vitesses critiques et validation d'une vitesse limite calculée à 4 936 tr/min.</figcaption>
</figure>

<div class="figure-pair equal-figures">
  <figure class="technical-figure">
    <a href="{{ '/assets/images/frf-c229583.png' | relative_url }}"><img src="{{ '/assets/images/frf-c229583.png' | relative_url }}" alt="Réponse fréquentielle de ASM_C229583"></a>
    <figcaption>Analyse de la réponse fréquentielle (FRF) sous sollicitation dynamique.</figcaption>
  </figure>

  <figure class="technical-figure">
    <a href="{{ '/assets/images/haigh-c229583.png' | relative_url }}"><img src="{{ '/assets/images/haigh-c229583.png' | relative_url }}" alt="Diagramme de Haigh de ASM_C229583"></a>
    <figcaption>Vérification de la tenue en fatigue de l’arbre via le diagramme de Haigh.</figcaption>
  </figure>
</div>

<div class="metric-strip">
  <div><b>4 936 tr/min</b><span>Vitesse limite critique</span></div>
  <div><b>362 904 h</b><span>Durée de vie L10h roulements</span></div>
  <div><b>10,58</b><span>Coeff. de sécurité fatigue (Haigh)</span></div>
  <div><b>0,031 mm</b><span>Flèche maximale d'arbre</span></div>
</div>

## 4. Décision de conception & Gains

Le concept `ASM_C229583` a servi de référence de validation. Après extraction du front de Pareto, l'architecture optimale `ASM_C288079` atteint **0,469 kg et 416 €**, contre **0,775 kg et 423 €** pour la référence initialement retenue. 

Cela représente une **réduction de masse de 39,5 %** à coût égal, tout en garantissant le respect strict du cahier des charges mécanique et dynamique.
