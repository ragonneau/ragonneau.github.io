+++
date = "2026-07-13"
draft = false
title = "COBYQA"
katex = true
type = "posts"
authors = ["Tom Ragonneau"]
categories = [
  "Projects",
  "Open Source",
]
tags = [
  "Applied Mathematics",
  "Optimisation",
  "Python",
  "SciPy",
]
+++

**COBYQA** (Constrained Optimisation BY Quadratic Approximations) is an open-source, high-performance derivative-free optimisation solver designed to solve general nonlinear optimisation problems of the form

$$\min_{x \in \mathcal{X}} \quad f(x) \quad \text{s.t.} \quad
\begin{cases}
    b_l \le A x \le b_u, \\\\
    c_l \le c(x) \le c_u,
\end{cases}$$

where $\mathcal{X} = \left\\{ x \in \mathbb{R}^n : l \le x \le u \right\\}$. It was developed to supersede the classical `COBYLA` algorithm, offering advanced capabilities for handling unconstrained, bound-constrained, linearly constrained, and nonlinearly constrained optimisation tasks using only objective and constraint function values, completely bypassing the need for derivative information.

---

## Key Features

* **Derivative-Free Trust-Region SQP Method:** Utilises a sequential quadratic programming (SQP) framework built on quadratic models from underdetermined interpolation.
* **Strict Bound Enforcement:** Always respects bound constraints throughout the entire optimisation process, making it ideal for engineering simulations where functions are physically undefined outside target boundaries.
* **Comprehensive Constraint Support:** Fully handles general linear and nonlinear equality and inequality constraints seamlessly.

## Ecosystem Integration

COBYQA is a native package in the modern scientific computing landscape. It is integrated directly into the core [SciPy](https://docs.scipy.org/doc/scipy/reference/optimize.minimize-cobyqa.html) library as part of the `scipy.optimize` module, putting advanced mathematical optimisation directly into the hands of millions of data scientists and engineers worldwide.

---

## Links

* [Official Documentation](https://www.cobyqa.com/)
* [Official Repository](https://github.com/cobyqa/cobyqa)
* [SciPy Integration Documentation](https://docs.scipy.org/doc/scipy/reference/optimize.minimize-cobyqa.html)
