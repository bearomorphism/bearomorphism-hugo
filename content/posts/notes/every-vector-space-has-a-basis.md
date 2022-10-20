---
title: "Every Vector Space Has a Basis"
date: 2022-10-03T20:19:18+08:00
math: true
tags: ["math", "linear algebra"]
---

## Theorem

Every vector space $V$ has a basis.

## Proof

The case $V$ is zero space is trivial, so we just consider the case $V$ is not zero.

We will use "Zorn's lemma" in the following proof.

Let $P$ be the collection of all linearly independent subset of $V$. Note that $P$ is partially ordered with respect to "inclusion". Also note that $P$ is not empty, since it must contain $\\{v\\}$ for some $v \in V$.

Take a chain $C$ in $P$. Denote $U = \bigcup_{S \in C} S$, the union of all elements of the chain $C$.

Now we need to show that $U$ is indeed an upper bound of $C$ in $P$. It suffices to show that $U$ is linearly independent. For each finite subset $\\{v_1, ..., v_k\\}$ of $U$, we can find $S_1, ..., S_k \in C$ such that $v_i \in S_i$ for $i = 1, ..., k$. Since $C$ is a chain, there is some $j$ such that $S_1, ..., S_k \subseteq S_j$, which also implies $v_1, ..., v_k \in S_j$. Notice that $S_j$ is linearly independent, the equality

$$a_1v_1 + ... + a_kv_k = 0$$

holds only if all coefficients $a_i = 0$. Therefore, $U$ is linearly independent.

The hypothesis of Zorn's lemma has been checked. Hence, there is a maximal element in $P$. Let's pick a maximal element from $P$ and call it $M$. The next goal is showing that $M$ is a basis.

By definition, $M$ is a linearly independent subset of $V$. To show $M$ is a basis of $V$, it suffices to check that $M$ spans $V$.

Suppose otherwise, $M$ does not span $V$. Take some $w \in V \setminus \text{span}(M)$. Now $\\{w\\} \cup M$ is a linearly independent subset of $V$ and a superset of $M$, which contradicts to the fact that $M$ is maximal. Therefore, $M$ indeed spans $V$, and thus a basis of $V$.
