---
title: "[Math] Partitions of Unity"
date: 2022-10-06
math: true
tags: ["math"]
---

## Theorem

Suppose $K$ is a compact set of $\mathbb{R}^n$, and $\\{V_\alpha\\}$ is an open cover of $K$. Then there exists functions $\psi_1, ..., \psi_s \in C(\mathbb{R}^n)$, such that

* $0 \leq \psi_i \leq 1$;
* each $\psi_i$ has its support in some $V_\alpha$; (subordinate)
* $\psi_1 + ... + \psi_s = 1$ on $K$. (partition of unity)

## Proof

Associate with each $x \in K$ an index $\alpha(x)$ such that $x \in V_{\alpha(x)}$. Then there are open balls $B(x)$ and $W(x)$ centered at $x$ with

$$\overline{B(x)} \subset W(x) \subset \overline{W(x)} \subset V_{\alpha(x)}$$

Since $K$ is compact, there are $x_1, ..., x_s$ such that

$$K \subset B(x_1) \cup ... \cup B(x_s)$$

There are functions $\varphi_1, ..., \varphi_s \in C(R^n)$, such that $\varphi_i = 1$ on $B(x_i)$, $\varphi_i = 0$ outside $W(x_i)$ and $0 \leq \varphi_i \leq 1$ on $\mathbb{R}^n$. Define $\psi_1 = \varphi_1$ and

$$\psi_{i+1} = (1 - \varphi_1)...(1 - \varphi_i)\varphi_{i+1}$$

for $i = 1, ..., s - 1$. It follows that

$$ \psi_1 + ... + \psi_s = 1 - \prod_{i=1}^s (1 - \varphi_i) \quad \text{ on } \mathbb{R}^n$$

