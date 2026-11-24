# Fourfolds and fivefolds without a Zoo record

These 628 germs of the [fourfold and fivefold screen](fourfold-fivefold-screen.md) have no complete Zoo record. All of them reached the 50-second budget, which is the only reason a germ of this screen has no record: none ended with a solver diagnostic or an unresolved pole check. [Per-case data](fourfold-fivefold-screen.json)

## Timeouts by family and step

| Family | Fourfolds | Fivefolds | Embedded resolution | Intrinsic resolution | Pole-check replay | Record assembly |
| --- | ---: | ---: | ---: | ---: | ---: | ---: |
| I02: Invertible polynomials: sums of chain, loop and Fermat blocks | 1 | 39 | 36 | 4 | 0 | 0 |
| I03: Arnold's simple, unimodal and bimodal germs and two-pair branches, stabilised by squares | 2 | 2 | 4 | 0 | 0 | 0 |
| I04: Joins of curve and surface germs in separate variables | 5 | 19 | 16 | 8 | 0 | 0 |
| I05: Cusps: a sum of powers plus the product of all variables | 14 | 35 | 43 | 5 | 0 | 1 |
| I06: Convenient Newton polyhedra with mixed monomials under the diagonal | 0 | 2 | 0 | 2 | 0 | 0 |
| I07: Cones over hypersurfaces of degree 3 and more | 6 | 5 | 10 | 1 | 0 | 0 |
| I08: Superisolated germs over hypersurfaces with isolated singular points | 2 | 6 | 8 | 0 | 0 | 0 |
| I09: Hidden coordinates: a known germ after a linear or triangular change of coordinates | 5 | 8 | 11 | 0 | 2 | 0 |
| N01: A monomial in k variables plus powers of the others | 2 | 6 | 3 | 5 | 0 | 0 |
| N02: Sums of monomials in disjoint groups of variables | 0 | 8 | 2 | 6 | 0 | 0 |
| N03: Non-isolated chains and loops | 23 | 36 | 32 | 10 | 17 | 0 |
| N04: Partial cusps: a product of distinct variables plus powers of some variables | 2 | 13 | 10 | 4 | 0 | 1 |
| N05: Transverse compositions h^j + powers along a singular hypersurface of a coordinate subspace | 28 | 38 | 52 | 14 | 0 | 0 |
| N06: Cones over singular hypersurfaces: a prescribed double or triple point, and classical examples | 15 | 18 | 26 | 2 | 5 | 0 |
| N07: Essential central hyperplane arrangements, one per intersection lattice | 40 | 39 | 27 | 52 | 0 | 0 |
| N08: Products of germs in separate variables | 41 | 49 | 61 | 29 | 0 | 0 |
| N09: Line singularities joined with isolated germs, and generalised Whitney umbrellas | 0 | 1 | 1 | 0 | 0 | 0 |
| N10: Suspensions of threefolds and surfaces of the catalogue | 11 | 11 | 19 | 3 | 0 | 0 |
| N11: Newton polyhedra with a B1 facet | 3 | 12 | 1 | 2 | 12 | 0 |
| N13: Random Newton polyhedra, singular along a coordinate subspace | 39 | 42 | 51 | 17 | 13 | 0 |

## Why these germs run out of time

The causes below were found while the solver was being fixed, by running examples of each family alone, without the six-way load of the screen.

- **Very large Newton fans** (I05, I02 in six variables, I04). The fan is verified chart by chart, at about 0.65 ms per chart in five variables and 1 ms in six. The cusp `x^3+y^6+z^7+t^7+u^9+v^11+x*y*z*t*u*v` has 58,053 charts and takes 57 s for the embedded step alone. Chains and loops in six variables have fans of 100,000 to 550,000 cones.
- **Arrangements and products: the intrinsic step** (N07, N08). The embedded resolution of an arrangement finishes in about 10 s by the fan of hyperplanes, which is an embedded method. For the intrinsic resolution of a reducible germ the smooth-centre rules reach a smooth model, but the exceptional complex on it is not certified in time.
- **A repeated factor that is not a graph** (N05, and some of N08 and N10). In `(x^3-y^4)^2+z^2+t^3+u^3` no polynomial change of coordinates makes `x^3-y^4` a coordinate. No Newton fan applies, and the smooth-centre rules need many blowups.
- **Singular lines that are not coordinate lines** (N06, I08). The cone `u*(x*y-z*t)+x^3+y^3+z^3+t^3` is singular along ten lines, nine of them not coordinate, so it is not toric in any frame.
- **Sparse polynomials with degenerate faces** (N13, N03). The search for adapted coordinates has 8 seconds and at most 64 frames. When it finds none, the smooth-centre rules take over, and the complete rule can spend more than its turn on one choice of centre.
- **Pole-check replay.** Both resolutions and both zeta functions were computed. The quick check left a pole without a witness, and the exhaustive search for nearby strata did not end within the budget.
- **Record assembly.** Two germs finished every step in about 49.5 s and were cut while their record was written.

## Timeouts (628)

At the cutoff, 413 were in the embedded resolution, 164 were in the intrinsic resolution, 49 were in the pole-check replay, 2 were in the record assembly. The last column lists the steps that had already finished, excluding the local dimension check.

### Fourfolds (239)

| # | ID | Equation | Running at 50 s | Time in step (s) | Finished steps (s) |
| ---: | --- | --- | --- | ---: | --- |
| 1 | f4-invertible-c4f-44445 | `x^4*y+y^4*z+z^4*t+t^4+u^5` | embedded resolution | 49.8 | none |
| 2 | f4-stable-branch-4-6-13 | `(y^2-x^3)^2+x^5*y+z^2+t^2+u^2` | embedded resolution | 49.8 | none |
| 3 | f4-stable-branch-4-6-15 | `(y^2-x^3)^2+x^6*y+z^2+t^2+u^2` | embedded resolution | 49.9 | none |
| 4 | f4-join-branch-4-6-13-branch-4-6-13-4 | `(y^2-x^3)^2+x^5*y+(t^2-z^3)^2+z^5*t+u^4` | embedded resolution | 49.8 | none |
| 5 | f4-join-e13-branch-4-6-13-2 | `x^3+x*y^5+(t^2-z^3)^2+z^5*t+u^2` | embedded resolution | 49.9 | none |
| 6 | f4-join-e19-branch-4-6-13-3 | `x^3+x*y^7+(t^2-z^3)^2+z^5*t+u^3` | embedded resolution | 49.9 | none |
| 7 | f4-join-t245-branch-4-6-13-4 | `x^4+x^2*y^2+y^5+(t^2-z^3)^2+z^5*t+u^4` | embedded resolution | 49.8 | none |
| 8 | f4-join-z13-branch-4-6-13-2 | `x^3*y+y^6+(t^2-z^3)^2+z^5*t+u^2` | embedded resolution | 49.9 | none |
| 9 | f4-cusp-4-4-7-8-9 | `x^4+y^4+z^7+t^8+u^9+x*y*z*t*u` | embedded resolution | 49.8 | none |
| 10 | f4-cusp-4-6-8-8-9 | `x^4+y^6+z^8+t^8+u^9+x*y*z*t*u` | intrinsic resolution | 29.6 | embedded resolution 20.2 |
| 11 | f4-cusp-4-7-7-9-9 | `x^4+y^7+z^7+t^9+u^9+x*y*z*t*u` | embedded resolution | 49.8 | none |
| 12 | f4-cusp-5-5-5-7-8 | `x^5+y^5+z^5+t^7+u^8+x*y*z*t*u` | intrinsic resolution | 8.6 | embedded resolution 41.2 |
| 13 | f4-cusp-5-5-6-6-7 | `x^5+y^5+z^6+t^6+u^7+x*y*z*t*u` | record assembly |  | embedded resolution 24.9, intrinsic resolution 24.5, Milnor number 0.0, Tjurina number 0.0 |
| 14 | f4-cusp-5-5-6-7-8 | `x^5+y^5+z^6+t^7+u^8+x*y*z*t*u` | embedded resolution | 49.9 | none |
| 15 | f4-cusp-5-5-7-9-9 | `x^5+y^5+z^7+t^9+u^9+x*y*z*t*u` | embedded resolution | 49.9 | none |
| 16 | f4-cusp-5-5-8-8-9 | `x^5+y^5+z^8+t^8+u^9+x*y*z*t*u` | embedded resolution | 49.9 | none |
| 17 | f4-cusp-5-6-6-7-7 | `x^5+y^6+z^6+t^7+u^7+x*y*z*t*u` | embedded resolution | 49.9 | none |
| 18 | f4-cusp-6-6-7-8-9 | `x^6+y^6+z^7+t^8+u^9+x*y*z*t*u` | embedded resolution | 49.9 | none |
| 19 | f4-cusp-6-6-7-9-9 | `x^6+y^6+z^7+t^9+u^9+x*y*z*t*u` | embedded resolution | 49.9 | none |
| 20 | f4-cusp-6-7-7-7-8 | `x^6+y^7+z^7+t^7+u^8+x*y*z*t*u` | embedded resolution | 49.9 | none |
| 21 | f4-cusp-7-7-7-8-8 | `x^7+y^7+z^7+t^8+u^8+x*y*z*t*u` | intrinsic resolution | 12.3 | embedded resolution 37.6 |
| 22 | f4-cusp-7-7-8-8-9 | `x^7+y^7+z^8+t^8+u^9+x*y*z*t*u` | embedded resolution | 49.9 | none |
| 23 | f4-cone-degree-4-11 | `x^4+y^4+z^4+t^4+u^4+2*y*z*t^2-2*x*y*u^2` | embedded resolution | 49.9 | none |
| 24 | f4-cone-degree-4-12 | `x^4+y^4+z^4+t^4+u^4+3*x^2*z*u-2*x*y*t^2` | embedded resolution | 49.9 | none |
| 25 | f4-cone-degree-4-2 | `x^4+y^4+z^4+t^4+u^4-2*x*y^2*t-y^2*z*t-t^3*u` | embedded resolution | 49.8 | none |
| 26 | f4-cone-degree-4-3 | `x^4+y^4+z^4+t^4+u^4-2*x*y^2*u+y*z^2*u-y^3*z` | embedded resolution | 49.9 | none |
| 27 | f4-cone-degree-4-8 | `x^4+y^4+z^4+t^4+u^4-z^3*u-2*x*z^2*u+3*x^3*t` | embedded resolution | 49.9 | none |
| 28 | f4-cone-degree-4-9 | `x^4+y^4+z^4+t^4+u^4-2*x*z^2*u+x*t*u^2+2*x^2*z^2` | intrinsic resolution | 49.1 | embedded resolution 0.7 |
| 29 | f4-superisolated-quartic-triple-generic | `u*(x^3+y^3+z^3+t^3)+x^4+y^4+z^4+t^4+(x+2*y+3*z+5*t+7*u)^5` | embedded resolution | 49.9 | none |
| 30 | f4-superisolated-segre-generic | `x^3+y^3+z^3+t^3+u^3-(x+y+z+t+u)^3+(x+2*y+3*z+5*t+7*u)^4` | embedded resolution | 49.9 | none |
| 31 | f4-hidden-plane-quadratic-tu | `x^2*y^2*z^6+3*x^2*y^2*z^4*u+2*x*y*z^6*t+3*x^2*y^2*z^2*u^2+6*x*y*z^4*t*u+z^6*t^2+x^2*y^2*u^3+6*x*y*z^…` | pole-check replay | 49.3 | embedded resolution 0.3, intrinsic resolution 0.3 |
| 32 | f4-hidden-xyz-rotation | `t^6+3*t^4*u+3*t^2*u^2+x^2*z-y^2*z+t^3+u^3` | embedded resolution | 49.9 | none |
| 33 | f4-hidden-xyz-shear-u | `x^3+3*x^2*y+3*x^2*z+3*x^2*t+3*x^2*u+3*x*y^2+7*x*y*z+6*x*y*t+6*x*y*u+3*x*z^2+6*x*z*t+6*x*z*u+3*x*t^2+…` | embedded resolution | 49.9 | none |
| 34 | f4-hidden-xyz-shear-xy | `x*y*z+y^2*z+t^3+u^3` | embedded resolution | 49.9 | none |
| 35 | f4-hidden-xyz-two-shears | `x*y*z+x*y*t+y^2*z+y^2*t+t^3+u^3` | embedded resolution | 49.8 | none |
| 36 | f4-monomial-311-34 | `x^3*y*z+t^3+u^4` | intrinsic resolution | 47.4 | embedded resolution 2.5 |
| 37 | f4-monomial-411-34 | `x^4*y*z+t^3+u^4` | intrinsic resolution | 47.9 | embedded resolution 2.1 |
| 38 | f4-chain-1112-2222-3 | `x*y^2+y*z^2+z*t^2+t^2*u^2+u^3` | embedded resolution | 49.9 | none |
| 39 | f4-chain-1121-2221-3 | `x*y^2+y*z^2+z^2*t^2+t*u+u^3` | intrinsic resolution | 9.8 | embedded resolution 40.1 |
| 40 | f4-chain-2331-2122-5 | `x^2*y^2+y^3*z+z^3*t^2+t*u^2+u^5` | pole-check replay | 46.4 | embedded resolution 1.9, intrinsic resolution 1.6 |
| 41 | f4-chain-3132-2211-5 | `x^3*y^2+y*z^2+z^3*t+t^2*u+u^5` | pole-check replay | 46.1 | embedded resolution 2.2, intrinsic resolution 1.6 |
| 42 | f4-chain-3133-1222-3 | `x^3*y+y*z^2+z^3*t^2+t^3*u^2+u^3` | embedded resolution | 49.9 | none |
| 43 | f4-chain-3133-1222-4 | `x^3*y+y*z^2+z^3*t^2+t^3*u^2+u^4` | embedded resolution | 49.9 | none |
| 44 | f4-chain-3133-2212-5 | `x^3*y^2+y*z^2+z^3*t+t^3*u^2+u^5` | pole-check replay | 43.9 | embedded resolution 2.9, intrinsic resolution 3.1 |
| 45 | f4-chain-3233-2112-5 | `x^3*y^2+y^2*z+z^3*t+t^3*u^2+u^5` | intrinsic resolution | 46.2 | embedded resolution 3.6 |
| 46 | f4-chain-3312-2122-5 | `x^3*y^2+y^3*z+z*t^2+t^2*u^2+u^5` | embedded resolution | 49.9 | none |
| 47 | f4-loop-1113-2211-2 | `x*y^2+y*z^2+z*t+t^3*u+u^2*x` | embedded resolution | 49.9 | none |
| 48 | f4-loop-1113-2211-4 | `x*y^2+y*z^2+z*t+t^3*u+u^4*x` | embedded resolution | 49.9 | none |
| 49 | f4-loop-1122-2212-3 | `x*y^2+y*z^2+z^2*t+t^2*u^2+u^3*x` | embedded resolution | 49.9 | none |
| 50 | f4-loop-1311-2112-5 | `x*y^2+y^3*z+z*t+t*u^2+u^5*x` | embedded resolution | 49.9 | none |
| 51 | f4-loop-1312-1112-5 | `x*y+y^3*z+z*t+t^2*u^2+u^5*x` | intrinsic resolution | 6.6 | embedded resolution 43.2 |
| 52 | f4-loop-1332-2212-5 | `x*y^2+y^3*z^2+z^3*t+t^2*u^2+u^5*x` | embedded resolution | 49.8 | none |
| 53 | f4-loop-2312-2222-5 | `x^2*y^2+y^3*z^2+z*t^2+t^2*u^2+u^5*x` | pole-check replay | 43.9 | embedded resolution 2.9, intrinsic resolution 3.2 |
| 54 | f4-loop-3212-2212-3 | `x^3*y^2+y^2*z^2+z*t+t^2*u^2+u^3*x` | pole-check replay | 37.6 | embedded resolution 5.6, intrinsic resolution 6.6 |
| 55 | f4-loop-3231-1222-3 | `x^3*y+y^2*z^2+z^3*t^2+t*u^2+u^3*x` | pole-check replay | 37.4 | embedded resolution 4.2, intrinsic resolution 8.2 |
| 56 | f4-loop-3322-2212-5 | `x^3*y^2+y^3*z^2+z^2*t+t^2*u^2+u^5*x` | pole-check replay | 15.9 | embedded resolution 14.3, intrinsic resolution 19.6 |
| 57 | f4-loop-3322-2221-5 | `x^3*y^2+y^3*z^2+z^2*t^2+t^2*u+u^5*x` | pole-check replay | 25.4 | embedded resolution 12.4, intrinsic resolution 11.9 |
| 58 | f4-loop-3322-2222-5 | `x^3*y^2+y^3*z^2+z^2*t^2+t^2*u^2+u^5*x` | pole-check replay | 38.8 | embedded resolution 4.2, intrinsic resolution 6.9 |
| 59 | f4-loop-3323-2121-3 | `x^3*y^2+y^3*z+z^2*t^2+t^3*u+u^3*x` | pole-check replay | 24.7 | embedded resolution 8.5, intrinsic resolution 16.6 |
| 60 | f4-loop-3331-1121-5 | `x^3*y+y^3*z+z^3*t^2+t*u+u^5*x` | pole-check replay | 0.2 | embedded resolution 24.0, intrinsic resolution 25.6 |
| 61 | f4-partial-cusp-3-0-56 | `x*y*z+t^5+u^6` | intrinsic resolution | 28.6 | embedded resolution 21.3 |
| 62 | f4-partial-cusp-4-3-6665 | `x*y*z*t+x^6+y^6+z^6+u^5` | record assembly |  | embedded resolution 19.6, intrinsic resolution 29.2, Milnor number 0.0, Tjurina number 0.0 |
| 63 | f4-transverse-a13-2-22 | `(x^2+y^2+z^2)^2+t^2+u^2` | intrinsic resolution | 49.5 | embedded resolution 0.4 |
| 64 | f4-transverse-a13-3-24-b | `(x^2+y^2+z^2)^3+t^2+u^4` | embedded resolution | 49.9 | none |
| 65 | f4-transverse-a13-3-44 | `(x^2+y^2+z^2)^3+t^4+u^4` | embedded resolution | 49.9 | none |
| 66 | f4-transverse-a23-2-23 | `(x^2+y^2+z^3)^2+t^2+u^3` | embedded resolution | 49.9 | none |
| 67 | f4-transverse-a23-2-42-b | `(x^2+y^2+z^3)^2+t^4+u^2` | intrinsic resolution | 48.5 | embedded resolution 1.4 |
| 68 | f4-transverse-a23-3-32 | `(x^2+y^2+z^3)^3+t^3+u^2` | embedded resolution | 49.9 | none |
| 69 | f4-transverse-a23-3-44-b | `(x^2+y^2+z^3)^3+t^4+u^4` | embedded resolution | 49.9 | none |
| 70 | f4-transverse-a24-2-3 | `(x^2+y^2+z^2+t^3)^2+u^3` | embedded resolution | 49.8 | none |
| 71 | f4-transverse-a24-2-4-b | `(x^2+y^2+z^2+t^3)^2+u^4` | intrinsic resolution | 48.5 | embedded resolution 1.3 |
| 72 | f4-transverse-a24-3-2 | `(x^2+y^2+z^2+t^3)^3+u^2` | embedded resolution | 49.9 | none |
| 73 | f4-transverse-a24-3-3-b | `(x^2+y^2+z^2+t^3)^3+u^3` | intrinsic resolution | 48.5 | embedded resolution 1.3 |
| 74 | f4-transverse-ca24-2-4 | `(x*y+z^3+t^3)^2+u^4` | intrinsic resolution | 24.2 | embedded resolution 25.7 |
| 75 | f4-transverse-ca24-3-3-b | `(x*y+z^3+t^3)^3+u^3` | embedded resolution | 49.7 | none |
| 76 | f4-transverse-ca24-3-4 | `(x*y+z^3+t^3)^3+u^4` | embedded resolution | 49.8 | none |
| 77 | f4-transverse-cusp2-2-244-b | `(x^2-y^3)^2+z^2+t^4+u^4` | intrinsic resolution | 10.3 | embedded resolution 39.6 |
| 78 | f4-transverse-cusp2-2-344 | `(x^2-y^3)^2+z^3+t^4+u^4` | embedded resolution | 49.9 | none |
| 79 | f4-transverse-cusp2-3-434 | `(x^2-y^3)^3+z^4+t^3+u^4` | embedded resolution | 49.9 | none |
| 80 | f4-transverse-d43-2-23-b | `(x^2+y^3+z^3)^2+t^2+u^3` | embedded resolution | 49.9 | none |
| 81 | f4-transverse-d43-2-42 | `(x^2+y^3+z^3)^2+t^4+u^2` | intrinsic resolution | 42.8 | embedded resolution 7.0 |
| 82 | f4-transverse-d43-3-34 | `(x^2+y^3+z^3)^3+t^3+u^4` | embedded resolution | 49.8 | none |
| 83 | f4-transverse-d43-3-42-b | `(x^2+y^3+z^3)^3+t^4+u^2` | embedded resolution | 49.9 | none |
| 84 | f4-transverse-e62-2-233-b | `(x^3-y^4)^2+z^2+t^3+u^3` | embedded resolution | 49.9 | none |
| 85 | f4-transverse-e62-2-443 | `(x^3-y^4)^2+z^4+t^4+u^3` | embedded resolution | 49.9 | none |
| 86 | f4-transverse-e62-3-342 | `(x^3-y^4)^3+z^3+t^4+u^2` | embedded resolution | 49.8 | none |
| 87 | f4-transverse-two-2-2 | `(x^2+y^2+z^2)^2+(t^2-u^3)^2` | embedded resolution | 49.9 | none |
| 88 | f4-transverse-two-2-3 | `(x^2+y^2+z^2)^2+(t^2-u^3)^3` | embedded resolution | 49.9 | none |
| 89 | f4-transverse-two-3-2 | `(x^2+y^2+z^2)^3+(t^2-u^3)^2` | embedded resolution | 49.9 | none |
| 90 | f4-transverse-umbrella3-3-23 | `(x^2-y^2*z)^3+t^2+u^3` | embedded resolution | 49.9 | none |
| 91 | f4-binary-quartic-discriminant | `256*x^3*u^3-192*x^2*y*t*u^2-128*x^2*z^2*u^2+144*x^2*z*t^2*u-27*x^2*t^4+144*x*y^2*z*u^2-6*x*y^2*t^2*u…` | embedded resolution | 49.9 | none |
| 92 | f4-burkhardt-quartic | `x^4-x*y^3-x*z^3-x*t^3-x*u^3+3*y*z*t*u` | embedded resolution | 49.8 | none |
| 93 | f4-cone-cubic-node-fermat | `u*(x*y-z*t)+x^3+y^3+z^3+t^3` | embedded resolution | 49.9 | none |
| 94 | f4-cone-cubic-node-loop | `u*(x*y-z*t)+x^2*y+y^2*z+z^2*t+t^2*x` | embedded resolution | 49.9 | none |
| 95 | f4-cone-cubic-rank1-loop | `u*(x^2)+x^2*y+y^2*z+z^2*t+t^2*x` | pole-check replay | 6.2 | embedded resolution 21.3, intrinsic resolution 22.4 |
| 96 | f4-cone-cubic-rank2-loop | `u*(x*y)+x^2*y+y^2*z+z^2*t+t^2*x` | embedded resolution | 49.9 | none |
| 97 | f4-cone-cubic-rank3-loop | `u*(x*y-z^2)+x^2*y+y^2*z+z^2*t+t^2*x` | intrinsic resolution | 20.4 | embedded resolution 29.5 |
| 98 | f4-cone-cubic-sum-loop | `u*(x^2+y^2+z^2+t^2)+x^2*y+y^2*z+z^2*t+t^2*x` | embedded resolution | 49.8 | none |
| 99 | f4-cone-quartic-node | `u^2*(x*y-z*t)+x^4+y^4+z^4+t^4` | embedded resolution | 49.9 | none |
| 100 | f4-cone-quartic-triple-fermat | `u*(x^3+y^3+z^3+t^3)+x^4+y^4+z^4+t^4` | pole-check replay | 9.1 | embedded resolution 40.4, intrinsic resolution 0.4 |
| 101 | f4-cone-quartic-triple-loop | `u*(x^2*y+y^2*z+z^2*t+t^2*x)+x^4+y^4+z^4+t^4` | pole-check replay | 42.7 | embedded resolution 4.2, intrinsic resolution 3.0 |
| 102 | f4-cone-quartic-triple-mixed | `u*(x*y*z+z^3+t^3)+x^4+y^4+z^4+t^4` | pole-check replay | 48.7 | embedded resolution 0.6, intrinsic resolution 0.6 |
| 103 | f4-dwork-conifold | `x^5-5*x*y*z*t*u+y^5+z^5+t^5+u^5` | embedded resolution | 49.9 | none |
| 104 | f4-igusa-quartic | `-4*x^4-8*x^3*y-8*x^3*z-8*x^3*t-8*x^3*u-12*x^2*y^2-32*x^2*y*z-32*x^2*y*t-32*x^2*y*u-12*x^2*z^2-32*x^2…` | embedded resolution | 49.9 | none |
| 105 | f4-segre-cubic | `-3*x^2*y-3*x^2*z-3*x^2*t-3*x^2*u-3*x*y^2-6*x*y*z-6*x*y*t-6*x*y*u-3*x*z^2-6*x*z*t-6*x*z*u-3*x*t^2-6*x…` | embedded resolution | 49.8 | none |
| 106 | f4-arrangement-6-1 | `x*y*z*t*u*(x+y+z+t+u)` | intrinsic resolution | 39.6 | embedded resolution 10.3 |
| 107 | f4-arrangement-6-2 | `x*y*z*t*u*(x+y+z)` | intrinsic resolution | 37.1 | embedded resolution 12.6 |
| 108 | f4-arrangement-6-3 | `x*y*z*t*u*(x+y)` | intrinsic resolution | 49.6 | embedded resolution 0.2 |
| 109 | f4-arrangement-7-10 | `x*y*z*t*u*(y+z+u)*(x-z)` | intrinsic resolution | 39.6 | embedded resolution 10.4 |
| 110 | f4-arrangement-7-11 | `x*y*z*(x+z-t)*(x-y)*(x-y+u)*(x-y-u)` | intrinsic resolution | 31.3 | embedded resolution 18.6 |
| 111 | f4-arrangement-7-12 | `x*y*z*t*u*(x+y)*(z+t)` | intrinsic resolution | 49.2 | embedded resolution 0.7 |
| 112 | f4-arrangement-7-13 | `x*y*z*t*u*(x+y)*(x-y)` | intrinsic resolution | 49.6 | embedded resolution 0.3 |
| 113 | f4-arrangement-7-4 | `x*y*z*t*u*(x+y+z+t+u)*(x+2*y+3*z+4*t+5*u)` | intrinsic resolution | 36.7 | embedded resolution 13.2 |
| 114 | f4-arrangement-7-5 | `x*y*z*t*(y+t+u)*(x-u)*(x-z+t)` | intrinsic resolution | 36.6 | embedded resolution 13.2 |
| 115 | f4-arrangement-7-6 | `x*y*z*t*u*(y+t-u)*(x-z-t)` | intrinsic resolution | 39.5 | embedded resolution 10.4 |
| 116 | f4-arrangement-7-7 | `x*y*z*t*u*(x-z-u)*(x-z+t)` | intrinsic resolution | 36.2 | embedded resolution 13.7 |
| 117 | f4-arrangement-7-8 | `x*y*z*(x+y-t)*(x-z)*(z-u)*(z+t)` | intrinsic resolution | 38.9 | embedded resolution 10.7 |
| 118 | f4-arrangement-7-9 | `x*y*z*t*(y-z+u)*(x-z+u)*(x+z-u)` | intrinsic resolution | 36.7 | embedded resolution 13.2 |
| 119 | f4-arrangement-8-14 | `x*y*z*t*(z-t+u)*(y+z+u)*(x+y-t)*(x-y+u)` | intrinsic resolution | 1.6 | embedded resolution 48.3 |
| 120 | f4-arrangement-8-15 | `x*y*z*t*(x+y+t)*(x+t-u)*(y+z-t)*(y-z+u)` | intrinsic resolution | 20.7 | embedded resolution 29.3 |
| 121 | f4-arrangement-8-16 | `x*y*z*t*u*(y-t-u)*(x-z-u)*(x-z-t)` | intrinsic resolution | 30.7 | embedded resolution 19.1 |
| 122 | f4-arrangement-8-17 | `x*y*z*t*u*(z-t-u)*(x+y-u)*(x+y+t)` | intrinsic resolution | 21.1 | embedded resolution 28.7 |
| 123 | f4-arrangement-8-18 | `x*y*z*t*u*(x-z-u)*(x-t-u)*(x-z+t)` | intrinsic resolution | 25.9 | embedded resolution 23.9 |
| 124 | f4-arrangement-8-19 | `x*y*z*t*(x+t)*(y+t+u)*(x-z+u)*(x+t-u)` | intrinsic resolution | 39.2 | embedded resolution 10.6 |
| 125 | f4-arrangement-8-20 | `x*y*z*t*(y-z+t)*(x+z+u)*(x+y-u)*(z+t)` | intrinsic resolution | 38.9 | embedded resolution 10.9 |
| 126 | f4-arrangement-8-21 | `x*y*z*t*(y+t-u)*(x-y+z)*(y+t)*(x-t-u)` | embedded resolution | 49.8 | none |
| 127 | f4-arrangement-8-22 | `x*y*z*t*u*(y-t-u)*(x+z)*(x-z+t)` | intrinsic resolution | 36.0 | embedded resolution 13.9 |
| 128 | f4-arrangement-8-23 | `x*y*z*t*u*(x-t)*(x+z-u)*(x-y+u)` | intrinsic resolution | 38.9 | embedded resolution 10.9 |
| 129 | f4-arrangement-8-24 | `x*y*z*t*u*(y-z-t)*(y-z+u)*(y-z-u)` | intrinsic resolution | 32.5 | embedded resolution 17.3 |
| 130 | f4-arrangement-8-25 | `x*y*z*t*u*(x-z+t)*(x-y+t)*(x+z)` | intrinsic resolution | 31.0 | embedded resolution 18.8 |
| 131 | f4-arrangement-8-26 | `x*y*z*t*(y+t+u)*(y-z+u)*(x+t)*(y-z-t)` | embedded resolution | 49.9 | none |
| 132 | f4-arrangement-8-27 | `x*y*z*t*(y+z+u)*(x+t)*(x-t+u)*(y-t)` | intrinsic resolution | 38.8 | embedded resolution 11.0 |
| 133 | f4-arrangement-8-28 | `x*y*z*t*(x-y+t)*(x+z)*(x-t)*(y+t+u)` | intrinsic resolution | 39.1 | embedded resolution 10.7 |
| 134 | f4-arrangement-8-29 | `x*y*z*t*u*(x-z-t)*(x-u)*(x-y)` | intrinsic resolution | 39.1 | embedded resolution 10.8 |
| 135 | f4-arrangement-8-30 | `x*y*z*t*(x+y)*(x-y+u)*(x-y-z)*(y-z)` | intrinsic resolution | 39.5 | embedded resolution 10.4 |
| 136 | f4-arrangement-8-31 | `x*y*z*t*u*(t+u)*(y+t-u)*(x-y)` | intrinsic resolution | 39.0 | embedded resolution 10.8 |
| 137 | f4-arrangement-8-32 | `x*y*z*t*u*(x-y)*(z+t)*(x-t-u)` | intrinsic resolution | 39.1 | embedded resolution 10.8 |
| 138 | f4-arrangement-8-33 | `x*y*z*t*u*(x-y-t)*(z+t)*(y-z)` | intrinsic resolution | 23.2 | embedded resolution 26.6 |
| 139 | f4-arrangement-8-34 | `x*y*z*t*(y-t)*(x-z-u)*(y+t)*(x+u)` | intrinsic resolution | 39.5 | embedded resolution 10.3 |
| 140 | f4-arrangement-8-35 | `x*y*z*t*u*(y+z+t)*(y-t)*(y+z)` | intrinsic resolution | 25.4 | embedded resolution 24.4 |
| 141 | f4-arrangement-8-36 | `x*y*z*t*u*(x+y)*(x-u)*(x-t-u)` | intrinsic resolution | 18.4 | embedded resolution 31.4 |
| 142 | f4-arrangement-8-37 | `x*y*z*t*u*(x-z-u)*(x-z)*(y-t)` | embedded resolution | 49.9 | none |
| 143 | f4-arrangement-8-38 | `x*y*z*t*u*(x-u)*(z-u)*(z+u)` | intrinsic resolution | 37.6 | embedded resolution 12.3 |
| 144 | f4-arrangement-8-39 | `x*y*z*t*u*(x+z)*(t+u)*(t-u)` | intrinsic resolution | 39.1 | embedded resolution 10.7 |
| 145 | f4-arrangement-8-40 | `x*y*z*t*u*(y+z-u)*(z-u)*(y+z)` | intrinsic resolution | 17.7 | embedded resolution 32.2 |
| 146 | f4-product-a42-a13 | `(x^2-y^5)*(z^2+t^2+u^2)` | embedded resolution | 49.8 | none |
| 147 | f4-product-a42-a23 | `(x^2-y^5)*(z^2+t^2+u^3)` | embedded resolution | 49.9 | none |
| 148 | f4-product-a42-cubic3 | `(x^2-y^5)*(z^3+t^3+u^3)` | embedded resolution | 49.9 | none |
| 149 | f4-product-a42-d43 | `(x^2-y^5)*(z^2+t^3+u^3)` | embedded resolution | 49.8 | none |
| 150 | f4-product-a42-t4443 | `(x^2-y^5)*(z*t*u+z^4+t^4+u^4)` | embedded resolution | 49.9 | none |
| 151 | f4-product-a42-umbrella3 | `(x^2-y^5)*(z^2-t^2*u)` | embedded resolution | 49.8 | none |
| 152 | f4-product-cusp2-a23 | `(x^2-y^3)*(z^2+t^2+u^3)` | embedded resolution | 49.7 | none |
| 153 | f4-product-cusp2-cubic3 | `(x^2-y^3)*(z^3+t^3+u^3)` | embedded resolution | 49.8 | none |
| 154 | f4-product-cusp2-d43 | `(x^2-y^3)*(z^2+t^3+u^3)` | embedded resolution | 49.9 | none |
| 155 | f4-product-cusp2-t4443 | `(x^2-y^3)*(z*t*u+z^4+t^4+u^4)` | embedded resolution | 49.8 | none |
| 156 | f4-product-cusp2-umbrella3 | `(x^2-y^3)*(z^2-t^2*u)` | embedded resolution | 49.9 | none |
| 157 | f4-product-d42-a23 | `(x^3-y^3)*(z^2+t^2+u^3)` | embedded resolution | 49.8 | none |
| 158 | f4-product-d42-cubic3 | `(x^3-y^3)*(z^3+t^3+u^3)` | embedded resolution | 49.8 | none |
| 159 | f4-product-d42-e63 | `(x^3-y^3)*(z^2+t^3+u^4)` | embedded resolution | 49.9 | none |
| 160 | f4-product-d42-umbrella3 | `(x^3-y^3)*(z^2-t^2*u)` | intrinsic resolution | 44.8 | embedded resolution 4.9 |
| 161 | f4-product-e62-a23 | `(x^3-y^4)*(z^2+t^2+u^3)` | embedded resolution | 49.9 | none |
| 162 | f4-product-e62-t4443 | `(x^3-y^4)*(z*t*u+z^4+t^4+u^4)` | embedded resolution | 49.9 | none |
| 163 | f4-product-e62-umbrella3 | `(x^3-y^4)*(z^2-t^2*u)` | embedded resolution | 49.9 | none |
| 164 | f4-product-h1-a24 | `x*(y^2+z^2+t^2+u^3)` | intrinsic resolution | 49.8 | embedded resolution 0.1 |
| 165 | f4-product-h1-a42-a42 | `x*(y^2-z^5)*(t^2-u^5)` | embedded resolution | 49.9 | none |
| 166 | f4-product-h1-a42-d42 | `x*(y^2-z^5)*(t^3-u^3)` | embedded resolution | 49.9 | none |
| 167 | f4-product-h1-a42-e62 | `x*(y^2-z^5)*(t^3-u^4)` | embedded resolution | 49.9 | none |
| 168 | f4-product-h1-ca24 | `x*(y*z+t^3+u^3)` | intrinsic resolution | 48.6 | embedded resolution 1.2 |
| 169 | f4-product-h1-cusp2-cusp2 | `x*(y^2-z^3)*(t^2-u^3)` | embedded resolution | 49.9 | none |
| 170 | f4-product-h1-cusp2-e62 | `x*(y^2-z^3)*(t^3-u^4)` | embedded resolution | 49.9 | none |
| 171 | f4-product-h1-cusp2-node2 | `x*(y^2-z^3)*(t^2-u^2)` | intrinsic resolution | 49.6 | embedded resolution 0.3 |
| 172 | f4-product-h1-d42-e62 | `x*(y^3-z^3)*(t^3-u^4)` | embedded resolution | 49.9 | none |
| 173 | f4-product-h1-d42-node2 | `x*(y^3-z^3)*(t^2-u^2)` | intrinsic resolution | 49.5 | embedded resolution 0.4 |
| 174 | f4-product-h1-e62-node2 | `x*(y^3-z^4)*(t^2-u^2)` | intrinsic resolution | 49.6 | embedded resolution 0.3 |
| 175 | f4-product-h1-h1-a13 | `x*y*(z^2+t^2+u^2)` | intrinsic resolution | 49.7 | embedded resolution 0.2 |
| 176 | f4-product-h1-h1-a23 | `x*y*(z^2+t^2+u^3)` | intrinsic resolution | 49.0 | embedded resolution 0.6 |
| 177 | f4-product-h1-h1-cubic3 | `x*y*(z^3+t^3+u^3)` | intrinsic resolution | 49.6 | embedded resolution 0.2 |
| 178 | f4-product-h1-h1-d43 | `x*y*(z^2+t^3+u^3)` | intrinsic resolution | 49.6 | embedded resolution 0.2 |
| 179 | f4-product-h1-h1-e63 | `x*y*(z^2+t^3+u^4)` | intrinsic resolution | 49.7 | embedded resolution 0.2 |
| 180 | f4-product-h1-h1-t4443 | `x*y*(z*t*u+z^4+t^4+u^4)` | intrinsic resolution | 49.1 | embedded resolution 0.6 |
| 181 | f4-product-h1-h1-umbrella3 | `x*y*(z^2-t^2*u)` | intrinsic resolution | 49.5 | embedded resolution 0.4 |
| 182 | f4-product-h1-node2-node2 | `x*(y^2-z^2)*(t^2-u^2)` | intrinsic resolution | 49.7 | embedded resolution 0.1 |
| 183 | f4-product-node2-a13 | `(x^2-y^2)*(z^2+t^2+u^2)` | intrinsic resolution | 48.9 | embedded resolution 1.0 |
| 184 | f4-product-node2-cubic3 | `(x^2-y^2)*(z^3+t^3+u^3)` | embedded resolution | 49.8 | none |
| 185 | f4-product-node2-t4443 | `(x^2-y^2)*(z*t*u+z^4+t^4+u^4)` | embedded resolution | 49.9 | none |
| 186 | f4-product-node2-umbrella3 | `(x^2-y^2)*(z^2-t^2*u)` | intrinsic resolution | 49.6 | embedded resolution 0.3 |
| 187 | f4-suspension-ns-cover-3-3-x-par-s14 | `z^3-(x)*(y+x^2)^3+t^2+u^3` | embedded resolution | 49.9 | none |
| 188 | f4-suspension-ns-jump-z11-1-3-2-s12 | `x^3*y+y^5+z^2*x*y^3+t^3+u^3` | intrinsic resolution | 49.4 | embedded resolution 0.5 |
| 189 | f4-suspension-ns-transverse-3-3-e8-s9 | `x^3+(y^3-z^5)^3+t^3+u^3` | intrinsic resolution | 48.2 | embedded resolution 1.6 |
| 190 | f4-suspension-ns-transverse-5-2-e7-s16 | `x^5+(y^3+y*z^3)^2+t^2+u^2` | embedded resolution | 49.9 | none |
| 191 | f4-suspension-nt-transverse-3-2-a1-30 | `x^3+(y^2+z^2+t^2)^2+u^3` | embedded resolution | 49.8 | none |
| 192 | f4-suspension-nt-transverse-4-2-a1-35 | `x^4+(y^2+z^2+t^2)^2+u^3` | embedded resolution | 49.8 | none |
| 193 | f4-suspension-s2-arrangement-8-37-s17 | `(x-y+z)*(x+y)*(x+y-z)*(x+2*y)*(y+z)*(y-z)*(x+y+z)*y+t^2+u^3` | embedded resolution | 49.9 | none |
| 194 | f4-suspension-s2-degenerate-a6-2-3-y-s26 | `(y^2-x^7)^2+z^3*y+t^2+u^3` | embedded resolution | 49.9 | none |
| 195 | f4-suspension-s2-image-quadruple-5-s21 | `x^8*y-2*x^4*y^2+4*x^2*y*z^2-z^4+y^3+t^3+u^3` | embedded resolution | 49.9 | none |
| 196 | f4-suspension-s2-trans-d6-cusp-s24 | `x^2*(y^2-z^3)+(y^2-z^3)^5+t^3+u^3` | embedded resolution | 49.9 | none |
| 197 | f4-suspension-t-cover-doubled-quadric-10 | `x^2+(y*z-t^2)^2+y^5+z^5+u^3` | embedded resolution | 49.9 | none |
| 198 | f4-b1-3-464-102-022 | `x^4+y^6+z^4+t*x*z^2+u*y^2*z^2` | pole-check replay | 47.3 | embedded resolution 0.7, intrinsic resolution 1.6 |
| 199 | f4-b1-4-3445-0103-2000-d | `x^3+y^4+z^4+t^5+u*y*t^3+u*x^2` | pole-check replay | 48.4 | embedded resolution 0.6, intrinsic resolution 0.9 |
| 200 | f4-b1-4-6665-1220 | `x^6+y^6+z^6+t^5+u*x*y^2*z^2` | pole-check replay | 42.4 | embedded resolution 3.4, intrinsic resolution 3.9 |
| 201 | f4-newton-1 | `3*x*z*t*u^2+2*x*z*t^3*u^2+x*y^3*z*t-x^2*z^2*t^2*u+2*x^3*y^3*t` | embedded resolution | 49.9 | none |
| 202 | f4-newton-11 | `-y*z^2*t*u^3-y^2*z^2*t*u^2+x*t^3*u^3-2*x*z^2*t-2*x^3*y*z*u^2` | embedded resolution | 49.8 | none |
| 203 | f4-newton-12 | `3*y*z*u-2*y^3*z*u^2+x*y^3*t*u+3*x^2*z^2*t^2*u+x^2*y*t^2*u^2-2*x^3*z*t^2*u` | intrinsic resolution | 45.1 | embedded resolution 4.8 |
| 204 | f4-newton-13 | `-2*y^3*t^3*u+3*x*t*u^2+3*x*y*z^2*u+2*x*y^3*z^2*u+2*x^2*z^3*u-2*x^3*y*z^2*u` | embedded resolution | 49.8 | none |
| 205 | f4-newton-15 | `t^3*u^2-y*z^3*u^3+y^2*z+3*x*z^3*u^3-x*y^2*z*t^2*u+x^2*y^2*t^3` | pole-check replay | 45.5 | embedded resolution 2.2, intrinsic resolution 2.0 |
| 206 | f4-newton-17 | `-z^3*u^2-y^2+2*y^2*z^2*t*u^2+x^2*z^2*u-x^3*u^3-2*x^3*t` | pole-check replay | 46.0 | embedded resolution 1.8, intrinsic resolution 2.1 |
| 207 | f4-newton-18 | `2*x*t^3*u^2+2*x*z*t^2+3*x*y^3*z^2*u-x^3*y*u^3` | intrinsic resolution | 42.9 | embedded resolution 7.0 |
| 208 | f4-newton-2 | `3*y^3*z*t^3-x*y*u+x^2*y*t*u^2+2*x^2*y^2*t^3-x^2*y^2*z^3-2*x^3*y*z*t*u` | pole-check replay | 38.2 | embedded resolution 7.2, intrinsic resolution 4.5 |
| 209 | f4-newton-21 | `y^2*z^2*t^2+2*x*y*z*u^2+x*y*z*t+3*x*y*z^2*u-x^2*y*z*u^3+3*x^3*y*t^3` | embedded resolution | 49.8 | none |
| 210 | f4-newton-22 | `y^2*z*t^3*u-2*x^2*u^3-x^2*y*z^2*t^2+x^3*z^2*t` | pole-check replay | 35.9 | embedded resolution 7.4, intrinsic resolution 6.5 |
| 211 | f4-newton-23 | `2*x*z^3*t-2*x*y*t*u^2-x^2*y*z*u+3*x^3*z^2*u^2+2*x^3*z^3-2*x^3*y*z*u` | intrinsic resolution | 33.1 | embedded resolution 16.8 |
| 212 | f4-newton-25 | `-2*y^3*z^3*t+x*z+3*x*y*z*t^2*u-x*y^3*u^3+x^2*t*u^3` | embedded resolution | 49.8 | none |
| 213 | f4-newton-26 | `-y^2*t^2*u-y^3*u^2-2*x*y*u+3*x^2*y^2*z^2-x^3*t*u^2+3*x^3*y^2*z*u` | embedded resolution | 49.9 | none |
| 214 | f4-newton-3 | `x*y^2*z+3*x*y^2*z^3+2*x^2*y^2*t^3+2*x^3*t*u^3-x^3*t^2*u` | pole-check replay | 17.5 | embedded resolution 21.7, intrinsic resolution 10.6 |
| 215 | f4-newton-30 | `2*z^2*u^3-2*y*z^2*t+x^2*y*z^2*t^2+3*x^2*y^2*t-x^3*t*u^3+x^3*y^2*z*t` | embedded resolution | 49.8 | none |
| 216 | f4-newton-31 | `z*t*u^3-2*x*z*t^3+x*y*z*t^2-x^2*z*u^2-2*x^3*z*t^3+x^3*y*z*t^2` | embedded resolution | 49.8 | none |
| 217 | f4-newton-32 | `-y*t^2*u+2*y*z^3*u-y^2*z*t-2*x*y^2*z^2*u^2+x^2*y*u^2-2*x^3*y^2*u` | embedded resolution | 49.9 | none |
| 218 | f4-newton-33 | `3*y^3*t*u^3-y^3*z^3+3*x*y^2*z^3*u-2*x^2*t*u+3*x^3*y*z*t^2` | embedded resolution | 49.8 | none |
| 219 | f4-newton-36 | `2*z^2*t*u+y*t^2*u+3*y^2*z^2*t*u+x*y*z-2*x*y^2*z^2*u-2*x^3*t^2*u^2` | embedded resolution | 49.8 | none |
| 220 | f4-newton-38 | `y*z^3*u+x*y*u-x*y*z*t^2*u^2+x*y^2*t^2*u-x^3*t^3*u` | embedded resolution | 49.9 | none |
| 221 | f4-newton-39 | `2*z^3*u^2+3*x*y*z^2*t*u^2+x*y^2*z^3+3*x^2*y^2*z*t^2` | pole-check replay | 38.4 | embedded resolution 11.1, intrinsic resolution 0.5 |
| 222 | f4-newton-4 | `3*z^3*t^3+3*y^2-y^2*z^2*u+x^2*t^2*u-2*x^3*y*t` | pole-check replay | 36.2 | embedded resolution 12.0, intrinsic resolution 1.6 |
| 223 | f4-newton-41 | `-x*z*t^3*u^2-2*x*y*z^2*u+3*x^2*z-2*x^2*y^2*t+x^3*y*t^3` | embedded resolution | 49.9 | none |
| 224 | f4-newton-42 | `2*z^2*u+3*y^3*z*t^2+3*x*z*u^3-2*x*y*z*t^3+3*x*y^2*t^3*u+3*x*y^2*z*t*u` | embedded resolution | 49.9 | none |
| 225 | f4-newton-43 | `3*z*t^3*u^3-x*z^3*t^2+x^2*y^2*z*t*u-x^2*y^3*u^2` | pole-check replay | 40.5 | embedded resolution 5.2, intrinsic resolution 4.2 |
| 226 | f4-newton-46 | `-z^3*t-2*x*z^2*t^2*u+x*y*t*u-2*x*y^2*t` | embedded resolution | 49.9 | none |
| 227 | f4-newton-47 | `3*z^3*u^3-2*x^2*y*z*t-x^3*z*t*u^2-x^3*y*z*u` | intrinsic resolution | 30.2 | embedded resolution 19.7 |
| 228 | f4-newton-48 | `y^2*t^2+x*y*z^2+3*x^2*y^3*z*t+3*x^3*y*z+3*x^3*y*z*t*u` | intrinsic resolution | 35.7 | embedded resolution 14.0 |
| 229 | f4-newton-49 | `3*z*t*u^2+3*z^3*t^3+3*y^3*u^2+2*x*t^3*u+x*z^3*t^2+x^2*z^3*t^2` | intrinsic resolution | 33.0 | embedded resolution 16.9 |
| 230 | f4-newton-51 | `-2*y*z*t^3+3*x*z^2*t^2*u^2-2*x*y*z^2*u^3+3*x^2*t^2*u-2*x^2*y*z^2*t` | embedded resolution | 49.9 | none |
| 231 | f4-newton-52 | `-z^2*t*u^2-z^2*t^2*u^3+y^2*t^3*u+x*y*z-x^2*y*z*u^3` | embedded resolution | 49.9 | none |
| 232 | f4-newton-53 | `y*t^3+2*y^3*z-x*y^3*u+2*x^2*z*t^2+2*x^2*z*t^3*u-2*x^3*y*u^3` | embedded resolution | 49.7 | none |
| 233 | f4-newton-54 | `-2*y^3*t^2*u+3*x*y*z^2*u^2+3*x^2*z*t^3-2*x^2*z^2*u^2` | pole-check replay | 29.9 | embedded resolution 9.8, intrinsic resolution 10.2 |
| 234 | f4-newton-57 | `-y^2*z*t-2*y^3*u+y^3*z*t^2*u+x^2*z^2*t^2*u+2*x^2*y*z^3` | pole-check replay | 44.2 | embedded resolution 2.3, intrinsic resolution 3.4 |
| 235 | f4-newton-58 | `y^2*z*u^3+3*x*y*z*t+x^2*t^2*u-2*x^3*z*t*u^2` | pole-check replay | 32.0 | embedded resolution 10.8, intrinsic resolution 7.0 |
| 236 | f4-newton-6 | `3*z^2*t^3*u+3*y*z*t*u^2+3*x*y^3*t^2*u-x^2*z*t^3*u+3*x^3*y*u^2` | intrinsic resolution | 21.0 | embedded resolution 28.9 |
| 237 | f4-newton-7 | `-2*x*y^2*z*t^3-x^2*u+x^2*t*u-2*x^3*z*u^3+x^3*y*u` | embedded resolution | 49.8 | none |
| 238 | f4-newton-8 | `2*y*z^2*t*u+2*y^2*t^2*u-2*x*y^2*t*u-x^2*y*u-x^2*y*z^2*u` | intrinsic resolution | 38.2 | embedded resolution 11.7 |
| 239 | f4-newton-9 | `3*y^2*z^3*t*u-x*y^2*z^3*u-x^2*z^2*t^2+3*x^2*y+x^2*y*z^2+3*x^3*t` | pole-check replay | 35.9 | embedded resolution 11.6, intrinsic resolution 2.4 |

### Fivefolds (389)

| # | ID | Equation | Running at 50 s | Time in step (s) | Finished steps (s) |
| ---: | --- | --- | --- | ---: | --- |
| 1 | f5-invertible-c3c2f-323445 | `x^3*y+y^2*z+z^3+t^4*u+u^4+v^5` | embedded resolution | 49.8 | none |
| 2 | f5-invertible-c3l3-242232 | `x^2*y+y^4*z+z^2+t^2*u+u^3*v+v^2*t` | intrinsic resolution | 12.8 | embedded resolution 37.0 |
| 3 | f5-invertible-c3l3-244334 | `x^2*y+y^4*z+z^4+t^3*u+u^3*v+v^4*t` | embedded resolution | 49.8 | none |
| 4 | f5-invertible-c3l3-333433 | `x^3*y+y^3*z+z^3+t^4*u+u^3*v+v^3*t` | embedded resolution | 49.9 | none |
| 5 | f5-invertible-c4c2-224423 | `x^2*y+y^2*z+z^4*t+t^4+u^2*v+v^3` | embedded resolution | 49.8 | none |
| 6 | f5-invertible-c4c2-322442 | `x^3*y+y^2*z+z^2*t+t^4+u^4*v+v^2` | embedded resolution | 49.8 | none |
| 7 | f5-invertible-c4c2-332434 | `x^3*y+y^3*z+z^2*t+t^4+u^3*v+v^4` | embedded resolution | 49.9 | none |
| 8 | f5-invertible-c4ff-234425 | `x^2*y+y^3*z+z^4*t+t^4+u^2+v^5` | embedded resolution | 49.9 | none |
| 9 | f5-invertible-c4l2-433432 | `x^4*y+y^3*z+z^3*t+t^4+u^3*v+v^2*u` | embedded resolution | 49.9 | none |
| 10 | f5-invertible-c4l2-442344 | `x^4*y+y^4*z+z^2*t+t^3+u^4*v+v^4*u` | embedded resolution | 49.8 | none |
| 11 | f5-invertible-c6-242244 | `x^2*y+y^4*z+z^2*t+t^2*u+u^4*v+v^4` | embedded resolution | 49.9 | none |
| 12 | f5-invertible-c6-334243 | `x^3*y+y^3*z+z^4*t+t^2*u+u^4*v+v^3` | embedded resolution | 49.9 | none |
| 13 | f5-invertible-c6-342422 | `x^3*y+y^4*z+z^2*t+t^4*u+u^2*v+v^2` | embedded resolution | 49.9 | none |
| 14 | f5-invertible-c6-433433 | `x^4*y+y^3*z+z^3*t+t^4*u+u^3*v+v^3` | embedded resolution | 49.9 | none |
| 15 | f5-invertible-l2l2l2-322442 | `x^3*y+y^2*x+z^2*t+t^4*z+u^4*v+v^2*u` | embedded resolution | 49.9 | none |
| 16 | f5-invertible-l2l2l2-423432 | `x^4*y+y^2*x+z^3*t+t^4*z+u^3*v+v^2*u` | embedded resolution | 49.9 | none |
| 17 | f5-invertible-l3c2f-223344 | `x^2*y+y^2*z+z^3*x+t^3*u+u^4+v^4` | intrinsic resolution | 15.1 | embedded resolution 34.7 |
| 18 | f5-invertible-l3c2f-433334 | `x^4*y+y^3*z+z^3*x+t^3*u+u^3+v^4` | embedded resolution | 49.9 | none |
| 19 | f5-invertible-l3l2f-244334 | `x^2*y+y^4*z+z^4*x+t^3*u+u^3*t+v^4` | embedded resolution | 49.9 | none |
| 20 | f5-invertible-l3l2f-334222 | `x^3*y+y^3*z+z^4*x+t^2*u+u^2*t+v^2` | embedded resolution | 49.9 | none |
| 21 | f5-invertible-l3l2f-424434 | `x^4*y+y^2*z+z^4*x+t^4*u+u^3*t+v^4` | embedded resolution | 49.9 | none |
| 22 | f5-invertible-l3l2f-443445 | `x^4*y+y^4*z+z^3*x+t^4*u+u^4*t+v^5` | embedded resolution | 49.8 | none |
| 23 | f5-invertible-l3l3-323224 | `x^3*y+y^2*z+z^3*x+t^2*u+u^2*v+v^4*t` | embedded resolution | 49.8 | none |
| 24 | f5-invertible-l3l3-344444 | `x^3*y+y^4*z+z^4*x+t^4*u+u^4*v+v^4*t` | embedded resolution | 49.9 | none |
| 25 | f5-invertible-l4c2-332323 | `x^3*y+y^3*z+z^2*t+t^3*x+u^2*v+v^3` | embedded resolution | 49.9 | none |
| 26 | f5-invertible-l4c2-442222 | `x^4*y+y^4*z+z^2*t+t^2*x+u^2*v+v^2` | embedded resolution | 49.8 | none |
| 27 | f5-invertible-l4c2-443422 | `x^4*y+y^4*z+z^3*t+t^4*x+u^2*v+v^2` | embedded resolution | 49.8 | none |
| 28 | f5-invertible-l4ff-222435 | `x^2*y+y^2*z+z^2*t+t^4*x+u^3+v^5` | embedded resolution | 49.9 | none |
| 29 | f5-invertible-l4ff-243234 | `x^2*y+y^4*z+z^3*t+t^2*x+u^3+v^4` | intrinsic resolution | 9.3 | embedded resolution 40.6 |
| 30 | f5-invertible-l4l2-344334 | `x^3*y+y^4*z+z^4*t+t^3*x+u^3*v+v^4*u` | embedded resolution | 49.9 | none |
| 31 | f5-invertible-l4l2-423342 | `x^4*y+y^2*z+z^3*t+t^3*x+u^4*v+v^2*u` | embedded resolution | 49.8 | none |
| 32 | f5-invertible-l4l2-434432 | `x^4*y+y^3*z+z^4*t+t^4*x+u^3*v+v^2*u` | embedded resolution | 49.9 | none |
| 33 | f5-invertible-l5f-224433 | `x^2*y+y^2*z+z^4*t+t^4*u+u^3*x+v^3` | embedded resolution | 49.7 | none |
| 34 | f5-invertible-l5f-233422 | `x^2*y+y^3*z+z^3*t+t^4*u+u^2*x+v^2` | intrinsic resolution | 20.0 | embedded resolution 29.9 |
| 35 | f5-invertible-l5f-333423 | `x^3*y+y^3*z+z^3*t+t^4*u+u^2*x+v^3` | embedded resolution | 49.9 | none |
| 36 | f5-invertible-l6-222432 | `x^2*y+y^2*z+z^2*t+t^4*u+u^3*v+v^2*x` | embedded resolution | 49.9 | none |
| 37 | f5-invertible-l6-224424 | `x^2*y+y^2*z+z^4*t+t^4*u+u^2*v+v^4*x` | embedded resolution | 49.9 | none |
| 38 | f5-invertible-l6-324442 | `x^3*y+y^2*z+z^4*t+t^4*u+u^4*v+v^2*x` | embedded resolution | 49.9 | none |
| 39 | f5-invertible-l6-434322 | `x^4*y+y^3*z+z^4*t+t^3*u+u^2*v+v^2*x` | embedded resolution | 49.9 | none |
| 40 | f5-stable-branch-4-6-13 | `(y^2-x^3)^2+x^5*y+z^2+t^2+u^2+v^2` | embedded resolution | 49.8 | none |
| 41 | f5-stable-branch-4-6-15 | `(y^2-x^3)^2+x^6*y+z^2+t^2+u^2+v^2` | embedded resolution | 49.9 | none |
| 42 | f5-join-d5-d6-d8 | `x^2*y+y^4+z^2*t+t^5+u^2*v+v^7` | embedded resolution | 49.9 | none |
| 43 | f5-join-d5-d7-j21 | `x^2*y+y^4+z^2*t+t^6+u^3+u^2*v^2+v^7` | intrinsic resolution | 0.4 | embedded resolution 49.5 |
| 44 | f5-join-d5-d7-t255 | `x^2*y+y^4+z^2*t+t^6+u^5+u^2*v^2+v^5` | embedded resolution | 49.9 | none |
| 45 | f5-join-d6-d7-d8 | `x^2*y+y^5+z^2*t+t^6+u^2*v+v^7` | embedded resolution | 49.8 | none |
| 46 | f5-join-d6-j21-e12 | `x^2*y+y^5+z^3+z^2*t^2+t^7+u^3+v^7+u*v^5` | intrinsic resolution | 2.8 | embedded resolution 47.0 |
| 47 | f5-join-d7-t245-e12 | `x^2*y+y^6+z^4+z^2*t^2+t^5+u^3+v^7+u*v^5` | intrinsic resolution | 16.0 | embedded resolution 33.9 |
| 48 | f5-join-d7-t255-t255 | `x^2*y+y^6+z^5+z^2*t^2+t^5+u^5+u^2*v^2+v^5` | intrinsic resolution | 9.7 | embedded resolution 40.2 |
| 49 | f5-join-q12-s11 | `x^3+y^5+y*z^2+t^4+u^2*v+t*v^2` | intrinsic resolution | 25.4 | embedded resolution 24.5 |
| 50 | f5-join-q17-s17 | `x^3+y*z^2+x*y^5+t^2*v+u*v^2+u^6` | intrinsic resolution | 17.8 | embedded resolution 32.1 |
| 51 | f5-join-s16-d4-2 | `x^2*z+y*z^2+x*y^4+t^2*u+u^3+v^2` | intrinsic resolution | 24.7 | embedded resolution 25.2 |
| 52 | f5-join-s16-t255-3 | `x^2*z+y*z^2+x*y^4+t^5+t^2*u^2+u^5+v^3` | embedded resolution | 49.9 | none |
| 53 | f5-join-t237-s16 | `x^2+y^3+z^7+x*y*z+t^2*v+u*v^2+t*u^4` | embedded resolution | 49.9 | none |
| 54 | f5-join-t334-s12 | `x^3+y^3+z^4+x*y*z+t^2*u+u^2*v+t*v^3` | intrinsic resolution | 24.2 | embedded resolution 25.7 |
| 55 | f5-join-t345-q16 | `x^3+y^4+z^5+x*y*z+t^3+u*v^2+u^7` | embedded resolution | 49.8 | none |
| 56 | f5-join-t345-q17 | `x^3+y^4+z^5+x*y*z+t^3+u*v^2+t*u^5` | embedded resolution | 49.7 | none |
| 57 | f5-join-t345-s16 | `x^3+y^4+z^5+x*y*z+t^2*v+u*v^2+t*u^4` | embedded resolution | 49.9 | none |
| 58 | f5-join-t345-t444 | `x^3+y^4+z^5+x*y*z+t^4+u^4+v^4+t*u*v` | embedded resolution | 49.9 | none |
| 59 | f5-join-u16-e19-4 | `x^3+x*z^2+y^5+t^3+t*u^7+v^4` | embedded resolution | 49.9 | none |
| 60 | f5-join-u16-z12-4 | `x^3+x*z^2+y^5+t^3*u+t*u^4+v^4` | embedded resolution | 49.8 | none |
| 61 | f5-cusp-3-5-7-9-10-10 | `x^3+y^5+z^7+t^9+u^10+v^10+x*y*z*t*u*v` | intrinsic resolution | 25.2 | embedded resolution 24.7 |
| 62 | f5-cusp-3-5-8-11-11-12 | `x^3+y^5+z^8+t^11+u^11+v^12+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 63 | f5-cusp-3-5-9-11-11-12 | `x^3+y^5+z^9+t^11+u^11+v^12+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 64 | f5-cusp-3-6-7-7-9-11 | `x^3+y^6+z^7+t^7+u^9+v^11+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 65 | f5-cusp-3-6-7-9-10-12 | `x^3+y^6+z^7+t^9+u^10+v^12+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 66 | f5-cusp-3-6-8-10-11-12 | `x^3+y^6+z^8+t^10+u^11+v^12+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 67 | f5-cusp-3-6-9-10-10-11 | `x^3+y^6+z^9+t^10+u^10+v^11+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 68 | f5-cusp-3-7-7-8-10-11 | `x^3+y^7+z^7+t^8+u^10+v^11+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 69 | f5-cusp-3-8-11-11-11-11 | `x^3+y^8+z^11+t^11+u^11+v^11+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 70 | f5-cusp-3-8-8-10-12-12 | `x^3+y^8+z^8+t^10+u^12+v^12+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 71 | f5-cusp-3-9-9-11-11-12 | `x^3+y^9+z^9+t^11+u^11+v^12+x*y*z*t*u*v` | embedded resolution | 49.7 | none |
| 72 | f5-cusp-4-11-11-11-11-12 | `x^4+y^11+z^11+t^11+u^11+v^12+x*y*z*t*u*v` | embedded resolution | 49.8 | none |
| 73 | f5-cusp-4-4-10-11-11-11 | `x^4+y^4+z^10+t^11+u^11+v^11+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 74 | f5-cusp-4-4-6-10-11-12 | `x^4+y^4+z^6+t^10+u^11+v^12+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 75 | f5-cusp-4-4-8-9-10-10 | `x^4+y^4+z^8+t^9+u^10+v^10+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 76 | f5-cusp-4-4-8-9-9-10 | `x^4+y^4+z^8+t^9+u^9+v^10+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 77 | f5-cusp-4-5-6-7-11-12 | `x^4+y^5+z^6+t^7+u^11+v^12+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 78 | f5-cusp-4-5-7-7-8-8 | `x^4+y^5+z^7+t^7+u^8+v^8+x*y*z*t*u*v` | intrinsic resolution | 28.6 | embedded resolution 21.3 |
| 79 | f5-cusp-4-5-9-9-11-11 | `x^4+y^5+z^9+t^9+u^11+v^11+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 80 | f5-cusp-4-6-10-10-11-12 | `x^4+y^6+z^10+t^10+u^11+v^12+x*y*z*t*u*v` | embedded resolution | 49.8 | none |
| 81 | f5-cusp-4-6-7-7-7-10 | `x^4+y^6+z^7+t^7+u^7+v^10+x*y*z*t*u*v` | embedded resolution | 49.8 | none |
| 82 | f5-cusp-4-6-7-8-8-11 | `x^4+y^6+z^7+t^8+u^8+v^11+x*y*z*t*u*v` | embedded resolution | 49.8 | none |
| 83 | f5-cusp-5-5-6-8-11-12 | `x^5+y^5+z^6+t^8+u^11+v^12+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 84 | f5-cusp-5-5-6-9-11-12 | `x^5+y^5+z^6+t^9+u^11+v^12+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 85 | f5-cusp-5-5-7-8-11-11 | `x^5+y^5+z^7+t^8+u^11+v^11+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 86 | f5-cusp-5-6-6-9-11-11 | `x^5+y^6+z^6+t^9+u^11+v^11+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 87 | f5-cusp-5-6-8-9-11-11 | `x^5+y^6+z^8+t^9+u^11+v^11+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 88 | f5-cusp-6-6-8-8-9-11 | `x^6+y^6+z^8+t^8+u^9+v^11+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 89 | f5-cusp-6-7-8-10-11-12 | `x^6+y^7+z^8+t^10+u^11+v^12+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 90 | f5-cusp-6-7-8-8-9-9 | `x^6+y^7+z^8+t^8+u^9+v^9+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 91 | f5-cusp-7-7-10-10-10-12 | `x^7+y^7+z^10+t^10+u^10+v^12+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 92 | f5-cusp-8-9-10-11-12-12 | `x^8+y^9+z^10+t^11+u^12+v^12+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 93 | f5-cusp-8-9-9-9-10-11 | `x^8+y^9+z^9+t^9+u^10+v^11+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 94 | f5-cusp-9-9-11-11-11-11 | `x^9+y^9+z^11+t^11+u^11+v^11+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 95 | f5-cusp-9-9-9-9-11-12 | `x^9+y^9+z^9+t^9+u^11+v^12+x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 96 | f5-newton-convenient-20 | `x^4+y^5+z^5+t^6+u^2+v^4+x*z*t^2+u*v+3*x*t*u-y*z*t` | intrinsic resolution | 12.7 | embedded resolution 37.2 |
| 97 | f5-newton-convenient-33 | `x^4+y^4+z^6+t^3+u^6+v^4-2*x*t+3*y*z*u+3*z^3*u` | intrinsic resolution | 13.7 | embedded resolution 36.2 |
| 98 | f5-cone-clebsch-cubic | `x^3+y^3+z^3+t^3+u^3+v^3-(x+y+z+t+u+v)^3` | embedded resolution | 49.9 | none |
| 99 | f5-cone-degree-4-1 | `x^4+y^4+z^4+t^4+u^4+v^4+x*u^3+2*y*u*v^2+x*t^2*v` | embedded resolution | 49.8 | none |
| 100 | f5-cone-degree-4-3 | `x^4+y^4+z^4+t^4+u^4+v^4-2*y^3*u+x^2*y*t-2*y^2*z*v` | embedded resolution | 49.8 | none |
| 101 | f5-cone-degree-4-5 | `x^4+y^4+z^4+t^4+u^4+v^4-2*x^3*t+3*y*t^2*u+x*y*t^2` | embedded resolution | 49.6 | none |
| 102 | f5-cone-dwork-2 | `x^6+y^6+z^6+t^6+u^6+v^6-12*x*y*z*t*u*v` | embedded resolution | 49.9 | none |
| 103 | f5-superisolated-a2-axis | `v*(x^2+y^2+z^2+t^2)+x^3+y^3+z^3+t^3+u^3+v^4` | embedded resolution | 49.9 | none |
| 104 | f5-superisolated-a2-generic | `v*(x^2+y^2+z^2+t^2)+x^3+y^3+z^3+t^3+u^3+(x+2*y+3*z+5*t+7*u+11*v)^4` | embedded resolution | 49.9 | none |
| 105 | f5-superisolated-node-axis | `v*(x^2+y^2+z^2+t^2+u^2)+x^3+y^3+z^3+t^3+u^3+v^4` | embedded resolution | 49.9 | none |
| 106 | f5-superisolated-node-generic | `v*(x^2+y^2+z^2+t^2+u^2)+x^3+y^3+z^3+t^3+u^3+(x+2*y+3*z+5*t+7*u+11*v)^4` | embedded resolution | 49.9 | none |
| 107 | f5-superisolated-quartic-node-axis | `v^2*(x^2+y^2+z^2+t^2+u^2)+x^4+y^4+z^4+t^4+u^4+v^5` | embedded resolution | 49.9 | none |
| 108 | f5-superisolated-quartic-triple-axis | `v*(x^3+y^3+z^3+t^3+u^3)+x^4+y^4+z^4+t^4+u^4+v^5` | embedded resolution | 49.9 | none |
| 109 | f5-hidden-chain-quadratic-u | `x^6+3*x^4*u+x^2*t^2+3*x^2*u^2+x^2*y+y^2*z+z^2*t+t^2*u+u^3+v^2` | embedded resolution | 49.9 | none |
| 110 | f5-hidden-chain-rotation | `t^6+3*t^4*u+t^4+3*t^2*u^2+x^3+x^2*y+x^2*z-x*y^2-2*x*y*z-y^3+y^2*z+z^2*t+t^2*u+u^3+v^2` | embedded resolution | 49.8 | none |
| 111 | f5-hidden-chain-shear-u | `x^3+4*x^2*y+3*x^2*z+3*x^2*t+3*x^2*u+3*x*y^2+6*x*y*z+6*x*y*t+6*x*y*u+3*x*z^2+6*x*z*t+6*x*z*u+4*x*t^2+…` | embedded resolution | 49.9 | none |
| 112 | f5-hidden-plane-quadratic-tu | `x^2*y^2*z^6+3*x^2*y^2*z^4*u+2*x*y*z^6*t+3*x^2*y^2*z^2*u^2+6*x*y*z^4*t*u+z^6*t^2+x^2*y^2*u^3+6*x*y*z^…` | pole-check replay | 49.3 | embedded resolution 0.2, intrinsic resolution 0.3 |
| 113 | f5-hidden-xyz-rotation | `t^6+3*t^4*u+3*t^2*u^2+x^2*z-y^2*z+t^3+u^3+v^2` | embedded resolution | 49.9 | none |
| 114 | f5-hidden-xyz-shear-u | `x^3+3*x^2*y+3*x^2*z+3*x^2*t+3*x^2*u+3*x*y^2+7*x*y*z+6*x*y*t+6*x*y*u+3*x*z^2+6*x*z*t+6*x*z*u+3*x*t^2+…` | embedded resolution | 49.9 | none |
| 115 | f5-hidden-xyz-shear-xy | `x*y*z+y^2*z+t^3+u^3+v^2` | embedded resolution | 49.9 | none |
| 116 | f5-hidden-xyz-two-shears | `x*y*z+x*y*t+y^2*z+y^2*t+t^3+u^3+v^2` | embedded resolution | 49.8 | none |
| 117 | f5-monomial-221-235 | `x^2*y^2*z+t^2+u^3+v^5` | embedded resolution | 49.8 | none |
| 118 | f5-monomial-3331-35 | `x^3*y^3*z^3*t+u^3+v^5` | embedded resolution | 49.9 | none |
| 119 | f5-monomial-3332-45 | `x^3*y^3*z^3*t^2+u^4+v^5` | intrinsic resolution | 15.5 | embedded resolution 34.4 |
| 120 | f5-monomial-411-235 | `x^4*y*z+t^2+u^3+v^5` | embedded resolution | 49.9 | none |
| 121 | f5-monomial-411-555 | `x^4*y*z+t^5+u^5+v^5` | intrinsic resolution | 48.5 | embedded resolution 1.4 |
| 122 | f5-monomial-432-235 | `x^4*y^3*z^2+t^2+u^3+v^5` | intrinsic resolution | 2.0 | embedded resolution 47.8 |
| 123 | f5-monomials-211-21-5 | `x^2*y*z+t^2*u+v^5` | intrinsic resolution | 13.5 | embedded resolution 36.4 |
| 124 | f5-monomials-211-33-4 | `x^2*y*z+t^3*u^3+v^4` | intrinsic resolution | 22.3 | embedded resolution 27.6 |
| 125 | f5-monomials-222-32-5 | `x^2*y^2*z^2+t^3*u^2+v^5` | embedded resolution | 49.9 | none |
| 126 | f5-monomials-311-21-3 | `x^3*y*z+t^2*u+v^3` | intrinsic resolution | 45.1 | embedded resolution 4.8 |
| 127 | f5-monomials-32-31-3-5 | `x^3*y^2+z^3*t+u^3+v^5` | intrinsic resolution | 31.2 | embedded resolution 18.7 |
| 128 | f5-monomials-322-31-5 | `x^3*y^2*z^2+t^3*u+v^5` | intrinsic resolution | 15.2 | embedded resolution 34.6 |
| 129 | f5-monomials-33-32-2-5 | `x^3*y^3+z^3*t^2+u^2+v^5` | intrinsic resolution | 7.1 | embedded resolution 42.8 |
| 130 | f5-monomials-331-21-5 | `x^3*y^3*z+t^2*u+v^5` | embedded resolution | 49.9 | none |
| 131 | f5-chain-11113-21222-5 | `x*y^2+y*z+z*t^2+t*u^2+u^3*v^2+v^5` | intrinsic resolution | 43.5 | embedded resolution 6.4 |
| 132 | f5-chain-11123-11211-5 | `x*y+y*z+z*t^2+t^2*u+u^3*v+v^5` | embedded resolution | 49.8 | none |
| 133 | f5-chain-13311-11121-5 | `x*y+y^3*z+z^3*t+t*u^2+u*v+v^5` | embedded resolution | 49.9 | none |
| 134 | f5-chain-13331-12122-3 | `x*y+y^3*z^2+z^3*t+t^3*u^2+u*v^2+v^3` | intrinsic resolution | 0.7 | embedded resolution 49.2 |
| 135 | f5-chain-13332-12212-4 | `x*y+y^3*z^2+z^3*t^2+t^3*u+u^2*v^2+v^4` | pole-check replay | 14.9 | embedded resolution 14.7, intrinsic resolution 20.4 |
| 136 | f5-chain-13333-12222-4 | `x*y+y^3*z^2+z^3*t^2+t^3*u^2+u^3*v^2+v^4` | embedded resolution | 49.9 | none |
| 137 | f5-chain-21122-12112-5 | `x^2*y+y*z^2+z*t+t^2*u+u^2*v^2+v^5` | embedded resolution | 49.8 | none |
| 138 | f5-chain-21321-11121-3 | `x^2*y+y*z+z^3*t+t^2*u^2+u*v+v^3` | pole-check replay | 27.9 | embedded resolution 10.8, intrinsic resolution 11.1 |
| 139 | f5-chain-21332-11121-2 | `x^2*y+y*z+z^3*t+t^3*u^2+u^2*v+v^2` | embedded resolution | 49.8 | none |
| 140 | f5-chain-22113-11112-4 | `x^2*y+y^2*z+z*t+t*u+u^3*v^2+v^4` | embedded resolution | 49.9 | none |
| 141 | f5-chain-22313-21112-4 | `x^2*y^2+y^2*z+z^3*t+t*u+u^3*v^2+v^4` | embedded resolution | 49.9 | none |
| 142 | f5-chain-22313-21122-3 | `x^2*y^2+y^2*z+z^3*t+t*u^2+u^3*v^2+v^3` | embedded resolution | 49.9 | none |
| 143 | f5-chain-22333-11222-3 | `x^2*y+y^2*z+z^3*t^2+t^3*u^2+u^3*v^2+v^3` | embedded resolution | 49.9 | none |
| 144 | f5-chain-23212-11122-2 | `x^2*y+y^3*z+z^2*t+t*u^2+u^2*v^2+v^2` | embedded resolution | 49.8 | none |
| 145 | f5-chain-31133-11221-5 | `x^3*y+y*z+z*t^2+t^3*u^2+u^3*v+v^5` | embedded resolution | 49.9 | none |
| 146 | f5-chain-31222-22112-2 | `x^3*y^2+y*z^2+z^2*t+t^2*u+u^2*v^2+v^2` | pole-check replay | 34.2 | embedded resolution 13.0, intrinsic resolution 2.8 |
| 147 | f5-chain-31331-21122-3 | `x^3*y^2+y*z+z^3*t+t^3*u^2+u*v^2+v^3` | pole-check replay | 39.0 | embedded resolution 5.4, intrinsic resolution 5.5 |
| 148 | f5-chain-32121-22221-3 | `x^3*y^2+y^2*z^2+z*t^2+t^2*u^2+u*v+v^3` | pole-check replay | 17.7 | embedded resolution 13.6, intrinsic resolution 18.5 |
| 149 | f5-chain-32323-12122-4 | `x^3*y+y^2*z^2+z^3*t+t^2*u^2+u^3*v^2+v^4` | embedded resolution | 49.9 | none |
| 150 | f5-chain-33221-12222-5 | `x^3*y+y^3*z^2+z^2*t^2+t^2*u^2+u*v^2+v^5` | intrinsic resolution | 23.0 | embedded resolution 26.9 |
| 151 | f5-loop-11133-12111-4 | `x*y+y*z^2+z*t+t^3*u+u^3*v+v^4*x` | embedded resolution | 49.9 | none |
| 152 | f5-loop-12221-11112-4 | `x*y+y^2*z+z^2*t+t^2*u+u*v^2+v^4*x` | intrinsic resolution | 17.0 | embedded resolution 32.9 |
| 153 | f5-loop-12222-22211-4 | `x*y^2+y^2*z^2+z^2*t^2+t^2*u+u^2*v+v^4*x` | embedded resolution | 49.9 | none |
| 154 | f5-loop-12313-21222-5 | `x*y^2+y^2*z+z^3*t^2+t*u^2+u^3*v^2+v^5*x` | pole-check replay | 9.9 | embedded resolution 16.9, intrinsic resolution 23.0 |
| 155 | f5-loop-22221-11221-5 | `x^2*y+y^2*z+z^2*t^2+t^2*u^2+u*v+v^5*x` | intrinsic resolution | 16.6 | embedded resolution 33.2 |
| 156 | f5-loop-22321-21221-5 | `x^2*y^2+y^2*z+z^3*t^2+t^2*u^2+u*v+v^5*x` | intrinsic resolution | 35.0 | embedded resolution 14.8 |
| 157 | f5-loop-23311-11221-5 | `x^2*y+y^3*z+z^3*t^2+t*u^2+u*v+v^5*x` | embedded resolution | 49.9 | none |
| 158 | f5-loop-23322-22221-4 | `x^2*y^2+y^3*z^2+z^3*t^2+t^2*u^2+u^2*v+v^4*x` | embedded resolution | 49.8 | none |
| 159 | f5-loop-31213-11221-2 | `x^3*y+y*z+z^2*t^2+t*u^2+u^3*v+v^2*x` | embedded resolution | 49.9 | none |
| 160 | f5-loop-31223-12211-3 | `x^3*y+y*z^2+z^2*t^2+t^2*u+u^3*v+v^3*x` | embedded resolution | 49.9 | none |
| 161 | f5-loop-31313-11122-5 | `x^3*y+y*z+z^3*t+t*u^2+u^3*v^2+v^5*x` | embedded resolution | 49.9 | none |
| 162 | f5-loop-32311-12221-2 | `x^3*y+y^2*z^2+z^3*t^2+t*u^2+u*v+v^2*x` | intrinsic resolution | 18.5 | embedded resolution 31.4 |
| 163 | f5-loop-33123-12121-4 | `x^3*y+y^3*z^2+z*t+t^2*u^2+u^3*v+v^4*x` | embedded resolution | 49.9 | none |
| 164 | f5-loop-33221-12111-3 | `x^3*y+y^3*z^2+z^2*t+t^2*u+u*v+v^3*x` | embedded resolution | 49.9 | none |
| 165 | f5-loop-33222-12211-5 | `x^3*y+y^3*z^2+z^2*t^2+t^2*u+u^2*v+v^5*x` | embedded resolution | 49.8 | none |
| 166 | f5-loop-33312-22122-4 | `x^3*y^2+y^3*z^2+z^3*t+t*u^2+u^2*v^2+v^4*x` | embedded resolution | 49.9 | none |
| 167 | f5-partial-cusp-3-0-536 | `x*y*z+t^5+u^3+v^6` | embedded resolution | 49.9 | none |
| 168 | f5-partial-cusp-4-0-25 | `x*y*z*t+u^2+v^5` | embedded resolution | 49.9 | none |
| 169 | f5-partial-cusp-4-2-4645 | `x*y*z*t+x^4+y^6+u^4+v^5` | embedded resolution | 49.9 | none |
| 170 | f5-partial-cusp-4-2-6425 | `x*y*z*t+x^6+y^4+u^2+v^5` | embedded resolution | 49.9 | none |
| 171 | f5-partial-cusp-4-3-64435 | `x*y*z*t+x^6+y^4+z^4+u^3+v^5` | intrinsic resolution | 3.9 | embedded resolution 46.0 |
| 172 | f5-partial-cusp-5-0-6 | `x*y*z*t*u+v^6` | embedded resolution | 49.9 | none |
| 173 | f5-partial-cusp-5-1-46 | `x*y*z*t*u+x^4+v^6` | intrinsic resolution | 2.6 | embedded resolution 47.2 |
| 174 | f5-partial-cusp-5-2-365 | `x*y*z*t*u+x^3+y^6+v^5` | embedded resolution | 49.8 | none |
| 175 | f5-partial-cusp-5-2-565 | `x*y*z*t*u+x^5+y^6+v^5` | embedded resolution | 49.9 | none |
| 176 | f5-partial-cusp-5-3-6536 | `x*y*z*t*u+x^6+y^5+z^3+v^6` | intrinsic resolution | 12.0 | embedded resolution 37.8 |
| 177 | f5-partial-cusp-5-4-66665 | `x*y*z*t*u+x^6+y^6+z^6+t^6+v^5` | embedded resolution | 49.9 | none |
| 178 | f5-partial-cusp-6-3-354 | `x*y*z*t*u*v+x^3+y^5+z^4` | embedded resolution | 49.8 | none |
| 179 | f5-partial-cusp-6-4-6554 | `x*y*z*t*u*v+x^6+y^5+z^5+t^4` | embedded resolution | 49.9 | none |
| 180 | f5-transverse-a13-2-424 | `(x^2+y^2+z^2)^2+t^4+u^2+v^4` | intrinsic resolution | 49.1 | embedded resolution 0.8 |
| 181 | f5-transverse-a13-3-234-b | `(x^2+y^2+z^2)^3+t^2+u^3+v^4` | embedded resolution | 49.9 | none |
| 182 | f5-transverse-a13-3-242 | `(x^2+y^2+z^2)^3+t^2+u^4+v^2` | embedded resolution | 49.9 | none |
| 183 | f5-transverse-a23-2-422 | `(x^2+y^2+z^3)^2+t^4+u^2+v^2` | intrinsic resolution | 48.3 | embedded resolution 1.5 |
| 184 | f5-transverse-a23-3-333 | `(x^2+y^2+z^3)^3+t^3+u^3+v^3` | intrinsic resolution | 48.1 | embedded resolution 1.8 |
| 185 | f5-transverse-a23-3-443-b | `(x^2+y^2+z^3)^3+t^4+u^4+v^3` | embedded resolution | 49.9 | none |
| 186 | f5-transverse-a24-2-34 | `(x^2+y^2+z^2+t^3)^2+u^3+v^4` | embedded resolution | 49.9 | none |
| 187 | f5-transverse-a24-3-23 | `(x^2+y^2+z^2+t^3)^3+u^2+v^3` | embedded resolution | 49.8 | none |
| 188 | f5-transverse-a24-3-34-b | `(x^2+y^2+z^2+t^3)^3+u^3+v^4` | embedded resolution | 49.8 | none |
| 189 | f5-transverse-ca24-2-23 | `(x*y+z^3+t^3)^2+u^2+v^3` | embedded resolution | 49.8 | none |
| 190 | f5-transverse-ca24-2-44-b | `(x*y+z^3+t^3)^2+u^4+v^4` | embedded resolution | 49.8 | none |
| 191 | f5-transverse-ca24-3-22 | `(x*y+z^3+t^3)^3+u^2+v^2` | embedded resolution | 49.9 | none |
| 192 | f5-transverse-ca24-3-42-b | `(x*y+z^3+t^3)^3+u^4+v^2` | embedded resolution | 49.9 | none |
| 193 | f5-transverse-cubic5-2-3-b | `(x^3+y^3+z^3+t^3+u^3)^2+v^3` | intrinsic resolution | 43.0 | embedded resolution 6.9 |
| 194 | f5-transverse-cubic5-2-4 | `(x^3+y^3+z^3+t^3+u^3)^2+v^4` | intrinsic resolution | 43.9 | embedded resolution 6.0 |
| 195 | f5-transverse-cubic5-3-2 | `(x^3+y^3+z^3+t^3+u^3)^3+v^2` | embedded resolution | 49.9 | none |
| 196 | f5-transverse-cusp2-2-2424 | `(x^2-y^3)^2+z^2+t^4+u^2+v^4` | embedded resolution | 49.9 | none |
| 197 | f5-transverse-cusp2-2-4323-b | `(x^2-y^3)^2+z^4+t^3+u^2+v^3` | embedded resolution | 49.9 | none |
| 198 | f5-transverse-cusp2-3-3242-b | `(x^2-y^3)^3+z^3+t^2+u^4+v^2` | embedded resolution | 49.9 | none |
| 199 | f5-transverse-cusp2-3-4423 | `(x^2-y^3)^3+z^4+t^4+u^2+v^3` | embedded resolution | 49.9 | none |
| 200 | f5-transverse-d43-2-324 | `(x^2+y^3+z^3)^2+t^3+u^2+v^4` | embedded resolution | 49.8 | none |
| 201 | f5-transverse-d43-3-232-b | `(x^2+y^3+z^3)^3+t^2+u^3+v^2` | embedded resolution | 49.9 | none |
| 202 | f5-transverse-d43-3-343 | `(x^2+y^3+z^3)^3+t^3+u^4+v^3` | embedded resolution | 49.8 | none |
| 203 | f5-transverse-e62-2-2432 | `(x^3-y^4)^2+z^2+t^4+u^3+v^2` | embedded resolution | 49.9 | none |
| 204 | f5-transverse-e62-2-3223-b | `(x^3-y^4)^2+z^3+t^2+u^2+v^3` | embedded resolution | 49.9 | none |
| 205 | f5-transverse-e62-3-3243 | `(x^3-y^4)^3+z^3+t^2+u^4+v^3` | embedded resolution | 49.9 | none |
| 206 | f5-transverse-quadric4-2-43 | `(x*y-z*t)^2+u^4+v^3` | embedded resolution | 49.8 | none |
| 207 | f5-transverse-quadric4-3-43-b | `(x*y-z*t)^3+u^4+v^3` | embedded resolution | 49.8 | none |
| 208 | f5-transverse-quadric4-3-44 | `(x*y-z*t)^3+u^4+v^4` | embedded resolution | 49.8 | none |
| 209 | f5-transverse-quadric5-2-3-b | `(x^2+y^2+z^2+t^2+u^2)^2+v^3` | intrinsic resolution | 34.0 | embedded resolution 15.9 |
| 210 | f5-transverse-quadric5-3-3 | `(x^2+y^2+z^2+t^2+u^2)^3+v^3` | intrinsic resolution | 48.9 | embedded resolution 1.0 |
| 211 | f5-transverse-two-2-2 | `(x^2+y^2+z^2)^2+(t^2-u^3)^2+v^2` | embedded resolution | 49.9 | none |
| 212 | f5-transverse-two-2-3 | `(x^2+y^2+z^2)^2+(t^2-u^3)^3+v^2` | embedded resolution | 49.9 | none |
| 213 | f5-transverse-two-3-2 | `(x^2+y^2+z^2)^3+(t^2-u^3)^2+v^2` | embedded resolution | 49.9 | none |
| 214 | f5-transverse-umbrella3-2-223-b | `(x^2-y^2*z)^2+t^2+u^2+v^3` | embedded resolution | 49.8 | none |
| 215 | f5-transverse-umbrella3-2-332 | `(x^2-y^2*z)^2+t^3+u^3+v^2` | embedded resolution | 49.9 | none |
| 216 | f5-transverse-umbrella3-3-223 | `(x^2-y^2*z)^3+t^2+u^2+v^3` | embedded resolution | 49.9 | none |
| 217 | f5-transverse-umbrella3-3-443-b | `(x^2-y^2*z)^3+t^4+u^4+v^3` | embedded resolution | 49.8 | none |
| 218 | f5-binary-quintic-discriminant | `3125*x^4*v^4-2500*x^3*y*u*v^3-3750*x^3*z*t*v^3+2000*x^3*z*u^2*v^2+2250*x^3*t^2*u*v^2-1600*x^3*t*u^3*…` | embedded resolution | 49.9 | none |
| 219 | f5-cone-cubic-node-fermat | `v*(x*y-z*t+u^2)+x^3+y^3+z^3+t^3+u^3` | embedded resolution | 49.9 | none |
| 220 | f5-cone-cubic-node-loop | `v*(x*y-z*t+u^2)+x^2*y+y^2*z+z^2*t+t^2*u+u^2*x` | embedded resolution | 49.9 | none |
| 221 | f5-cone-cubic-node-mixed | `v*(x*y-z*t+u^2)+x*y*z+z^3+t^3+u^3` | embedded resolution | 49.9 | none |
| 222 | f5-cone-cubic-rank1-loop | `v*(x^2)+x^2*y+y^2*z+z^2*t+t^2*u+u^2*x` | intrinsic resolution | 15.8 | embedded resolution 34.0 |
| 223 | f5-cone-cubic-rank2-loop | `v*(x*y)+x^2*y+y^2*z+z^2*t+t^2*u+u^2*x` | embedded resolution | 49.9 | none |
| 224 | f5-cone-cubic-rank3-loop | `v*(x*y-z^2)+x^2*y+y^2*z+z^2*t+t^2*u+u^2*x` | embedded resolution | 49.9 | none |
| 225 | f5-cone-cubic-rank4-fermat | `v*(x*y-z*t)+x^3+y^3+z^3+t^3+u^3` | embedded resolution | 49.9 | none |
| 226 | f5-cone-cubic-rank4-loop | `v*(x*y-z*t)+x^2*y+y^2*z+z^2*t+t^2*u+u^2*x` | embedded resolution | 49.9 | none |
| 227 | f5-cone-quartic-node | `v^2*(x*y-z*t+u^2)+x^4+y^4+z^4+t^4+u^4` | embedded resolution | 49.9 | none |
| 228 | f5-cone-quartic-rank4 | `v^2*(x*y-z*t)+x^4+y^4+z^4+t^4+u^4` | embedded resolution | 49.7 | none |
| 229 | f5-cone-quartic-triple-fermat | `v*(x^3+y^3+z^3+t^3+u^3)+x^4+y^4+z^4+t^4+u^4` | embedded resolution | 49.8 | none |
| 230 | f5-cone-quartic-triple-loop | `v*(x^2*y+y^2*z+z^2*t+t^2*u+u^2*x)+x^4+y^4+z^4+t^4+u^4` | embedded resolution | 49.9 | none |
| 231 | f5-cone-quartic-triple-mixed | `v*(x*y*z+z^3+t^3+u^3)+x^4+y^4+z^4+t^4+u^4` | embedded resolution | 49.8 | none |
| 232 | f5-dwork-conifold | `x^6-6*x*y*z*t*u*v+y^6+z^6+t^6+u^6+v^6` | embedded resolution | 49.9 | none |
| 233 | f5-resultant-2-2 | `x^2*v^2-x*y*u*v-2*x*z*t*v+x*z*u^2+y^2*t*v-y*z*t*u+z^2*t^2` | pole-check replay | 15.6 | embedded resolution 23.8, intrinsic resolution 10.5 |
| 234 | f5-sigma4 | `x*y*z*t+x*y*z*u+x*y*z*v+x*y*t*u+x*y*t*v+x*y*u*v+x*z*t*u+x*z*t*v+x*z*u*v+x*t*u*v+y*z*t*u+y*z*t*v+y*z*…` | embedded resolution | 49.8 | none |
| 235 | f5-sigma5 | `x*y*z*t*u+x*y*z*t*v+x*y*z*u*v+x*y*t*u*v+x*z*t*u*v+y*z*t*u*v` | embedded resolution | 49.9 | none |
| 236 | f5-arrangement-7-1 | `x*y*z*t*u*v*(x+y+z+t+u+v)` | intrinsic resolution | 39.5 | embedded resolution 10.3 |
| 237 | f5-arrangement-7-2 | `x*y*z*t*u*v*(x+y+z)` | intrinsic resolution | 37.9 | embedded resolution 12.0 |
| 238 | f5-arrangement-7-3 | `x*y*z*t*u*v*(x+y)` | intrinsic resolution | 49.6 | embedded resolution 0.2 |
| 239 | f5-arrangement-8-10 | `x*y*z*t*(z-u)*(z-t-u)*(x-u+v)*(x+z+u)` | embedded resolution | 49.9 | none |
| 240 | f5-arrangement-8-11 | `x*y*z*t*u*v*(x+u+v)*(u+v)` | embedded resolution | 49.9 | none |
| 241 | f5-arrangement-8-12 | `x*y*z*t*u*v*(x+y)*(z+t)` | intrinsic resolution | 47.3 | embedded resolution 2.5 |
| 242 | f5-arrangement-8-13 | `x*y*z*t*u*v*(x+y)*(x-y)` | intrinsic resolution | 49.2 | embedded resolution 0.6 |
| 243 | f5-arrangement-8-4 | `x*y*z*t*u*v*(x+y+z+t+u+v)*(x+2*y+3*z+4*t+5*u+6*v)` | intrinsic resolution | 38.3 | embedded resolution 11.4 |
| 244 | f5-arrangement-8-5 | `x*y*z*t*(z-t-u)*(y+t+u)*(x-y+v)*(y-z+v)` | embedded resolution | 49.9 | none |
| 245 | f5-arrangement-8-6 | `x*y*z*t*u*v*(x+u+v)*(x-z-v)` | intrinsic resolution | 39.4 | embedded resolution 10.5 |
| 246 | f5-arrangement-8-7 | `x*y*z*t*u*v*(x+y-z)*(x+y-v)` | intrinsic resolution | 1.5 | embedded resolution 48.4 |
| 247 | f5-arrangement-8-8 | `x*y*z*t*u*(y-z)*(x+y-v)*(x-t+v)` | intrinsic resolution | 32.6 | embedded resolution 17.3 |
| 248 | f5-arrangement-8-9 | `x*y*z*t*u*v*(z+t)*(y+z-t)` | intrinsic resolution | 38.8 | embedded resolution 11.1 |
| 249 | f5-arrangement-9-14 | `x*y*z*t*u*(x+t-v)*(z+t-u)*(x+z+v)*(y-z+v)` | embedded resolution | 49.8 | none |
| 250 | f5-arrangement-9-15 | `x*y*z*t*u*(x+z+u)*(x-u+v)*(y+z-v)*(z-t-u)` | embedded resolution | 49.9 | none |
| 251 | f5-arrangement-9-16 | `x*y*z*t*u*v*(t+u+v)*(y-u+v)*(x-z+v)` | intrinsic resolution | 38.4 | embedded resolution 11.5 |
| 252 | f5-arrangement-9-17 | `x*y*z*t*u*(y+z+v)*(x-z+v)*(y+z-u)*(x+y+v)` | embedded resolution | 49.8 | none |
| 253 | f5-arrangement-9-18 | `x*y*z*t*u*v*(x-y-u)*(y-t-v)*(y+u-v)` | embedded resolution | 49.9 | none |
| 254 | f5-arrangement-9-19 | `x*y*z*t*u*v*(y+t+v)*(z+t+v)*(y-z-v)` | embedded resolution | 49.7 | none |
| 255 | f5-arrangement-9-20 | `x*y*z*t*u*(y+u-v)*(x+y+v)*(z+u)*(z+u+v)` | embedded resolution | 49.9 | none |
| 256 | f5-arrangement-9-21 | `x*y*z*t*u*(x-u)*(x+v)*(x-u-v)*(y+z+v)` | embedded resolution | 49.8 | none |
| 257 | f5-arrangement-9-22 | `x*y*z*t*u*(y+z+t)*(t-v)*(x+z+v)*(x+t-v)` | embedded resolution | 49.9 | none |
| 258 | f5-arrangement-9-23 | `x*y*z*t*u*(y-z-u)*(z+t-v)*(x-z+v)*(y+z-u)` | embedded resolution | 49.9 | none |
| 259 | f5-arrangement-9-24 | `x*y*z*t*u*v*(x-t-v)*(x+z-u)*(u+v)` | intrinsic resolution | 38.8 | embedded resolution 11.1 |
| 260 | f5-arrangement-9-25 | `x*y*z*t*u*(x-y+u)*(x+y+u)*(x+t+u)*(x+y-v)` | embedded resolution | 49.9 | none |
| 261 | f5-arrangement-9-26 | `x*y*z*t*u*v*(y+t+u)*(t+u-v)*(t-u+v)` | embedded resolution | 49.8 | none |
| 262 | f5-arrangement-9-27 | `x*y*z*t*u*v*(y-u+v)*(t-u+v)*(x-t)` | embedded resolution | 49.8 | none |
| 263 | f5-arrangement-9-28 | `x*y*z*t*u*(y+z-t)*(x+v)*(y+u-v)*(y-t)` | embedded resolution | 49.9 | none |
| 264 | f5-arrangement-9-29 | `x*y*z*t*u*v*(y-t-u)*(z-u)*(y-t+u)` | embedded resolution | 49.9 | none |
| 265 | f5-arrangement-9-30 | `x*y*z*t*u*(y+t)*(t+u+v)*(z+u-v)*(z-u)` | intrinsic resolution | 38.9 | embedded resolution 10.9 |
| 266 | f5-arrangement-9-31 | `x*y*z*t*u*v*(x+z+t)*(x-y+v)*(z+t)` | embedded resolution | 49.9 | none |
| 267 | f5-arrangement-9-32 | `x*y*z*t*u*(z+v)*(x+z)*(z+u+v)*(x-y-z)` | embedded resolution | 49.9 | none |
| 268 | f5-arrangement-9-33 | `x*y*z*t*u*v*(x-z+v)*(z+u)*(y+t)` | intrinsic resolution | 39.4 | embedded resolution 10.5 |
| 269 | f5-arrangement-9-34 | `x*y*z*t*u*(z-t-u)*(x+z-u)*(z-t)*(t-u+v)` | embedded resolution | 49.8 | none |
| 270 | f5-arrangement-9-35 | `x*y*z*t*u*(y+t)*(t-u-v)*(y-t)*(y-u+v)` | embedded resolution | 49.9 | none |
| 271 | f5-arrangement-9-36 | `x*y*z*t*u*(z+t+u)*(x-z-u)*(z+u+v)*(z+u)` | embedded resolution | 49.9 | none |
| 272 | f5-arrangement-9-37 | `x*y*z*t*u*v*(z-v)*(y+z)*(z+t-v)` | embedded resolution | 49.9 | none |
| 273 | f5-arrangement-9-38 | `x*y*z*t*u*v*(y-t)*(t-v)*(x-u)` | intrinsic resolution | 39.3 | embedded resolution 10.6 |
| 274 | f5-arrangement-9-39 | `x*y*z*t*u*v*(y-u)*(y+u)*(y+u+v)` | embedded resolution | 49.7 | none |
| 275 | f5-product-a13-a23 | `(x^2+y^2+z^2)*(t^2+u^2+v^3)` | embedded resolution | 49.9 | none |
| 276 | f5-product-a13-cubic3 | `(x^2+y^2+z^2)*(t^3+u^3+v^3)` | embedded resolution | 49.8 | none |
| 277 | f5-product-a13-d43 | `(x^2+y^2+z^2)*(t^2+u^3+v^3)` | embedded resolution | 49.9 | none |
| 278 | f5-product-a13-t4443 | `(x^2+y^2+z^2)*(t*u*v+t^4+u^4+v^4)` | embedded resolution | 49.7 | none |
| 279 | f5-product-a13-umbrella3 | `(x^2+y^2+z^2)*(t^2-u^2*v)` | intrinsic resolution | 44.9 | embedded resolution 5.0 |
| 280 | f5-product-a23-a23 | `(x^2+y^2+z^3)*(t^2+u^2+v^3)` | embedded resolution | 49.8 | none |
| 281 | f5-product-a23-d43 | `(x^2+y^2+z^3)*(t^2+u^3+v^3)` | embedded resolution | 49.8 | none |
| 282 | f5-product-a23-t4443 | `(x^2+y^2+z^3)*(t*u*v+t^4+u^4+v^4)` | embedded resolution | 49.8 | none |
| 283 | f5-product-a42-a24 | `(x^2-y^5)*(z^2+t^2+u^2+v^3)` | embedded resolution | 49.8 | none |
| 284 | f5-product-a42-ca24 | `(x^2-y^5)*(z*t+u^3+v^3)` | embedded resolution | 49.9 | none |
| 285 | f5-product-a42-cubic4 | `(x^2-y^5)*(z^3+t^3+u^3+v^3)` | embedded resolution | 49.9 | none |
| 286 | f5-product-a42-cusp2-d42 | `(x^2-y^5)*(z^2-t^3)*(u^3-v^3)` | embedded resolution | 49.9 | none |
| 287 | f5-product-a42-node4 | `(x^2-y^5)*(z*t-u*v)` | embedded resolution | 49.9 | none |
| 288 | f5-product-cubic3-d43 | `(x^3+y^3+z^3)*(t^2+u^3+v^3)` | embedded resolution | 49.7 | none |
| 289 | f5-product-cubic3-umbrella3 | `(x^3+y^3+z^3)*(t^2-u^2*v)` | intrinsic resolution | 44.0 | embedded resolution 5.9 |
| 290 | f5-product-cusp2-a24 | `(x^2-y^3)*(z^2+t^2+u^2+v^3)` | embedded resolution | 49.9 | none |
| 291 | f5-product-cusp2-cubic4 | `(x^2-y^3)*(z^3+t^3+u^3+v^3)` | embedded resolution | 49.9 | none |
| 292 | f5-product-cusp2-cusp2-e62 | `(x^2-y^3)*(z^2-t^3)*(u^3-v^4)` | embedded resolution | 49.9 | none |
| 293 | f5-product-cusp2-d42-d42 | `(x^2-y^3)*(z^3-t^3)*(u^3-v^3)` | embedded resolution | 49.9 | none |
| 294 | f5-product-cusp2-d42-node2 | `(x^2-y^3)*(z^3-t^3)*(u^2-v^2)` | embedded resolution | 49.9 | none |
| 295 | f5-product-cusp2-umbrella4 | `(x^2-y^3)*(z^2-t^2*u+v^2)` | embedded resolution | 49.9 | none |
| 296 | f5-product-d42-e62-e62 | `(x^3-y^3)*(z^3-t^4)*(u^3-v^4)` | embedded resolution | 49.9 | none |
| 297 | f5-product-d42-node2-node2 | `(x^3-y^3)*(z^2-t^2)*(u^2-v^2)` | intrinsic resolution | 49.5 | embedded resolution 0.4 |
| 298 | f5-product-d42-node4 | `(x^3-y^3)*(z*t-u*v)` | intrinsic resolution | 38.8 | embedded resolution 11.0 |
| 299 | f5-product-d42-umbrella4 | `(x^3-y^3)*(z^2-t^2*u+v^2)` | embedded resolution | 49.8 | none |
| 300 | f5-product-d43-d43 | `(x^2+y^3+z^3)*(t^2+u^3+v^3)` | embedded resolution | 49.8 | none |
| 301 | f5-product-d43-e63 | `(x^2+y^3+z^3)*(t^2+u^3+v^4)` | embedded resolution | 49.8 | none |
| 302 | f5-product-d43-t4443 | `(x^2+y^3+z^3)*(t*u*v+t^4+u^4+v^4)` | embedded resolution | 49.9 | none |
| 303 | f5-product-e62-ca24 | `(x^3-y^4)*(z*t+u^3+v^3)` | embedded resolution | 49.9 | none |
| 304 | f5-product-e62-node4 | `(x^3-y^4)*(z*t-u*v)` | embedded resolution | 49.9 | none |
| 305 | f5-product-e62-umbrella4 | `(x^3-y^4)*(z^2-t^2*u+v^2)` | embedded resolution | 49.9 | none |
| 306 | f5-product-h1-a25 | `x*(y^2+z^2+t^2+u^2+v^3)` | intrinsic resolution | 48.8 | embedded resolution 0.7 |
| 307 | f5-product-h1-a42-a23 | `x*(y^2-z^5)*(t^2+u^2+v^3)` | embedded resolution | 49.9 | none |
| 308 | f5-product-h1-a42-d43 | `x*(y^2-z^5)*(t^2+u^3+v^3)` | embedded resolution | 49.9 | none |
| 309 | f5-product-h1-a42-t4443 | `x*(y^2-z^5)*(t*u*v+t^4+u^4+v^4)` | embedded resolution | 49.9 | none |
| 310 | f5-product-h1-cusp2-a23 | `x*(y^2-z^3)*(t^2+u^2+v^3)` | embedded resolution | 49.9 | none |
| 311 | f5-product-h1-cusp2-cubic3 | `x*(y^2-z^3)*(t^3+u^3+v^3)` | embedded resolution | 49.9 | none |
| 312 | f5-product-h1-d42-a13 | `x*(y^3-z^3)*(t^2+u^2+v^2)` | intrinsic resolution | 27.6 | embedded resolution 22.3 |
| 313 | f5-product-h1-d42-a23 | `x*(y^3-z^3)*(t^2+u^2+v^3)` | embedded resolution | 49.9 | none |
| 314 | f5-product-h1-d42-e63 | `x*(y^3-z^3)*(t^2+u^3+v^4)` | embedded resolution | 49.9 | none |
| 315 | f5-product-h1-d42-umbrella3 | `x*(y^3-z^3)*(t^2-u^2*v)` | intrinsic resolution | 36.7 | embedded resolution 13.2 |
| 316 | f5-product-h1-e62-d43 | `x*(y^3-z^4)*(t^2+u^3+v^3)` | embedded resolution | 49.9 | none |
| 317 | f5-product-h1-h1-a24 | `x*y*(z^2+t^2+u^2+v^3)` | intrinsic resolution | 49.6 | embedded resolution 0.3 |
| 318 | f5-product-h1-h1-ca24 | `x*y*(z*t+u^3+v^3)` | intrinsic resolution | 47.9 | embedded resolution 2.0 |
| 319 | f5-product-h1-h1-cubic4 | `x*y*(z^3+t^3+u^3+v^3)` | intrinsic resolution | 49.5 | embedded resolution 0.4 |
| 320 | f5-product-h1-h1-umbrella4 | `x*y*(z^2-t^2*u+v^2)` | intrinsic resolution | 48.9 | embedded resolution 1.0 |
| 321 | f5-product-node2-a24 | `(x^2-y^2)*(z^2+t^2+u^2+v^3)` | embedded resolution | 49.9 | none |
| 322 | f5-product-node2-ca24 | `(x^2-y^2)*(z*t+u^3+v^3)` | intrinsic resolution | 39.0 | embedded resolution 10.8 |
| 323 | f5-product-umbrella3-umbrella3 | `(x^2-y^2*z)*(t^2-u^2*v)` | intrinsic resolution | 36.4 | embedded resolution 13.4 |
| 324 | f5-line-t-inf-5-3-t444 | `x*y*z+y^5+z^3+t*u*v+t^4+u^4+v^4` | embedded resolution | 49.8 | none |
| 325 | f5-suspension-ns-cover-3-3-x-par-s14 | `z^3-(x)*(y+x^2)^3+t^2+u^2+v^3` | embedded resolution | 49.9 | none |
| 326 | f5-suspension-ns-transverse-3-3-e8-s9 | `x^3+(y^3-z^5)^3+t^2+u^3+v^3` | embedded resolution | 49.6 | none |
| 327 | f5-suspension-ns-transverse-5-2-e7-s16 | `x^5+(y^3+y*z^3)^2+t^2+u^2+v^2` | embedded resolution | 49.9 | none |
| 328 | f5-suspension-nt-transverse-3-2-a1-30 | `x^3+(y^2+z^2+t^2)^2+u^2+v^3` | embedded resolution | 49.8 | none |
| 329 | f5-suspension-s2-arrangement-9-85-s18 | `x*y*z*(x-y)*(x-z)*(y-z)*(x+y)*(x+z)*(y+z)+t^2+u^3+v^3` | embedded resolution | 49.9 | none |
| 330 | f5-suspension-s2-image-quadruple-5-s21 | `x^8*y-2*x^4*y^2+4*x^2*y*z^2-z^4+y^3+t^2+u^3+v^3` | embedded resolution | 49.9 | none |
| 331 | f5-suspension-s2-trans-e13-e6-s25 | `x^3+x*(y^3-z^4)^5+t^2+u^2+v^2` | embedded resolution | 49.9 | none |
| 332 | f5-suspension-t-ca-cross-ratio-6 | `x*y+z*t*(z-t)*(z+2*t)+u^2+v^3` | intrinsic resolution | 15.3 | embedded resolution 34.6 |
| 333 | f5-suspension-t-cover-doubled-quadric-10 | `x^2+(y*z-t^2)^2+y^5+z^5+u^2+v^3` | embedded resolution | 49.9 | none |
| 334 | f5-suspension-t3-cone-degree-4-12-68 | `x^4+y^4+z^4+t^4-y*z^2*t+x^3*t+x*y^2*z+2*x*t^3+u^3+v^3` | embedded resolution | 49.9 | none |
| 335 | f5-suspension-tacnode-curve-a1-s2 | `x^2+(y^2-z^4)^2+t^2+u^2+v^3` | embedded resolution | 49.9 | none |
| 336 | f5-b1-4-4355-3000-1021 | `x^4+y^3+z^5+t^5+u*x^3+v*x*z^2*t` | pole-check replay | 17.9 | embedded resolution 10.3, intrinsic resolution 21.6 |
| 337 | f5-b1-4-4453-0021-1210 | `x^4+y^4+z^5+t^3+u*z^2*t+v*x*y^2*z` | pole-check replay | 36.9 | embedded resolution 3.4, intrinsic resolution 9.6 |
| 338 | f5-b1-4-4453-0200-0011 | `x^4+y^4+z^5+t^3+u*y^2+v*z*t` | embedded resolution | 49.9 | none |
| 339 | f5-b1-4-4653-0102-1001 | `x^4+y^6+z^5+t^3+u*y*t^2+v*x*t` | intrinsic resolution | 18.5 | embedded resolution 31.3 |
| 340 | f5-b1-4-5335-2011-0013 | `x^5+y^3+z^3+t^5+u*x^2*z*t+v*z*t^3` | pole-check replay | 48.6 | embedded resolution 0.4, intrinsic resolution 0.8 |
| 341 | f5-b1-4-5564-1101-1300 | `x^5+y^5+z^6+t^4+u*x*y*t+v*x*y^3` | intrinsic resolution | 0.7 | embedded resolution 49.2 |
| 342 | f5-b1-5-33564-10201 | `x^3+y^3+z^5+t^6+u^4+v*x*z^2*u` | pole-check replay | 46.2 | embedded resolution 1.5, intrinsic resolution 2.1 |
| 343 | f5-b1-5-44543-02010 | `x^4+y^4+z^5+t^4+u^3+v*y^2*t` | pole-check replay | 8.0 | embedded resolution 21.9, intrinsic resolution 19.9 |
| 344 | f5-b1-5-46366-00032 | `x^4+y^6+z^3+t^6+u^6+v*t^3*u^2` | pole-check replay | 48.8 | embedded resolution 0.4, intrinsic resolution 0.6 |
| 345 | f5-b1-5-55646-30002 | `x^5+y^5+z^6+t^4+u^6+v*x^3*u^2` | pole-check replay | 47.0 | embedded resolution 1.4, intrinsic resolution 1.6 |
| 346 | f5-b1-5-55666-02030 | `x^5+y^5+z^6+t^6+u^6+v*y^2*t^3` | pole-check replay | 47.7 | embedded resolution 0.8, intrinsic resolution 1.3 |
| 347 | f5-b1-5-63465-30011-10003-d | `x^6+y^3+z^4+t^6+u^5+v*x^3*t*u+v*x*u^3` | pole-check replay | 42.9 | embedded resolution 2.4, intrinsic resolution 4.6 |
| 348 | f5-newton-1 | `-x*y*z^2*t*u*v-x*y*z^3*t^2-x^2*y*v^3+3*x^2*y*z^3*v+2*x^2*y^3*v^2` | intrinsic resolution | 31.5 | embedded resolution 18.4 |
| 349 | f5-newton-11 | `-y^2*t*v^3+x*z*u-x*z^3*t^3-x*y*t*v+3*x^2*y^2*u*v^2+2*x^3*t*v` | embedded resolution | 49.7 | none |
| 350 | f5-newton-12 | `-2*y*z*t*u*v^3+x*y^3*z*u^2-2*x^2*y^3*u*v+3*x^3*t*u^2` | embedded resolution | 49.7 | none |
| 351 | f5-newton-13 | `y*t*u^2*v^3+2*y^2*z*t*u^2+3*x*z*t*u+3*x*z^2*t-2*x^3*y*z*u^2` | embedded resolution | 49.9 | none |
| 352 | f5-newton-15 | `y^2*z^2*t*v-y^2*z^2*t^2-x^2*z*t^3+2*x^2*y*t*u^2` | intrinsic resolution | 18.1 | embedded resolution 31.5 |
| 353 | f5-newton-16 | `3*y*z*u^2-2*x*z*v^3+x^2*z^2*t*u*v+x^2*y^2*t^2+x^3*y^2*u*v` | embedded resolution | 49.7 | none |
| 354 | f5-newton-18 | `2*y^2*t*v^2-y^3*z*t*u*v+3*x*y*z^2*t*u^2+x*y^2*t^3+x^2*z*v^2-2*x^3*t^3` | embedded resolution | 49.8 | none |
| 355 | f5-newton-19 | `2*y^2*t*u^2*v^2+x*z*t^3*u-x*y*z^2*u^3-x*y^3*z*v^2` | embedded resolution | 49.9 | none |
| 356 | f5-newton-2 | `3*x*z*t^2*u*v+3*x*z^3*t^3+2*x*y^2*u+3*x*y^2*t*v^2+2*x^2*z*u^2` | embedded resolution | 49.9 | none |
| 357 | f5-newton-21 | `z^3*t^3*v+y^2*z^3*t*u-2*x*z^2*t*v+2*x^2*t^2*u*v` | embedded resolution | 49.9 | none |
| 358 | f5-newton-22 | `-2*z^2*t*v^2+2*y*z^3*t*u^2+y^2*t^2+2*y^2*z^3*u-x*y*t^2*u^2*v` | intrinsic resolution | 17.9 | embedded resolution 32.0 |
| 359 | f5-newton-23 | `2*y^3*z^2*v+3*x^2*y*u^2-x^2*y*z*t*v^2+x^3*z*u^2` | intrinsic resolution | 25.9 | embedded resolution 23.9 |
| 360 | f5-newton-25 | `-2*y^3*t*v-2*x^2*z*u*v^3+2*x^2*z^2*u*v^2-2*x^3*z*u*v^2-x^3*y*t*v^2` | embedded resolution | 49.8 | none |
| 361 | f5-newton-26 | `-y^2*t^2*v^2+y^2*t^3*u-y^2*z*t*v-2*x^2*y^2*z^3+2*x^3*y*u-2*x^3*y*u^3` | embedded resolution | 49.8 | none |
| 362 | f5-newton-28 | `2*y^3*z^3+x*y*z^3*t*u+x*y^2*t^2*v^2-x^2*u^3*v^2+3*x^3*y*u*v` | embedded resolution | 49.8 | none |
| 363 | f5-newton-29 | `-2*y^2*t^3*u*v+y^2*z^2*v^2-y^3*z*t^2*v-2*x*y^2*u+3*x^2*u*v-x^3*z*u^3` | embedded resolution | 49.8 | none |
| 364 | f5-newton-3 | `-2*z^2*t^3*u^2+y^3*t^3*v-x*z^2*v^3+x^3*z*u*v-2*x^3*y*v^2` | embedded resolution | 49.9 | none |
| 365 | f5-newton-31 | `2*z^2*t^3*u*v+x*y^3*u+3*x^2*y^2+x^3*z^2*t^2` | embedded resolution | 49.8 | none |
| 366 | f5-newton-32 | `2*z*t^2*u+z^2*t*u*v^3+2*x*t*v-x*y^2*t*u*v^2-2*x^2*y*t^3*v` | intrinsic resolution | 26.1 | embedded resolution 23.7 |
| 367 | f5-newton-33 | `-2*y*z^2*u*v^2+2*y*z^2*t*u^3-2*x*t^2+3*x*y*z^2*u^3+3*x^3*y*z*v` | embedded resolution | 49.9 | none |
| 368 | f5-newton-35 | `-z^2*t^3+x*y*z^3*u*v-2*x^2*u^2*v^3+2*x^2*y*v^3` | embedded resolution | 49.5 | none |
| 369 | f5-newton-36 | `y^2*z*u*v^2+3*y^2*z^2*t*v-x*y^2*z^2*t^2-2*x*y^3*z*t+x^2*y*t^2*u*v+2*x^2*y*z^2*t*v` | embedded resolution | 49.8 | none |
| 370 | f5-newton-38 | `2*y^2*z^2*v-2*y^3*z^2*t*u-x*y*z^2*u^3+3*x^2*u*v^3+2*x^2*y^3*t*u` | embedded resolution | 49.8 | none |
| 371 | f5-newton-39 | `-y^2*z^2+3*x*y*u*v^2-2*x*y*t^2*u*v+3*x^2*y^2*z` | embedded resolution | 49.9 | none |
| 372 | f5-newton-41 | `-y*t*u^2*v^2+2*x*z^2*t+2*x*y^2*t*u*v^2-x^2*z*v^2` | embedded resolution | 49.9 | none |
| 373 | f5-newton-42 | `2*y^3*t^2*v^2-x*y*t-2*x*y^2*v^2+2*x*y^3*t^3-2*x^2*z*t^2*v+2*x^3*u^2*v^2` | pole-check replay | 40.6 | embedded resolution 5.1, intrinsic resolution 4.2 |
| 374 | f5-newton-43 | `2*y^2*t^2*u*v^2+3*y^2*z^2*u*v-x*y*t^2*v^2+x^3*y*z^2` | embedded resolution | 49.6 | none |
| 375 | f5-newton-45 | `-y^3*u^2+y^3*z*u*v^2+2*x*z*t^3*u*v+2*x*y*t*u*v^3-x*y*z*t^2*v` | embedded resolution | 49.9 | none |
| 376 | f5-newton-46 | `-2*z*t^2*u^2*v^2-y^2*t^2*u^3-2*x*z*u^2*v^3+2*x^2*t*u*v+x^3*y*z*t^2` | embedded resolution | 49.9 | none |
| 377 | f5-newton-48 | `2*y*z^3*t^2*v-y^3*t^2*u+3*x^2*y^2*t*v+x^2*y^3*t-2*x^3*z^2` | embedded resolution | 49.9 | none |
| 378 | f5-newton-49 | `3*y^2*z*t*u^2*v-y^3*t*u*v^2-2*x*y*t*v^3-2*x*y^2*z*t*v^2+2*x^3*y*u^3-x^3*y^2*u*v` | embedded resolution | 49.9 | none |
| 379 | f5-newton-5 | `3*x*y^3*u^3+2*x*y^3*z^3+3*x^3*z^2*u^2+3*x^3*y*t^2*v` | embedded resolution | 49.5 | none |
| 380 | f5-newton-51 | `-2*y^3-2*x*z*t*v^3-2*x*y*v^2-x^2*t*u*v^2-2*x^2*t^2*v-x^3*y*z*t^2` | intrinsic resolution | 29.4 | embedded resolution 20.4 |
| 381 | f5-newton-52 | `-2*t^2*u^2*v^3-y^2*t^2*u+2*x*z*t^2*v-x*z^3*t*u^2+2*x^3*y^2*t*u` | embedded resolution | 49.9 | none |
| 382 | f5-newton-53 | `-2*y*z*t*u^2*v+x*y^2*u*v^2+2*x*y^3*z^2*t+x^2*z*u^3*v` | embedded resolution | 49.9 | none |
| 383 | f5-newton-55 | `2*y*z*u^2*v^2+2*y*z^2*t^2+x*z*t^3*v^2+3*x*z^2*t^3+2*x^2*z*t*v^3-x^2*z^3*t*u` | embedded resolution | 49.9 | none |
| 384 | f5-newton-56 | `3*x*y^2*t^2*v^2-x*y^2*z*u+2*x^2*z*u^3-2*x^2*z^3-2*x^2*y^2*z*t+x^3*t*u` | embedded resolution | 49.7 | none |
| 385 | f5-newton-58 | `-2*z^3*t^3*u+y^2*z*v^2+3*x*z*v^3-2*x*z^2*t^2+3*x*z^3*t*v^2+2*x^2*y^2*t^2` | embedded resolution | 49.9 | none |
| 386 | f5-newton-59 | `-2*x*y^3*z^3-2*x^2*t^2*v^3+2*x^2*z^2*u^2+3*x^3*y^2*u*v` | intrinsic resolution | 9.3 | embedded resolution 40.6 |
| 387 | f5-newton-6 | `-2*x*y*z*u^2*v+3*x*y^2*z*u^2*v-x*y^2*z^2+3*x^2*y*t^3-2*x^2*y^3*t+2*x^3*t^3*u` | intrinsic resolution | 25.1 | embedded resolution 24.8 |
| 388 | f5-newton-8 | `y^2*z*u^2+y^3*z*u*v+x^2*z^2*t^2+x^3*y*z*t^2` | intrinsic resolution | 34.8 | embedded resolution 15.1 |
| 389 | f5-newton-9 | `y^2*t^2*v^2+3*y^2*z^2*v-y^3*u^3-2*x*y*z^2*v^3+x^2*z^2*u+3*x^3*z*t*u` | embedded resolution | 49.8 | none |
