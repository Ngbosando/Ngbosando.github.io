---
layout: post
order: 1
title: Conception d’un assemblage mécanique
description: Génération, filtrage, définition CAO et vérification mécanique d’assemblages arbre, poulie et roulements.
skills: [Conception mécanique, Automatisation CAO, Tolérancement, Dimensionnement / FEM, Dynamique des rotors]
main-image: /assets/images/assembly-exploded.png
permalink: /projects/mechanical-assembly-design/
---

<div class="project-intro"><b>Objectif</b><span>Générer des architectures mécaniques, éliminer les concepts non réalisables puis vérifier les solutions retenues par la CAO et le calcul mécanique.</span></div>

## 1. Génération et filtrage des architectures

La grammaire génère les combinaisons possibles d’arbre, poulie, roulements, palier et dispositifs de maintien. Un parcours aléatoire échantillonne cet espace puis des vérifications analytiques et dynamiques éliminent progressivement les concepts non admissibles.

<div class="pipeline">
  <div><b>Grammaire</b><small>314 928 possibles<br>14 624 échantillonnés</small></div>
  <div><b>Filtrage analytique</b><small>2 266 admissibles<br>2 000 après Campbell</small></div>
  <div><b>CAO + FEM</b><small>1 935 calculés<br>1 654 validés</small></div>
  <div><b>Sélection</b><small>51 solutions de Pareto<br>9 architectures finales</small></div>
</div>

<div class="figure-pair">
  <figure class="technical-figure">
    <a href="{{ '/assets/images/design-space.png' | relative_url }}"><img src="{{ '/assets/images/design-space.png' | relative_url }}" alt="Espace de conception des assemblages mécaniques"></a>
    <figcaption>Comparaison des candidats admissibles dans l’espace de conception.</figcaption>
  </figure>

  <figure class="technical-figure">
    <a href="{{ '/assets/images/design-selection.png' | relative_url }}"><img src="{{ '/assets/images/design-selection.png' | relative_url }}" alt="Sélection des concepts d’assemblage mécanique"></a>
    <figcaption>Examen des concepts retenus avec leur géométrie et leurs résultats de validation.</figcaption>
  </figure>
</div>

<p class="section-note">La masse, le coût et le balourd sont les objectifs d’optimisation. La marge de résonance reste une contrainte de faisabilité.</p>

## 2. Définition mécanique

ASM_C229583 est conservé comme référence stable pendant la vérification des critères de filtrage et des modèles réduits. L’architecture est ensuite reconstruite en assemblage puis traduite en géométrie de pièce fabricable.

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/assembly-exploded.png' | relative_url }}"><img src="{{ '/assets/images/assembly-exploded.png' | relative_url }}" alt="Vue éclatée de ASM_C229583"></a>
  <figcaption>Vue éclatée utilisée pour vérifier la séquence d’assemblage, les interfaces et le maintien axial.</figcaption>
</figure>

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/shaft-drawing.png' | relative_url }}"><img src="{{ '/assets/images/shaft-drawing.png' | relative_url }}" alt="Plan de fabrication de l’arbre ASM_C229583"></a>
  <figcaption>Plan de l’arbre utilisé pour définir les diamètres fonctionnels, les longueurs et les ajustements.</figcaption>
</figure>

## 3. Vérification mécanique

L’assemblage de référence est vérifié pour une vitesse de fonctionnement requise de 3 000 tr/min. La réponse dynamique et la tenue en fatigue de l’arbre sont ensuite contrôlées avant validation.

<figure class="figure-wide technical-figure">
  <a href="{{ '/assets/images/campbell-c229583.png' | relative_url }}"><img src="{{ '/assets/images/campbell-c229583.png' | relative_url }}" alt="Diagramme de Campbell de ASM_C229583"></a>
  <figcaption>Diagramme de Campbell avec une vitesse limite calculée de 4 936 tr/min.</figcaption>
</figure>

<div class="figure-pair">
  <figure class="technical-figure">
    <a href="{{ '/assets/images/frf-c229583.png' | relative_url }}"><img src="{{ '/assets/images/frf-c229583.png' | relative_url }}" alt="Réponse fréquentielle de ASM_C229583"></a>
    <figcaption>Vérification de la réponse fréquentielle de l’assemblage de référence.</figcaption>
  </figure>

  <figure class="technical-figure">
    <a href="{{ '/assets/images/haigh-c229583.png' | relative_url }}"><img src="{{ '/assets/images/haigh-c229583.png' | relative_url }}" alt="Diagramme de Haigh de ASM_C229583"></a>
    <figcaption>Vérification en fatigue de l’arbre par diagramme de Haigh.</figcaption>
  </figure>
</div>

<div class="metric-strip">
  <div><b>4 936 tr/min</b><span>vitesse limite</span></div>
  <div><b>362 904 h</b><span>durée de vie des roulements</span></div>
  <div><b>10,58</b><span>coefficient de sécurité en fatigue</span></div>
  <div><b>0,0313 mm</b><span>flèche de l’arbre</span></div>
</div>

## 4. Décision de conception

ASM_C229583 sert de référence de comparaison et non d’optimum final. Après filtrage et sélection de Pareto, ASM_C288079 atteint **0,469 kg et 416 €**, contre **0,775 kg et 423 €** pour la référence, soit une **réduction de masse de 39,5 %** à coût comparable.
