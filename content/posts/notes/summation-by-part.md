---
title: "Summation by Part"
date: 2022-10-05T13:33:15+08:00
math: true
tags: ["math"]
---

## Theorem

Give 2 sequences $\\{a_n\\}$ and $\\{b_n\\}$, put

$$ A_n = \sum_{k=0}^n a_n$$

if $n \geq 0$; put $A_{-1} = 0$. Then, if $0 \leq p \leq q$, we have

$$\sum_{n=p}^q a_n b_n = \sum_{n=p}^{q-1} A_n(b_n - b_{n+1}) + A_qb_q - A_{p-1}b_p$$

## Proof

$$ \sum_{n=p}^q a_n b_n = \sum_{n=p}^q (A_n - A_{n-1}) b_n = \sum_{n=p}^q A_nb_n - \sum_{n=p-1}^{q-1}A_nb_{n+1}$$

Simplify the last expression.

## Note

每次我要用這東西的時候都會忘記，就這樣記下來。
