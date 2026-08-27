---
layout: post
order: 2
title: Réduction de modèle d’un câble à 7 torons
description: Réduction progressive d’un modèle éléments finis de câble pour accélérer l’analyse de dispersion et de transmission vibratoire.
skills: [ANSYS Workbench / APDL, Dynamique des structures, Mécanique du contact, WFEM / GBMS, Réduction de modèles]
main-image: /assets/images/cable-3d.png
permalink: /projects/seven-wire-cable/
---

<div class="project-intro"><b>Objectif :</b><span>Exploiter des sous-structures et des modèles réduits pour obtenir rapidement les indicateurs de dispersion d’un câble à 7 torons, tout en conservant le niveau de fidélité dynamique nécessaire pour comparer les formulations de calcul.</span></div>

## 1. Problème étudié

Le stage porte sur la propagation d’ondes élastiques et la transmission vibratoire dans des câbles de transport. Le point de départ est un modèle éléments finis détaillé du toron, suffisamment riche pour représenter sa géométrie et ses interactions, mais trop coûteux pour multiplier les analyses de dispersion.

<div class="figure-pair equal-figures">
  <figure class="technical-figure">
    <a href="{{ '/assets/images/cable-3d.png' | relative_url }}"><img src="{{ '/assets/images/cable-3d.png' | relative_url }}" alt="Modèle tridimensionnel du câble à 7 torons"></a>
    <figcaption>Modèle tridimensionnel du câble à 7 torons utilisé comme point de départ.</figcaption>
  </figure>

  <figure class="technical-figure">
    <a href="{{ '/assets/images/cable-beam-spring.jpg' | relative_url }}"><img src="{{ '/assets/images/cable-beam-spring.jpg' | relative_url }}" alt="Modèle poutres-ressorts du câble à 7 torons"></a>
    <figcaption>Modèle lattice beam-spring obtenu après simplification de la formulation initiale.</figcaption>
  </figure>
</div>

## 2. Réduction progressive du modèle

La démarche consiste à conserver une hiérarchie de modèles plutôt qu’à remplacer directement le modèle détaillé par une formulation minimale. Chaque niveau sert de référence au suivant et permet de contrôler la perte d’information dynamique.

<div class="pipeline">
  <div><b>Modèle EF initial</b><small>≈ 40 000 DDL<br>géométrie détaillée et contacts</small></div>
  <div><b>FE-WFEM-GBMS</b><small>676 DDL<br>238 + 238 frontière, 200 internes</small></div>
  <div><b>Lattice beam-spring</b><small>42 DDL<br>lecture rapide de la dispersion</small></div>
  <div><b>Comparaison</b><small>dispersion, erreur relative<br>et temps de calcul</small></div>
</div>

## 3. Validation par les courbes de dispersion

Les branches de dispersion constituent l’indicateur principal pour comparer les formulations. La réduction est retenue si elle permet de retrouver les tendances et branches utiles du modèle de référence avec un coût numérique nettement inférieur.

<div class="figure-pair equal-figures">
  <figure class="technical-figure">
    <a href="{{ '/assets/images/parallel7_dispersion.png' | relative_url }}"><img src="{{ '/assets/images/parallel7_dispersion.png' | relative_url }}" alt="Courbes de dispersion du modèle de câble à 7 torons"></a>
    <figcaption>Courbes de dispersion utilisées pour comparer les formulations du câble à 7 torons.</figcaption>
  </figure>

  <figure class="technical-figure">
    <a href="{{ '/assets/images/twisted7_probe_dispersion.png' | relative_url }}"><img src="{{ '/assets/images/twisted7_probe_dispersion.png' | relative_url }}" alt="Dispersion du câble hélicoïdal à 7 torons"></a>
    <figcaption>Vérification de la dispersion sur la géométrie hélicoïdale du toron.</figcaption>
  </figure>
</div>

<figure class="figure-wide technical-figure single-figure">
  <a href="{{ '/assets/images/beam_spring_wfem_fe_relative_error.png' | relative_url }}"><img src="{{ '/assets/images/beam_spring_wfem_fe_relative_error.png' | relative_url }}" alt="Erreur relative entre modèles réduits et référence éléments finis"></a>
  <figcaption>Erreur relative entre les formulations beam-spring, WFEM et la référence éléments finis réduite.</figcaption>
</figure>


## 4. Gain en coût de calcul

La réduction permet de choisir le niveau de détail adapté au besoin : modèle de référence pour les vérifications détaillées, FE-WFEM-GBMS pour une réduction intermédiaire et beam-spring pour l’exploration rapide de la dispersion.

<figure class="figure-wide technical-figure single-figure">
  <a href="{{ '/assets/images/cable-time.png' | relative_url }}"><img src="{{ '/assets/images/cable-time.png' | relative_url }}" alt="Comparaison des temps de calcul des modèles du câble"></a>
  <figcaption>Temps de calcul pour un même balayage de dispersion : 0,6 s pour beam-spring SAFE, 6,3 s pour beam-spring WFEM et 2 022 s pour FE-WFEM-GBMS.</figcaption>
</figure>

<div class="metric-strip">
  <div><b>≈ 40 000</b><span>DDL du modèle EF initial</span></div>
  <div><b>676</b><span>DDL après FE-WFEM-GBMS</span></div>
  <div><b>42</b><span>DDL du modèle beam-spring</span></div>
  <div><b>0,6 s</b><span>beam-spring SAFE</span></div>
</div>

## 5. Résultat

La démarche établit une hiérarchie de modèles de complexité décroissante permettant de comparer rapidement les formulations et de sélectionner le niveau de détail adapté au besoin de calcul, sans utiliser systématiquement le modèle éléments finis le plus coûteux.
