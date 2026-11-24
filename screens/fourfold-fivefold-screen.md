# Screen of fourfolds and fivefolds

The screen tested 1,000 fourfolds and 1,000 fivefolds. 1,372 produced complete Zoo records: 761 fourfolds and 611 fivefolds. 1,083 of them joined the catalogue (634 fourfolds, 449 fivefolds). The other 289 have records larger than 1 MB and [are not published yet](#certified-records-not-yet-published). 628 (239 fourfolds, 389 fivefolds) reached the 50-second budget. None ended with a solver diagnostic or an unresolved pole check. [Open germs with reasons](fourfold-fivefold-open.md) · [Per-case data](fourfold-fivefold-screen.json)

## Selection and conditions

The equations come from 21 families in five variables (fourfolds) and in six variables (fivefolds). Nine families are isolated singularities and twelve are non-isolated, with singular loci of every dimension from 1 to the largest possible. Several families are chosen because candidate poles of the topological zeta function are expected to cancel: Newton polyhedra with a B1 facet, products and joins in separate variables, decomposable arrangements, and germs in hidden coordinates. Atlas expanded every substituted or determinantal polynomial and computed the two binary-form discriminants as resultants. Before any resolution, Atlas checked that each polynomial is reduced (`squarefree-factor`), involves every variable and is singular at the origin, and computed the dimension of its singular locus there (`local-dimension` of the ideal of the polynomial and its partial derivatives). Equations that agree with a catalogue entry or with another candidate after permuting coordinates and changing signs were removed, as were equations with more than 150 terms.

One worker per equation runs the Zoo record builder: local dimension, embedded resolution with both zetas and the pole check, intrinsic resolution, an exhaustive pole-check replay when the quick check is unresolved, then the Milnor and Tjurina numbers. The 50-second wall-clock budget covers every step. Six equations ran at once on an Intel Core i7-1355U (10 cores, 12 threads). A certified case has complete geometry in both modes, both zetas and a verified pole check. The screen ran once, at Atlas revision [`c3de444`](https://github.com/pportilla/atlas/commit/c3de44402cf82522fb89005c3403d0ece4e3cf4c).

## Solver changes behind this screen

A first pass at revision `2975cad` ended with a solver diagnostic for about four germs in ten: 608 of the first 1,465, against 742 certified and 115 at the budget. Its per-germ results were lost when the machine was switched off, so only that tally remains. Each kind of diagnostic was traced to a general cause in Atlas and fixed. The screen reported here ran once, after the fixes. No germ ends with a diagnostic.

**Newton fans in coordinates adapted to the singular locus.** Most diagnostics said that the strict transform fails normal crossings along a curve of an orbit. On a non-convenient germ such as `x^2*y+z^2+t^3+u^4`, the fan has a boundary ray over a coordinate subspace that lies on the hypersurface outside its singular locus, here the x-axis. The verifier is right to refuse it. The linear shears tried next created faces with a repeated factor. The native kernel now proposes triangular substitutions of Jacobian determinant one that take such a subspace off the hypersurface and fix the coordinate subspaces of the singular locus, or that make a linear factor of a degenerate face a coordinate. A search over these steps stops at a frame whose fan passes the existing verifier. The certificate records the steps, and replay recomputes the adapted equation from them.

**Fan of hyperplanes in four to eight variables.** For an arrangement, the "degenerate" faces are planes crossing normally. The fan that verifies each plane as its own branch was limited to four variables.

**Fans bounded by memory, with exact subdivision rays.** Cusps and invertible polynomials in five and six variables stopped at fixed counts of cones and strata. The fan now chooses each subdivision ray among all lattice points of the cone's parallelepiped, which gave 24,295 cones instead of 339,349 on `x^3+y^5+z^8+t^9+u^9+x*y*z*t*u`, and it is bounded by the memory its charts need.

**A quick search that does not give up.** A quick search gave the general smooth-centre rules a fixed 20 seconds and then returned its diagnostic. The rules are now the safe method: when the fast methods do not apply or decline, they take turns, keep their state, and have no deadline or budget of their own. After them the projective search continues. A quick request ends with a certified answer or when its caller stops it. A resolved record with a partial dual complex or a missing zeta function is not returned.

**Factors as components.** Embedded blowups carry each rational factor of a reducible germ as its own component and stop when the total transform has normal crossings. Parts of a centre that meet only inside a removed centre are blown up one by one.

**Internal errors.** A fast method that stops on an internal error has its proposal rejected like a failed check. The safe method takes over, and the certified answer lists the error under `defects`. No record of this screen has one.

**Record builder.** When the builder replays a pole check, it compares the zeta functions at the origin. A quick request may stop its optional search for nearby strata after 10 seconds, and the replay carries that search to its end.

These changes are in Atlas from revision `c3de444`. All 227 test modules pass there.

## Results by family

### Fourfolds

| Family | Equations | Certified | Timeouts |
| --- | ---: | ---: | ---: |
| I01: Brieskorn–Pham germs | 60 | 60 | 0 |
| I02: Invertible polynomials: sums of chain, loop and Fermat blocks | 75 | 74 | 1 |
| I03: Arnold's simple, unimodal and bimodal germs and two-pair branches, stabilised by squares | 47 | 45 | 2 |
| I04: Joins of curve and surface germs in separate variables | 75 | 70 | 5 |
| I05: Cusps: a sum of powers plus the product of all variables | 40 | 26 | 14 |
| I06: Convenient Newton polyhedra with mixed monomials under the diagonal | 45 | 45 | 0 |
| I07: Cones over hypersurfaces of degree 3 and more | 31 | 25 | 6 |
| I08: Superisolated germs over hypersurfaces with isolated singular points | 12 | 10 | 2 |
| I09: Hidden coordinates: a known germ after a linear or triangular change of coordinates | 48 | 43 | 5 |
| N01: A monomial in k variables plus powers of the others | 75 | 73 | 2 |
| N02: Sums of monomials in disjoint groups of variables | 45 | 45 | 0 |
| N03: Non-isolated chains and loops | 52 | 29 | 23 |
| N04: Partial cusps: a product of distinct variables plus powers of some variables | 32 | 30 | 2 |
| N05: Transverse compositions h^j + powers along a singular hypersurface of a coordinate subspace | 32 | 4 | 28 |
| N06: Cones over singular hypersurfaces: a prescribed double or triple point, and classical examples | 32 | 17 | 15 |
| N07: Essential central hyperplane arrangements, one per intersection lattice | 40 | 0 | 40 |
| N08: Products of germs in separate variables | 44 | 3 | 41 |
| N09: Line singularities joined with isolated germs, and generalised Whitney umbrellas | 50 | 50 | 0 |
| N10: Suspensions of threefolds and surfaces of the catalogue | 60 | 49 | 11 |
| N11: Newton polyhedra with a B1 facet | 61 | 58 | 3 |
| N13: Random Newton polyhedra, singular along a coordinate subspace | 44 | 5 | 39 |

### Fivefolds

| Family | Equations | Certified | Timeouts |
| --- | ---: | ---: | ---: |
| I01: Brieskorn–Pham germs | 60 | 60 | 0 |
| I02: Invertible polynomials: sums of chain, loop and Fermat blocks | 71 | 32 | 39 |
| I03: Arnold's simple, unimodal and bimodal germs and two-pair branches, stabilised by squares | 47 | 45 | 2 |
| I04: Joins of curve and surface germs in separate variables | 71 | 52 | 19 |
| I05: Cusps: a sum of powers plus the product of all variables | 40 | 5 | 35 |
| I06: Convenient Newton polyhedra with mixed monomials under the diagonal | 43 | 41 | 2 |
| I07: Cones over hypersurfaces of degree 3 and more | 26 | 21 | 5 |
| I08: Superisolated germs over hypersurfaces with isolated singular points | 9 | 3 | 6 |
| I09: Hidden coordinates: a known germ after a linear or triangular change of coordinates | 48 | 40 | 8 |
| N01: A monomial in k variables plus powers of the others | 71 | 65 | 6 |
| N02: Sums of monomials in disjoint groups of variables | 55 | 47 | 8 |
| N03: Non-isolated chains and loops | 50 | 14 | 36 |
| N04: Partial cusps: a product of distinct variables plus powers of some variables | 32 | 19 | 13 |
| N05: Transverse compositions h^j + powers along a singular hypersurface of a coordinate subspace | 39 | 1 | 38 |
| N06: Cones over singular hypersurfaces: a prescribed double or triple point, and classical examples | 32 | 14 | 18 |
| N07: Essential central hyperplane arrangements, one per intersection lattice | 39 | 0 | 39 |
| N08: Products of germs in separate variables | 52 | 3 | 49 |
| N09: Line singularities joined with isolated germs, and generalised Whitney umbrellas | 52 | 51 | 1 |
| N10: Suspensions of threefolds and surfaces of the catalogue | 57 | 46 | 11 |
| N11: Newton polyhedra with a B1 facet | 64 | 52 | 12 |
| N13: Random Newton polyhedra, singular along a coordinate subspace | 42 | 0 | 42 |

## Results by dimension of the singular locus

| Dimension | Singular locus | Equations | Certified | Timeouts |
| --- | ---: | ---: | ---: | ---: |
| Fourfolds | 0 | 434 | 403 | 31 |
| Fourfolds | 1 | 232 | 187 | 45 |
| Fourfolds | 2 | 132 | 95 | 37 |
| Fourfolds | 3 | 202 | 76 | 126 |
| Fivefolds | 0 | 417 | 303 | 114 |
| Fivefolds | 1 | 216 | 154 | 62 |
| Fivefolds | 2 | 110 | 61 | 49 |
| Fivefolds | 3 | 72 | 39 | 33 |
| Fivefolds | 4 | 185 | 54 | 131 |

## Certified records not yet published

These 289 germs have a complete record with a verified pole check. Each record is larger than 1 MB, 1.4 GB in all, because the dual complex of a resolution with thousands of charts is listed cell by cell. They stay out of the catalogue until it has a compact format for large dual complexes.

| # | ID | Dim. | Equation | Charts | Record (MB) |
| ---: | --- | ---: | --- | ---: | ---: |
| 1 | f4-invertible-c2c2f-34334 | 4 | `x^3*y+y^4+z^3*t+t^3+u^4` | 2,255 | 1.5 |
| 2 | f4-invertible-c2l2f-24344 | 4 | `x^2*y+y^4+z^3*t+t^4*z+u^4` | 3,105 | 2.0 |
| 3 | f4-invertible-c2l2f-24445 | 4 | `x^2*y+y^4+z^4*t+t^4*z+u^5` | 7,933 | 6.5 |
| 4 | f4-invertible-c2l2f-34445 | 4 | `x^3*y+y^4+z^4*t+t^4*z+u^5` | 2,981 | 1.9 |
| 5 | f4-invertible-c3l2-23234 | 4 | `x^2*y+y^3*z+z^2+t^3*u+u^4*t` | 2,051 | 1.1 |
| 6 | f4-invertible-c3l2-33343 | 4 | `x^3*y+y^3*z+z^3+t^4*u+u^3*t` | 4,523 | 2.8 |
| 7 | f4-invertible-c3l2-33434 | 4 | `x^3*y+y^3*z+z^4+t^3*u+u^4*t` | 4,741 | 3.5 |
| 8 | f4-invertible-c5-22233 | 4 | `x^2*y+y^2*z+z^2*t+t^3*u+u^3` | 2,893 | 1.8 |
| 9 | f4-invertible-c5-32344 | 4 | `x^3*y+y^2*z+z^3*t+t^4*u+u^4` | 6,429 | 4.6 |
| 10 | f4-invertible-c5-32422 | 4 | `x^3*y+y^2*z+z^4*t+t^2*u+u^2` | 2,373 | 1.3 |
| 11 | f4-invertible-c5-33324 | 4 | `x^3*y+y^3*z+z^3*t+t^2*u+u^4` | 9,953 | 7.2 |
| 12 | f4-invertible-c5-42332 | 4 | `x^4*y+y^2*z+z^3*t+t^3*u+u^2` | 4,577 | 2.8 |
| 13 | f4-invertible-l2fff-23435 | 4 | `x^2*y+y^3*x+z^4+t^3+u^5` | 1,753 | 1.0 |
| 14 | f4-invertible-l2l2f-33234 | 4 | `x^3*y+y^3*x+z^2*t+t^3*z+u^4` | 2,657 | 1.7 |
| 15 | f4-invertible-l2l2f-34245 | 4 | `x^3*y+y^4*x+z^2*t+t^4*z+u^5` | 20,317 | 14.1 |
| 16 | f4-invertible-l2l2f-34422 | 4 | `x^3*y+y^4*x+z^4*t+t^2*z+u^2` | 3,599 | 1.9 |
| 17 | f4-invertible-l2l2f-44425 | 4 | `x^4*y+y^4*x+z^4*t+t^2*z+u^5` | 5,637 | 3.7 |
| 18 | f4-invertible-l3c2-22423 | 4 | `x^2*y+y^2*z+z^4*x+t^2*u+u^3` | 5,851 | 3.7 |
| 19 | f4-invertible-l3c2-23444 | 4 | `x^2*y+y^3*z+z^4*x+t^4*u+u^4` | 9,569 | 6.2 |
| 20 | f4-invertible-l3c2-24434 | 4 | `x^2*y+y^4*z+z^4*x+t^3*u+u^4` | 8,491 | 5.0 |
| 21 | f4-invertible-l3c2-42432 | 4 | `x^4*y+y^2*z+z^4*x+t^3*u+u^2` | 4,193 | 2.2 |
| 22 | f4-invertible-l3ff-43435 | 4 | `x^4*y+y^3*z+z^4*x+t^3+u^5` | 4,567 | 2.5 |
| 23 | f4-invertible-l3ff-44225 | 4 | `x^4*y+y^4*z+z^2*x+t^2+u^5` | 2,491 | 1.3 |
| 24 | f4-invertible-l3l2-23324 | 4 | `x^2*y+y^3*z+z^3*x+t^2*u+u^4*t` | 5,321 | 2.7 |
| 25 | f4-invertible-l3l2-24243 | 4 | `x^2*y+y^4*z+z^2*x+t^4*u+u^3*t` | 8,969 | 5.1 |
| 26 | f4-invertible-l3l2-24442 | 4 | `x^2*y+y^4*z+z^4*x+t^4*u+u^2*t` | 9,275 | 4.8 |
| 27 | f4-invertible-l3l2-42233 | 4 | `x^4*y+y^2*z+z^2*x+t^3*u+u^3*t` | 5,831 | 3.4 |
| 28 | f4-invertible-l3l2-44322 | 4 | `x^4*y+y^4*z+z^3*x+t^2*u+u^2*t` | 15,051 | 9.5 |
| 29 | f4-invertible-l4f-22343 | 4 | `x^2*y+y^2*z+z^3*t+t^4*x+u^3` | 4,801 | 3.0 |
| 30 | f4-invertible-l4f-23333 | 4 | `x^2*y+y^3*z+z^3*t+t^3*x+u^3` | 2,655 | 1.5 |
| 31 | f4-invertible-l4f-33434 | 4 | `x^3*y+y^3*z+z^4*t+t^3*x+u^4` | 13,071 | 8.9 |
| 32 | f4-invertible-l4f-43333 | 4 | `x^4*y+y^3*z+z^3*t+t^3*x+u^3` | 3,373 | 1.9 |
| 33 | f4-invertible-l5-22443 | 4 | `x^2*y+y^2*z+z^4*t+t^4*u+u^3*x` | 10,607 | 6.2 |
| 34 | f4-invertible-l5-23444 | 4 | `x^2*y+y^3*z+z^4*t+t^4*u+u^4*x` | 13,085 | 8.3 |
| 35 | f4-invertible-l5-32342 | 4 | `x^3*y+y^2*z+z^3*t+t^4*u+u^2*x` | 6,883 | 4.0 |
| 36 | f4-invertible-l5-33323 | 4 | `x^3*y+y^3*z+z^3*t+t^2*u+u^3*x` | 6,865 | 4.0 |
| 37 | f4-invertible-l5-33342 | 4 | `x^3*y+y^3*z+z^3*t+t^4*u+u^2*x` | 8,599 | 4.9 |
| 38 | f4-join-d7-e13-4 | 4 | `x^2*y+y^6+z^3+z*t^5+u^4` | 2,475 | 1.4 |
| 39 | f4-join-d8-e7-4 | 4 | `x^2*y+y^7+z^3+z*t^3+u^4` | 5,651 | 3.4 |
| 40 | f4-join-d8-z17-4 | 4 | `x^2*y+y^7+z^3*t+t^8+u^4` | 13,893 | 8.5 |
| 41 | f4-join-e13-z12-4 | 4 | `x^3+x*y^5+z^3*t+z*t^4+u^4` | 5,571 | 3.4 |
| 42 | f4-join-e19-z17-3 | 4 | `x^3+x*y^7+z^3*t+t^8+u^3` | 2,031 | 1.2 |
| 43 | f4-join-q11-z17 | 4 | `x^3+y^2*z+x*z^3+t^3*u+u^8` | 6,565 | 4.1 |
| 44 | f4-join-q12-z17 | 4 | `x^3+y^5+y*z^2+t^3*u+u^8` | 3,181 | 1.6 |
| 45 | f4-join-q16-d7 | 4 | `x^3+y*z^2+y^7+t^2*u+u^6` | 9,867 | 5.4 |
| 46 | f4-join-q17-e19 | 4 | `x^3+y*z^2+x*y^5+t^3+t*u^7` | 2,135 | 1.1 |
| 47 | f4-join-q17-w13 | 4 | `x^3+y*z^2+x*y^5+t^4+t*u^4` | 5,115 | 2.7 |
| 48 | f4-join-q17-z11 | 4 | `x^3+y*z^2+x*y^5+t^3*u+u^5` | 4,603 | 2.5 |
| 49 | f4-join-s11-d7 | 4 | `x^4+y^2*z+x*z^2+t^2*u+u^6` | 5,895 | 3.6 |
| 50 | f4-join-s11-j21 | 4 | `x^4+y^2*z+x*z^2+t^3+t^2*u^2+u^7` | 2,501 | 1.3 |
| 51 | f4-join-s11-z13 | 4 | `x^4+y^2*z+x*z^2+t^3*u+u^6` | 9,643 | 6.8 |
| 52 | f4-join-s16-z17 | 4 | `x^2*z+y*z^2+x*y^4+t^3*u+u^8` | 8,081 | 5.5 |
| 53 | f4-join-s17-d5 | 4 | `x^2*z+y*z^2+y^6+t^2*u+u^4` | 10,129 | 6.3 |
| 54 | f4-join-s17-j21 | 4 | `x^2*z+y*z^2+y^6+t^3+t^2*u^2+u^7` | 2,907 | 1.7 |
| 55 | f4-join-s17-w13 | 4 | `x^2*z+y*z^2+y^6+t^4+t*u^4` | 5,277 | 2.9 |
| 56 | f4-join-s17-w17 | 4 | `x^2*z+y*z^2+y^6+t^4+t*u^5` | 5,067 | 3.1 |
| 57 | f4-join-t255-z11-4 | 4 | `x^5+x^2*y^2+y^5+z^3*t+t^5+u^4` | 1,913 | 1.3 |
| 58 | f4-join-t255-z18-2 | 4 | `x^5+x^2*y^2+y^5+z^3*t+z*t^6+u^2` | 5,985 | 2.9 |
| 59 | f4-join-t345-d7 | 4 | `x^3+y^4+z^5+x*y*z+t^2*u+u^6` | 15,607 | 9.5 |
| 60 | f4-join-t345-z13 | 4 | `x^3+y^4+z^5+x*y*z+t^3*u+u^6` | 31,663 | 27.1 |
| 61 | f4-join-t345-z17 | 4 | `x^3+y^4+z^5+x*y*z+t^3*u+u^8` | 14,067 | 12.1 |
| 62 | f4-join-t444-d8 | 4 | `x^4+y^4+z^4+x*y*z+t^2*u+u^7` | 3,593 | 2.7 |
| 63 | f4-join-t444-e12 | 4 | `x^4+y^4+z^4+x*y*z+t^3+u^7+t*u^5` | 6,731 | 5.8 |
| 64 | f4-join-t444-e19 | 4 | `x^4+y^4+z^4+x*y*z+t^3+t*u^7` | 17,521 | 14.0 |
| 65 | f4-join-t444-w17 | 4 | `x^4+y^4+z^4+x*y*z+t^4+t*u^5` | 2,379 | 1.5 |
| 66 | f4-join-w13-z17-4 | 4 | `x^4+x*y^4+z^3*t+t^8+u^4` | 2,625 | 1.6 |
| 67 | f4-join-z13-z18-2 | 4 | `x^3*y+y^6+z^3*t+z*t^6+u^2` | 16,153 | 12.4 |
| 68 | f4-join-z18-z18-4 | 4 | `x^3*y+x*y^6+z^3*t+z*t^6+u^4` | 18,497 | 13.8 |
| 69 | f4-cusp-3-5-8-9-9 | 4 | `x^3+y^5+z^8+t^9+u^9+x*y*z*t*u` | 24,295 | 21.1 |
| 70 | f4-cusp-3-6-6-7-8 | 4 | `x^3+y^6+z^6+t^7+u^8+x*y*z*t*u` | 3,421 | 3.2 |
| 71 | f4-cusp-3-6-7-7-8 | 4 | `x^3+y^6+z^7+t^7+u^8+x*y*z*t*u` | 7,641 | 7.2 |
| 72 | f4-cusp-3-7-7-7-9 | 4 | `x^3+y^7+z^7+t^7+u^9+x*y*z*t*u` | 4,269 | 3.6 |
| 73 | f4-cusp-3-8-8-9-9 | 4 | `x^3+y^8+z^8+t^9+u^9+x*y*z*t*u` | 29,227 | 30.7 |
| 74 | f4-cusp-4-4-5-6-9 | 4 | `x^4+y^4+z^5+t^6+u^9+x*y*z*t*u` | 1,459 | 1.1 |
| 75 | f4-cusp-4-4-5-8-9 | 4 | `x^4+y^4+z^5+t^8+u^9+x*y*z*t*u` | 6,777 | 6.3 |
| 76 | f4-cusp-4-4-7-8-8 | 4 | `x^4+y^4+z^7+t^8+u^8+x*y*z*t*u` | 2,201 | 2.0 |
| 77 | f4-cusp-4-5-5-8-8 | 4 | `x^4+y^5+z^5+t^8+u^8+x*y*z*t*u` | 1,373 | 1.1 |
| 78 | f4-cusp-4-5-6-6-6 | 4 | `x^4+y^5+z^6+t^6+u^6+x*y*z*t*u` | 1,927 | 1.3 |
| 79 | f4-cusp-4-7-8-8-8 | 4 | `x^4+y^7+z^8+t^8+u^8+x*y*z*t*u` | 18,965 | 18.0 |
| 80 | f4-cusp-5-5-5-6-8 | 4 | `x^5+y^5+z^5+t^6+u^8+x*y*z*t*u` | 2,829 | 2.3 |
| 81 | f4-cusp-5-5-5-9-9 | 4 | `x^5+y^5+z^5+t^9+u^9+x*y*z*t*u` | 7,613 | 6.4 |
| 82 | f4-cusp-5-6-6-8-8 | 4 | `x^5+y^6+z^6+t^8+u^8+x*y*z*t*u` | 24,679 | 21.7 |
| 83 | f4-cusp-5-6-6-9-9 | 4 | `x^5+y^6+z^6+t^9+u^9+x*y*z*t*u` | 32,213 | 27.5 |
| 84 | f4-cusp-5-7-7-7-7 | 4 | `x^5+y^7+z^7+t^7+u^7+x*y*z*t*u` | 9,551 | 7.4 |
| 85 | f4-cusp-6-6-6-6-8 | 4 | `x^6+y^6+z^6+t^6+u^8+x*y*z*t*u` | 1,625 | 1.5 |
| 86 | f4-newton-convenient-18 | 4 | `x^5+y^3+z^4+t^6+u^5+3*y*z*u-x*y+y*z*u^2` | 1,917 | 1.1 |
| 87 | f4-newton-convenient-32 | 4 | `x^3+y^6+z^4+t^5+u^2+x*y*z+y^3*t^2-2*y^3*t-x^2*y` | 1,755 | 1.2 |
| 88 | f4-newton-convenient-57 | 4 | `x^4+y^5+z^5+t^6+u^3+3*y*u+y*t^2*u` | 2,505 | 1.6 |
| 89 | f4-newton-convenient-67 | 4 | `x^4+y^5+z^5+t^3+u^6-z^3*t+3*y*u^3` | 2,377 | 1.6 |
| 90 | f4-monomial-221-35 | 4 | `x^2*y^2*z+t^3+u^5` | 1,760 | 1.6 |
| 91 | f4-monomial-322-35 | 4 | `x^3*y^2*z^2+t^3+u^5` | 2,356 | 1.9 |
| 92 | f4-monomial-421-45 | 4 | `x^4*y^2*z+t^4+u^5` | 2,231 | 1.6 |
| 93 | f4-monomial-442-35 | 4 | `x^4*y^4*z^2+t^3+u^5` | 5,595 | 5.0 |
| 94 | f4-monomials-21-22-5 | 4 | `x^2*y+z^2*t^2+u^5` | 3,066 | 2.1 |
| 95 | f4-monomials-32-22-5 | 4 | `x^3*y^2+z^2*t^2+u^5` | 2,700 | 2.5 |
| 96 | f4-chain-1223-1211-5 | 4 | `x*y+y^2*z^2+z^2*t+t^3*u+u^5` | 6,937 | 4.2 |
| 97 | f4-chain-3312-2221-4 | 4 | `x^3*y^2+y^3*z^2+z*t^2+t^2*u+u^4` | 2,234 | 1.4 |
| 98 | f4-loop-2231-1212-3 | 4 | `x^2*y+y^2*z^2+z^3*t+t*u^2+u^3*x` | 3,582 | 2.0 |
| 99 | f4-partial-cusp-3-2-5523 | 4 | `x*y*z+x^5+y^5+t^2+u^3` | 4,345 | 2.9 |
| 100 | f4-partial-cusp-3-2-5556 | 4 | `x*y*z+x^5+y^5+t^5+u^6` | 8,114 | 6.2 |
| 101 | f4-partial-cusp-4-1-43 | 4 | `x*y*z*t+x^4+u^3` | 1,823 | 1.2 |
| 102 | f4-partial-cusp-4-1-66 | 4 | `x*y*z*t+x^6+u^6` | 1,203 | 1.2 |
| 103 | f4-partial-cusp-4-2-533 | 4 | `x*y*z*t+x^5+y^3+u^3` | 1,667 | 1.1 |
| 104 | f4-partial-cusp-4-2-534 | 4 | `x*y*z*t+x^5+y^3+u^4` | 7,679 | 4.9 |
| 105 | f4-partial-cusp-4-3-6546 | 4 | `x*y*z*t+x^6+y^5+z^4+u^6` | 7,832 | 7.3 |
| 106 | f4-partial-cusp-5-2-35 | 4 | `x*y*z*t*u+x^3+y^5` | 1,717 | 1.1 |
| 107 | f4-partial-cusp-5-2-46 | 4 | `x*y*z*t*u+x^4+y^6` | 1,322 | 1.1 |
| 108 | f4-partial-cusp-5-2-54 | 4 | `x*y*z*t*u+x^5+y^4` | 5,080 | 3.5 |
| 109 | f4-partial-cusp-5-3-356 | 4 | `x*y*z*t*u+x^3+y^5+z^6` | 3,059 | 2.3 |
| 110 | f4-partial-cusp-5-4-5663 | 4 | `x*y*z*t*u+x^5+y^6+z^6+t^3` | 1,906 | 1.3 |
| 111 | f4-partial-cusp-5-4-6455 | 4 | `x*y*z*t*u+x^6+y^4+z^5+t^5` | 7,376 | 5.1 |
| 112 | f4-line-t-inf-4-4-d5 | 4 | `x*y*z+y^4+z^4+t^2*u+u^4` | 1,370 | 1.1 |
| 113 | f4-suspension-t3-cusp-5-7-7-7-46 | 4 | `x^5+y^7+z^7+t^7+x*y*z*t+u^2` | 17,929 | 11.7 |
| 114 | f4-b1-3-455-021-110 | 4 | `x^4+y^5+z^5+t*y^2*z+u*x*y` | 2,587 | 1.4 |
| 115 | f4-b1-3-556-200-101 | 4 | `x^5+y^5+z^6+t*x^2+u*x*z` | 2,257 | 1.1 |
| 116 | f4-b1-3-654-002-310 | 4 | `x^6+y^5+z^4+t*z^2+u*x^3*y` | 5,561 | 4.8 |
| 117 | f4-b1-4-4546-2100 | 4 | `x^4+y^5+z^4+t^6+u*x^2*y` | 1,447 | 1.0 |
| 118 | f4-b1-4-4553-2010 | 4 | `x^4+y^5+z^5+t^3+u*x^2*z` | 1,603 | 1.0 |
| 119 | f4-b1-4-4566-0031 | 4 | `x^4+y^5+z^6+t^6+u*z^3*t` | 4,465 | 3.6 |
| 120 | f4-b1-4-4566-1002 | 4 | `x^4+y^5+z^6+t^6+u*x*t^2` | 4,025 | 2.7 |
| 121 | f4-b1-4-5466-1102 | 4 | `x^5+y^4+z^6+t^6+u*x*y*t^2` | 3,741 | 2.4 |
| 122 | f4-b1-4-6454-0200-0220-d | 4 | `x^6+y^4+z^5+t^4+u*y^2+u*y^2*z^2` | 2,425 | 1.7 |
| 123 | f4-b1-4-6543-0011-0201-d | 4 | `x^6+y^5+z^4+t^3+u*z*t+u*y^2*t` | 7,745 | 5.9 |
| 124 | f4-b1-4-6543-3200-0021-d | 4 | `x^6+y^5+z^4+t^3+u*x^3*y^2+u*z^2*t` | 1,669 | 1.2 |
| 125 | f4-b1-4-6564-1300 | 4 | `x^6+y^5+z^6+t^4+u*x*y^3` | 1,831 | 1.3 |
| 126 | f4-b1-4-6566-2011 | 4 | `x^6+y^5+z^6+t^6+u*x^2*z*t` | 5,328 | 4.4 |
| 127 | f4-b1-4-6655-0310 | 4 | `x^6+y^6+z^5+t^5+u*y^3*z` | 1,650 | 1.2 |
| 128 | f5-brieskorn-2-5-5-6-7-8 | 5 | `x^2+y^5+z^5+t^6+u^7+v^8` | 1,747 | 1.1 |
| 129 | f5-invertible-c2c2c2-224422 | 5 | `x^2*y+y^2+z^4*t+t^4+u^2*v+v^2` | 3,991 | 3.7 |
| 130 | f5-invertible-c2c2c2-232344 | 5 | `x^2*y+y^3+z^2*t+t^3+u^4*v+v^4` | 19,154 | 22.4 |
| 131 | f5-invertible-c2l2ff-432452 | 5 | `x^4*y+y^3+z^2*t+t^4*z+u^5+v^2` | 2,077 | 1.1 |
| 132 | f5-invertible-c3c2f-434334 | 5 | `x^4*y+y^3*z+z^4+t^3*u+u^3+v^4` | 7,060 | 6.3 |
| 133 | f5-invertible-c3c3-334223 | 5 | `x^3*y+y^3*z+z^4+t^2*u+u^2*v+v^3` | 9,293 | 6.9 |
| 134 | f5-invertible-c3c3-343323 | 5 | `x^3*y+y^4*z+z^3+t^3*u+u^2*v+v^3` | 2,918 | 2.1 |
| 135 | f5-invertible-c3c3-434233 | 5 | `x^4*y+y^3*z+z^4+t^2*u+u^3*v+v^3` | 21,410 | 18.2 |
| 136 | f5-invertible-c3l2f-222344 | 5 | `x^2*y+y^2*z+z^2+t^3*u+u^4*t+v^4` | 20,591 | 17.9 |
| 137 | f5-invertible-c3l2f-243432 | 5 | `x^2*y+y^4*z+z^3+t^4*u+u^3*t+v^2` | 12,201 | 9.4 |
| 138 | f5-invertible-c3l2f-342323 | 5 | `x^3*y+y^4*z+z^2+t^3*u+u^2*t+v^3` | 3,308 | 2.0 |
| 139 | f5-invertible-c3l2f-424222 | 5 | `x^4*y+y^2*z+z^4+t^2*u+u^2*t+v^2` | 20,430 | 14.6 |
| 140 | f5-invertible-c3l3-443232 | 5 | `x^4*y+y^4*z+z^3+t^2*u+u^3*v+v^2*t` | 29,166 | 26.2 |
| 141 | f5-invertible-c4c2-222432 | 5 | `x^2*y+y^2*z+z^2*t+t^4+u^3*v+v^2` | 4,363 | 2.7 |
| 142 | f5-invertible-c4ff-242422 | 5 | `x^2*y+y^4*z+z^2*t+t^4+u^2+v^2` | 5,271 | 2.6 |
| 143 | f5-invertible-c4l2-223222 | 5 | `x^2*y+y^2*z+z^3*t+t^2+u^2*v+v^2*u` | 5,026 | 3.2 |
| 144 | f5-invertible-c5f-223433 | 5 | `x^2*y+y^2*z+z^3*t+t^4*u+u^3+v^3` | 5,477 | 2.7 |
| 145 | f5-invertible-c5f-242324 | 5 | `x^2*y+y^4*z+z^2*t+t^3*u+u^2+v^4` | 4,093 | 3.6 |
| 146 | f5-invertible-c5f-332324 | 5 | `x^3*y+y^3*z+z^2*t+t^3*u+u^2+v^4` | 5,866 | 4.0 |
| 147 | f5-invertible-l2l2l2-323332 | 5 | `x^3*y+y^2*x+z^3*t+t^3*z+u^3*v+v^2*u` | 3,088 | 1.8 |
| 148 | f5-invertible-l3c2f-222234 | 5 | `x^2*y+y^2*z+z^2*x+t^2*u+u^3+v^4` | 5,287 | 2.5 |
| 149 | f5-invertible-l3l3-233222 | 5 | `x^2*y+y^3*z+z^3*x+t^2*u+u^2*v+v^2*t` | 20,338 | 11.7 |
| 150 | f5-invertible-l4c2-223243 | 5 | `x^2*y+y^2*z+z^3*t+t^2*x+u^4*v+v^3` | 4,725 | 2.7 |
| 151 | f5-invertible-l4ff-224434 | 5 | `x^2*y+y^2*z+z^4*t+t^4*x+u^3+v^4` | 21,472 | 22.3 |
| 152 | f5-invertible-l4ff-434255 | 5 | `x^4*y+y^3*z+z^4*t+t^2*x+u^5+v^5` | 10,590 | 5.0 |
| 153 | f5-invertible-l5f-322242 | 5 | `x^3*y+y^2*z+z^2*t+t^2*u+u^4*x+v^2` | 24,373 | 17.6 |
| 154 | f5-join-d4-d4-e14 | 5 | `x^2*y+y^3+z^2*t+t^3+u^3+v^8+u*v^6` | 6,617 | 3.9 |
| 155 | f5-join-d4-d4-j21 | 5 | `x^2*y+y^3+z^2*t+t^3+u^3+u^2*v^2+v^7` | 8,299 | 4.5 |
| 156 | f5-join-d4-d4-t245 | 5 | `x^2*y+y^3+z^2*t+t^3+u^4+u^2*v^2+v^5` | 11,756 | 7.5 |
| 157 | f5-join-d4-d5-x9 | 5 | `x^2*y+y^3+z^2*t+t^4+u^4+v^4+u^2*v^2` | 3,766 | 1.3 |
| 158 | f5-join-d4-d6-d6 | 5 | `x^2*y+y^3+z^2*t+t^5+u^2*v+v^5` | 30,082 | 25.2 |
| 159 | f5-join-d4-d8-j10 | 5 | `x^2*y+y^3+z^2*t+t^7+u^3+v^6+u^2*v^2` | 14,673 | 8.7 |
| 160 | f5-join-d4-x9-e12 | 5 | `x^2*y+y^3+z^4+t^4+z^2*t^2+u^3+v^7+u*v^5` | 5,562 | 2.0 |
| 161 | f5-join-d5-d5-d8 | 5 | `x^2*y+y^4+z^2*t+t^4+u^2*v+v^7` | 6,810 | 6.3 |
| 162 | f5-join-d7-e7-j10 | 5 | `x^2*y+y^6+z^3+z*t^3+u^3+v^6+u^2*v^2` | 5,407 | 2.4 |
| 163 | f5-join-d8-j10-t245 | 5 | `x^2*y+y^7+z^3+t^6+z^2*t^2+u^4+u^2*v^2+v^5` | 6,303 | 3.1 |
| 164 | f5-join-q10-d6-2 | 5 | `x^3+y^4+y*z^2+t^2*u+u^5+v^2` | 5,124 | 3.0 |
| 165 | f5-join-q10-q11 | 5 | `x^3+y^4+y*z^2+t^3+u^2*v+t*v^3` | 7,480 | 3.2 |
| 166 | f5-join-q10-q17 | 5 | `x^3+y^4+y*z^2+t^3+u*v^2+t*u^5` | 8,114 | 3.4 |
| 167 | f5-join-q10-s11 | 5 | `x^3+y^4+y*z^2+t^4+u^2*v+t*v^2` | 17,364 | 14.1 |
| 168 | f5-join-q10-w17-4 | 5 | `x^3+y^4+y*z^2+t^4+t*u^5+v^4` | 5,384 | 3.1 |
| 169 | f5-join-q11-q11 | 5 | `x^3+y^2*z+x*z^3+t^3+u^2*v+t*v^3` | 4,830 | 2.5 |
| 170 | f5-join-q12-q16 | 5 | `x^3+y^5+y*z^2+t^3+u*v^2+u^7` | 5,657 | 1.7 |
| 171 | f5-join-q12-s12 | 5 | `x^3+y^5+y*z^2+t^2*u+u^2*v+t*v^3` | 24,776 | 18.7 |
| 172 | f5-join-q17-e7-2 | 5 | `x^3+y*z^2+x*y^5+t^3+t*u^3+v^2` | 5,413 | 2.3 |
| 173 | f5-join-q17-t245-4 | 5 | `x^3+y*z^2+x*y^5+t^4+t^2*u^2+u^5+v^4` | 5,349 | 3.1 |
| 174 | f5-join-s11-s11 | 5 | `x^4+y^2*z+x*z^2+t^4+u^2*v+t*v^2` | 9,661 | 6.0 |
| 175 | f5-join-s12-e12-2 | 5 | `x^2*y+y^2*z+x*z^3+t^3+u^7+t*u^5+v^2` | 10,762 | 7.4 |
| 176 | f5-join-s16-e12-4 | 5 | `x^2*z+y*z^2+x*y^4+t^3+u^7+t*u^5+v^4` | 24,678 | 18.8 |
| 177 | f5-join-s16-w12-3 | 5 | `x^2*z+y*z^2+x*y^4+t^4+u^5+t^2*u^3+v^3` | 14,773 | 9.6 |
| 178 | f5-join-s17-d8-2 | 5 | `x^2*z+y*z^2+y^6+t^2*u+u^7+v^2` | 7,020 | 5.2 |
| 179 | f5-join-s17-s17 | 5 | `x^2*z+y*z^2+y^6+t^2*v+u*v^2+u^6` | 6,885 | 4.4 |
| 180 | f5-join-t237-e7-3 | 5 | `x^2+y^3+z^7+x*y*z+t^3+t*u^3+v^3` | 2,572 | 1.5 |
| 181 | f5-join-t237-w17-2 | 5 | `x^2+y^3+z^7+x*y*z+t^4+t*u^5+v^2` | 2,540 | 1.3 |
| 182 | f5-join-t334-t444 | 5 | `x^3+y^3+z^4+x*y*z+t^4+u^4+v^4+t*u*v` | 3,845 | 3.4 |
| 183 | f5-join-t334-u16 | 5 | `x^3+y^3+z^4+x*y*z+t^3+t*v^2+u^5` | 3,863 | 1.7 |
| 184 | f5-join-t345-u16 | 5 | `x^3+y^4+z^5+x*y*z+t^3+t*v^2+u^5` | 23,406 | 11.6 |
| 185 | f5-join-t444-e7-4 | 5 | `x^4+y^4+z^4+x*y*z+t^3+t*u^3+v^4` | 18,358 | 16.3 |
| 186 | f5-join-t444-s17 | 5 | `x^4+y^4+z^4+x*y*z+t^2*v+u*v^2+u^6` | 13,428 | 13.5 |
| 187 | f5-cusp-3-6-7-7-9-10 | 5 | `x^3+y^6+z^7+t^7+u^9+v^10+x*y*z*t*u*v` | 2,622 | 2.2 |
| 188 | f5-cusp-4-6-6-7-8-8 | 5 | `x^4+y^6+z^6+t^7+u^8+v^8+x*y*z*t*u*v` | 6,634 | 7.0 |
| 189 | f5-cusp-4-6-6-9-9-12 | 5 | `x^4+y^6+z^6+t^9+u^9+v^12+x*y*z*t*u*v` | 16,740 | 26.5 |
| 190 | f5-cusp-5-5-5-5-12-12 | 5 | `x^5+y^5+z^5+t^5+u^12+v^12+x*y*z*t*u*v` | 1,166 | 1.4 |
| 191 | f5-newton-convenient-13 | 5 | `x^6+y^2+z^4+t^5+u^4+v^3-2*x*u^3-x^2*z*v` | 8,028 | 6.0 |
| 192 | f5-newton-convenient-14 | 5 | `x^4+y^6+z^5+t^3+u^3+v^2+x*y^2*z-x*u-2*x*y^3` | 2,669 | 1.5 |
| 193 | f5-newton-convenient-18 | 5 | `x^6+y^5+z^4+t^2+u^5+v^3-2*t*v+3*x^2*u^2+2*x^3*z+2*x^3*v` | 2,625 | 1.7 |
| 194 | f5-newton-convenient-27 | 5 | `x^5+y^3+z^5+t^3+u^4+v^5+2*z*t^2-2*x^3*v-2*z*u*v^2+2*x*u^2*v` | 7,208 | 5.2 |
| 195 | f5-newton-convenient-30 | 5 | `x^2+y^2+z^5+t^4+u^6+v^3-t^2*u-z*t*u+3*t*u*v+2*y*z*u` | 3,193 | 1.5 |
| 196 | f5-newton-convenient-32 | 5 | `x^3+y^4+z^6+t^5+u^2+v^3-2*x*z^2+x*z` | 4,041 | 2.3 |
| 197 | f5-newton-convenient-35 | 5 | `x^6+y^3+z^4+t^5+u^4+v^6+x*y*v+2*y*t^2*u+z^2*v^2` | 13,821 | 9.2 |
| 198 | f5-newton-convenient-41 | 5 | `x^2+y^3+z^5+t^5+u^4+v^5+2*x*u*v-y*z*v` | 5,298 | 3.4 |
| 199 | f5-newton-convenient-50 | 5 | `x^6+y^2+z^5+t^6+u^4+v^5+2*x^2*z^2*v-x*z^3*v+2*x^3*z` | 2,785 | 2.0 |
| 200 | f5-newton-convenient-55 | 5 | `x^2+y^6+z^3+t^6+u^3+v^5-t*v^2-2*y^2*t-2*z*u` | 8,363 | 5.9 |
| 201 | f5-newton-convenient-59 | 5 | `x^2+y^3+z^6+t^5+u^3+v^3-y*u-2*y*z*t-2*z*t^2` | 1,842 | 1.1 |
| 202 | f5-newton-convenient-68 | 5 | `x^6+y^4+z^4+t^2+u^6+v^5+2*x^2*t+2*z*t+3*x*z*v^2` | 3,103 | 1.9 |
| 203 | f5-newton-convenient-8 | 5 | `x^4+y^6+z^5+t^6+u^6+v^5+2*t*v^2-u^2*v^3` | 3,794 | 1.9 |
| 204 | f5-cone-chain-cubic | 5 | `x^2*y+y^2*z+z^2*t+t^2*u+u^2*v+v^3` | 2,618 | 1.4 |
| 205 | f5-cone-loop-cubic | 5 | `x^2*y+y^2*z+z^2*t+t^2*u+u^2*v+v^2*x` | 4,367 | 2.1 |
| 206 | f5-hidden-chain-quadratic-tu | 5 | `x^2*y^2*z^2+z^6+x^2*y^2*u+2*x*y*z^2*t+3*z^4*u+x*y*z^2+2*x*y*t*u+z^2*t^2+3*z^2*u^2+x^2*y+y^2*z+z^2*t+…` | 8,282 | 5.8 |
| 207 | f5-monomial-321-234 | 5 | `x^3*y^2*z+t^2+u^3+v^4` | 1,810 | 1.3 |
| 208 | f5-monomial-322-234 | 5 | `x^3*y^2*z^2+t^2+u^3+v^4` | 1,635 | 1.4 |
| 209 | f5-monomial-331-335 | 5 | `x^3*y^3*z+t^3+u^3+v^5` | 3,255 | 2.0 |
| 210 | f5-monomial-332-225 | 5 | `x^3*y^3*z^2+t^2+u^2+v^5` | 2,470 | 2.0 |
| 211 | f5-monomial-332-255 | 5 | `x^3*y^3*z^2+t^2+u^5+v^5` | 2,379 | 1.9 |
| 212 | f5-monomial-3332-34 | 5 | `x^3*y^3*z^3*t^2+u^3+v^4` | 1,376 | 1.7 |
| 213 | f5-monomial-421-234 | 5 | `x^4*y^2*z+t^2+u^3+v^4` | 2,324 | 2.2 |
| 214 | f5-monomial-422-234 | 5 | `x^4*y^2*z^2+t^2+u^3+v^4` | 1,441 | 1.3 |
| 215 | f5-monomial-4221-24 | 5 | `x^4*y^2*z^2*t+u^2+v^4` | 1,616 | 1.6 |
| 216 | f5-monomial-4221-25 | 5 | `x^4*y^2*z^2*t+u^2+v^5` | 12,737 | 15.0 |
| 217 | f5-monomial-43-3445 | 5 | `x^4*y^3+z^3+t^4+u^4+v^5` | 1,885 | 1.0 |
| 218 | f5-monomial-432-234 | 5 | `x^4*y^3*z^2+t^2+u^3+v^4` | 1,557 | 1.6 |
| 219 | f5-monomial-432-355 | 5 | `x^4*y^3*z^2+t^3+u^5+v^5` | 2,128 | 1.7 |
| 220 | f5-monomial-4321-25 | 5 | `x^4*y^3*z^2*t+u^2+v^5` | 3,288 | 3.8 |
| 221 | f5-monomial-4321-34 | 5 | `x^4*y^3*z^2*t+u^3+v^4` | 3,977 | 5.1 |
| 222 | f5-monomial-433-345 | 5 | `x^4*y^3*z^3+t^3+u^4+v^5` | 13,039 | 17.7 |
| 223 | f5-monomial-4331-25 | 5 | `x^4*y^3*z^3*t+u^2+v^5` | 5,170 | 7.3 |
| 224 | f5-monomial-4333-35 | 5 | `x^4*y^3*z^3*t^3+u^3+v^5` | 3,495 | 3.8 |
| 225 | f5-monomial-4421-34 | 5 | `x^4*y^4*z^2*t+u^3+v^4` | 8,273 | 10.9 |
| 226 | f5-monomial-443-355 | 5 | `x^4*y^4*z^3+t^3+u^5+v^5` | 1,579 | 1.4 |
| 227 | f5-monomial-4432-45 | 5 | `x^4*y^4*z^3*t^2+u^4+v^5` | 13,169 | 18.2 |
| 228 | f5-monomials-111-31-3 | 5 | `x*y*z+t^3*u+v^3` | 5,361 | 4.2 |
| 229 | f5-monomials-2222-33 | 5 | `x^2*y^2*z^2*t^2-u^3*v^3` | 915 | 2.8 |
| 230 | f5-monomials-31-22-32 | 5 | `x^3*y+z^2*t^2+u^3*v^2` | 1,581 | 1.5 |
| 231 | f5-monomials-311-22-4 | 5 | `x^3*y*z+t^2*u^2+v^4` | 821 | 1.2 |
| 232 | f5-monomials-32-32-31 | 5 | `x^3*y^2+z^3*t^2+u^3*v` | 2,222 | 2.0 |
| 233 | f5-monomials-32-32-33 | 5 | `x^3*y^2+z^3*t^2+u^3*v^3` | 1,215 | 1.1 |
| 234 | f5-monomials-321-21-4 | 5 | `x^3*y^2*z+t^2*u+v^4` | 2,570 | 2.1 |
| 235 | f5-chain-11332-12111-5 | 5 | `x*y+y*z^2+z^3*t+t^3*u+u^2*v+v^5` | 6,816 | 4.4 |
| 236 | f5-chain-13322-22211-4 | 5 | `x*y^2+y^3*z^2+z^3*t^2+t^2*u+u^2*v+v^4` | 6,327 | 4.1 |
| 237 | f5-chain-22132-12211-4 | 5 | `x^2*y+y^2*z^2+z*t^2+t^3*u+u^2*v+v^4` | 5,174 | 3.6 |
| 238 | f5-chain-22223-12122-4 | 5 | `x^2*y+y^2*z^2+z^2*t+t^2*u^2+u^3*v^2+v^4` | 2,475 | 2.0 |
| 239 | f5-chain-32223-21111-2 | 5 | `x^3*y^2+y^2*z+z^2*t+t^2*u+u^3*v+v^2` | 4,340 | 3.1 |
| 240 | f5-partial-cusp-3-1-3525 | 5 | `x*y*z+x^3+t^5+u^2+v^5` | 4,511 | 1.9 |
| 241 | f5-partial-cusp-3-1-4454 | 5 | `x*y*z+x^4+t^4+u^5+v^4` | 3,579 | 1.6 |
| 242 | f5-partial-cusp-4-0-26 | 5 | `x*y*z*t+u^2+v^6` | 1,960 | 1.8 |
| 243 | f5-partial-cusp-5-1-36 | 5 | `x*y*z*t*u+x^3+v^6` | 1,939 | 3.5 |
| 244 | f5-partial-cusp-5-3-4646 | 5 | `x*y*z*t*u+x^4+y^6+z^4+v^6` | 2,379 | 3.1 |
| 245 | f5-partial-cusp-6-2-43 | 5 | `x*y*z*t*u*v+x^4+y^3` | 5,132 | 5.8 |
| 246 | f5-partial-cusp-6-4-3654 | 5 | `x*y*z*t*u*v+x^3+y^6+z^5+t^4` | 2,447 | 1.9 |
| 247 | f5-line-j3-inf-t444 | 5 | `x^3*y^2+y^3+z^2+t*u*v+t^4+u^4+v^4` | 5,269 | 4.4 |
| 248 | f5-line-line-1-t444 | 5 | `x*y^3+x^3*y^2+z^2+t*u*v+t^4+u^4+v^4` | 4,755 | 3.4 |
| 249 | f5-line-t-inf-3-3-t444 | 5 | `x*y*z+y^3+z^3+t*u*v+t^4+u^4+v^4` | 9,288 | 8.5 |
| 250 | f5-line-t-inf-4-3-t444 | 5 | `x*y*z+y^4+z^3+t*u*v+t^4+u^4+v^4` | 8,467 | 8.0 |
| 251 | f5-umbrella-3-2-3 | 5 | `x^3-y^2*(z*t-u*v)` | 2,415 | 1.4 |
| 252 | f5-suspension-t3-brieskorn-4-6-6-7-39 | 5 | `x^4+y^6+z^6+t^7+u*v` | 9,738 | 3.2 |
| 253 | f5-suspension-t3-cdv-ce7-4-43 | 5 | `x^2+y^3+y*z^3+t^4+u*v` | 9,611 | 5.2 |
| 254 | f5-suspension-t3-join-d5-d5-47 | 5 | `x^2*y+y^4+z^2*t+t^4+u*v` | 2,164 | 1.3 |
| 255 | f5-suspension-t3-join-d6-w13-48 | 5 | `x^2*y+y^5+z^4+z*t^4+u^3+v^3` | 5,826 | 2.7 |
| 256 | f5-suspension-t3-newton-convenient-62-54 | 5 | `x^4+y^5+z^4+t^5+3*x*z*t+3*x^2*t+u^2+v^3` | 7,893 | 6.3 |
| 257 | f5-b1-3-335-003-200-011 | 5 | `x^3+y^3+z^5+t*z^3+u*x^2+v*y*z` | 2,384 | 1.4 |
| 258 | f5-b1-3-335-012-110-200 | 5 | `x^3+y^3+z^5+t*y*z^2+u*x*y+v*x^2` | 2,382 | 1.1 |
| 259 | f5-b1-3-543-110-020-111 | 5 | `x^5+y^4+z^3+t*x*y+u*y^2+v*x*y*z` | 3,179 | 1.2 |
| 260 | f5-b1-3-635-101-103-200 | 5 | `x^6+y^3+z^5+t*x*z+u*x*z^3+v*x^2` | 2,504 | 1.1 |
| 261 | f5-b1-3-643-110-002-012 | 5 | `x^6+y^4+z^3+t*x*y+u*z^2+v*y*z^2` | 2,072 | 1.2 |
| 262 | f5-b1-4-3335-1100-1001 | 5 | `x^3+y^3+z^3+t^5+u*x*y+v*x*t` | 2,549 | 1.5 |
| 263 | f5-b1-4-3346-1001-0031 | 5 | `x^3+y^3+z^4+t^6+u*x*t+v*z^3*t` | 1,644 | 1.3 |
| 264 | f5-b1-4-3556-0111-1111 | 5 | `x^3+y^5+z^5+t^6+u*y*z*t+v*x*y*z*t` | 5,266 | 3.7 |
| 265 | f5-b1-4-4346-1001-0030 | 5 | `x^4+y^3+z^4+t^6+u*x*t+v*z^3` | 7,548 | 6.5 |
| 266 | f5-b1-4-4653-0002-1021 | 5 | `x^4+y^6+z^5+t^3+u*t^2+v*x*z^2*t` | 2,781 | 1.6 |
| 267 | f5-b1-4-5344-0210-3000 | 5 | `x^5+y^3+z^4+t^4+u*y^2*z+v*x^3` | 7,920 | 6.7 |
| 268 | f5-b1-4-5344-3000-1020 | 5 | `x^5+y^3+z^4+t^4+u*x^3+v*x*z^2` | 9,306 | 6.7 |
| 269 | f5-b1-4-5655-3010-3110 | 5 | `x^5+y^6+z^5+t^5+u*x^3*z+v*x^3*y*z` | 1,462 | 1.1 |
| 270 | f5-b1-4-6355-2003-3011 | 5 | `x^6+y^3+z^5+t^5+u*x^2*t^3+v*x^3*z*t` | 2,585 | 1.4 |
| 271 | f5-b1-4-6466-0110-0301 | 5 | `x^6+y^4+z^6+t^6+u*y*z+v*y^3*t` | 1,956 | 1.1 |
| 272 | f5-b1-4-6664-3200-1100 | 5 | `x^6+y^6+z^6+t^4+u*x^3*y^2+v*x*y` | 2,310 | 1.7 |
| 273 | f5-b1-5-33534-11100 | 5 | `x^3+y^3+z^5+t^3+u^4+v*x*y*z` | 3,334 | 3.1 |
| 274 | f5-b1-5-34456-01120 | 5 | `x^3+y^4+z^4+t^5+u^6+v*y*z*t^2` | 2,140 | 1.4 |
| 275 | f5-b1-5-34664-10101-00111-d | 5 | `x^3+y^4+z^6+t^6+u^4+v*x*z*u+v*z*t*u` | 4,831 | 4.7 |
| 276 | f5-b1-5-35354-01120 | 5 | `x^3+y^5+z^3+t^5+u^4+v*y*z*t^2` | 1,732 | 1.4 |
| 277 | f5-b1-5-35463-02010 | 5 | `x^3+y^5+z^4+t^6+u^3+v*y^2*t` | 5,843 | 3.4 |
| 278 | f5-b1-5-36645-11101 | 5 | `x^3+y^6+z^6+t^4+u^5+v*x*y*z*u` | 12,777 | 17.0 |
| 279 | f5-b1-5-43454-00012-20000-d | 5 | `x^4+y^3+z^4+t^5+u^4+v*t*u^2+v*x^2` | 10,437 | 7.8 |
| 280 | f5-b1-5-43543-02000 | 5 | `x^4+y^3+z^5+t^4+u^3+v*y^2` | 2,046 | 1.0 |
| 281 | f5-b1-5-43544-11000 | 5 | `x^4+y^3+z^5+t^4+u^4+v*x*y` | 3,956 | 1.7 |
| 282 | f5-b1-5-45455-11011 | 5 | `x^4+y^5+z^4+t^5+u^5+v*x*y*t*u` | 2,245 | 2.1 |
| 283 | f5-b1-5-45654-00120 | 5 | `x^4+y^5+z^6+t^5+u^4+v*z*t^2` | 5,489 | 2.6 |
| 284 | f5-b1-5-53344-11000 | 5 | `x^5+y^3+z^3+t^4+u^4+v*x*y` | 5,613 | 3.1 |
| 285 | f5-b1-5-53535-01101 | 5 | `x^5+y^3+z^5+t^3+u^5+v*y*z*u` | 1,254 | 1.0 |
| 286 | f5-b1-5-54355-10002 | 5 | `x^5+y^4+z^3+t^5+u^5+v*x*u^2` | 17,646 | 17.7 |
| 287 | f5-b1-5-63345-00111 | 5 | `x^6+y^3+z^3+t^4+u^5+v*z*t*u` | 6,623 | 5.8 |
| 288 | f5-b1-5-65544-11020 | 5 | `x^6+y^5+z^5+t^4+u^4+v*x*y*t^2` | 8,635 | 8.0 |
| 289 | f5-b1-5-65633-01201 | 5 | `x^6+y^5+z^6+t^3+u^3+v*y*z^2*u` | 2,063 | 1.7 |
