---
title: Proof Techniques
category: crypto-topics
layout: cayman

---

## Proof the Average-Case Hardness of A Problem

A problem is hard on average, if we can reduce some hard problem (preferably NP-complete) problem, into its average
case.
The idea is to give a reduction from worst-case hardness problem $A$ to average-case hardness problem $B$.

Suppose there exists a reduction from $A$ to the average case of $P$, given any instance of $A$, it can be solved,
using the **average case oracle** for $B$. Namely, the average case of $B$ is as hard as the worst case of $A$.

The **average case oracle** for a problem can solve any random instance sampling from its distribution with probability
$\geq \frac{1}{2}$.

Examples: [short integer solution problem](/100-topics-in-crypto/topic-lattice.html#short-integer-solutions-sis_qnmbeta)
