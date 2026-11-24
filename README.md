# A nonrational four-polytope with fifteen vertices

This project contains the full Lean4 formalisation of my paper *A nonrational four-polytope with fifteen vertices*. I've included the paper as [paper.pdf](paper.pdf).

## Verification

If you have Elan and Git installed, run these commands from this directory.

```sh
lake exe cache get
lake build
```

## Main results

Here's a guide to the main results and their Lean4 declarations. The declarations in the table use the namespace `Papers.Nonrational.Fifteen`.

| Paper result | Lean declaration | Conclusion |
| --- | --- | --- |
| Theorem 1 | [`theoremOne`](Fifteen.lean#L64) | There is a convex four-polytope with fifteen vertices whose combinatorial type is realisable over a real subfield $K$ if and only if $\sqrt{5}\in K$. |
| Proposition 2 | [`propositionTwo`](Fifteen/Projection.lean#L86) | The fifteen specified vertices give the seven polygonal faces, five coordinate facets and projection edge used in the construction. |
| Nonrationality | [`not_rationallyRealizable`](Fifteen.lean#L73) | The face lattice of this particular polytope has no rational realisation. |
