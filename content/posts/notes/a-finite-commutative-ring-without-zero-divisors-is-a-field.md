---
title: "A Finite Commutative Ring Without Zero Divisors Is a Field"
date: 2022-10-08T12:54:34+08:00
tags: ["math"]
math: true
---

## Problem

A finite commutative ring $R$ without zero divisors is a field. Here we don't assume that $R$ has an identity.

## Proof

### $R$ has an identity

For each $a \neq 0$ in $R$, consider the map

$$\phi_a: x \mapsto ax$$

Since $a$ is not a zero divisor, $\phi_a$ is injective. Because $R$ is finite, $\phi_a$ is also surjective. Hence, there is $e \in R$ such that

$$a = \phi_a(e) = ea$$

Now, for each $b \in R$, again by the fact that $\phi_a$ is surjective, we can find $x_b \in R$ such that

$$b = \phi_a(x_b) = ax_b$$

Multiply the first equality by $x_b$, and we obtain

$$b = ax_b = eax_b = eb$$

Therefore, $e$ is an identity in $R$.

Then use the fact that $\phi_a$ is surjective again, there is $c \in R$ such that

$$e = \phi_a(c) = ac$$

Here $c$ is the inverse of $a$.

## Random Notes

### $\phi_a$ is injective

Let $x, y \in R$ be such that $\phi_a(x) = \phi_a(y)$, then $a(x - y) = 0$. Since $a$ is not a zero divisor, it follows that $x = y$.

