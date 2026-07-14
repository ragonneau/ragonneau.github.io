+++
date = "2026-07-14"
draft = false
title = "COBYQA"
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
  "SciPy",
]
+++

**COBYQA** (Constrained Optimisation BY Quadratic Approximations) est un solveur d'optimisation sans dérivée, open-source et de haute performance, conçu pour résoudre des problèmes d'optimisation non linéaire de la forme :

$$\min_{x \in \mathcal{X}} \quad f(x) \quad \text{s.t.} \quad
\begin{cases}
    b_l \le A x \le b_u, \\\\
    c_l \le c(x) \le c_u,
\end{cases}$$

où $\mathcal{X} = \left\\{ x \in \mathbb{R}^n : l \le x \le u \right\\}$. Il a été développé pour succéder à l'algorithme classique `COBYLA`, offrant des fonctionnalités avancées pour traiter les tâches d'optimisation non contraintes, contraintes par des bornes, linéairement contraintes et non-linéairement contraintes en utilisant uniquement les valeurs des fonctions objectif et des contraintes, évitant ainsi complètement le recours aux informations de dérivées.

---

## Fonctionnalités clés

* **Méthode SQP à région de confiance sans dérivée :** Utilise un framework de programmation quadratique successive (SQP) basé sur des modèles quadratiques issus d'interpolations sous-déterminées.
* **Respect strict des bornes :** Respecte systématiquement les contraintes de bornes tout au long du processus d'optimisation, ce qui le rend idéal pour les simulations d'ingénierie où les fonctions sont physiquement indéfinies en dehors des limites cibles.
* **Gestion complète des contraintes :** Gère de manière totalement transparente les contraintes d'égalité et d'inégalité générales, linéaires et non linéaires.

## Intégration dans l'écosystème

COBYQA est un package natif du paysage moderne du calcul scientifique. Il est directement intégré au cœur de la bibliothèque [SciPy](https://docs.scipy.org/doc/scipy/reference/optimize.minimize-cobyqa.html) au sein du module `scipy.optimize`, mettant ainsi l'optimisation mathématique de pointe à la portée de millions de data scientists et d'ingénieurs à travers le monde.

---

## Liens

* [Documentation officielle](https://www.cobyqa.com/)
* [Dépôt officiel](https://github.com/cobyqa/cobyqa)
* [Documentation de l'intégration dans SciPy](https://docs.scipy.org/doc/scipy/reference/optimize.minimize-cobyqa.html)
