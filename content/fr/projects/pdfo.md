+++
date = "2026-07-14"
draft = false
title = "PDFO"
katex = true
type = "posts"
authors = ["Tom Ragonneau"]
categories = [
  "Projets",
  "Open Source",
]
tags = [
  "Mathématiques Appliquées",
  "Optimisation",
  "Python",
  "MATLAB",
  "Fortran",
]
+++

**PDFO** (Powell's Derivative-Free Optimisation solvers) est une interface open-source et de haute performance qui encapsule les légendaires solveurs d'optimisation sans dérivée développés par le professeur M. J. D. Powell. Plutôt qu'une réimplémentation, PDFO sert de wrapper multiplateforme autour des backends Fortran originaux hautement optimisés, les rendant nativement accessibles aux environnements de calcul modernes.

PDFO vise à résoudre des problèmes d'optimisation non linéaire générale de la forme :

$$\min_{x \in \mathcal{X}} \quad f (x)$$

où les contraintes définissant l'ensemble admissible $\mathcal{X} \subseteq \mathbb{R}^n$ dépendent entièrement du solveur de Powell sous-jacent sélectionné pour exécuter la tâche :

* **UOBYQA et NEWUOA :** Problèmes non contraints.
* **BOBYQA :** Problèmes contraints par des bornes ($l \le x \le u$).
* **LINCOA :** Problèmes linéairement contraints ($b_l \le A x \le b_u$).
* **COBYLA :** Problèmes non-linéairement contraints ($c_l \le c(x) \le c_u$).

---

## Fonctionnalités clés

* **Efficacité native du Fortran :** Tire parti des bases de code originales en Fortran 77, mathématiquement rigoureuses, pour une vitesse d'exécution algorithmique et une fiabilité numérique maximales.
* **Support multilingue :** Entièrement disponible sous forme de package facile à utiliser pour les utilisateurs de **Python** et de **MATLAB**.
* **Sélection automatique du solveur :** Détecte automatiquement la structure des contraintes de votre problème et l'oriente vers le solveur de Powell sous-jacent le plus efficace, sans nécessiter de configuration manuelle.

---

## Liens officiels

* [Documentation officielle](https://www.pdfo.net/)
* [Dépôt officiel](https://github.com/pdfo/pdfo)
