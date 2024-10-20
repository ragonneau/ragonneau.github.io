+++
title = "Kantorovich inequality"
date = "2023-06-13"
lastmod = "2024-10-20"
author = "Tom Ragonneau"
tags = ["Mathematics", "Optimization", "Probability"]
description = "We provide two proofs of the Kantorovich inequality based on probability and optimization theories."
+++

In this post, we propose two proofs of the Kantorovich inequality, one based on probability theory and the other one based on optimization theory.

Let $A \in \mathbb{R}^{n \times n}$ be a given symmetric positive definite matrix and denote its eigenvalues $\lambda_1 \le \lambda_2 \le \dots \le \lambda_n$.
The Kantorovich inequality states that for all vector $x \in \mathbb{R}^n$ of unit norm, we have
$$ \langle x, A x \rangle \langle x, A^{-1} x \rangle \le \frac{(\lambda_1 + \lambda_n)^2}{4 \lambda_1 \lambda_n}.$$
Such an inequality is widely used in convergence analysis (e.g., the convergence rate of the [steepest descent method](https://en.wikipedia.org/wiki/Gradient_descent) can be derived from the Kantorovich inequality).

## Proof based on probability theory

We first state three lemmas on which we will base our proof.

> **Lemma 1.**
> Let $X$ and $Y$ be two jointly distributed real-valued random variables with finite second-order moments.
> Then
> $$\mathbb{E}[X] \mathbb{E}[Y] \le \mathbb{E}[XY] + \sqrt{\operatorname{Var}[X] \operatorname{Var}[Y]}.$$

*Proof.*
This is a direct consequence of the Cauchy-Schwarz inequality applied to $\operatorname{Var}[X] \operatorname{Var}[Y]$.

> **Lemma 2.** (Popoviciu’s inequality)
> Let $X$ be a real-valued random variable taking values in $[\alpha, \beta]$, with $\alpha \le \beta$.
> Then
> $$\operatorname{Var}[X] \le \frac{(\beta - \alpha)^2}{4}.$$

*Proof.*
Let $\varphi$ be the univariate function defined by $\varphi(t) = \mathbb{E}[(X - t)^2]$.
It easily reaches its minimum at $t = \mathbb{E}[X]$, so that
$$\operatorname{Var}[X] = \varphi(\mathbb{E}[X]) \le \varphi \bigg(\frac{\alpha + \beta}{2}\bigg) = \frac{\mathbb{E}[(2X - \alpha - \beta)^2]}{4}.$$
Remarking that $X - \alpha \ge 0$ and $X - \beta \le 0$, we thus obtain the desired result.

> **Lemma 3.**
> Let $X$ be a real-valued random variable taking values in $[\alpha, \beta]$, with $0 < \alpha \le \beta$.
> Then
> $$\mathbb{E}[X] \mathbb{E}[X^{-1}] \le \frac{(\alpha + \beta)^2}{4 \alpha \beta}.$$

*Proof.*
Lemmas 1 and 2 together provide
$$\mathbb{E}[X] \mathbb{E}[X^{-1}] \le \mathbb{E}[XX^{-1}] + \sqrt{\operatorname{Var}[X] \operatorname{Var}[X^{-1}]} \le 1 + \sqrt{\frac{(\beta - \alpha)^2 (\alpha^{-1} - \beta^{-1})^2}{16}} = \frac{(\alpha + \beta)^2}{4 \alpha \beta}.$$

We are now ready to prove the Kantorovich inequality.
We let $x \in \mathbb{R}^n$ be any vector of unit norm.
Since $A$ is symmetric positive definite, it admits an eigendecomposition $A = Q \Lambda Q^{\mathsf{T}}$ with $Q \in \mathbb{R}^{n \times n}$ an orthogonal matrix and $\Lambda = \operatorname{diag} \\{ \lambda_1, \dots, \lambda_n \\}$.
We then have
$$\langle x, A x \rangle = \sum\_{i = 1}^n \lambda_i v_i^2 \quad \text{and} \quad \langle x, A^{-1} x \rangle = \sum\_{i = 1}^n \lambda_i^{-1} v_i^2,$$
where $v_i$ denotes the $i$th component of $Q^{\mathsf{T}} x$.
Let $X$ the any random variable that takes the value $\lambda_i$ with probability $v_i^2$ for $i \in \\{ 1, \dots, n \\}$.
Since $X$ takes its values in $[\lambda_1, \lambda_n]$, according to Lemma 3, we have
$$\langle x, A x \rangle \langle x, A^{-1} x \rangle = \mathbb{E}[X] \mathbb{E}[X^{-1}] \le \frac{(\lambda_1 + \lambda_n)^2}{4 \lambda_1 \lambda_n},$$
which concludes our proof of the Kantorovich inequality based on probability theory.

## Proof based on optimization theory

We let $x \in \mathbb{R}^n$ be any vector of unit norm and $\varphi$ be the univariate function defined on $(0, \infty)$ by $\varphi(t) = t \langle x, A x \rangle + t^{-1} \langle x, A^{-1} x \rangle$.
The minimum of $\varphi$ is reached at $t = \sqrt{\langle x, A^{-1} x \rangle \langle x, A x \rangle^{-1}}$, providing
$$\sqrt{\langle x, A x \rangle \langle x, A^{-1} x \rangle} \le \frac{1}{2} \langle x, (t A + t^{-1} A^{-1}) x \rangle.$$
According to the Courant-Fischer theorem, we have
$$\sqrt{\langle x, A x \rangle \langle x, A^{-1} x \rangle} \le \frac{1}{2} \max_{i = 1, 2, \dots, n} (t \lambda_i + t^{-1} \lambda_i^{-1}) = \frac{1}{2} \max \\{  t \lambda_1 + t^{-1} \lambda_1^{-1}, t \lambda_n + t^{-1} \lambda_n^{-1} \\}.$$
The evaluation of the above right-hand side at $t = 1 / \sqrt{\lambda_1 \lambda_n}$ provides
$$ \sqrt{\langle x, A x \rangle \langle x, A^{-1} x \rangle} \le \frac{\lambda_1 + \lambda_n}{2 \sqrt{\lambda_1 \lambda_n}},$$
which concludes our proof of the Kantorovich inequality based on optimization theory.
