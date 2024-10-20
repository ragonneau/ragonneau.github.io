+++
title = "An exercise that GPT-4 fails to solve"
date = "2023-06-17"
lastmod = "2024-10-20"
author = "Tom Ragonneau"
tags = ["Mathematics", "Algebra", "LLM"]
description = "We present an exercise proposed by Dr. Dongyi Wei that GPT-4 fails to solve."
+++

Dr. [Dongyi Wei](https://www.math.pku.edu.cn/jsdw/js_20180628175159671361/w_20180628175159671361/110443.htm) is an assistant professor at the [School of Mathematical Sciences](https://www.math.pku.edu.cn/en/) of [Peking University](https://english.pku.edu.cn/).
He recently proposed the below exercise that GPT-4 fails to solve.
I propose in this post two solutions, a direct one and another one based on functional analysis.

> **Exercise.**
> Let $\\{a_1, \dots, a_n\\} \subseteq (-1, 1)$ be given. Show that
> $$\prod_{1 \le i, j \le n} \frac{1 + a_i a_j}{1 - a_i a_j} \ge 1.$$

## Direct proof

Remark that we only need to prove that
$$\sum_{1 \le i, j \le n} \log ( 1 + a_i a_j ) - \log ( 1 - a_i a_j ) \ge 0.$$
Recall that for all $t \in (-1, 1)$, we have
$$\log(1 + t) = \sum_{k = 1}^{\infty} \frac{(-1)^{k + 1} t^k}{k}.$$
Therefore, we have
$$\begin{aligned}
\sum_{1 \le i, j \le n} \log ( 1 + a_i a_j ) - \log ( 1 - a_i a_j ) & = \sum_{1 \le i, j \le n} \sum_{k = 1}^{\infty} \frac{(-1)^{k + 1} a_i^k a_j^k}{k} + \frac{a_i^k a_j^k}{k}\\\\
    & = \sum_{1 \le i, j \le n} \sum_{k = 0}^{\infty} \frac{2 a_i^{2 k + 1} a_j^{2 k + 1}}{2 k + 1}\\\\
    & = \sum_{k = 0}^{\infty} \frac{2}{2 k + 1} \sum_{1 \le i, j \le n} a_i^{2 k + 1} a_j^{2 k + 1}\\\\
    & = \sum_{k = 0}^{\infty} \frac{2}{2 k + 1} \bigg( \sum_{i = 1}^n a_i^{2 k + 1} \bigg)^2 \ge 0.
\end{aligned}$$
The last equality is the key to the proof, although it is not obvious at first sight.

## Proof based on functional analysis

This proof has been proposed to me by Dr. [Zaikun Zhang](https://www.zhangzk.net).
It reformulates the above problem into a (more general) $2$-dimensional problem.
We first prove the following theorem.

> **Theorem.**
> Let $f$ be an integrable function on $\mathbb{R}$ with $\lVert f \rVert_{\infty} < 1$.
> Then
> $$\iint_{\mathbb{R}^2} \log \big( 1 + f ( x ) f ( y ) \big) \mathrm{d} x \mathrm{d} y \ge \iint_{\mathbb{R}^2} \log \big( 1 - f ( x ) f ( y ) \big) \mathrm{d} x \mathrm{d} y$$

*Proof.*
In a similar way as in the direct proof, since $\lVert f \rVert_{\infty} < 1$, for $( x, y ) \in \mathbb{R}^2$, we have
$$\log \big( 1 + f ( x ) f ( y ) \big) - \log \big( 1 - f ( x ) f ( y ) \big) = \sum_{k = 0}^{\infty} \frac{2 f^{2k + 1} ( x ) f^{2k + 1} ( y )}{2k + 1}.$$
Therefore, the integrability of $f$ and the fact that $\lVert f \rVert_{\infty} < 1$ provide
$$\begin{aligned}
    \iint_{\mathbb{R}^2} \big[ \log \big( 1 + f ( x ) f ( y ) \big) - \log \big( 1 - f ( x ) f ( y ) \big) \big] \mathrm{d} x \mathrm{d} y  & = \sum_{k = 0}^{\infty} \frac{2}{2k + 1} \iint_{\mathbb{R}^2} f^{2k + 1} ( x ) f^{2k + 1} ( y ) \mathrm{d} x \mathrm{d} y\\\\
    & = \sum_{k = 0}^{\infty} \frac{2}{2k + 1} \bigg( \int_{\mathbb{R}} f^{2k + 1} ( x ) \mathrm{d} x \bigg)^2 \ge 0,
\end{aligned}$$
which concludes the proof.

The solution to the original problem is a straightforward consequence of the above theorem, with
$$f(x) =
\begin{cases}
    a_1 & \text{if $0 \le x < 1$,}\\\\
    \vdots\\\\
    a_n & \text{if $n - 1 \le x < n$,}\\\\
    0   & \text{otherwise.}
\end{cases}$$
