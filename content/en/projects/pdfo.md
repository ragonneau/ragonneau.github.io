+++
date = "2026-07-13"
draft = false
title = "PDFO"
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
  "MATLAB",
  "Fortran",
]
+++

**PDFO** (Powell's Derivative-Free Optimisation solvers) is an open-source, high-performance interface that wraps the legendary derivative-free optimisation solvers developed by Professor M. J. D. Powell. Rather than a reimplementation, PDFO serves as a cross-platform wrapper around the original, highly optimised Fortran backends, making them natively accessible to modern computing environments.

PDFO aims at solving general nonlinear optimisation problems of the form:

$$\min_{x \in \mathcal{X}} \quad f (x)$$

where the constraints defining the feasible set $\mathcal{X} \subseteq \mathbb{R}^n$ depend entirely on the underlying Powell solver selected to execute the task:

* **UOBYQA and NEWUOA:** Unconstrained problems.
* **BOBYQA:** Bound-constrained problems ($l \le x \le u$).
* **LINCOA:** Linearly constrained problems ($b_l \le A x \le b_u$).
* **COBYLA:** Nonlinearly constrained problems ($c_l \le c(x) \le c_u$).

---

## Key Features

* **Native Fortran Efficiency:** Leverages the original, mathematically rigorous Fortran 77 codebases for maximum algorithmic execution speed and numerical reliability.
* **Multi-Language Support:** Fully available as an easy-to-use package for both **Python** and **MATLAB** users.
* **Automated Solver Selection:** Automatically detects your problem's constraint structures and routes it to the most efficient underlying Powell solver without requiring manual configuration.

---

## Official Links

* [Official Documentation](https://www.pdfo.net/)
* [Official Repository](https://github.com/pdfo/pdfo)
