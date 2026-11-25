# Screen of surfaces and threefolds with a 10-second budget

The screen tested 1,325 surfaces and 1,909 threefolds to bring the catalogue to 2,000 of each. 2,193 produced complete Zoo records within 10 seconds: 952 surfaces and 1,241 threefolds. 1,590 of them joined the catalogue (565 surfaces, 1,025 threefolds), which now has 2,000 of each. 577 more were certified but not needed, and 26 have records larger than 1 MB. 1,041 reached the 10-second budget (373 surfaces, 668 threefolds). None ended with a solver diagnostic. [Timeouts](surface-threefold-timeouts.md) · [Per-case data](surface-threefold-screen.json)

## Selection and conditions

The new equations come from 20 families in three variables (surfaces) and four variables (threefolds), the families of the fourfold and fivefold screen with tables of their own where the number of variables matters. The screen also reran the 1,009 germs of the earlier surface and threefold screens that had no record (family R): 341 of them now finish within 10 seconds. Before any resolution, Atlas checked that each polynomial is reduced (`squarefree-factor`), involves every variable and is singular at the origin, and computed the dimension of its singular locus there (`local-dimension`). Equations that agree with a catalogue entry or with another candidate after permuting coordinates and changing signs were removed. The records added to the catalogue are spread evenly over the families, up to 2,000 entries per dimension, and none is larger than 1 MB.

One worker per equation runs the Zoo record builder: local dimension, embedded resolution with both zetas and the pole check, intrinsic resolution, an exhaustive pole-check replay when the quick check is unresolved, then the Milnor and Tjurina numbers. Each resolution is a quick search with a 10-second budget, and the 10-second wall clock covers the whole record. Six equations ran at once on an Intel Core i7-1355U (10 cores, 12 threads). A certified case has complete geometry in both modes, both zetas and a verified pole check. The screen ran once, at Atlas revision [`787d5c1`](https://github.com/pportilla/atlas/commit/787d5c11cb0874e38c6494e4975dc4afe00d777d).

## Results by family

### Surfaces

| Family | Equations | Certified | Added | Reserve | Over 1 MB | Timeouts |
| --- | ---: | ---: | ---: | ---: | ---: | ---: |
| I01: Brieskorn–Pham germs | 82 | 82 | 44 | 38 | 0 | 0 |
| I02: Invertible polynomials: sums of chain, loop and Fermat blocks | 67 | 62 | 44 | 18 | 0 | 5 |
| I03: Curve and surface germs, stabilised by squares or suspended by a power | 55 | 52 | 44 | 8 | 0 | 3 |
| I04: Joins of curve and surface germs in separate variables | 57 | 55 | 43 | 12 | 0 | 2 |
| I05: Cusps: a sum of powers plus the product of all variables | 55 | 55 | 43 | 12 | 0 | 0 |
| I06: Convenient Newton polyhedra with mixed monomials under the diagonal | 140 | 139 | 43 | 96 | 0 | 1 |
| I07: Cones over hypersurfaces of degree 3 to 5 | 56 | 56 | 43 | 13 | 0 | 0 |
| I08: Superisolated germs over hypersurfaces with isolated singular points | 13 | 13 | 13 | 0 | 0 | 0 |
| I09: Hidden coordinates: a known germ after a linear or triangular change of coordinates | 48 | 46 | 43 | 3 | 0 | 2 |
| N01: A monomial in k variables plus powers of the others | 10 | 10 | 10 | 0 | 0 | 0 |
| N03: Non-isolated chains and loops | 83 | 79 | 43 | 36 | 0 | 4 |
| N04: Partial cusps: a product of distinct variables plus powers of some variables | 9 | 9 | 9 | 0 | 0 | 0 |
| N05: Transverse compositions h^j + powers along a singular hypersurface of a coordinate subspace | 8 | 2 | 2 | 0 | 0 | 6 |
| N06: Cones over singular curves and surfaces with a prescribed double or triple point | 9 | 8 | 8 | 0 | 0 | 1 |
| N08: Products of germs in separate variables | 3 | 1 | 1 | 0 | 0 | 2 |
| N09: Line singularities, alone or joined with a power | 3 | 3 | 3 | 0 | 0 | 0 |
| N11: Newton polyhedra with a B1 facet | 52 | 49 | 43 | 6 | 0 | 3 |
| N13: Random Newton polyhedra, singular along a coordinate subspace | 73 | 50 | 43 | 7 | 0 | 23 |
| R: Germs of earlier screens that had no record | 502 | 181 | 43 | 138 | 0 | 321 |

### Threefolds

| Family | Equations | Certified | Added | Reserve | Over 1 MB | Timeouts |
| --- | ---: | ---: | ---: | ---: | ---: | ---: |
| I01: Brieskorn–Pham germs | 58 | 58 | 58 | 0 | 0 | 0 |
| I02: Invertible polynomials: sums of chain, loop and Fermat blocks | 115 | 114 | 85 | 26 | 3 | 1 |
| I03: Curve and surface germs, stabilised by squares or suspended by a power | 58 | 53 | 53 | 0 | 0 | 5 |
| I04: Joins of curve and surface germs in separate variables | 129 | 116 | 85 | 27 | 4 | 13 |
| I05: Cusps: a sum of powers plus the product of all variables | 53 | 48 | 32 | 0 | 16 | 5 |
| I06: Convenient Newton polyhedra with mixed monomials under the diagonal | 153 | 140 | 85 | 55 | 0 | 13 |
| I07: Cones over hypersurfaces of degree 3 to 5 | 50 | 40 | 40 | 0 | 0 | 10 |
| I08: Superisolated germs over hypersurfaces with isolated singular points | 12 | 10 | 10 | 0 | 0 | 2 |
| I09: Hidden coordinates: a known germ after a linear or triangular change of coordinates | 48 | 42 | 42 | 0 | 0 | 6 |
| N01: A monomial in k variables plus powers of the others | 90 | 90 | 84 | 6 | 0 | 0 |
| N02: Sums of monomials in disjoint groups of variables | 55 | 54 | 54 | 0 | 0 | 1 |
| N03: Non-isolated chains and loops | 88 | 64 | 64 | 0 | 0 | 24 |
| N04: Partial cusps: a product of distinct variables plus powers of some variables | 21 | 20 | 17 | 0 | 3 | 1 |
| N05: Transverse compositions h^j + powers along a singular hypersurface of a coordinate subspace | 48 | 8 | 8 | 0 | 0 | 40 |
| N06: Cones over singular curves and surfaces with a prescribed double or triple point | 20 | 16 | 16 | 0 | 0 | 4 |
| N08: Products of germs in separate variables | 31 | 4 | 4 | 0 | 0 | 27 |
| N09: Line singularities, alone or joined with a power | 23 | 23 | 23 | 0 | 0 | 0 |
| N10: Suspensions of catalogue surfaces | 142 | 81 | 81 | 0 | 0 | 61 |
| N11: Newton polyhedra with a B1 facet | 96 | 84 | 84 | 0 | 0 | 12 |
| N13: Random Newton polyhedra, singular along a coordinate subspace | 112 | 16 | 16 | 0 | 0 | 96 |
| R: Germs of earlier screens that had no record | 507 | 160 | 84 | 76 | 0 | 347 |

## Results by dimension of the singular locus

| Dimension | Singular locus | Equations | Certified | Timeouts |
| --- | ---: | ---: | ---: | ---: |
| Surfaces | 0 | 567 | 554 | 13 |
| Surfaces | 1 | 758 | 398 | 360 |
| Threefolds | 0 | 708 | 639 | 69 |
| Threefolds | 1 | 623 | 408 | 215 |
| Threefolds | 2 | 578 | 194 | 384 |
