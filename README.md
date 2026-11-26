# A nonrational 4-polytope with fifteen vertices

[![Palomar preflight](https://github.com/caiusdfolkerts/palomar-submissions/actions/workflows/fifteen-vertex.yml/badge.svg?branch=main)](https://github.com/caiusdfolkerts/palomar-submissions/actions/runs/45414389435)

## Abstract

We construct a convex 4-polytope with fifteen vertices and no rational realisation. This improves Richter-Gebert’s upper bound of thirty-three vertices. The smallest field over which our polytope can be realised is $\mathbb{Q}(\sqrt{5})$.

## Formalisation

| Result in the current manuscript | Lean declaration |
| --- | --- |
| Theorem 1.1. Existence and characterisation of the realisation fields | [theoremOne](Fifteen.lean#L64) |
| Proposition 3.1. The explicit construction, its faces and the projected rays | [propositionTwo](Fifteen/Projection.lean#L86), [projected_rays](Fifteen/PaperCoordinates.lean#L48) |
| The explicit polytope has no rational realisation | [not_rationallyRealizable](Fifteen.lean#L73) |

The [included manuscript](paper.pdf) uses the earlier numbering Theorem 1 and Proposition 2.

## Building

With [elan](https://github.com/leanprover/elan) installed, run from the repository root.

```sh
lake exe cache get
lake build
```

## Verification

[Click here for the verification record](https://github.com/caiusdfolkerts/palomar-submissions/actions/runs/45414389435). Palomar checked that the [proof](Solution.lean#L21) matches the independently written [statement](Challenge.lean#L107) for the explicit fifteen-vertex construction and its realisation fields. The statement file uses a deliberate placeholder for that comparison.

The proofs use only Lean’s standard axioms `propext`, `Classical.choice`, and `Quot.sound`. After building, you can reproduce the axiom audit with the command below.

```sh
lake env lean --stdin <<'LEAN'
import Solution

#print axioms Papers.Nonrational.Fifteen.theoremOne
#print axioms Papers.Nonrational.Fifteen.propositionTwo
#print axioms Papers.Nonrational.Fifteen.projected_rays
#print axioms Papers.Nonrational.Fifteen.not_rationallyRealizable
#print axioms Papers.Nonrational.Fifteen.explicitFifteenVertexField
LEAN
```
