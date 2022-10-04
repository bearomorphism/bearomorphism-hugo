---
title: "[Math] Q8 is not Isomorphic to any subgroup of S7"
date: 2022-10-04T11:05:53+08:00
math: true
tags: ["math", "abstract algebra"]
---

## Problem

The Quaternion group $G = Q_8$ is not isomorphic to any subgroup of $S_7$.

## Proof

Let $A$ be a set with 7 elements. Any homomorphism $\alpha: G \to S_7$ can be viewed as a group action $G$ on $A$.

For each $a \in A$, consider the size of its orbit $Ga$ and stabilizer $G_a$. Orbit-stabilizer theorem gives the following equality:

$$ |Ga| = \frac{|G|}{|G_a|} $$

Since $Ga \subseteq A$, we have $|G_a| \leq 7$. Then

$$ 7 \geq |Ga| = \frac{8}{|G_a|} $$

Simplify the inequality,

$$ |G_a| \geq \frac{8}{7} $$

Hence $|G_a|$ is at least 2. Now, consider the kernel of the homomorphism $\alpha$. By definition, we have $\ker \alpha = \bigcap_{a \in A} G_a$. Notice that all non-trivial subgroup of $G$ contains $\\{\pm 1\\}$, so $\\{\pm 1\\} \subseteq \ker \alpha$.

Since $\ker \alpha$ is non-trivial, the homomorphism cannot be injective. Therefore, $\alpha$ is not an isomorphism to any subgroup of $S_7$.
