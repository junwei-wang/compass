---
title: Lattice
category: crypto-topics
layout: cayman

---

* TOC
{:toc}

Organized from the a talk entitled The Mathematics of Lattices ([1](https://youtu.be/LlPXfy6bKIY) &
[2](https://youtu.be/SZkTJMorxnM)) given by [Vinod Vaikuntanathan]({{ site.data.people["Vinod Vaikuntanathan"].url }}).

## Definition

> A $n$-dimensional lattice is all **integer** linear combinations of $n$ basis vectors $b_1,b_2,\cdots,b_n$.

The same lattice can be generated through several basis. A "good" basis means the vectors $(b_i)_i$ are short, while the
vectors are long for the "bad" basis.

## Basic Hard Problems

Here, "short" means [Euclidean norm](https://en.wikipedia.org/wiki/Norm_(mathematics)#Euclidean_norm).

### Shortest Vector Problem (SVP)

> Given a basis (unbounded, i.e., could be good basis or bad basis), find the **shortest non-zero vector**.

Proven to be NP-hard!

#### $\alpha$-Approximate Shortest Vector Problem

> Given a basis, find $\alpha$-approximate shortest vector (a non-zero vector of length at most $\alpha \lambda_1$ where
> $\lambda_1$ is the length of the shortest vector).

- **LLL**: in polynomial time, we can find the at most length $2^{\frac{n}{2}}\lambda_1$ vector (i.e.,
  $2^\frac{n}{2}$-approximate SVP).
- Best known of $2^k$-approximation SVP is $2^{\widetilde{O}(n/k)}$. (even for quantum computers)

### Shortest Independent Vector Problem (SIVP)

> Let $\lambda_n = \min(r:$ there are $n$ linearly independent lattice vectors of length $\leq r.)$
> Given a basis, find $n$ vectors of length at most $\lambda_n$.

SVP and SIVP are two distinct interesting problems.


## Why Lattice in Crypto?

- Common-sense safety
- Quantum resistance (so far)
- Worst-case hardness (unique feature of lattice-based crypto)
- Simplicity and efficiency
- Tons of application (FHE, FE, Obfuscation, etc.)

For lattice problem, worst-case hardness = average-case hardness
**Worst-case hardness**: at least one instance hard (safest to assume)
**Average-case hardness**: average instance hard (preferred in crypto)

## From Hardness to Usefulness

- Short integer solutions (SIS)
  - One-way function [Ajtai96]
  - Collision-resistance hashing [Ajtai96,GGH96]
-  Learning with errors (LWE)
  - PRNG [Ajtai96,Regev05]
  - PKE [AD97,GGH97,HPS98,Regev05]
  - OT and secure MPC [PVW08]
- Lattice trapdoors
  - Trapdoor functions [Ajtai99,GPV08,MP12]
  - Digital signatures [GGH97,HPS98,GPV08,LyuMic08]
- Punctured trapdoors
  - IBE [GPV08,CHKP10,ABB10]
  - ABE [GVW13,BGGHNSVV14]
  - Predicate Encryption [GVW15]

### Other usage

- Cryptanalytic uses of lattice
- Ideal lattice, Ring-SIS and Ring-LWE

Primitives:
- PRF [BPR10,BLMR13]
- FHE [Gen09,BV11,GSW13]
- mmaps and Obfuscation (based on non-standard lattice problems) [GGH13,...]


## Short Integer Solutions ($\SIS_{q,n,m,\beta}$)

Given a matrix $A \in \ZZ_{q}^{n\times m}$, find a vector $r \in \ZZ^m$ s.t.
- $Ar = 0$ over $\ZZ_q^n$,
- $\norm{r}_2 \leq \beta$.

For example, given equations systems over $\ZZ_q$,
$$
\left[
\begin{array}[ccc]?
 5 & 2 & 3 \nonumber \\
 4 & 6 & 9 \nonumber
\end{array}
\right] \vec{r} = \left[
\begin{array}[c]?
0 \\
0
\end{array}
\right]
$$,
find a *short* $\vec{r} \in \ZZ^{m}$. Without "short", we can give any solution by Gaussian elimination.
