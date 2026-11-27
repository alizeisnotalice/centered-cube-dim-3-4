# Weak-Type Bounds for the Centered Cubic Maximal Operator in Dimensions Three and Four

Three-dimensional paper: [English](cube-finite-dim-bounds/papers/n3/main-en.pdf) · [Chinese](cube-finite-dim-bounds/papers/n3/main.pdf) | Four-dimensional paper: [English](cube-finite-dim-bounds/papers/n4/main-en.pdf) · [Chinese](cube-finite-dim-bounds/papers/n4/main.pdf) · [Reproduction guide](REPRODUCE.md) · [Citation](#citation)

This repository contains two manuscripts on upper bounds and separate lower-bound certificates. Here $C_n$ is the optimal weak-type $(1,1)$ constant for the centered Hardy–Littlewood maximal operator over axis-parallel cubes in $\mathbb R^n$ with Lebesgue measure.

## Main results

| Dimension | Certified lower bound | Upper bound in the manuscript |
|---:|---:|---:|
| 3 | $C_3>1.7941091664563071$ | $C_3<7.916$ |
| 4 | $C_4>1.90174261110095$ | $C_4<14.371$ |

The upper bounds use Cauchy potentials associated with finitely many directions and an obstacle comparison. The lower bounds come from finite witnesses in periodic constructions. [Exact intervals and comparison constants](cube-finite-dim-bounds/results/released_bounds.json)

A separate covering argument for the same operator gives $C_4<13.6947031585$. The exact values of $C_3$ and $C_4$ remain open. [Covering estimates by dimension](https://github.com/alizeisnotalice/centered-cube-covering-upper-bounds/blob/c39475811fc51875df03c04f1042f34dac7d14d7/paper/dimension-table.md)

## Reproduction

The repository contains the scripts and inputs for checking both upper bounds and both lower bounds. The command below reproduces the algebraic lower-bound certificates using the Python standard library. The guide gives the full certificate checks and manuscript build commands. [Three-dimensional LaTeX source](cube-finite-dim-bounds/papers/n3/main.tex) · [Four-dimensional LaTeX source](cube-finite-dim-bounds/papers/n4/) · [Reproduction guide](REPRODUCE.md) · [Checksums](SHA256SUMS)

```sh
python3 cube-finite-dim-bounds/baseline/reproduce.py
```

## Citation

Both manuscripts are archived in [v1.0.0](https://github.com/alizeisnotalice/centered-cube-dim-3-4/releases/tag/v1.0.0). Use the [BibTeX entry](https://github.com/alizeisnotalice/centered-cube-dim-3-4/blob/v1.0.0/citation.bib) for the dimension you cite.
