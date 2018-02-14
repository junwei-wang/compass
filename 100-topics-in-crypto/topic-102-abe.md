---
title: Attribute-Based Encryption
layout: cayman
topic_id: 102
category: crypto-topics
---

Introduced in SW05, GPSW06 (inspired by IBE, Fuzzy IBE, etc). They are only for (access policy) circuits with depth
$\NC^1$.

First ABE for general circuits (i.e., polynomial depth circuits):

- GVW13 (based on sub-exponential LWE)
- GGHSW13 (based on "mmaps")
- BGGHNSVV14 (based on sub-exp LWE, IND-selective security, can be leveraged to IND-adaptive security)

## Key-Policy Attributed-Based Encryption (KP-ABE)

A lively introduction to the notation given by
[Vinod Vaikuntanathan](https://scholar.google.com/citations?user=a8jIPIkAAAAJ) available at
[YouTube](https://youtu.be/O0NoW4UOd9Y) from the beginning to the 12th minutes.


## Ciphertext-Policy Attributed-Based Encryption (CP-ABE)


## References

- [EC14] Boneh, Gentry, Gorbunov, Halevi, Nikolaenko, Segev, Vaikuntanathan. **Fully Key-Homomorphic Encryption,
  Arithmetic Circuit ABE and Compact Garbled Circuits.**
  [ia.cr/2014/356](https://eprint.iacr.org/2014/356)
>
> We construct the first (key-policy) attribute-based encryption (ABE) system with short secret keys: the size
> of keys in our system depends only on the depth of the policy circuit, not its size. Our constructions extend
> naturally to arithmetic circuits with arbitrary fan-in gates thereby further reducing the circuit depth. Building on
> this ABE system we obtain the first reusable circuit garbling scheme that produces garbled circuits whose size is the
> same as the original circuit plus an additive $\poly(\lambda,d)$ bits, where $\lambda$ is the security parameter and
> $d$ is the circuit depth. Save the additive $\poly(\lambda,d)$ factor, this is the best one could hope for. All
> previous constructions incurred a multiplicative $\poly(\lambda)$ blowup. As another application, we obtain (single key
> secure) functional encryption with short secret keys.
>
> We construct our attribute-based system using a mechanism we call **fully key-homomorphic encryption** which is a
> public-key system that lets anyone translate a ciphertext encrypted under a public-key $x$ into a ciphertext encrypted
> under the public-key $(f(x),f)$ of the same plaintext, for any efficiently computable $f$. We show that this mechanism
> gives an ABE with short keys. Security is based on the subexponential hardness of the learning with errors problem.
>
> We also present a second (key-policy) ABE, using multilinear maps, with short ciphertexts: an encryption to an
> attribute vector $x$ is the size of $x$ plus $\poly(\lambda, d)$ additional bits. This gives a reusable circuit
> garbling scheme where the size of the garbled input is short, namely the same as that of the original input, plus a
> $\poly(\lambda, d)$ factor.
