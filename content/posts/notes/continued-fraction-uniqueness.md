---
title: "Uniqueness of Continued Fraction Representation of Rational Numbers"
date: 2022-10-05T16:52:06+08:00
tags: ["math"]
math: true
---

## Property

The continued fraction representation of a rational is unique.

## Proof

Let $r \in \mathbb{Q}$ and $[p_0, p_1, ..., p_n], [q_0, q_1, ..., q_m]$ be continued fraction representations of $r$. Now, process induction on $\min(n, m)$. The case $\min(n, m) = 0$ is trivial.

By definition, we know that $p_0 = q_0 = \lfloor r \rfloor$. Then,

$$(r - \lfloor r \rfloor)^{-1} = [p_1, ..., p_n] = [q_1, ..., q_m]$$

the rest can be shown by induction hypothesis.
