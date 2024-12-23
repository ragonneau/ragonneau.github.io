+++
title = "Monotonicity and continuity"
date = "2024-01-26"
lastmod = "2024-10-20"
author = "Tom Ragonneau"
tags = ["Mathematics", "Topology", "Order"]
description = "We show that a function is monotone if and only if it is continuous for some topology."
+++

In this post, we show that a function between two preordered sets is monotone if and only if it is continuous for some topology.
This is a well-known result that we rediscovered during a discussion with Cunxin Huang, Haitian Li, and Zaikun Zhang at PolyU.

## Preliminaries

We first recall some definitions that will be useful in the sequel.

### Preordered sets and upper sets

Given a set $X$, recall that a preorder $\le_X$ is a relation on $X$ that is reflexive and transitive, i.e.,
1. for all $x \in X$, we have $x \le_X x$, and
2. Given $x, y, z \in X$, if $x \le_X y$ and $y \le_X z$, then $x \le_X z$.

Given a preordered set $(X, \le_X)$, we say that $U \subseteq X$ is an upper set if and only if
$$U = \bigcup_{u \in U} \\{ x \in X : u \le_X x \\}.$$
In other words, $U$ is an upper set if and only if for all $u \in U$ and $x \in X$, if $u \le_X x$, then $x \in U$.
A classical example of an upper set in $\mathbb{R}^n$ with the usual preorder is the nonnegative orthant $\mathbb{R}^n_+$.
Upper sets have the following useful property: the union and the intersection of upper sets are upper sets.

### Alexandrov topology

Given a set $X$, recall that a topology $\mathcal{T}$ on $X$ is a collection of subsets of $X$ satisfying
1. $\emptyset \in \mathcal{T}$ and $X \in \mathcal{T}$,
2. Arbitrary unions of elements of $\mathcal{T}$ are in $\mathcal{T}$, and
3. Finite intersections of elements of $\mathcal{T}$ are in $\mathcal{T}$.

Recall also that the elements of $\mathcal{T}$ are called open sets.
If infinite intersections of elements of $\mathcal{T}$ are also in $\mathcal{T}$, then $\mathcal{T}$ is referred to as an Alexandrov topology.
Given a preordered set $(X, \le_X)$, we can define an Alexandrov topology $\mathcal{T}_X$ on $X$ as the collection of all upper sets of $X$.
We will refer to $\mathcal{T}_X$ as the Alexandrov topology associated with $(X, \le_X)$.

## Main result

> **Theorem.**
> Let $(X, \le_X)$ and $(Y, \le_Y)$ be two preordered sets.
> A function $f \colon X \to Y$ is monotone if and only if $f$ is continuous for the Alexandrov topologies associated with $(X, \le_X)$ and $(Y, \le_Y)$.

The proof of this theorem is straightforward.
Let $\mathcal{T}_X$ and $\mathcal{T}_Y$ be the Alexandrov topologies associated with $(X, \le_X)$ and $(Y, \le_Y)$, respectively.
If $f$ is monotone, then for all $x \in X$ and $x' \in X$, if $x \le_X x'$, then $f ( x ) \le_Y f ( x' )$.
Therefore, for any open set $U \in \mathcal{T}_Y$, we have
$$f^{-1} ( U ) = \\{ x \in X : f ( x ) \in U \\} \in \mathcal{T}_X.$$
Indeed, given $x \in f^{-1} ( U )$ and $x' \in X$, if $x \le_X x'$, then $f ( x ) \le_Y f ( x' )$ and hence, $x' \in f^{-1} ( U )$.
Therefore, $f$ is continuous.

Conversely, if $f$ is continuous, then for all $U \in \mathcal{T}_Y$, we have $f^{-1} ( U ) \in \mathcal{T}_X$.
Let $x \in X$ and let $U_x$ be the open set of $Y$ defined by
$$U_x = \\{ y \in Y : f ( x ) \le_Y y \\}.$$
We then have $f^{-1} ( U_x ) = \\{ x' \in X : f ( x ) \le_Y f ( x' ) \\} \in \mathcal{T}_X$.
Hence, for all $x' \in X$ such that $x \le_X x'$, we have $f ( x ) \le_Y f ( x' )$.
Therefore, $f$ is monotone.

## What about univariate real-valued functions?

A natural question arises: what does this theorem say about univariate real-valued functions?
In other words, what does this mean when $X = Y = \mathbb{R}$ for the usual order in $\mathbb{R}$?
The definition of monotonous functions corresponds to the usual definition of increasing functions.
Moreover, the Alexandrov topology associated with $(\mathbb{R}, \le)$ is given by
$$\mathcal{T}_{\mathbb{R}} = \\{ [x, \infty) : x \in \mathbb{R} \\}.$$
The theorem states then than increasing functions in $\mathbb{R}$ are continuous for the above topology.
