---
title: "Quantum Algorithm"
date: 2022-10-08T12:41:57+08:00
math: true
tags: ["math"]
---

## Probability of collapsing

$a |0 \rangle + b |1 \rangle$ 變成 0 的機率是 $|a|^2$ 變成 $1$ 的機率是 $|b|^2$

* Unitary operator 保長保角
* $M_{\text{NOT}} = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$
* $W_2 = \begin{pmatrix} \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} & \frac{-1}{\sqrt{2}} \end{pmatrix}$ fair coin toss

## Tensor product

* Entangled state v.s. decomposable state
* $\langle a \otimes b, c \otimes d \rangle = \langle a, c \rangle \langle b, d \rangle$
* $$\begin{align*}M_{\text{CNOT}}: &|00\rangle \mapsto |00\rangle, |01\rangle \mapsto |01\rangle, \\&|10\rangle \mapsto |11\rangle, |11\rangle \mapsto |10\rangle \end{align*}$$

## EPR Pair

$$M_{\text{CNOT}}\left((\frac{1}{\sqrt{2}} | 0 \rangle +\frac{1} {\sqrt{2}} |1\rangle) \otimes |0\rangle\right) = \frac{1}{\sqrt{2}} |00 \rangle +\frac{1} {\sqrt{2}} |11\rangle$$

## Shor's algorithm

Problem: Factor a number $n$. That is, find a pair $(p, q)$ such that $pq = n$.

### Step 1

Choose a random number $a \in \\{2,3,4,...,n - 1\\}$.
If $\gcd(a, n) = 1$ then move to next step. Otherwise, done.

### Step 2

From now the operations are under the ring $\mathbb{Z} / n\mathbb{Z}$.

Since $\gcd(a, n) = 1$, there is a positive even integer $r$ such that

$$\begin{align}a^r = 1 \\ a^{r/2} \neq 1 \end{align}$$

Denote $b = a^{r / 2} - 1$ and $c = a^{r/2} + 1$, then

$$bc = (a^{r / 2} - 1)(a^{r / 2} + 1) = a^r - 1 = 0$$

If $c \neq 0$, then the pair $(\gcd(b, n), \gcd(c, n))$ is the answer.

### Step 3

Since $pq \mid bc$, we have (i) $p \mid b$ and $q \mid c$ or (ii) $p \mid c$ and $q \mid b$. Thus, $(p, q) = (\gcd(b, n), \gcd(c, n))$.

## Find the $r$ in step 2 of Shor's

