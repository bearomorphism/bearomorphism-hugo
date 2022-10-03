---
title: "[Math] Uncountable summation diverges"
date: 2022-10-03T19:06:42+08:00
math: true
tags: ["math"]
---

## Problem

If $S$ is an uncountable collection of positive real numbers, then the summation of $S$ diverges.

## Proof

Suppose otherwise, the summation converges. For $n = 1, 2, ...$, denote $A_n = \{x \mid x \in S \text{ and } x \geq \frac{1}{n}\}$. Notice that $A_n$ is a subset of $S$, so its summation must converge. Since each element of $A_n$ has a lower bound $1/n > 0$, the cardinality of $A_n$ must be finite. Finally, observe that $S = \bigcup_{n=1}^\infty A_n$, then $S$ is at most countable, contradict to our assumption that $S$ is uncountable.
