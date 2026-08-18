# Multiplicative-Order Parametrized Digraphs

Computational verification code and manuscript source for the article
*Multiplicative-Order Parametrized Digraphs*.

**Authors:** William Kau&atilde; Soares da Silva (Federal Rural University of Pernambuco) and Maigan Stefanne Da Silva Alc\^{a}ntara (Federal Rural University of Pernambuco)

## Overview

For a set $\mathcal{P} = \{p_1, \dots, p_n\}$ of distinct odd primes and a
positive integer $m$, the digraph $\Xi_m(\mathcal{P})$ has vertex set
$\mathcal{P}$ and an edge from $p_i$ to $p_j$ exactly when
$p_i^{m} \equiv 1 \pmod{p_j}$. Writing $r_{ij} = \operatorname{ord}_{p_j}(p_i)$,
an edge is present exactly when $r_{ij} \mid m$, so the family
$\Xi(\mathcal{P})$ swept out by $m$ is finite and is governed entirely by the
multiset of the $n(n-1)$ multiplicative orders.

The article studies three nested classes of prime sets defined by conditions on
these orders:

- **Realizing sets** ($\mathcal{R}_n$): every one of the $2^{n(n-1)}$ digraphs
  on $\mathcal{P}$ is realized by some exponent. Characterized by
  lcm-independence of the orders; infinitely many exist for every $n$
  (proved unconditionally via Kummer theory and the Chebotarev density theorem).
- **Pairwise coprime sets** ($\mathcal{R}_n^{\mathrm{c}}$): the orders are
  pairwise coprime. Characterized as the exact condition under which the
  realization densities form a product measure (edges become independent
  events).
- **Aligned sets** ($\mathcal{R}_n^{\mathrm{a}}$): the orders are prime and
  pairwise distinct. Characterized as the exact condition under which the map
  from divisors of the fundamental exponent to digraphs is a Boolean algebra
  isomorphism.

Aligned sets exist for $n = 2$ (e.g. $\{3, 11\}$); none of cardinality
$n \geq 3$ is known. The article proves unconditional constraints on such sets
(a divisibility constraint on each column, and a cyclotomic confinement theorem
reducing the search space to the prime divisors of explicit integers) and
conjectures that no aligned set of cardinality $n \geq 4$ exists. The case
$n = 3$ is left open.

## Repository contents

- `manuscript/` &mdash; LaTeX source of the article.
- `Multiplicative_Order_Parametrized_Digraphs.ipynb` &mdash; Python scripts (sympy/numpy) implementing the computational
  searches reported in the article:
  - exhaustive triangle search over all odd primes below $3 \times 10^{5}$
    for aligned triples;
  - cyclotomic-confinement search: for each prime $p < 100$ and each prime
    $r \leq 23$, complete factorization of $\Phi_r(p)$ and inspection of all
    resulting candidate pairs, with no upper bound on the candidates;
  - independent recomputation routines used to cross-check every reported
    order.
- `data/` &mdash; near_misses_.csv.

## Reproducibility

Every computational claim in the article is intended to be independently
reproducible from this repository. Each search script records its parameters,
its input range, and a run log; duplicate detection and canonical ordering of
keys guarantee that reported counts are stable across re-runs. Orders reported
by any search are recomputed by an independent routine before being cited in
the manuscript.

Requirements: Python 3.10+, `sympy 1.14.0`, `numpy 2.0.2`.


## License

- Manuscript: &copy; The author.
- Code: MIT License (see `LICENSE`).

