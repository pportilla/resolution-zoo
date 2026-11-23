# Screen of 2,000 surfaces and threefolds

The screen tested 1,000 non-isolated surfaces and 1,000 threefolds (448 isolated, 552 non-isolated). 1,151 produced complete Zoo records and joined the catalogue: 596 surfaces and 555 threefolds (406 isolated, 149 non-isolated). 741 reached the 20-second budget (333 surfaces, 408 threefolds) and 108 ended with an error (71 surfaces, 37 threefolds). [Per-case data](zoo-screen-2000.json)

## Selection and conditions

The equations come from 35 families that the earlier screens did not cover. Each family varies one feature: the combinatorics of a plane arrangement, the curve under a cone, the contact between smooth sheets, the multiple points of a map image, a discriminant or caustic, the moduli of a transverse type, and so on. Atlas computed every equation given by a map, a discriminant or a caustic, with `eliminate`, `resultant` and `polynomial-arithmetic`, and took square-free parts with `squarefree-factor`. Before any resolution, Atlas checked that each polynomial is reduced (`squarefree-factor`), involves every variable, is singular at the origin and, for surfaces, has a positive-dimensional singular locus there (`local-dimension` of the ideal of the polynomial and its partial derivatives). Equations that agree with a catalogue entry or with a germ of the [1,000-germ screen](https://github.com/pportilla/atlas/blob/main/benchmarks/nonisolated-screen-1000.md) after permuting coordinates and changing signs were removed. Equations with more than 150 terms were left out. From the remaining candidates, 1,000 of each dimension were taken, at evenly spaced positions within each family, with smaller shares for the three randomly generated families.

One worker per equation runs the Zoo record builder: local dimension, embedded resolution with both zetas and the pole check, intrinsic resolution, an exhaustive pole-check replay when the quick check is unresolved, then the Milnor and Tjurina numbers. The 20-second wall-clock budget covers every step, and each equation ran once. Six equations ran at once on an Intel Core i7-1355U (10 cores, 12 threads). A certified case has complete geometry in both modes, both zetas and a verified pole check. The run used Atlas revision [`89decdb`](https://github.com/pportilla/atlas/commit/89decdb987fff4e329cd7304c7be2602bd74ed32).

| Family | Equations | Certified | Timeouts | Errors |
| --- | ---: | ---: | ---: | ---: |
| S01: Central plane arrangements, one per intersection lattice | 102 | 89 | 13 | 0 |
| S02: Cones over classical plane curves and over curves z^(d-m) g_m + g_d with a prescribed singular point | 106 | 70 | 36 | 0 |
| S03: Three or four smooth sheets z = p_i(x, y) with prescribed contact | 106 | 12 | 57 | 37 |
| S04: Images of finite map germs (C², 0) → (C³, 0): Mond's simple germs, triple and quadruple points, corank 2 | 46 | 29 | 13 | 4 |
| S05: Discriminants and caustics: swallowtail, sections of the A4 and A5 discriminants, B3, umbilic, D5 and E6 caustics | 28 | 1 | 19 | 8 |
| S06: Ruled families b(x, y) + z^k a(x, y) of binary forms: moving cross-ratio or multiplicity jump | 106 | 96 | 10 | 0 |
| S07: Transverse D, E, W and Z curve germs along a singular plane curve | 96 | 59 | 31 | 6 |
| S08: Transverse type along a singular plane curve that degenerates at the origin: h^j + z^k m(x, y) | 91 | 41 | 50 | 0 |
| S09: Singular along a complete-intersection space curve | 48 | 7 | 33 | 8 |
| S10: Quasi-ordinary surfaces with two characteristic exponents | 27 | 7 | 17 | 3 |
| S11: Tangent developables of monomial space curves | 14 | 5 | 5 | 4 |
| S12: Steiner-type surfaces: three singular axes with a triple-point term | 36 | 30 | 6 | 0 |
| S13: A cylinder over a plane curve together with a smooth sheet | 56 | 45 | 10 | 1 |
| S14: Non-isolated chain trinomials x^a y^b + y^c z^d + z^e | 52 | 45 | 7 | 0 |
| S15: Random non-convenient Newton polyhedra, singular along one or two axes | 52 | 26 | 26 | 0 |
| S16: Lines of exceptional and parabolic curve germs with the modulus as coordinate | 34 | 34 | 0 | 0 |
| T01: Brieskorn–Pham threefolds | 68 | 68 | 0 | 0 |
| T02: Compound Du Val threefolds, including Laufer's flops | 33 | 30 | 3 | 0 |
| T03: Threefold cusps x^p + y^q + z^r + t^s + xyzt | 35 | 34 | 1 | 0 |
| T04: Joins g(x, y) + h(z, t) of two plane curve germs | 76 | 62 | 14 | 0 |
| T05: Convenient Newton polyhedra with interior mixed monomials | 78 | 73 | 5 | 0 |
| T06: Superisolated threefolds C_d + L^(d+1) over cubic and quartic surfaces with isolated singular points | 30 | 24 | 5 | 1 |
| T07: Invertible polynomials: chain, loop and Fermat blocks | 86 | 76 | 9 | 1 |
| T08: Cones over smooth cubic, quartic and quintic surfaces | 40 | 36 | 4 | 0 |
| T09: Lines of exceptional unimodal surface germs with the modulus as coordinate; Briançon–Speder | 33 | 30 | 3 | 0 |
| T10: Central hyperplane arrangements in C⁴, one per intersection lattice; the D4 reflection arrangement | 91 | 0 | 91 | 0 |
| T11: Discriminants and caustics in C⁴: A4, B4, sections of A5, D4, D5 and E6 | 11 | 0 | 11 | 0 |
| T12: Images of map germs (C³, 0) → (C⁴, 0): double, triple and corank-2 types | 34 | 1 | 24 | 9 |
| T13: Cones over singular surfaces: Roman surface, Cayley cubic, t^(d-m) g_m + g_d | 38 | 11 | 26 | 1 |
| T14: A singular plane whose transverse type jumps along a plane curve: A + B·h(z, t) | 40 | 40 | 0 | 0 |
| T15: Smooth sheets t = p_i(x, y, z), and unions with isolated threefolds | 51 | 4 | 43 | 4 |
| T16: Non-isolated chain quadrinomials x^a y^b + y^c z^d + z^e t^f + t^g | 65 | 23 | 37 | 5 |
| T17: Random non-convenient Newton polyhedra, singular along a line or a plane | 64 | 11 | 52 | 1 |
| T18: Joins of a non-reduced plane curve with a plane curve | 42 | 8 | 26 | 8 |
| T19: Suspensions f(x, y, z) + t^m of surfaces from this screen | 85 | 24 | 54 | 7 |

## Timeouts (741)

At the cutoff, 615 were in the embedded resolution, 81 were in the intrinsic resolution, 43 were in the pole-check replay, 2 were in the Tjurina number. The last column lists the steps that had already finished, excluding the local dimension check.

### Surfaces (333)

| # | ID | Equation | Running at 20 s | Time in step (s) | Finished steps (s) |
| ---: | --- | --- | --- | ---: | --- |
| 1 | s2-arrangement-9-103 | `(x+y+z)*(x+y)*y*(x-y)*(x-2*y)*(x+2*y)*(x+3*y)*(x+2*z)*(2*x+y)` | embedded resolution | 19.6 | none |
| 2 | s2-arrangement-9-57 | `(2*x-y+z)*(x+y+z)*(x-y+z)*(-x+y+z)*(y+2*z)*y*(x+3*y)*(x+y+2*z)*(3*x+z)` | embedded resolution | 19.9 | none |
| 3 | s2-arrangement-9-58 | `(-x+y+z)*(x+3*y)*(x+2*y+3*z)*(x+2*z)*(x+y+2*z)*x*(x-y+z)*(x+y-z)*(y+3*z)` | embedded resolution | 19.7 | none |
| 4 | s2-arrangement-9-59 | `(x-2*y)*(x+3*y)*(x-y+z)*(2*x-y+z)*(x+z)*(x+y-z)*(x-z)*(x+y+2*z)*(-x+y+z)` | embedded resolution | 19.9 | none |
| 5 | s2-arrangement-9-60 | `(2*x-y+z)*(x+y-z)*(x+2*y)*(-x+y+z)*(x+2*y+3*z)*(x-y+z)*(x+3*y)*(3*x+z)*y` | embedded resolution | 19.8 | none |
| 6 | s2-arrangement-9-66 | `(x-y+z)*(x+y+2*z)*(x+z)*(y+z)*(x+2*y+3*z)*(-x+y+z)*(y+3*z)*(x+y-z)*(x+3*y)` | embedded resolution | 19.8 | none |
| 7 | s2-arrangement-9-68 | `y*(x-2*y)*(x-y)*(x-y+z)*(3*x+z)*(x+z)*(x+y+2*z)*(x+y-z)*(x+2*y)` | embedded resolution | 19.9 | none |
| 8 | s2-arrangement-9-69 | `(x-2*y)*(x+y+z)*(x+3*y)*(-x+y+z)*(x+y+2*z)*(y+3*z)*y*x*(x-z)` | embedded resolution | 19.8 | none |
| 9 | s2-arrangement-9-70 | `(y-z)*(x+y)*(x+3*y)*y*(x+y+z)*(x+y-z)*(x+2*z)*(x-2*y)*(2*x-y+z)` | embedded resolution | 19.8 | none |
| 10 | s2-arrangement-9-86 | `(x+y+z)*y*(3*x+z)*(x-2*y)*(-x+y+z)*(x+2*y)*(x+3*y)*(y+3*z)*(x+y)` | embedded resolution | 19.8 | none |
| 11 | s2-arrangement-9-92 | `(x-2*y)*(x+y+2*z)*(x+3*y)*(3*x+z)*(x+z)*(x+2*y+3*z)*(x+y)*y*(x-y)` | embedded resolution | 19.8 | none |
| 12 | s2-arrangement-9-97 | `(x-2*y)*(x+2*y)*y*(-x+y+z)*(x-y)*x*(y+3*z)*(2*x+y)*(x+2*y+3*z)` | embedded resolution | 19.8 | none |
| 13 | s2-arrangement-9-98 | `(x-y)*(x+y)*(2*x+y)*(y-z)*(x+2*y)*(x-2*y)*(x+y+2*z)*x*(x-y+z)` | embedded resolution | 19.8 | none |
| 14 | s2-cone-ampersand | `(y^2-x^2)*(x-z)*(2*x-3*z)-4*(x^2+y^2-2*x*z)^2` | intrinsic resolution | 16.8 | embedded resolution 3.1 |
| 15 | s2-cone-astroid | `(x^2+y^2-z^2)^3+27*x^2*y^2*z^2` | embedded resolution | 19.7 | none |
| 16 | s2-cone-bicorn | `y^2*(z^2-x^2)-(x^2+2*y*z-z^2)^2` | embedded resolution | 19.9 | none |
| 17 | s2-cone-cardioid | `(x^2+y^2-x*z)^2-z^2*(x^2+y^2)` | embedded resolution | 19.7 | none |
| 18 | s2-cone-d5-x2-1 | `z^3*x^2+y^5+x^4*y` | embedded resolution | 19.7 | none |
| 19 | s2-cone-d5-x2-1-b | `z^3*x^2+y^5+x^4*y+z^2*(y^3)` | embedded resolution | 19.8 | none |
| 20 | s2-cone-d5-x2y-1 | `z^2*x^2*y+y^5+x^4*y` | intrinsic resolution | 19.5 | embedded resolution 0.3 |
| 21 | s2-cone-d5-x2y-1-b | `z^2*x^2*y+y^5+x^4*y+z*(x*y^3)` | intrinsic resolution | 19.5 | embedded resolution 0.3 |
| 22 | s2-cone-d5-x2y-2-b | `z^2*x^2*y+x*y^4+y^5+z*(x*y^3)` | intrinsic resolution | 19.6 | embedded resolution 0.2 |
| 23 | s2-cone-d5-x3-1 | `z^2*x^3+y^5+x^4*y` | pole-check replay | 1.1 | embedded resolution 8.7, intrinsic resolution 10.0 |
| 24 | s2-cone-d5-x3-1-b | `z^2*x^3+y^5+x^4*y+z*(y^4)` | embedded resolution | 19.8 | none |
| 25 | s2-cone-d5-x3-4-b | `z^2*x^3+x^2*y^3+x^5+z*(y^4)` | embedded resolution | 19.9 | none |
| 26 | s2-cone-d5-xy-1 | `z^3*x*y+y^5+x^4*y` | intrinsic resolution | 19.7 | embedded resolution 0.2 |
| 27 | s2-cone-d5-xyxy-1 | `z^2*x*y*(x+y)+y^5+x^4*y` | intrinsic resolution | 19.7 | embedded resolution 0.2 |
| 28 | s2-cone-d5-xyxy-1-b | `z^2*x*y*(x+y)+y^5+x^4*y+z*(y^4)` | intrinsic resolution | 19.6 | embedded resolution 0.3 |
| 29 | s2-cone-d5-xyxy-2 | `z^2*x*y*(x+y)+x*y^4+y^5` | intrinsic resolution | 6.4 | embedded resolution 13.5 |
| 30 | s2-cone-d5-xyxy-3 | `z^2*x*y*(x+y)+x^5+y^5` | intrinsic resolution | 9.7 | embedded resolution 10.2 |
| 31 | s2-cone-d5-xyxy-4 | `z^2*x*y*(x+y)+x^2*y^3+x^5` | intrinsic resolution | 7.2 | embedded resolution 12.6 |
| 32 | s2-cone-d5-xyxy-4-b | `z^2*x*y*(x+y)+x^2*y^3+x^5+z*(y^4)` | intrinsic resolution | 3.2 | embedded resolution 16.6 |
| 33 | s2-cone-d6-x2-1-b | `z^4*x^2+y^6+x^5*y+z^3*(y^3)` | embedded resolution | 19.8 | none |
| 34 | s2-cone-d6-x2-3-b | `z^4*x^2+x*y^5+x^6+z^3*(y^3)` | embedded resolution | 19.8 | none |
| 35 | s2-cone-d6-x2y-1 | `z^3*x^2*y+y^6+x^5*y` | intrinsic resolution | 19.5 | embedded resolution 0.3 |
| 36 | s2-cone-d6-x2y-1-b | `z^3*x^2*y+y^6+x^5*y+z^2*(x*y^3)` | intrinsic resolution | 19.6 | embedded resolution 0.2 |
| 37 | s2-cone-d6-x2y-3-b | `z^3*x^2*y+x*y^5+x^6+z^2*(x*y^3)` | intrinsic resolution | 19.5 | embedded resolution 0.3 |
| 38 | s2-cone-d6-x3-1 | `z^3*x^3+y^6+x^5*y` | embedded resolution | 19.8 | none |
| 39 | s2-cone-d6-x3-3-b | `z^3*x^3+x*y^5+x^6+z^2*(y^4)` | embedded resolution | 19.8 | none |
| 40 | s2-cone-d6-xy-1 | `z^4*x*y+y^6+x^5*y` | intrinsic resolution | 19.6 | embedded resolution 0.2 |
| 41 | s2-cone-d6-xy-1-b | `z^4*x*y+y^6+x^5*y+z^3*(x^3+y^3)` | embedded resolution | 19.8 | none |
| 42 | s2-cone-d6-xyxy-1 | `z^3*x*y*(x+y)+y^6+x^5*y` | embedded resolution | 19.8 | none |
| 43 | s2-cone-d6-xyxy-3-b | `z^3*x*y*(x+y)+x*y^5+x^6+z^2*(y^4)` | embedded resolution | 19.8 | none |
| 44 | s2-cone-deltoid | `(x^2+y^2)^2+18*z^2*(x^2+y^2)-27*z^4-8*z*(x^3-3*x*y^2)` | embedded resolution | 19.8 | none |
| 45 | s2-cone-lemniscate | `(x^2+y^2)^2-z^2*(x^2-y^2)` | intrinsic resolution | 10.9 | embedded resolution 8.9 |
| 46 | s2-cone-quadrifolium | `(x^2+y^2)^3-4*x^2*y^2*z^2` | embedded resolution | 19.9 | none |
| 47 | s2-cone-quartic-1 | `(y*z-x^2)^2-x*y^3` | embedded resolution | 19.8 | none |
| 48 | s2-cone-quartic-3 | `(y*z-x^2)^2-y^3*x-y^4` | intrinsic resolution | 5.8 | embedded resolution 14.0 |
| 49 | s2-cone-tangent-conics | `(y*z-x^2)*(y*z-x^2-y^2)` | embedded resolution | 19.9 | none |
| 50 | s2-sheets-3-1 | `(z-(-x^2))*(z-(x*y))*(z-(x+y^2))` | embedded resolution | 19.8 | none |
| 51 | s2-sheets-3-13 | `(z-(x))*(z-(x^2-y^2))*(z-(x*y+x^3))` | embedded resolution | 19.8 | none |
| 52 | s2-sheets-3-17 | `(z-(x^2))*(z-(y^2))*(z-(x*y+x^3))` | embedded resolution | 19.8 | none |
| 53 | s2-sheets-3-19 | `(z-(x^2+y^2))*(z-(x^2+y^3))*(z-(y^2-x^3))` | embedded resolution | 19.9 | none |
| 54 | s2-sheets-3-2 | `(z-(-x^2))*(z-(x*y))*(z-(x^3))` | embedded resolution | 19.8 | none |
| 55 | s2-sheets-3-21 | `(z-(x^2+y^3))*(z-(x*y+x^3))*(z-(y^2-x^3))` | embedded resolution | 19.8 | none |
| 56 | s2-sheets-3-22 | `(z-(y))*(z-(2*x^2))*(z-(x+y^2))` | intrinsic resolution | 19.6 | embedded resolution 0.3 |
| 57 | s2-sheets-3-23 | `(z-(y))*(z-(x+y^2))*(z-(x*y+x^3))` | intrinsic resolution | 19.4 | embedded resolution 0.5 |
| 58 | s2-sheets-3-24 | `(z-(y))*(z-(x^2+y^2))*(z-(2*x^2))` | intrinsic resolution | 19.5 | embedded resolution 0.3 |
| 59 | s2-sheets-3-26 | `(z-(y))*(z-(x^2+y^3))*(z-(x+y^2))` | intrinsic resolution | 19.4 | embedded resolution 0.4 |
| 60 | s2-sheets-3-27 | `(z-(y))*(z-(x^2-y^2))*(z-(2*x^2))` | intrinsic resolution | 19.6 | embedded resolution 0.2 |
| 61 | s2-sheets-3-28 | `(z-(y))*(z-(y^2))*(z-(x^2+y^2))` | embedded resolution | 19.9 | none |
| 62 | s2-sheets-3-29 | `(z-(y^2))*(z-(x*y))*(z-(y^2-x^3))` | intrinsic resolution | 5.7 | embedded resolution 13.8 |
| 63 | s2-sheets-3-30 | `(z-(y^3))*(z-(x^2-y^2))*(z-(y^2-x^3))` | intrinsic resolution | 12.5 | embedded resolution 7.3 |
| 64 | s2-sheets-3-6 | `z*(z-(x+y^2))*(z-(x*y+x^3))` | embedded resolution | 19.8 | none |
| 65 | s2-sheets-4-100 | `(z-(x^2))*(z-(y^3))*(z-(x^2+y^3))*(z-(x+y^2))` | embedded resolution | 19.8 | none |
| 66 | s2-sheets-4-102 | `(z-(x^2+y^2))*(z-(x*y))*(z-(y^3))*(z-(x+y^2))` | embedded resolution | 19.8 | none |
| 67 | s2-sheets-4-103 | `(z-(x^2+y^2))*(z-(y^3))*(z-(2*x^2))*(z-(y^2-x^3))` | embedded resolution | 19.8 | none |
| 68 | s2-sheets-4-104 | `(z-(x^2+y^2))*(z-(y^3))*(z-(x+y^2))*(z-(x*y+x^3))` | embedded resolution | 19.8 | none |
| 69 | s2-sheets-4-105 | `(z-(x^2+y^2))*(z-(y^3))*(z-(x^2+y^3))*(z-(x^2-y^2))` | embedded resolution | 19.9 | none |
| 70 | s2-sheets-4-106 | `(z-(x^3))*(z-(y^3))*(z-(x^2-y^2))*(z-(2*x^2))` | embedded resolution | 19.7 | none |
| 71 | s2-sheets-4-109 | `(z-(y))*(z-(-x^2))*(z-(x^2+y^2))*(z-(x^3))` | embedded resolution | 19.5 | none |
| 72 | s2-sheets-4-110 | `(z-(y))*(z-(-x^2))*(z-(x^2+y^3))*(z-(y^2-x^3))` | embedded resolution | 19.9 | none |
| 73 | s2-sheets-4-111 | `(z-(y))*(z-(-x^2))*(z-(y^2))*(z-(x*y+x^3))` | embedded resolution | 19.7 | none |
| 74 | s2-sheets-4-113 | `(z-(y))*(z-(2*x^2))*(z-(x+y^2))*(z-(x*y+x^3))` | embedded resolution | 19.9 | none |
| 75 | s2-sheets-4-114 | `(z-(y))*(z-(x*y))*(z-(2*x^2))*(z-(x+y^2))` | embedded resolution | 19.9 | none |
| 76 | s2-sheets-4-115 | `(z-(y))*(z-(x^2))*(z-(x*y))*(z-(x*y+x^3))` | embedded resolution | 19.8 | none |
| 77 | s2-sheets-4-118 | `(z-(y))*(z-(x^2+y^2))*(z-(x^2+y^3))*(z-(x^2-y^2))` | embedded resolution | 19.9 | none |
| 78 | s2-sheets-4-119 | `(z-(y))*(z-(x^2-y^2))*(z-(2*x^2))*(z-(x*y+x^3))` | embedded resolution | 19.7 | none |
| 79 | s2-sheets-4-120 | `(z-(y))*(z-(x^2-y^2))*(z-(x*y+x^3))*(z-(y^2-x^3))` | embedded resolution | 19.8 | none |
| 80 | s2-sheets-4-121 | `(z-(y))*(z-(x^3))*(z-(x^2-y^2))*(z-(x*y+x^3))` | embedded resolution | 19.9 | none |
| 81 | s2-sheets-4-122 | `(z-(y))*(z-(y^2))*(z-(x^2+y^3))*(z-(y^2-x^3))` | embedded resolution | 19.9 | none |
| 82 | s2-sheets-4-124 | `(z-(y^2))*(z-(x*y))*(z-(x^3))*(z-(x^2+y^3))` | embedded resolution | 19.6 | none |
| 83 | s2-sheets-4-126 | `(z-(y^2))*(z-(x^2+y^2))*(z-(x+y^2))*(z-(x*y+x^3))` | embedded resolution | 19.8 | none |
| 84 | s2-sheets-4-127 | `(z-(y^2))*(z-(x^2+y^3))*(z-(2*x^2))*(z-(x*y+x^3))` | embedded resolution | 19.6 | none |
| 85 | s2-sheets-4-129 | `(z-(y^2))*(z-(y^3))*(z-(2*x^2))*(z-(y^2-x^3))` | embedded resolution | 19.8 | none |
| 86 | s2-sheets-4-34 | `(z-(-x^2))*(z-(x^2+y^2))*(z-(x^2-y^2))*(z-(2*x^2))` | embedded resolution | 19.8 | none |
| 87 | s2-sheets-4-37 | `(z-(-x^2))*(z-(y^3))*(z-(2*x^2))*(z-(y^2-x^3))` | embedded resolution | 19.5 | none |
| 88 | s2-sheets-4-40 | `z*(z-(-x^2))*(z-(x+y^2))*(z-(x*y+x^3))` | embedded resolution | 19.8 | none |
| 89 | s2-sheets-4-43 | `z*(z-(x))*(z-(x*y))*(z-(2*x^2))` | embedded resolution | 19.8 | none |
| 90 | s2-sheets-4-44 | `z*(z-(x))*(z-(x*y))*(z-(x^3))` | embedded resolution | 19.8 | none |
| 91 | s2-sheets-4-45 | `z*(z-(x))*(z-(y))*(z-(x^2+y^3))` | embedded resolution | 19.9 | none |
| 92 | s2-sheets-4-51 | `z*(z-(x^2))*(z-(y^2))*(z-(y^2-x^3))` | embedded resolution | 19.8 | none |
| 93 | s2-sheets-4-56 | `z*(z-(x^2+y^3))*(z-(2*x^2))*(z-(x*y+x^3))` | embedded resolution | 19.8 | none |
| 94 | s2-sheets-4-62 | `z*(z-(y))*(z-(-x^2))*(z-(x+y^2))` | embedded resolution | 19.9 | none |
| 95 | s2-sheets-4-67 | `z*(z-(y))*(z-(x^2-y^2))*(z-(2*x^2))` | embedded resolution | 19.9 | none |
| 96 | s2-sheets-4-70 | `z*(z-(y^2))*(z-(x^2+y^2))*(z-(y^3))` | embedded resolution | 19.7 | none |
| 97 | s2-sheets-4-73 | `(z-(x))*(z-(-x^2))*(z-(x^2+y^2))*(z-(y^2-x^3))` | embedded resolution | 19.8 | none |
| 98 | s2-sheets-4-75 | `(z-(x))*(z-(x*y))*(z-(x+y^2))*(z-(y^2-x^3))` | embedded resolution | 19.8 | none |
| 99 | s2-sheets-4-81 | `(z-(x))*(z-(x^2+y^2))*(z-(x*y+x^3))*(z-(y^2-x^3))` | embedded resolution | 19.8 | none |
| 100 | s2-sheets-4-82 | `(z-(x))*(z-(x^2+y^2))*(z-(x+y^2))*(z-(x*y+x^3))` | embedded resolution | 19.8 | none |
| 101 | s2-sheets-4-83 | `(z-(x))*(z-(x^2+y^3))*(z-(2*x^2))*(z-(y^2-x^3))` | embedded resolution | 19.9 | none |
| 102 | s2-sheets-4-86 | `(z-(x))*(z-(y))*(z-(x^2+y^2))*(z-(x^3))` | embedded resolution | 19.9 | none |
| 103 | s2-sheets-4-87 | `(z-(x))*(z-(y))*(z-(x^2+y^3))*(z-(y^2-x^3))` | embedded resolution | 19.8 | none |
| 104 | s2-sheets-4-91 | `(z-(x^2))*(z-(-x^2))*(z-(x^3))*(z-(y^3))` | embedded resolution | 19.9 | none |
| 105 | s2-sheets-4-92 | `(z-(x^2))*(z-(2*x^2))*(z-(x*y+x^3))*(z-(y^2-x^3))` | embedded resolution | 19.8 | none |
| 106 | s2-sheets-4-93 | `(z-(x^2))*(z-(x*y))*(z-(2*x^2))*(z-(x*y+x^3))` | embedded resolution | 19.8 | none |
| 107 | s2-image-corank2-1 | `x^6-2*x^3*y^3+y^6-2*x^4*y-2*x^3*z^2-8*x^2*y^2*z-2*x*y^4-2*y^3*z^2+x^2*y^2-2*x*y*z^2+z^4` | embedded resolution | 19.8 | none |
| 108 | s2-image-corank2-2 | `x^6-2*x^4*y-2*x^3*z^2+x^2*y^2-2*x*y*z^2+z^4` | embedded resolution | 19.8 | none |
| 109 | s2-image-corank2-6 | `y^8-x^7+7*x^5*y^2-14*x^3*y^4-2*x^2*y^4*z+7*x*y^6+4*y^6*z+2*x^5*z+x^4*z^2-10*x^3*y^2*z-4*x^2*y^2*z^2+10*x*y^4*z…` | embedded resolution | 19.6 | none |
| 110 | s2-image-mond-b5 | `y^11+2*x^2*y^6+x^4*y-z^2` | embedded resolution | 19.4 | none |
| 111 | s2-image-mond-h2 | `y^5+x^3*y+3*x*y^2*z-z^3` | embedded resolution | 19.9 | none |
| 112 | s2-image-mond-h3 | `y^8+3*x*y^3*z+x^3*y-z^3` | embedded resolution | 19.8 | none |
| 113 | s2-image-mond-h4 | `y^11+3*x*y^4*z+x^3*y-z^3` | embedded resolution | 19.8 | none |
| 114 | s2-image-mond-h5 | `y^14+3*x*y^5*z+x^3*y-z^3` | embedded resolution | 19.8 | none |
| 115 | s2-image-quadruple-7 | `x^4*y^2-2*x^2*y*z^2-4*x*y^3*z-y^5+z^4` | embedded resolution | 19.8 | none |
| 116 | s2-image-quadruple-8 | `x^4*y^2-x^4*y-4*x^3*y^2-4*x^3*y*z-2*x^2*y*z^2+2*x^2*y^2-4*x*y^2*z-4*x*y*z^2+z^4-y^3` | embedded resolution | 19.8 | none |
| 117 | s2-image-triple-13 | `x^6*y^2+3*x^4*y^3+3*x^2*y^4+3*x^3*y*z+y^5+x^3*y+3*x*y^2*z-z^3` | embedded resolution | 19.8 | none |
| 118 | s2-image-triple-6 | `x^3*y^2+3*x^2*y^3+3*x*y^4+y^5+x^3*y+3*x^2*y*z+3*x*y^2*z-z^3` | embedded resolution | 19.8 | none |
| 119 | s2-image-triple-7 | `x^6*y+3*x^4*y^2+x^3*y^2+3*x^3*y*z+3*x^2*y^3+3*x*y^2*z+y^4-z^3` | embedded resolution | 19.9 | none |
| 120 | s2-a4-section-a-0 | `-108*x^5*z+27*x^4*y^2-2250*x^2*y*z^2+1600*x*y^3*z-256*y^5-3125*z^4` | embedded resolution | 19.9 | none |
| 121 | s2-a4-section-a-c2 | `108*y^10*z^2-72*x*y^9*z+16*y^11+16*x^3*y^6*z-4*x^2*y^8-900*y^7*z^2+825*x^2*y^4*z^2+560*x*y^6*z-128*y^8-630*x^3…` | embedded resolution | 19.8 | none |
| 122 | s2-a4-section-a-db | `108*x^5*z^7-72*x^5*y*z^5+16*x^4*y^3*z^4+16*x^6*z^4-4*x^5*y^2*z^3-900*x^3*y*z^5+825*x^4*z^4+560*x^3*y^2*z^3-128…` | embedded resolution | 19.7 | none |
| 123 | s2-a4-section-b-0 | `108*x^5*z^2+16*x^4*y^3-900*x^3*y*z^2-128*x^2*y^4+2000*x*y^2*z^2+256*y^5+3125*z^4` | embedded resolution | 19.5 | none |
| 124 | s2-a4-section-b-c2 | `108*y^10*z+16*x^3*y^6*z-27*y^10-4*x^3*y^6-630*x*y^7*z-72*x^4*y^3*z+825*x^2*y^4*z^2+144*x*y^7+108*x^5*z^2+16*x^…` | embedded resolution | 19.9 | none |
| 125 | s2-a4-section-b-da | `108*x^5*z^6+16*x^6*z^4-27*x^4*y^2*z^4-4*x^5*y^2*z^2-630*x^4*y*z^4-72*x^5*y*z^2+825*x^4*z^4+144*x^3*y^3*z^2+108…` | embedded resolution | 19.8 | none |
| 126 | s2-a4-section-c-0 | `108*x^5*z^2+16*x^3*y^3*z+825*x^2*y^2*z^2+108*y^5*z-3750*x*y*z^3+3125*z^4` | embedded resolution | 19.8 | none |
| 127 | s2-a4-section-c-b2 | `16*x^4*y^6-128*x^2*y^8+256*y^10-4*x^3*y^6+144*x*y^8-72*x^4*y^3*z+560*x^2*y^5*z-27*y^8-1600*y^7*z+108*x^5*z^2+1…` | embedded resolution | 19.8 | none |
| 128 | s2-a4-section-c-da | `16*x^7*z^3-128*x^6*z^4+256*x^5*z^5-4*x^5*y^2*z^2+144*x^4*y^2*z^3-72*x^5*y*z^2+560*x^4*y*z^3-1600*x^3*y*z^4-27*…` | embedded resolution | 19.6 | none |
| 129 | s2-a4-section-d-ca | `108*x^7*z^2-72*x^5*y*z^2-900*x^5*z^3+16*x^4*y^3*z+825*x^4*y^2*z^2-3750*x^4*y*z^3+3125*x^4*z^4+16*x^4*z^3-4*x^3…` | embedded resolution | 19.8 | none |
| 130 | s2-a5-section-ac | `729*x^6*z^2+108*x^5*y^3-8748*x^4*z^3-1350*x^3*y^3*z+34992*x^2*z^4+27000*x*y^3*z^2+3125*y^6-46656*z^5` | embedded resolution | 19.8 | none |
| 131 | s2-a5-section-ae | `(-108*x^5*z+27*x^4*y^2-2250*x^2*y*z^2+1600*x*y^3*z-256*y^5-3125*z^4)*(z)` | embedded resolution | 19.8 | none |
| 132 | s2-a5-section-be | `(108*x^5*z^2+16*x^4*y^3-900*x^3*y*z^2-128*x^2*y^4+2000*x*y^2*z^2+256*y^5+3125*z^4)*(z)` | embedded resolution | 19.8 | none |
| 133 | s2-a5-section-cd | `(-1024*x^6*z+108*x^3*y^4-8640*x^3*y^2*z+729*y^6-13824*x^3*z^2-8748*y^4*z+34992*y^2*z^2-46656*z^3)*(z)` | embedded resolution | 19.5 | none |
| 134 | s2-b3-discriminant | `-4*x^3*z^2+x^2*y^2*z+18*x*y*z^2-4*y^3*z-27*z^3` | embedded resolution | 19.7 | none |
| 135 | s2-caustic-d4-elliptic | `x^8-6*x^4*y^2-6*x^4*z^2-8*x^2*y^3+24*x^2*y*z^2-3*y^4-6*y^2*z^2-3*z^4` | embedded resolution | 19.8 | none |
| 136 | s2-caustic-d4-hyperbolic | `x^8-6*x^4*y^2+18*x^4*z^2-8*x^2*y^3-72*x^2*y*z^2-3*y^4+18*y^2*z^2-27*z^4` | embedded resolution | 19.6 | none |
| 137 | s2-caustic-d5-slice | `864*x^5*y^2+128*x^3*z^3+3300*x^2*y^2*z^2-7500*x*y^4*z+3125*y^6+432*z^5` | embedded resolution | 19.8 | none |
| 138 | s2-swallowtail-tangent-plane | `-16*x^5*z+4*x^4*y^2+128*x^3*z^2-144*x^2*y^2*z+27*x*y^4-256*x*z^3` | embedded resolution | 19.8 | none |
| 139 | s2-ruled-jump-4-2-2-3 | `x*y*(x-y)*(x-2*y)+z*(x^2+y^2)` | embedded resolution | 19.8 | none |
| 140 | s2-ruled-jump-4-2-3-1 | `x*y*(x^2+y^2)+z*(x*y)` | intrinsic resolution | 19.1 | embedded resolution 0.4 |
| 141 | s2-ruled-jump-4-2-3-3 | `x*y*(x^2+y^2)+z*(x^2+y^2)` | intrinsic resolution | 19.3 | embedded resolution 0.4 |
| 142 | s2-ruled-jump-4-3-3-3 | `x*y*(x^2+y^2)+z*(x*(x^2+y^2))` | intrinsic resolution | 19.0 | embedded resolution 0.6 |
| 143 | s2-ruled-jump-5-3-1-3 | `x*y*(x-y)*(x+y)*(x-2*y)+z*(x*(x^2+y^2))` | embedded resolution | 19.9 | none |
| 144 | s2-ruled-jump-5-3-3-2 | `x*y*(x^3+y^3)+z*(x*y*(x+y))` | embedded resolution | 19.8 | none |
| 145 | s2-ruled-jump-5-3-3-4 | `x*y*(x^3+y^3)+z*(x^3+y^3)` | intrinsic resolution | 19.6 | embedded resolution 0.2 |
| 146 | s2-ruled-jump-5-4-3-1 | `x*y*(x^3+y^3)+z*(x*y*(x-y)*(x+y))` | intrinsic resolution | 10.6 | embedded resolution 9.3 |
| 147 | s2-ruled-jump-5-4-3-2 | `x*y*(x^3+y^3)+z*(x*y*(x-y)*(x-2*y))` | pole-check replay | 5.2 | embedded resolution 0.4, intrinsic resolution 14.1 |
| 148 | s2-ruled-jump-5-4-3-4 | `x*y*(x^3+y^3)+z*(x^4+y^4)` | pole-check replay | 15.8 | embedded resolution 2.0, intrinsic resolution 1.8 |
| 149 | s2-trans-d4-d4 | `x^2*(y^3-z^3)+(y^3-z^3)^3` | embedded resolution | 19.8 | none |
| 150 | s2-trans-d4-node | `x^2*(y^2-z^2)+(y^2-z^2)^3` | embedded resolution | 19.9 | none |
| 151 | s2-trans-d4-tacnode | `x^2*(y^2-z^4)+(y^2-z^4)^3` | embedded resolution | 19.8 | none |
| 152 | s2-trans-d5-d5-s | `(y^2*z+z^4)^2*x+x^4` | embedded resolution | 19.7 | none |
| 153 | s2-trans-d5-node | `x^2*(y^2-z^2)+(y^2-z^2)^4` | embedded resolution | 19.8 | none |
| 154 | s2-trans-d5-tacnode | `x^2*(y^2-z^4)+(y^2-z^4)^4` | embedded resolution | 19.7 | none |
| 155 | s2-trans-d6-cusp-s | `(y^2-z^3)^2*x+x^5` | embedded resolution | 19.7 | none |
| 156 | s2-trans-d6-d4 | `x^2*(y^3-z^3)+(y^3-z^3)^5` | embedded resolution | 19.8 | none |
| 157 | s2-trans-d6-d4-s | `(y^3-z^3)^2*x+x^5` | intrinsic resolution | 19.0 | embedded resolution 0.8 |
| 158 | s2-trans-d6-node | `x^2*(y^2-z^2)+(y^2-z^2)^5` | embedded resolution | 19.7 | none |
| 159 | s2-trans-d6-node-s | `(y^2-z^2)^2*x+x^5` | embedded resolution | 19.9 | none |
| 160 | s2-trans-d6-tacnode | `x^2*(y^2-z^4)+(y^2-z^4)^5` | embedded resolution | 19.8 | none |
| 161 | s2-trans-d6-tacnode-s | `(y^2-z^4)^2*x+x^5` | embedded resolution | 19.8 | none |
| 162 | s2-trans-e13-d4-s | `(y^3-z^3)^3+(y^3-z^3)*x^5` | intrinsic resolution | 16.0 | embedded resolution 3.8 |
| 163 | s2-trans-e13-d5 | `x^3+x*(y^2*z+z^4)^5` | pole-check replay | 16.2 | embedded resolution 1.7, intrinsic resolution 1.8 |
| 164 | s2-trans-e13-d5-s | `(y^2*z+z^4)^3+(y^2*z+z^4)*x^5` | embedded resolution | 19.8 | none |
| 165 | s2-trans-e13-e6-s | `(y^3-z^4)^3+(y^3-z^4)*x^5` | embedded resolution | 19.9 | none |
| 166 | s2-trans-e13-tacnode | `x^3+x*(y^2-z^4)^5` | pole-check replay | 17.0 | embedded resolution 1.3, intrinsic resolution 1.6 |
| 167 | s2-trans-e7-d4-s | `(y^3-z^3)^3+(y^3-z^3)*x^3` | embedded resolution | 19.5 | none |
| 168 | s2-trans-e7-d5-s | `(y^2*z+z^4)^3+(y^2*z+z^4)*x^3` | embedded resolution | 19.6 | none |
| 169 | s2-trans-e7-e6-s | `(y^3-z^4)^3+(y^3-z^4)*x^3` | embedded resolution | 19.7 | none |
| 170 | s2-trans-w13-d4-s | `(y^3-z^3)^4+(y^3-z^3)*x^4` | intrinsic resolution | 5.8 | embedded resolution 13.9 |
| 171 | s2-trans-w13-d5 | `x^4+x*(y^2*z+z^4)^4` | embedded resolution | 19.8 | none |
| 172 | s2-trans-w13-tacnode-s | `(y^2-z^4)^4+(y^2-z^4)*x^4` | embedded resolution | 19.9 | none |
| 173 | s2-trans-z11-d4 | `x^3*(y^3-z^3)+(y^3-z^3)^5` | embedded resolution | 19.7 | none |
| 174 | s2-trans-z11-d4-s | `(y^3-z^3)^3*x+x^5` | intrinsic resolution | 18.1 | embedded resolution 1.7 |
| 175 | s2-trans-z11-d5 | `x^3*(y^2*z+z^4)+(y^2*z+z^4)^5` | embedded resolution | 19.7 | none |
| 176 | s2-trans-z13-cusp-s | `(y^2-z^3)^3*x+x^6` | intrinsic resolution | 17.7 | embedded resolution 2.1 |
| 177 | s2-trans-z13-d4 | `x^3*(y^3-z^3)+(y^3-z^3)^6` | embedded resolution | 19.8 | none |
| 178 | s2-trans-z13-d5 | `x^3*(y^2*z+z^4)+(y^2*z+z^4)^6` | embedded resolution | 19.6 | none |
| 179 | s2-trans-z13-tacnode | `x^3*(y^2-z^4)+(y^2-z^4)^6` | embedded resolution | 19.8 | none |
| 180 | s2-degenerate-a4-2-2-x | `(y^2-x^5)^2+z^2*x` | embedded resolution | 19.8 | none |
| 181 | s2-degenerate-a4-2-2-x2y2 | `(y^2-x^5)^2+z^2*(x^2+y^2)` | embedded resolution | 19.8 | none |
| 182 | s2-degenerate-a4-2-3-x | `(y^2-x^5)^2+z^3*x` | embedded resolution | 19.8 | none |
| 183 | s2-degenerate-a4-2-3-x2y2 | `(y^2-x^5)^2+z^3*(x^2+y^2)` | embedded resolution | 19.8 | none |
| 184 | s2-degenerate-a4-2-3-xy | `(y^2-x^5)^2+z^3*(x*y)` | embedded resolution | 19.9 | none |
| 185 | s2-degenerate-a4-3-2-x | `(y^2-x^5)^3+z^2*x` | embedded resolution | 19.8 | none |
| 186 | s2-degenerate-a4-3-2-x2y2 | `(y^2-x^5)^3+z^2*(x^2+y^2)` | embedded resolution | 19.9 | none |
| 187 | s2-degenerate-a4-3-2-xy | `(y^2-x^5)^3+z^2*(x*y)` | embedded resolution | 19.7 | none |
| 188 | s2-degenerate-a6-2-2-x | `(y^2-x^7)^2+z^2*x` | embedded resolution | 19.8 | none |
| 189 | s2-degenerate-a6-2-2-x2y2 | `(y^2-x^7)^2+z^2*(x^2+y^2)` | embedded resolution | 19.5 | none |
| 190 | s2-degenerate-a6-2-3-x | `(y^2-x^7)^2+z^3*x` | intrinsic resolution | 17.9 | embedded resolution 1.9 |
| 191 | s2-degenerate-a6-2-3-x2y2 | `(y^2-x^7)^2+z^3*(x^2+y^2)` | embedded resolution | 19.8 | none |
| 192 | s2-degenerate-a6-2-3-xy | `(y^2-x^7)^2+z^3*(x*y)` | embedded resolution | 19.6 | none |
| 193 | s2-degenerate-a6-3-2-x | `(y^2-x^7)^3+z^2*x` | embedded resolution | 19.8 | none |
| 194 | s2-degenerate-a6-3-2-x2y2 | `(y^2-x^7)^3+z^2*(x^2+y^2)` | embedded resolution | 19.8 | none |
| 195 | s2-degenerate-a6-3-2-xy | `(y^2-x^7)^3+z^2*(x*y)` | embedded resolution | 19.8 | none |
| 196 | s2-degenerate-cusp-2-2-x | `(y^2-x^3)^2+z^2*x` | embedded resolution | 19.9 | none |
| 197 | s2-degenerate-cusp-2-2-x2y2 | `(y^2-x^3)^2+z^2*(x^2+y^2)` | embedded resolution | 19.9 | none |
| 198 | s2-degenerate-cusp-2-3-xy | `(y^2-x^3)^2+z^3*(x*y)` | embedded resolution | 19.8 | none |
| 199 | s2-degenerate-cusp-3-2-x | `(y^2-x^3)^3+z^2*x` | embedded resolution | 19.8 | none |
| 200 | s2-degenerate-cusp-3-2-x2y2 | `(y^2-x^3)^3+z^2*(x^2+y^2)` | embedded resolution | 19.8 | none |
| 201 | s2-degenerate-d4-2-2-x2y2 | `(x^3-y^3)^2+z^2*(x^2+y^2)` | embedded resolution | 19.8 | none |
| 202 | s2-degenerate-d4-2-2-xy | `(x^3-y^3)^2+z^2*(x*y)` | embedded resolution | 19.9 | none |
| 203 | s2-degenerate-d4-3-2-x | `(x^3-y^3)^3+z^2*x` | embedded resolution | 19.9 | none |
| 204 | s2-degenerate-d4-3-2-y | `(x^3-y^3)^3+z^2*y` | embedded resolution | 19.9 | none |
| 205 | s2-degenerate-e6-2-2-x2y2 | `(y^3-x^4)^2+z^2*(x^2+y^2)` | embedded resolution | 19.7 | none |
| 206 | s2-degenerate-e6-2-2-y | `(y^3-x^4)^2+z^2*y` | embedded resolution | 19.8 | none |
| 207 | s2-degenerate-e6-2-3-x | `(y^3-x^4)^2+z^3*x` | embedded resolution | 19.8 | none |
| 208 | s2-degenerate-e6-2-3-x2y2 | `(y^3-x^4)^2+z^3*(x^2+y^2)` | embedded resolution | 19.8 | none |
| 209 | s2-degenerate-e6-3-2-x2y2 | `(y^3-x^4)^3+z^2*(x^2+y^2)` | embedded resolution | 19.8 | none |
| 210 | s2-degenerate-e6-3-2-y | `(y^3-x^4)^3+z^2*y` | embedded resolution | 19.8 | none |
| 211 | s2-degenerate-e8-2-2-x2y2 | `(y^3-x^5)^2+z^2*(x^2+y^2)` | embedded resolution | 19.8 | none |
| 212 | s2-degenerate-e8-2-2-xy | `(y^3-x^5)^2+z^2*(x*y)` | embedded resolution | 19.8 | none |
| 213 | s2-degenerate-e8-2-3-x | `(y^3-x^5)^2+z^3*x` | embedded resolution | 19.4 | none |
| 214 | s2-degenerate-e8-2-3-x2y2 | `(y^3-x^5)^2+z^3*(x^2+y^2)` | embedded resolution | 19.8 | none |
| 215 | s2-degenerate-e8-3-2-x | `(y^3-x^5)^3+z^2*x` | embedded resolution | 19.9 | none |
| 216 | s2-degenerate-e8-3-2-x2y2 | `(y^3-x^5)^3+z^2*(x^2+y^2)` | embedded resolution | 19.9 | none |
| 217 | s2-degenerate-e8-3-2-xy | `(y^3-x^5)^3+z^2*(x*y)` | embedded resolution | 19.8 | none |
| 218 | s2-degenerate-e8-3-2-y | `(y^3-x^5)^3+z^2*y` | embedded resolution | 19.8 | none |
| 219 | s2-degenerate-node-2-2-x2y2 | `(y^2-x^2)^2+z^2*(x^2+y^2)` | intrinsic resolution | 18.3 | embedded resolution 1.4 |
| 220 | s2-degenerate-node-2-2-xy | `(y^2-x^2)^2+z^2*(x*y)` | intrinsic resolution | 18.8 | embedded resolution 1.0 |
| 221 | s2-degenerate-node-2-3-x | `(y^2-x^2)^2+z^3*x` | embedded resolution | 19.4 | none |
| 222 | s2-degenerate-node-3-2-x2y2 | `(y^2-x^2)^3+z^2*(x^2+y^2)` | embedded resolution | 19.9 | none |
| 223 | s2-degenerate-node-3-2-xy | `(y^2-x^2)^3+z^2*(x*y)` | embedded resolution | 19.4 | none |
| 224 | s2-degenerate-tacnode-2-2-x2y2 | `(y^2-x^4)^2+z^2*(x^2+y^2)` | intrinsic resolution | 2.4 | embedded resolution 17.2 |
| 225 | s2-degenerate-tacnode-2-2-y | `(y^2-x^4)^2+z^2*y` | intrinsic resolution | 18.9 | embedded resolution 0.9 |
| 226 | s2-degenerate-tacnode-2-3-x2y2 | `(y^2-x^4)^2+z^3*(x^2+y^2)` | embedded resolution | 19.9 | none |
| 227 | s2-degenerate-tacnode-2-3-y | `(y^2-x^4)^2+z^3*y` | embedded resolution | 19.8 | none |
| 228 | s2-degenerate-tacnode-3-2-x2y2 | `(y^2-x^4)^3+z^2*(x^2+y^2)` | embedded resolution | 19.9 | none |
| 229 | s2-degenerate-tacnode-3-2-y | `(y^2-x^4)^3+z^2*y` | embedded resolution | 19.7 | none |
| 230 | s2-space-4611-2-2 | `(y^2-x^3)^2+(z^2-x^4*y)^2` | embedded resolution | 19.9 | none |
| 231 | s2-space-4611-2-3 | `(y^2-x^3)^2+(z^2-x^4*y)^3` | embedded resolution | 19.9 | none |
| 232 | s2-space-4611-2-uv-3 | `(y^2-x^3)^2+(y^2-x^3)*(z^2-x^4*y)+(z^2-x^4*y)^3` | embedded resolution | 19.8 | none |
| 233 | s2-space-4611-2-x2 | `(y^2-x^3)^2+x*(z^2-x^4*y)^2` | intrinsic resolution | 17.1 | embedded resolution 2.8 |
| 234 | s2-space-4611-3-2 | `(y^2-x^3)^3+(z^2-x^4*y)^2` | intrinsic resolution | 15.4 | embedded resolution 4.4 |
| 235 | s2-space-4611-3-3 | `(y^2-x^3)^3+(z^2-x^4*y)^3` | embedded resolution | 19.7 | none |
| 236 | s2-space-467-2-2 | `(y^2-x^3)^2+(z^2-x^2*y)^2` | intrinsic resolution | 19.1 | embedded resolution 0.7 |
| 237 | s2-space-467-2-3 | `(y^2-x^3)^2+(z^2-x^2*y)^3` | embedded resolution | 19.6 | none |
| 238 | s2-space-467-2-4 | `(y^2-x^3)^2+(z^2-x^2*y)^4` | intrinsic resolution | 17.4 | embedded resolution 2.5 |
| 239 | s2-space-467-2-uv-3 | `(y^2-x^3)^2+(y^2-x^3)*(z^2-x^2*y)+(z^2-x^2*y)^3` | embedded resolution | 19.6 | none |
| 240 | s2-space-467-3-3 | `(y^2-x^3)^3+(z^2-x^2*y)^3` | intrinsic resolution | 18.2 | embedded resolution 1.4 |
| 241 | s2-space-467-d4 | `(y^2-x^3)^2*(z^2-x^2*y)+(z^2-x^2*y)^3` | embedded resolution | 19.8 | none |
| 242 | s2-space-469-2-2 | `(y^2-x^3)^2+(z^2-y^3)^2` | intrinsic resolution | 18.5 | embedded resolution 1.3 |
| 243 | s2-space-469-2-3 | `(y^2-x^3)^2+(z^2-y^3)^3` | embedded resolution | 19.8 | none |
| 244 | s2-space-469-2-uv-3 | `(y^2-x^3)^2+(y^2-x^3)*(z^2-y^3)+(z^2-y^3)^3` | embedded resolution | 19.8 | none |
| 245 | s2-space-469-3-3 | `(y^2-x^3)^3+(z^2-y^3)^3` | intrinsic resolution | 18.6 | embedded resolution 1.3 |
| 246 | s2-space-469-d4 | `(y^2-x^3)^2*(z^2-y^3)+(z^2-y^3)^3` | intrinsic resolution | 17.5 | embedded resolution 2.3 |
| 247 | s2-space-6910-2-2 | `(y^2-x^3)^2+(z^3-x^5)^2` | embedded resolution | 19.4 | none |
| 248 | s2-space-6910-2-4 | `(y^2-x^3)^2+(z^3-x^5)^4` | embedded resolution | 19.6 | none |
| 249 | s2-space-6910-2-uv-3 | `(y^2-x^3)^2+(y^2-x^3)*(z^3-x^5)+(z^3-x^5)^3` | embedded resolution | 19.6 | none |
| 250 | s2-space-6910-3-2 | `(y^2-x^3)^3+(z^3-x^5)^2` | embedded resolution | 19.6 | none |
| 251 | s2-space-6910-3-3 | `(y^2-x^3)^3+(z^3-x^5)^3` | embedded resolution | 19.6 | none |
| 252 | s2-space-cone-cusp-2-2 | `(x*y-z^2)^2+(x^2-y^3)^2` | intrinsic resolution | 12.8 | embedded resolution 7.0 |
| 253 | s2-space-cone-cusp-2-uv-3 | `(x*y-z^2)^2+(x*y-z^2)*(x^2-y^3)+(x^2-y^3)^3` | embedded resolution | 19.7 | none |
| 254 | s2-space-cone-cusp-2-x2 | `(x*y-z^2)^2+x*(x^2-y^3)^2` | intrinsic resolution | 17.1 | embedded resolution 2.6 |
| 255 | s2-space-cone-cusp-3-3 | `(x*y-z^2)^3+(x^2-y^3)^3` | embedded resolution | 19.6 | none |
| 256 | s2-space-cone-cusp-d4 | `(x*y-z^2)^2*(x^2-y^3)+(x^2-y^3)^3` | embedded resolution | 19.8 | none |
| 257 | s2-space-two-cones-2-2 | `(x*y-z^2)^2+(x*z-y^2-z^3)^2` | embedded resolution | 19.8 | none |
| 258 | s2-space-two-cones-2-uv-3 | `(x*y-z^2)^2+(x*y-z^2)*(x*z-y^2-z^3)+(x*z-y^2-z^3)^3` | embedded resolution | 19.8 | none |
| 259 | s2-space-two-cones-2-x2 | `(x*y-z^2)^2+x*(x*z-y^2-z^3)^2` | embedded resolution | 19.8 | none |
| 260 | s2-space-two-cones-3-2 | `(x*y-z^2)^3+(x*z-y^2-z^3)^2` | embedded resolution | 19.8 | none |
| 261 | s2-space-two-cones-3-3 | `(x*y-z^2)^3+(x*z-y^2-z^3)^3` | embedded resolution | 19.8 | none |
| 262 | s2-space-two-cones-d4 | `(x*y-z^2)^2*(x*z-y^2-z^3)+(x*z-y^2-z^3)^3` | embedded resolution | 19.8 | none |
| 263 | s2-quasi-ordinary-02-33 | `x^6*y^6-2*x^3*y^3*z^4-12*x^3*y^4*z^2-2*x^3*y^5+z^8-4*y*z^6+6*y^2*z^4-4*y^3*z^2+y^4` | embedded resolution | 19.7 | none |
| 264 | s2-quasi-ordinary-20-23 | `x^4*y^6-2*x^2*y^3*z^4-12*x^3*y^3*z^2+z^8-2*x^4*y^3-4*x*z^6+6*x^2*z^4-4*x^3*z^2+x^4` | embedded resolution | 19.5 | none |
| 265 | s2-quasi-ordinary-20-41 | `x^8*y^2-2*x^4*y*z^4-12*x^5*y*z^2+z^8-2*x^6*y-4*x*z^6+6*x^2*z^4-4*x^3*z^2+x^4` | pole-check replay | 18.2 | embedded resolution 0.8, intrinsic resolution 0.7 |
| 266 | s2-quasi-ordinary-20-51 | `x^10*y^2-2*x^5*y*z^4-12*x^6*y*z^2-2*x^7*y+z^8-4*x*z^6+6*x^2*z^4-4*x^3*z^2+x^4` | pole-check replay | 1.1 | embedded resolution 17.9, intrinsic resolution 0.7 |
| 267 | s2-quasi-ordinary-22-32 | `x^6*y^4-2*x^5*y^4-12*x^4*y^3*z^2-2*x^3*y^2*z^4+x^4*y^4-4*x^3*y^3*z^2+6*x^2*y^2*z^4-4*x*y*z^6+z^8` | embedded resolution | 19.7 | none |
| 268 | s2-quasi-ordinary-22-34 | `x^6*y^8-2*x^5*y^6-12*x^4*y^5*z^2-2*x^3*y^4*z^4+x^4*y^4-4*x^3*y^3*z^2+6*x^2*y^2*z^4-4*x*y*z^6+z^8` | embedded resolution | 19.8 | none |
| 269 | s2-quasi-ordinary-24-25 | `x^4*y^10-2*x^4*y^9+x^4*y^8-12*x^3*y^7*z^2-4*x^3*y^6*z^2-2*x^2*y^5*z^4+6*x^2*y^4*z^4-4*x*y^2*z^6+z^8` | embedded resolution | 19.9 | none |
| 270 | s2-quasi-ordinary-24-27 | `x^4*y^14-2*x^4*y^11-12*x^3*y^9*z^2-2*x^2*y^7*z^4+x^4*y^8-4*x^3*y^6*z^2+6*x^2*y^4*z^4-4*x*y^2*z^6+z^8` | embedded resolution | 19.9 | none |
| 271 | s2-quasi-ordinary-24-35 | `x^6*y^10-2*x^5*y^9-12*x^4*y^7*z^2+x^4*y^8-2*x^3*y^5*z^4-4*x^3*y^6*z^2+6*x^2*y^4*z^4-4*x*y^2*z^6+z^8` | pole-check replay | 14.6 | embedded resolution 3.4, intrinsic resolution 1.8 |
| 272 | s2-quasi-ordinary-24-45 | `x^8*y^10-2*x^6*y^9-12*x^5*y^7*z^2-2*x^4*y^5*z^4+x^4*y^8-4*x^3*y^6*z^2+6*x^2*y^4*z^4-4*x*y^2*z^6+z^8` | pole-check replay | 9.9 | embedded resolution 8.5, intrinsic resolution 0.9 |
| 273 | s2-quasi-ordinary-24-55 | `x^10*y^10-2*x^7*y^9-12*x^6*y^7*z^2-2*x^5*y^5*z^4+x^4*y^8-4*x^3*y^6*z^2+6*x^2*y^4*z^4-4*x*y^2*z^6+z^8` | embedded resolution | 19.8 | none |
| 274 | s2-quasi-ordinary-42-73 | `x^14*y^6-2*x^11*y^5-12*x^9*y^4*z^2-2*x^7*y^3*z^4+x^8*y^4-4*x^6*y^3*z^2+6*x^4*y^2*z^4-4*x^2*y*z^6+z^8` | embedded resolution | 19.6 | none |
| 275 | s2-quasi-ordinary-62-63 | `x^12*y^6-2*x^12*y^5+x^12*y^4-12*x^9*y^4*z^2-4*x^9*y^3*z^2-2*x^6*y^3*z^4+6*x^6*y^2*z^4-4*x^3*y*z^6+z^8` | embedded resolution | 19.5 | none |
| 276 | s2-quasi-ordinary-62-72 | `x^14*y^4-2*x^13*y^4+x^12*y^4-12*x^10*y^3*z^2-4*x^9*y^3*z^2-2*x^7*y^2*z^4+6*x^6*y^2*z^4-4*x^3*y*z^6+z^8` | embedded resolution | 19.7 | none |
| 277 | s2-quasi-ordinary-62-73 | `x^7*y^3-x^6*y^2+4*x^5*y^2*z+2*x^3*y*z^2-z^4` | pole-check replay | 17.7 | embedded resolution 1.3, intrinsic resolution 0.7 |
| 278 | s2-quasi-ordinary-62-74 | `x^14*y^8-2*x^13*y^6-12*x^10*y^5*z^2+x^12*y^4-2*x^7*y^4*z^4-4*x^9*y^3*z^2+6*x^6*y^2*z^4-4*x^3*y*z^6+z^8` | embedded resolution | 19.9 | none |
| 279 | s2-quasi-ordinary-62-83 | `x^16*y^6-2*x^14*y^5-12*x^11*y^4*z^2+x^12*y^4-2*x^8*y^3*z^4-4*x^9*y^3*z^2+6*x^6*y^2*z^4-4*x^3*y*z^6+z^8` | embedded resolution | 19.9 | none |
| 280 | s2-developable-126 | `-128*x^6*z+24*x^2*y^5+240*x^4*y*z-25*y^6-120*x^2*y^2*z+10*y^3*z-z^2` | embedded resolution | 19.8 | none |
| 281 | s2-developable-134 | `-27*x^4*z^2+16*x^3*y^3+6*x^2*y^2*z+48*x*y*z^2-27*y^4-16*z^3` | embedded resolution | 19.8 | none |
| 282 | s2-developable-145 | `-256*x^5*z^3+125*x^4*y^4+60*x^3*y^3*z+30*x^2*y^2*z^2+540*x*y*z^3-256*y^5-243*z^4` | embedded resolution | 19.8 | none |
| 283 | s2-developable-237 | `-3888*x^7*z+1792*x^3*y^5+5985*x^4*y^2*z-2000*y^7-1680*x*y^4*z-210*x^2*y*z^2+z^3` | embedded resolution | 19.7 | none |
| 284 | s2-developable-345 | `-16*x^5*z+15*x^4*y^2-30*x^2*y*z^2+80*x*y^3*z-48*y^5-z^4` | embedded resolution | 19.8 | none |
| 285 | s2-steiner-222-sum-m1 | `(x*y)^2+(y*z)^2+(z*x)^2-x*y*z*(x+y+z)` | intrinsic resolution | 17.7 | embedded resolution 2.0 |
| 286 | s2-steiner-222-x-2 | `(x*y)^2+(y*z)^2+(z*x)^2+2*x*y*z*x` | intrinsic resolution | 12.6 | embedded resolution 7.2 |
| 287 | s2-steiner-222-x-m1 | `(x*y)^2+(y*z)^2+(z*x)^2-x*y*z*x` | intrinsic resolution | 19.7 | embedded resolution 0.2 |
| 288 | s2-steiner-223-sum-2 | `(x*y)^2+(y*z)^2+(z*x)^3+2*x*y*z*(x+y+z)` | embedded resolution | 19.9 | none |
| 289 | s2-steiner-333-x-2 | `(x*y)^3+(y*z)^3+(z*x)^3+2*x*y*z*x` | pole-check replay | 19.2 | embedded resolution 0.2, intrinsic resolution 0.3 |
| 290 | s2-steiner-333-x-m1 | `(x*y)^3+(y*z)^3+(z*x)^3-x*y*z*x` | pole-check replay | 18.5 | embedded resolution 0.5, intrinsic resolution 0.4 |
| 291 | s2-cylinder-sheet-a6-x2y2 | `(y^2-x^7)*(z-(x^2+y^2))` | embedded resolution | 19.8 | none |
| 292 | s2-cylinder-sheet-a6-xy | `(y^2-x^7)*(z-x*y)` | intrinsic resolution | 5.6 | embedded resolution 14.1 |
| 293 | s2-cylinder-sheet-e8-xy | `(y^3-x^5)*(z-x*y)` | intrinsic resolution | 18.4 | embedded resolution 1.4 |
| 294 | s2-cylinder-sheet-tacnode-plane | `(y^2-x^4)*z` | intrinsic resolution | 19.1 | embedded resolution 0.5 |
| 295 | s2-cylinder-sheet-tacnode-x2 | `(y^2-x^4)*(z-x^2)` | intrinsic resolution | 19.6 | embedded resolution 0.2 |
| 296 | s2-cylinder-sheet-tacnode-x2y2 | `(y^2-x^4)*(z-(x^2+y^2))` | embedded resolution | 19.9 | none |
| 297 | s2-cylinder-sheet-tacnode-x3 | `(y^2-x^4)*(z-x^3)` | intrinsic resolution | 19.4 | embedded resolution 0.4 |
| 298 | s2-cylinder-sheet-tacnode-xy | `(y^2-x^4)*(z-x*y)` | intrinsic resolution | 19.1 | embedded resolution 0.4 |
| 299 | s2-cylinder-sheet-tacnode-y2 | `(y^2-x^4)*(z-y^2)` | intrinsic resolution | 19.4 | embedded resolution 0.3 |
| 300 | s2-cylinder-sheet-tacnode-y3 | `(y^2-x^4)*(z-y^3)` | intrinsic resolution | 19.5 | embedded resolution 0.3 |
| 301 | s2-chain-12135 | `x*y^2+y*z^3+z^5` | embedded resolution | 19.8 | none |
| 302 | s2-chain-13334 | `x*y^3+y^3*z^3+z^4` | embedded resolution | 19.9 | none |
| 303 | s2-chain-13424 | `x*y^3+y^4*z^2+z^4` | embedded resolution | 19.8 | none |
| 304 | s2-chain-21326 | `x^2*y+y^3*z^2+z^6` | embedded resolution | 19.8 | none |
| 305 | s2-chain-31334 | `x^3*y+y^3*z^3+z^4` | embedded resolution | 19.8 | none |
| 306 | s2-chain-31424 | `x^3*y+y^4*z^2+z^4` | embedded resolution | 19.5 | none |
| 307 | s2-chain-42213 | `x^4*y^2+y^2*z+z^3` | embedded resolution | 19.7 | none |
| 308 | s2-newton-115 | `-y*z^3-y^2*z^2+x^3*y*z^4+3*x^4*y*z^2+2*x^4*y^3` | pole-check replay | 17.7 | embedded resolution 0.3, intrinsic resolution 1.9 |
| 309 | s2-newton-120 | `-z^3-2*x*y^4*z^3-2*x^2*y*z^2+x^3*y^4*z` | pole-check replay | 19.2 | embedded resolution 0.3, intrinsic resolution 0.3 |
| 310 | s2-newton-125 | `-2*y^2*z^3+2*x*y*z^3-x*y^3*z-2*x^2*y^2*z+x^3*y^2+3*x^4*y*z^2` | intrinsic resolution | 19.4 | embedded resolution 0.4 |
| 311 | s2-newton-13 | `2*y^2*z^3+y^3*z^4-y^4+x*y*z^4+2*x^2*y^2*z^3+3*x^2*y^4*z^2` | pole-check replay | 19.2 | embedded resolution 0.3, intrinsic resolution 0.3 |
| 312 | s2-newton-137 | `-y^2*z-2*x*y^3-x*y^3*z^2+3*x^2*y*z^2+x^2*y^3*z-2*x^4*y^3*z` | pole-check replay | 16.9 | embedded resolution 1.9, intrinsic resolution 0.9 |
| 313 | s2-newton-141 | `2*x*y^2*z^4-2*x*y^4*z^3-2*x^2*z^3+3*x^2*y^4*z^2-2*x^5*y^2*z` | pole-check replay | 13.7 | embedded resolution 0.6, intrinsic resolution 5.4 |
| 314 | s2-newton-156 | `-y^4*z^3+x^2*y^4+x^3*y^2+3*x^5*y*z^2` | pole-check replay | 17.8 | embedded resolution 0.7, intrinsic resolution 1.0 |
| 315 | s2-newton-165 | `-y*z^3-2*x*z^2-x^3*y^3-x^5*z^3+x^5*y^2*z` | pole-check replay | 18.2 | embedded resolution 0.8, intrinsic resolution 0.8 |
| 316 | s2-newton-177 | `3*x*y^2-2*x*y^2*z^4+2*x^2*y^3+2*x^3*y^2*z^2+2*x^3*y^4*z+x^4*z^4` | pole-check replay | 19.1 | embedded resolution 0.3, intrinsic resolution 0.4 |
| 317 | s2-newton-19 | `2*y*z^3-2*x^2*y^2*z^2+2*x^2*y^2*z^4-x^2*y^3*z^2+x^2*y^4*z` | pole-check replay | 19.3 | embedded resolution 0.2, intrinsic resolution 0.3 |
| 318 | s2-newton-199 | `3*x*y*z^2+x*y*z^3-x*y^4*z^2-2*x^2*y^3*z+2*x^2*y^4*z^2+x^3*y^2` | pole-check replay | 3.4 | embedded resolution 15.5, intrinsic resolution 0.8 |
| 319 | s2-newton-214 | `3*y^4*z+x*y^4+2*x^2*y^2*z+3*x^3*y^2*z^3-x^4*y*z^3+2*x^5*y^3` | pole-check replay | 17.2 | embedded resolution 1.2, intrinsic resolution 1.2 |
| 320 | s2-newton-224 | `2*x*y*z-x*y*z^3-2*x*y^2*z^2-x^2*y*z^2-x^3*z^2` | intrinsic resolution | 19.6 | embedded resolution 0.2 |
| 321 | s2-newton-239 | `3*y^4*z-x^2*y^3*z^3-x^3*y^4-x^5*y*z` | pole-check replay | 15.7 | embedded resolution 2.6, intrinsic resolution 1.4 |
| 322 | s2-newton-251 | `z^4-x*y^3+3*x^3*y*z^3+2*x^3*y^2` | embedded resolution | 19.9 | none |
| 323 | s2-newton-258 | `-2*x*y^2*z^2-2*x*y^3*z^2-2*x^2*y^3*z-x^3*y^3-2*x^4*z^4+2*x^5*z^2` | pole-check replay | 17.2 | embedded resolution 1.4, intrinsic resolution 1.0 |
| 324 | s2-newton-268 | `3*x*y^4*z+3*x^3*y^2*z^3-2*x^4*y^2*z^2+x^5*y*z^2` | pole-check replay | 17.9 | embedded resolution 0.6, intrinsic resolution 1.1 |
| 325 | s2-newton-31 | `-2*y^3*z^2+3*x*y*z^3+3*x*y^3*z^4-2*x*y^4+x^2*y^2*z^4` | embedded resolution | 19.8 | none |
| 326 | s2-newton-39 | `-z^3+2*y^3*z^3+x^2*z^2-2*x^2*y^4-x^3*y^3*z+2*x^3*y^4` | pole-check replay | 18.9 | embedded resolution 0.6, intrinsic resolution 0.3 |
| 327 | s2-newton-46 | `-y^2*z+2*y^3-2*y^3*z^2+x^2*y^4*z^2+x^3*z^3-x^3*y*z^3` | pole-check replay | 19.2 | embedded resolution 0.2, intrinsic resolution 0.4 |
| 328 | s2-newton-51 | `-2*y^4*z^4+3*x*y^3*z^3+x*y^4*z-2*x*y^4*z^2+3*x^4*y*z^3` | pole-check replay | 18.7 | embedded resolution 0.5, intrinsic resolution 0.5 |
| 329 | s2-newton-62 | `3*x*z^2+3*x*z^4+x*y*z^2-x^2*z^2+2*x^2*y*z+2*x^4*y*z^2` | pole-check replay | 19.1 | embedded resolution 0.3, intrinsic resolution 0.4 |
| 330 | s2-newton-71 | `-y^4*z^3-2*x*y^2*z^2-x^2*y*z+3*x^3*y^2*z^3-x^4*y*z^3` | pole-check replay | 18.6 | embedded resolution 0.3, intrinsic resolution 0.9 |
| 331 | s2-newton-77 | `-2*x*y*z^2-2*x*y^3*z^2+x^3*y^2*z^3+x^4*y*z^3+3*x^4*y^3` | pole-check replay | 18.6 | embedded resolution 0.2, intrinsic resolution 1.0 |
| 332 | s2-newton-8 | `2*y^3*z^4-x^2*y^2*z+3*x^4*y*z+x^5*z^3+2*x^5*y^2*z` | pole-check replay | 16.7 | embedded resolution 0.5, intrinsic resolution 2.5 |
| 333 | s2-newton-83 | `2*y*z^2+3*y*z^3+x*y^4*z^2-x^2*y^4+x^3*y*z^3-2*x^3*y^2*z^3` | pole-check replay | 18.7 | embedded resolution 0.4, intrinsic resolution 0.7 |

### Threefolds (408)

| # | ID | Equation | Running at 20 s | Time in step (s) | Finished steps (s) |
| ---: | --- | --- | --- | ---: | --- |
| 1 | t3-cdv-laufer-3 | `x^2+y^3+t*z^2+t^7*y` | embedded resolution | 19.8 | none |
| 2 | t3-cdv-laufer-4 | `x^2+y^3+t*z^2+t^9*y` | embedded resolution | 19.8 | none |
| 3 | t3-cdv-laufer-5 | `x^2+y^3+t*z^2+t^11*y` | embedded resolution | 19.5 | none |
| 4 | t3-cusp-4-5-6-7 | `x^4+y^5+z^6+t^7+x*y*z*t` | embedded resolution | 19.7 | none |
| 5 | t3-join-branch467-a1 | `(y^2-x^3)^2+x^5*y+z^2+t^2` | embedded resolution | 19.9 | none |
| 6 | t3-join-branch467-a3 | `(y^2-x^3)^2+x^5*y+z^2+t^4` | embedded resolution | 19.8 | none |
| 7 | t3-join-branch467-branch467 | `(y^2-x^3)^2+x^5*y+(t^2-z^3)^2+z^5*t` | embedded resolution | 19.7 | none |
| 8 | t3-join-branch467-e12 | `(y^2-x^3)^2+x^5*y+z^3+t^7+z*t^5` | embedded resolution | 19.8 | none |
| 9 | t3-join-branch467-e6 | `(y^2-x^3)^2+x^5*y+z^3+t^4` | embedded resolution | 19.8 | none |
| 10 | t3-join-d4-branch467 | `x^2*y+y^3+(t^2-z^3)^2+z^5*t` | embedded resolution | 19.8 | none |
| 11 | t3-join-d5-branch467 | `x^2*y+y^4+(t^2-z^3)^2+z^5*t` | embedded resolution | 19.8 | none |
| 12 | t3-join-d6-branch467 | `x^2*y+y^5+(t^2-z^3)^2+z^5*t` | embedded resolution | 19.9 | none |
| 13 | t3-join-e7-branch467 | `x^3+x*y^3+(t^2-z^3)^2+z^5*t` | embedded resolution | 19.5 | none |
| 14 | t3-join-e7-j10 | `x^3+x*y^3+z^3+t^6+z^2*t^2` | intrinsic resolution | 19.6 | embedded resolution 0.3 |
| 15 | t3-join-j10-branch467 | `x^3+y^6+x^2*y^2+(t^2-z^3)^2+z^5*t` | embedded resolution | 19.9 | none |
| 16 | t3-join-w13-branch467 | `x^4+x*y^4+(t^2-z^3)^2+z^5*t` | embedded resolution | 19.8 | none |
| 17 | t3-join-x9-branch467 | `x^4+y^4+x^2*y^2+(t^2-z^3)^2+z^5*t` | embedded resolution | 19.8 | none |
| 18 | t3-join-z11-branch467 | `x^3*y+y^5+(t^2-z^3)^2+z^5*t` | embedded resolution | 19.7 | none |
| 19 | t3-newton-convenient-12 | `x^2+y^2+z^6+t^3+z^2*t-z^3*t+3*z^3*t+2*z*t^2` | embedded resolution | 19.8 | none |
| 20 | t3-newton-convenient-16 | `x^7+y^7+z^5+t^6+x^3*y^2*z-x*y^3*t-x*t` | embedded resolution | 19.8 | none |
| 21 | t3-newton-convenient-34 | `x^5+y^7+z^3+t^6+2*x^3*z-2*x^2*y^2*t+2*z^2*t+3*y^3*z` | Tjurina number | 12.4 | embedded resolution 5.8, intrinsic resolution 0.7, Milnor number 1.0 |
| 22 | t3-newton-convenient-35 | `x^5+y^7+z^7+t^4+3*x*z^2*t^2-x*y*t-x^2*t^2+3*x^3*y` | Tjurina number | 4.4 | embedded resolution 14.2, intrinsic resolution 1.0, Milnor number 0.2 |
| 23 | t3-newton-convenient-47 | `x^7+y^6+z^5+t^7+x*y^2*z*t^2-y*z^3+x^2*y^2*z*t+3*z^2*t^3` | embedded resolution | 19.8 | none |
| 24 | t3-superisolated-3a2-generic | `x*y*z-t^3+(x-y+2*z+t)^4` | embedded resolution | 19.8 | none |
| 25 | t3-superisolated-a4-generic | `t*x*y+x*z^2+y^3+x^3+(x+2*y+3*z+5*t)^4` | embedded resolution | 19.9 | none |
| 26 | t3-superisolated-a5 | `t*x*y+x*z^2+y^3+t^4` | embedded resolution | 19.9 | none |
| 27 | t3-superisolated-a5-generic | `t*x*y+x*z^2+y^3+(x+2*y+3*z+5*t)^4` | embedded resolution | 19.8 | none |
| 28 | t3-superisolated-e6-generic | `t*x^2+x*z^2+y^3+(x+2*y+3*z+5*t)^4` | embedded resolution | 19.8 | none |
| 29 | t3-chain2-chain2-4234 | `x^4*y+y^2+z^3*t+t^4` | embedded resolution | 19.7 | none |
| 30 | t3-chain2-chain2-4243 | `x^4*y+y^2+z^4*t+t^3` | embedded resolution | 19.9 | none |
| 31 | t3-chain2-fermat2-4223 | `x^4*y+y^2+z^2+t^3` | embedded resolution | 19.8 | none |
| 32 | t3-chain2-fermat2-4233 | `x^4*y+y^2+z^3+t^3` | embedded resolution | 19.7 | none |
| 33 | t3-chain3-fermat-2424 | `x^2*y+y^4*z+z^2+t^4` | embedded resolution | 19.8 | none |
| 34 | t3-chain3-fermat-3424 | `x^3*y+y^4*z+z^2+t^4` | embedded resolution | 19.8 | none |
| 35 | t3-chain4-3442 | `x^3*y+y^4*z+z^4*t+t^2` | embedded resolution | 19.9 | none |
| 36 | t3-loop2-chain2-2342 | `x^2*y+y^3*x+z^4*t+t^2` | embedded resolution | 19.8 | none |
| 37 | t3-loop2-chain2-4442 | `x^4*y+y^4*x+z^4*t+t^2` | embedded resolution | 19.8 | none |
| 38 | t3-cone-degree-5-1 | `x^5+y^5+z^5+t^5+2*x^2*y*t^2-2*x^3*z*t` | embedded resolution | 19.6 | none |
| 39 | t3-cone-degree-5-10 | `x^5+y^5+z^5+t^5-x*y*z^3+x^3*y*t` | embedded resolution | 19.9 | none |
| 40 | t3-cone-degree-5-4 | `x^5+y^5+z^5+t^5-x*y^4+3*z^3*t^2+x^3*z*t` | intrinsic resolution | 1.0 | embedded resolution 18.8 |
| 41 | t3-cone-degree-5-9 | `x^5+y^5+z^5+t^5+2*x^2*z*t^2+3*x*z^4+2*x*y^3*z` | embedded resolution | 19.9 | none |
| 42 | t3-briancon-speder-3 | `z^5+t^2*y^6*z+x*y^7+x^15` | embedded resolution | 19.9 | none |
| 43 | t3-modulus-z11-1 | `x^3*y+y^5+z^2+t*x*y^4` | intrinsic resolution | 7.5 | embedded resolution 12.4 |
| 44 | t3-modulus-z11-2 | `x^3*y+y^5+z^2+t^2*x*y^4` | intrinsic resolution | 6.0 | embedded resolution 13.8 |
| 45 | t3-arrangement-5-1 | `t*z*(y+z-t)*(y+z)*(x+y-t)` | embedded resolution | 19.8 | none |
| 46 | t3-arrangement-6-2 | `y*x*t*(y+z)*(x+y+z)*(x-y)` | embedded resolution | 19.8 | none |
| 47 | t3-arrangement-6-3 | `t*z*(y+z+t)*(x+z)*(y+z)*(y-t)` | embedded resolution | 19.8 | none |
| 48 | t3-arrangement-6-4 | `t*z*(y+z+t)*(x+2*y)*(x+y-z)*(x+y+2*z)` | embedded resolution | 19.8 | none |
| 49 | t3-arrangement-6-5 | `z*y*t*x*(x+2*y)*(x-y-z-t)` | embedded resolution | 19.9 | none |
| 50 | t3-arrangement-6-6 | `x*t*y*(y-z+t)*(x+2*t)*(z-t)` | embedded resolution | 19.8 | none |
| 51 | t3-arrangement-7-10 | `t*z*(x+y+z-t)*(x+z)*(x+y-z+t)*(y-z-t)*(y-z)` | embedded resolution | 19.7 | none |
| 52 | t3-arrangement-7-11 | `t*z*y*(x-y+z)*(x-y-z)*(y+z)*(x+y-z)` | embedded resolution | 19.8 | none |
| 53 | t3-arrangement-7-12 | `t*y*z*x*(x+y-z-t)*(x+z-t)*(x+2*t)` | embedded resolution | 19.8 | none |
| 54 | t3-arrangement-7-13 | `z*x*y*(x-z+t)*(x-y-z-t)*(x+y-z+t)*(x-y+z-t)` | embedded resolution | 19.8 | none |
| 55 | t3-arrangement-7-14 | `z*t*x*(x+y-z-t)*(y+z+2*t)*(x+y+t)*(x+y-z+t)` | embedded resolution | 19.9 | none |
| 56 | t3-arrangement-7-15 | `z*y*x*(z+t)*(x-t)*(x+2*y)*(x+y-z+t)` | embedded resolution | 19.8 | none |
| 57 | t3-arrangement-7-16 | `y*x*z*(x+2*y)*(y-z-t)*(y-z+t)*(y+z)` | embedded resolution | 19.9 | none |
| 58 | t3-arrangement-7-17 | `y*x*z*t*(x-y-z-t)*(y-t)*(x+z-t)` | embedded resolution | 19.8 | none |
| 59 | t3-arrangement-7-18 | `z*t*(y+z-t)*(x-y-z+t)*(y+z+2*t)*(x+y+z)*(x+2*y+3*z)` | embedded resolution | 19.8 | none |
| 60 | t3-arrangement-7-19 | `y*z*x*t*(x-z+t)*(y-z)*(x-z-t)` | embedded resolution | 19.8 | none |
| 61 | t3-arrangement-7-20 | `z*t*(x+y+2*z)*(y-z+t)*(x+t)*(x+2*y)*(y+z+t)` | embedded resolution | 19.5 | none |
| 62 | t3-arrangement-7-21 | `t*y*x*z*(x-y+t)*(z+t)*(x-y-z)` | embedded resolution | 19.9 | none |
| 63 | t3-arrangement-7-22 | `z*t*(y+z+t)*(x-y+z+t)*(y+t)*(x-y+z)*(x-z-t)` | embedded resolution | 19.8 | none |
| 64 | t3-arrangement-7-23 | `t*z*y*x*(x+z+t)*(x+t)*(x+y+t)` | embedded resolution | 19.9 | none |
| 65 | t3-arrangement-7-24 | `y*z*t*x*(y-z)*(x+y+2*z)*(y+z-t)` | embedded resolution | 19.8 | none |
| 66 | t3-arrangement-7-25 | `z*x*y*t*(x-z-t)*(z+t)*(x-t)` | embedded resolution | 19.8 | none |
| 67 | t3-arrangement-7-7 | `x*y*z*(x-y)*(x+y+2*z)*(y+z+t)*(x-y-t)` | embedded resolution | 19.8 | none |
| 68 | t3-arrangement-7-8 | `y*z*(x+y+z+t)*(x+y-z-t)*(x+2*y)*(x+y)*(x-y+t)` | embedded resolution | 19.8 | none |
| 69 | t3-arrangement-7-9 | `z*y*x*(x+z-t)*(y+z-t)*(x+y-t)*(x-y-z+t)` | embedded resolution | 19.8 | none |
| 70 | t3-arrangement-8-26 | `y*t*z*x*(x+2*y)*(x+y-t)*(x+2*y+3*z)*(y-z-t)` | embedded resolution | 19.8 | none |
| 71 | t3-arrangement-8-27 | `z*t*x*y*(x+y-z)*(y-z)*(y+t)*(x+z-t)` | embedded resolution | 19.8 | none |
| 72 | t3-arrangement-8-28 | `y*x*t*(x-y-z)*(y-z)*(x+y-z-t)*(x-y+z+t)*(x-y-z+t)` | embedded resolution | 19.7 | none |
| 73 | t3-arrangement-8-29 | `z*x*y*(x-t)*(x+t)*(x+y-z+t)*(x-y+z)*(y-z)` | embedded resolution | 19.8 | none |
| 74 | t3-arrangement-8-30 | `y*z*(x-z+t)*(z+t)*(y-z-t)*(y+z)*x*(y-z)` | embedded resolution | 19.5 | none |
| 75 | t3-arrangement-8-31 | `t*y*(x+2*y+3*z)*(z+t)*(x+2*y)*(y+z-t)*(x+y+z-t)*(y+t)` | embedded resolution | 19.8 | none |
| 76 | t3-arrangement-8-32 | `t*y*z*x*(x+2*t)*(y+t)*(x-z+t)*(x+z+t)` | embedded resolution | 19.9 | none |
| 77 | t3-arrangement-8-33 | `x*t*(x+2*y+3*z)*(x+2*y)*(y-t)*(x+y+t)*(y+z+2*t)*(x+t)` | embedded resolution | 19.9 | none |
| 78 | t3-arrangement-8-34 | `y*x*(x+y)*(x-y-z-t)*(x+y+2*z)*(x+2*y+3*z)*(y+t)*(x-y+z)` | embedded resolution | 19.8 | none |
| 79 | t3-arrangement-8-35 | `z*x*(x+z+t)*(y-z)*(y-z-t)*(y-z+t)*(x+y+z)*(x-y-z-t)` | embedded resolution | 19.9 | none |
| 80 | t3-arrangement-8-36 | `t*x*z*(x-z)*(x-y-z)*(x-y-z-t)*(x+z+t)*(z+t)` | embedded resolution | 19.6 | none |
| 81 | t3-arrangement-8-37 | `y*x*(x+2*y+3*z)*(z+t)*(x-y-z-t)*(x-y+z)*(x-y-z+t)*(x+y-z+t)` | embedded resolution | 19.8 | none |
| 82 | t3-arrangement-8-38 | `t*z*(x+y-z-t)*(x-t)*(x+z-t)*(y-z)*(x+z)*(x-y+z+t)` | embedded resolution | 19.9 | none |
| 83 | t3-arrangement-8-39 | `t*y*x*z*(x+z)*(x+y-z+t)*(x-z-t)*(x+t)` | embedded resolution | 19.8 | none |
| 84 | t3-arrangement-8-40 | `y*t*x*(x+y+z-t)*(y+2*z)*(x+y+z)*(x+y-z)*(x+y-t)` | embedded resolution | 19.9 | none |
| 85 | t3-arrangement-8-41 | `z*t*y*(x+y-z)*(x+y+2*z)*(y+z-t)*(x-y+z)*(x-y-z)` | embedded resolution | 19.8 | none |
| 86 | t3-arrangement-8-42 | `z*t*y*(x-z+t)*(x+y+t)*(x+y+2*z)*(x-z-t)*(z+t)` | embedded resolution | 19.9 | none |
| 87 | t3-arrangement-8-43 | `y*x*z*(x-y+z-t)*(x+y-z)*(x-y-z+t)*(y+z+2*t)*(y-z+t)` | embedded resolution | 19.8 | none |
| 88 | t3-arrangement-8-44 | `x*z*y*t*(y-t)*(y+t)*(y+z+t)*(x-y-z+t)` | embedded resolution | 19.5 | none |
| 89 | t3-arrangement-8-45 | `y*z*t*(x+2*y)*(x-t)*(x+y-z-t)*(x+y+z+t)*(x-y-t)` | embedded resolution | 19.8 | none |
| 90 | t3-arrangement-8-46 | `t*z*y*(x+y)*(x-y-z+t)*(x+y-t)*(y-t)*(x+y+z)` | embedded resolution | 19.8 | none |
| 91 | t3-arrangement-8-47 | `y*z*t*x*(y-t)*(x-y-z+t)*(x-y)*(x-y+z+t)` | embedded resolution | 19.8 | none |
| 92 | t3-arrangement-8-48 | `x*y*(x-z+t)*(x+y-z-t)*(x+y+2*z)*(y+z-t)*(x-y-z+t)*(x+2*t)` | embedded resolution | 19.9 | none |
| 93 | t3-arrangement-8-49 | `y*t*(x+y+z)*x*(y-t)*(y+2*z)*(x+y)*(z-t)` | embedded resolution | 19.9 | none |
| 94 | t3-arrangement-8-50 | `t*x*y*z*(x-y+z)*(x-t)*(x-y+z+t)*(x+y-z)` | embedded resolution | 19.8 | none |
| 95 | t3-arrangement-8-51 | `y*x*z*(x-y-z-t)*t*(y+z-t)*(x+z+t)*(x+y+z-t)` | embedded resolution | 19.8 | none |
| 96 | t3-arrangement-8-52 | `x*t*z*(z-t)*(y-z)*(x+2*y)*(x+y+z+t)*(x+y-t)` | embedded resolution | 19.8 | none |
| 97 | t3-arrangement-8-53 | `z*x*y*(x+y+z-t)*(y-z)*(x-t)*(x+y+2*z)*(x-y-z-t)` | embedded resolution | 19.9 | none |
| 98 | t3-arrangement-8-54 | `z*y*(y+2*z)*(x-z+t)*(y+z-t)*(x+z+t)*(x-y)*(x-y+z-t)` | embedded resolution | 19.8 | none |
| 99 | t3-arrangement-8-55 | `z*y*(y+2*z)*(x-t)*(x+y-z-t)*(y-z+t)*(x-y-t)*(x+y-t)` | embedded resolution | 19.8 | none |
| 100 | t3-arrangement-8-56 | `x*z*y*t*(x+2*y+3*z)*(x+y-z+t)*(x+z)*(x-z-t)` | embedded resolution | 19.9 | none |
| 101 | t3-arrangement-8-57 | `z*y*t*(y+t)*(x-y-z)*(x-z)*(y+z)*(x+z+t)` | embedded resolution | 19.8 | none |
| 102 | t3-arrangement-8-58 | `x*t*(x-z-t)*(y-z)*(y+z+2*t)*(x+z)*(x-y+z)*(z-t)` | embedded resolution | 19.8 | none |
| 103 | t3-arrangement-8-59 | `y*t*z*x*(x+y+t)*(x-y-z)*(x+t)*(x+y-z-t)` | embedded resolution | 19.8 | none |
| 104 | t3-arrangement-8-60 | `z*x*t*(x+2*t)*(y-z)*(x-y-z)*(y-z+t)*(x-y)` | embedded resolution | 19.9 | none |
| 105 | t3-arrangement-8-61 | `t*y*(x+2*y)*(x+y+t)*(x+y-z+t)*(x-y+t)*(z-t)*(y+z)` | embedded resolution | 19.8 | none |
| 106 | t3-arrangement-8-62 | `t*z*y*(y+z)*(x+y)*x*(y-t)*(x+2*y)` | embedded resolution | 19.8 | none |
| 107 | t3-arrangement-8-63 | `t*y*z*(x-t)*(y-z)*(x-y-z-t)*(z+t)*(z-t)` | embedded resolution | 19.9 | none |
| 108 | t3-arrangement-8-64 | `z*t*x*(x+y-z-t)*(x-y-z+t)*(x+y+z-t)*(z+t)*(x-z-t)` | embedded resolution | 19.9 | none |
| 109 | t3-arrangement-8-65 | `z*y*x*(x+2*y+3*z)*(x+y)*(y+t)*(x-t)*(x+y+2*z)` | embedded resolution | 19.9 | none |
| 110 | t3-arrangement-8-66 | `y*z*(x+2*t)*(x+2*y+3*z)*(x-y-z+t)*(y+2*z)*(y+z)*(x+y)` | embedded resolution | 19.8 | none |
| 111 | t3-arrangement-8-67 | `y*t*z*x*(x-y+z-t)*(z-t)*(x+y-t)*(y+t)` | embedded resolution | 19.9 | none |
| 112 | t3-arrangement-8-68 | `t*y*(x+2*y)*(x+y+z+t)*(x-y+z)*(x+y+z-t)*(x-t)*(y+z-t)` | embedded resolution | 19.8 | none |
| 113 | t3-arrangement-8-69 | `t*x*(x+2*t)*(x+t)*(x+y)*(x+z+t)*(y+z+2*t)*(x+z-t)` | embedded resolution | 19.5 | none |
| 114 | t3-arrangement-8-70 | `t*x*(x-y)*(x+t)*(x-y+z+t)*(x-z+t)*(x-y-z)*(x-t)` | embedded resolution | 19.9 | none |
| 115 | t3-arrangement-8-71 | `y*z*(x-y+z+t)*(x+z)*(y-t)*(x+y-z-t)*(y+z-t)*(x+z-t)` | embedded resolution | 19.9 | none |
| 116 | t3-arrangement-8-72 | `t*x*z*(y-z+t)*(x-y+t)*(y+z+t)*(y-z)*(y-t)` | embedded resolution | 19.8 | none |
| 117 | t3-arrangement-8-73 | `x*t*y*(x-t)*(x-y-z)*(x+y+z+t)*(z+t)*(x+z+t)` | embedded resolution | 19.8 | none |
| 118 | t3-arrangement-8-74 | `z*x*(x+y-z+t)*(y-z-t)*t*(x+y)*(y+z-t)*(x-y)` | embedded resolution | 19.8 | none |
| 119 | t3-arrangement-8-75 | `t*z*y*x*(y+z-t)*(y+t)*(x+y)*(x-y+z)` | embedded resolution | 19.6 | none |
| 120 | t3-arrangement-8-76 | `x*t*(y-z+t)*(y-z-t)*(x+y-t)*(y+z+2*t)*(y+z+t)*(x-y+t)` | embedded resolution | 19.8 | none |
| 121 | t3-arrangement-8-77 | `x*t*(x+2*y+3*z)*(x+y+t)*(x-y-z+t)*(z+t)*(x+z)*z` | embedded resolution | 19.7 | none |
| 122 | t3-arrangement-8-78 | `y*z*t*(x-y+t)*(x+t)*(y-z)*(x-t)*(x+z-t)` | embedded resolution | 19.9 | none |
| 123 | t3-arrangement-8-79 | `z*t*y*(z-t)*(x+y+z-t)*(x+z-t)*(x-y-z)*(z+t)` | embedded resolution | 19.9 | none |
| 124 | t3-arrangement-8-80 | `z*x*t*y*(x-y)*(y-z+t)*(x+y+z+t)*(y+z+2*t)` | embedded resolution | 19.9 | none |
| 125 | t3-arrangement-8-81 | `t*y*x*(y+t)*(x+z-t)*(x-y)*(x+t)*(y-t)` | embedded resolution | 19.4 | none |
| 126 | t3-arrangement-8-82 | `x*t*y*z*(x-y)*(x+y+2*z)*(x+y)*(y+t)` | embedded resolution | 19.7 | none |
| 127 | t3-arrangement-8-83 | `z*t*(x+t)*(y-z+t)*(x-y)*x*(x+z)*y` | embedded resolution | 19.9 | none |
| 128 | t3-arrangement-8-84 | `t*y*x*z*(x+y-t)*(x+t)*(x-z-t)*(y-t)` | embedded resolution | 19.8 | none |
| 129 | t3-arrangement-8-85 | `z*x*y*(x+y-z-t)*(x-y)*(x+y+2*z)*(x-y+t)*(x+y+z-t)` | embedded resolution | 19.3 | none |
| 130 | t3-arrangement-8-86 | `t*x*(x+y-z)*(x+y-z+t)*(x-z+t)*(z-t)*(x-t)*(y+z+t)` | embedded resolution | 19.8 | none |
| 131 | t3-arrangement-8-87 | `z*x*y*t*(x+z+t)*(x+t)*(x-y-z-t)*(x-y+z)` | embedded resolution | 19.8 | none |
| 132 | t3-arrangement-8-88 | `y*z*(x-y+z+t)*(x+y+z)*(x-y-z+t)*(x-y-z)*(x-y+z-t)*(x-y-z-t)` | embedded resolution | 19.8 | none |
| 133 | t3-arrangement-8-89 | `y*t*x*z*(y-z)*(x+2*y+3*z)*(x+z)*(y+2*z)` | embedded resolution | 19.9 | none |
| 134 | t3-arrangement-8-90 | `x*t*z*y*(x+z)*(x+2*y)*(x+y+z+t)*(x-y-z-t)` | embedded resolution | 19.8 | none |
| 135 | t3-arrangement-d4 | `(x+y)*(x-y)*(x+z)*(x-z)*(x+t)*(x-t)*(y+z)*(y-z)*(y+t)*(y-t)*(z+t)*(z-t)` | embedded resolution | 19.8 | none |
| 136 | t3-a4-discriminant | `-108*x^5*t^2+72*x^4*y*z*t-16*x^4*z^3-16*x^3*y^3*t+4*x^3*y^2*z^2+900*x^3*z*t^2-825*x^2*y^2*t^2-560*x^2*y*z^2*t+…` | embedded resolution | 19.8 | none |
| 137 | t3-a5-section-a | `-729*x^6*t^2+486*x^5*y*z*t-108*x^5*z^3-108*x^4*y^3*t+27*x^4*y^2*z^2+8748*x^4*t^3-21384*x^3*y*z*t^2+1350*x^3*z^…` | embedded resolution | 19.8 | none |
| 138 | t3-a5-section-b | `-1024*x^6*t^3+512*x^5*y^2*t^2-576*x^5*y*z^2*t+108*x^5*z^4-64*x^4*y^4*t+16*x^4*y^3*z^2+9216*x^4*y*t^3-192*x^4*z…` | embedded resolution | 19.9 | none |
| 139 | t3-a5-section-c | `-1024*x^6*t^3+768*x^5*y*z*t^2+108*x^5*z^4+24*x^4*y^2*z^2*t+108*x^3*y^4*t^2+16*x^3*y^3*z^3-192*x^4*z^2*t^2-8640…` | embedded resolution | 19.8 | none |
| 140 | t3-a5-section-d | `-1024*x^6*t^3+512*x^5*z^2*t^2-576*x^4*y^2*z*t^2-64*x^4*z^4*t+108*x^3*y^4*t^2+16*x^3*y^2*z^3*t+9216*x^4*z*t^3-8…` | embedded resolution | 19.8 | none |
| 141 | t3-a5-section-e | `(-108*x^5*t^2+72*x^4*y*z*t-16*x^4*z^3-16*x^3*y^3*t+4*x^3*y^2*z^2+900*x^3*z*t^2-825*x^2*y^2*t^2-560*x^2*y*z^2*t…` | embedded resolution | 19.8 | none |
| 142 | t3-b4-discriminant | `-27*x^4*t^3+18*x^3*y*z*t^2-4*x^3*z^3*t-4*x^2*y^3*t^2+x^2*y^2*z^2*t+144*x^2*y*t^3-6*x^2*z^2*t^2-80*x*y^2*z*t^2+…` | embedded resolution | 19.8 | none |
| 143 | t3-caustic-d4-plus | `4*x^2*t^6+3*t^8-48*x^2*z*t^4-48*z*t^6-1728*x^4*y^2-1728*x^2*y^2*t^2+192*x^2*z^2*t^2-288*y^2*t^4+288*z^2*t^4+69…` | embedded resolution | 19.8 | none |
| 144 | t3-caustic-d5 | `972*x^5*t^4-648*x^4*z^2*t^2+972*x^3*y^2*z*t^2-5400*x^3*y*t^4-243*x^2*y^4*t^2+108*x^3*z^4-36*x^2*y^2*z^3+2520*x…` | embedded resolution | 19.8 | none |
| 145 | t3-d4-discriminant | `27*x^4*y^4+72*x^3*y^2*z*t+144*x^2*y^4*z-16*x^2*y^2*z^3+64*x^3*t^3+24*x^2*y^2*t^2-16*x^2*z^2*t^2+192*x*y^4*t+32…` | embedded resolution | 19.8 | none |
| 146 | t3-d5-discriminant-slice | `1728*x^5*z^4+4608*x^4*y*z^2*t-1024*x^3*y^3*z^2-14400*x^3*z^4*t+13200*x^2*y^2*z^4+15000*x*y*z^6+3125*z^8+4096*x…` | embedded resolution | 19.8 | none |
| 147 | t3-image-corank2-1 | `x^4*y^2-2*x^4*y*z+x^4*z^2-2*x^2*y^2*z-2*x^2*y*z^2-8*x^2*y*z*t-2*x^2*y*t^2-2*x^2*z*t^2+y^2*z^2-2*y*z*t^2+t^4` | embedded resolution | 19.5 | none |
| 148 | t3-image-corank2-2 | `x^8*y^2-2*x^4*y*z^3-2*x^4*y^2*z-2*x^4*y*t^2-8*x^2*y*z^2*t+z^6-2*y*z^4-2*z^3*t^2+y^2*z^2-2*y*z*t^2+t^4` | embedded resolution | 19.8 | none |
| 149 | t3-image-corank2-4 | `x^6*y^3-4*x^5*y^3-3*x^4*y^2*z^2+6*x^4*y^3+8*x^3*y^2*z^2+3*x^2*y*z^4-4*x^3*y^3-8*x^2*y^2*z^2+6*x^2*y*z*t^2-4*x*…` | embedded resolution | 19.8 | none |
| 150 | t3-image-double-1 | `t^2-z*(z+x^2+y^2)^2` | embedded resolution | 19.9 | none |
| 151 | t3-image-double-2 | `t^2-z*(z+x*y)^2` | embedded resolution | 19.8 | none |
| 152 | t3-image-double-3 | `t^2-z*(z+x^2+y^3)^2` | embedded resolution | 19.8 | none |
| 153 | t3-image-double-6 | `t^2-z*(z+x^2+y^4)^2` | embedded resolution | 19.8 | none |
| 154 | t3-image-double-7 | `t^2-z*(z+x*y+x^3)^2` | embedded resolution | 19.8 | none |
| 155 | t3-image-double-8 | `t^2-z*(z+x^2*y+y^3)^2` | embedded resolution | 19.6 | none |
| 156 | t3-image-double-9 | `t^2-z*(z+x^2+y^5)^2` | embedded resolution | 19.8 | none |
| 157 | t3-image-double5-3 | `t^2-z*(z^2+x^2+y^3)^2` | embedded resolution | 19.9 | none |
| 158 | t3-image-double5-6 | `t^2-z*(z^2+x^2+y^4)^2` | embedded resolution | 19.6 | none |
| 159 | t3-image-double5-7 | `t^2-z*(z^2+x*y+x^3)^2` | embedded resolution | 19.8 | none |
| 160 | t3-image-double5-9 | `t^2-z*(z^2+x^2+y^5)^2` | embedded resolution | 19.8 | none |
| 161 | t3-image-multiple-1 | `y^3*z^2+x^3*z+3*x*y*z*t-t^3` | embedded resolution | 19.8 | none |
| 162 | t3-image-multiple-10 | `y^4*z^2-x^4*z-4*x^2*y*z*t-2*y^2*z*t^2+t^4` | embedded resolution | 19.8 | none |
| 163 | t3-image-multiple-11 | `y^4*z^3-2*x^2*y^2*z^2+x^4*z+4*x*y*z*t^2-t^4` | embedded resolution | 19.9 | none |
| 164 | t3-image-multiple-12 | `y^4*z^2-x^4*z-4*x^2*y*z*t-4*x*y^2*z^2-2*y^2*z*t^2+2*x^2*z^2-4*x*z*t^2-4*y*z^2*t+t^4-z^3` | embedded resolution | 19.8 | none |
| 165 | t3-image-multiple-14 | `z^7+3*x*z^5+3*x^2*z^3+y^3*z^2+3*y*z^3*t+x^3*z+3*x*y*z*t-t^3` | embedded resolution | 19.9 | none |
| 166 | t3-image-multiple-2 | `y^6*z^2+3*x*y^2*z*t+x^3*z-t^3` | embedded resolution | 19.9 | none |
| 167 | t3-image-multiple-4 | `y^3*z^2+x^3*z+3*x^2*z^2+3*x*y*z*t+3*x*z^3+3*y*z^2*t+z^4-t^3` | embedded resolution | 19.9 | none |
| 168 | t3-image-multiple-6 | `x^6*z+3*x^2*y*z*t+y^3*z^2-t^3` | embedded resolution | 19.8 | none |
| 169 | t3-image-multiple-7 | `y^3*z^2+3*y^2*z^3+3*y*z^4+z^5+x^3*z+3*x*y*z*t+3*x*z^2*t-t^3` | embedded resolution | 19.7 | none |
| 170 | t3-image-multiple-9 | `x^3*y^3*z+3*x^2*y^2*z^2+x^3*z^2+3*x^2*y*z*t+3*x*y*z^3+3*x*z^2*t+z^4-t^3` | embedded resolution | 19.8 | none |
| 171 | t3-cone-d4-a-rank1-1 | `t^2*(x^2)+z^4+x*y^3` | embedded resolution | 19.8 | none |
| 172 | t3-cone-d4-a-rank2-1 | `t^2*(x^2+y^2)+z^4+x*y^3` | embedded resolution | 19.8 | none |
| 173 | t3-cone-d4-a-rank2-3 | `t^2*(x^2+y^2)+z^4+x^3*z` | embedded resolution | 19.8 | none |
| 174 | t3-cone-d4-a-rank2-4 | `t^2*(x^2+y^2)+y^4+z^4+x^2*z^2` | intrinsic resolution | 19.3 | embedded resolution 0.5 |
| 175 | t3-cone-d4-d4-1 | `t*(x*y*z)+z^4+x*y^3` | embedded resolution | 19.7 | none |
| 176 | t3-cone-d4-x2y-1 | `t*(x^2*y)+z^4+x*y^3` | embedded resolution | 19.8 | none |
| 177 | t3-cone-d4-x2y-4 | `t*(x^2*y)+y^4+z^4+x^2*z^2` | embedded resolution | 19.8 | none |
| 178 | t3-cone-d4-x3-1 | `t*(x^3+y^3)+z^4+x*y^3` | embedded resolution | 19.8 | none |
| 179 | t3-cone-d4-x3-2 | `t*(x^3+y^3)+z^4+y^4` | embedded resolution | 19.9 | none |
| 180 | t3-cone-d4-x3-3 | `t*(x^3+y^3)+z^4+x^3*z` | embedded resolution | 19.8 | none |
| 181 | t3-cone-d4-x3-4 | `t*(x^3+y^3)+y^4+z^4+x^2*z^2` | embedded resolution | 19.8 | none |
| 182 | t3-cone-d4-xy-1 | `t^2*(x*y)+z^4+x*y^3` | embedded resolution | 19.9 | none |
| 183 | t3-cone-d4-xy-2 | `t^2*(x*y)+z^4+y^4` | embedded resolution | 19.8 | none |
| 184 | t3-cone-d4-xy-3 | `t^2*(x*y)+z^4+x^3*z` | embedded resolution | 19.9 | none |
| 185 | t3-cone-d4-xy-4 | `t^2*(x*y)+y^4+z^4+x^2*z^2` | embedded resolution | 19.8 | none |
| 186 | t3-cone-d5-a-rank1-1 | `t^3*(x^2)+z^5+x*y^4` | embedded resolution | 19.8 | none |
| 187 | t3-cone-d5-a-rank2-1 | `t^3*(x^2+y^2)+z^5+x*y^4` | embedded resolution | 19.8 | none |
| 188 | t3-cone-d5-a-rank2-3 | `t^3*(x^2+y^2)+y^5+z^5+x*y^2*z^2` | pole-check replay | 17.3 | embedded resolution 0.6, intrinsic resolution 1.9 |
| 189 | t3-cone-d5-d4-1 | `t^2*(x*y*z)+z^5+x*y^4` | embedded resolution | 19.9 | none |
| 190 | t3-cone-d5-x2y-1 | `t^2*(x^2*y)+z^5+x*y^4` | embedded resolution | 19.7 | none |
| 191 | t3-cone-d5-x2y-3 | `t^2*(x^2*y)+y^5+z^5+x*y^2*z^2` | embedded resolution | 19.8 | none |
| 192 | t3-cone-d5-x3-1 | `t^2*(x^3+y^3)+z^5+x*y^4` | embedded resolution | 19.8 | none |
| 193 | t3-cone-d5-x3-2 | `t^2*(x^3+y^3)+z^5+y^5+x^5` | embedded resolution | 19.8 | none |
| 194 | t3-cone-d5-x3-3 | `t^2*(x^3+y^3)+y^5+z^5+x*y^2*z^2` | pole-check replay | 18.7 | embedded resolution 0.3, intrinsic resolution 0.8 |
| 195 | t3-cone-d5-xy-1 | `t^3*(x*y)+z^5+x*y^4` | embedded resolution | 19.8 | none |
| 196 | t3-cone-d5-xy-3 | `t^3*(x*y)+y^5+z^5+x*y^2*z^2` | embedded resolution | 19.6 | none |
| 197 | t3-sheets-1 | `t*(t-(x))*(t-(x^2+y^2+z^2))` | embedded resolution | 19.8 | none |
| 198 | t3-sheets-10 | `(t-(x))*(t-(x^2+y^2))*(t-(x^2-y*z))` | embedded resolution | 19.6 | none |
| 199 | t3-sheets-11 | `(t-(x))*(t-(y^2))*(t-(x*y*z))` | pole-check replay | 13.1 | embedded resolution 2.0, intrinsic resolution 4.8 |
| 200 | t3-sheets-12 | `(t-(x))*(t-(z^2))*(t-(x^2+y^2+z^2))` | embedded resolution | 19.7 | none |
| 201 | t3-sheets-13 | `(t-(x*y))*(t-(x^2-y*z))*(t-(y*z+x^3))` | embedded resolution | 19.7 | none |
| 202 | t3-sheets-14 | `(t-(x*y))*(t-(y*z+x^3))*(t-(x^2+z^3))` | embedded resolution | 19.9 | none |
| 203 | t3-sheets-15 | `(t-(x*y))*(t-(z^2))*(t-(x*y*z))` | embedded resolution | 19.8 | none |
| 204 | t3-sheets-16 | `(t-(x*y))*(t-(z^2))*(t-(x^2-y*z))` | embedded resolution | 19.9 | none |
| 205 | t3-sheets-17 | `(t-(x*y*z))*(t-(x^2-y*z))*(t-(x^2+z^3))` | embedded resolution | 19.9 | none |
| 206 | t3-sheets-19 | `(t-(x^2))*(t-(x*y*z))*(t-(x^2-y*z))` | embedded resolution | 19.7 | none |
| 207 | t3-sheets-2 | `t*(t-(x))*(t-(x^2-y*z))` | intrinsic resolution | 6.9 | embedded resolution 12.8 |
| 208 | t3-sheets-21 | `(t-(x^2))*(t-(x^2+y^2+z^2))*(t-(x*y*z))` | embedded resolution | 19.8 | none |
| 209 | t3-sheets-23 | `(t-(x^2))*(t-(x^2-y*z))*(t-(y*z+x^3))` | embedded resolution | 19.8 | none |
| 210 | t3-sheets-24 | `(t-(x^2))*(t-(y^2))*(t-(x^2+z^3))` | embedded resolution | 19.8 | none |
| 211 | t3-sheets-25 | `(t-(x^2))*(t-(z^2))*(t-(x^2+y^2+z^2))` | embedded resolution | 19.8 | none |
| 212 | t3-sheets-26 | `(t-(x^2))*(t-(z^2))*(t-(y*z+x^3))` | embedded resolution | 19.9 | none |
| 213 | t3-sheets-27 | `(t-(x^2+y^2))*(t-(x*y*z))*(t-(x^2-y*z))` | embedded resolution | 19.8 | none |
| 214 | t3-sheets-28 | `(t-(x^2+y^2))*(t-(x^2+y^2+z^2))*(t-(x^2-y*z))` | pole-check replay | 7.5 | embedded resolution 6.5, intrinsic resolution 5.9 |
| 215 | t3-sheets-29 | `(t-(x^2+y^2))*(t-(y*z+x^3))*(t-(x^2+z^3))` | embedded resolution | 19.8 | none |
| 216 | t3-sheets-30 | `(t-(x^2+y^2+z^2))*(t-(x*y*z))*(t-(x^2+z^3))` | embedded resolution | 19.8 | none |
| 217 | t3-sheets-31 | `(t-(x^2+y^2+z^2))*(t-(x*y*z))*(t-(x^2-y*z))` | embedded resolution | 19.8 | none |
| 218 | t3-sheets-32 | `(t-(y^2))*(t-(x*y))*(t-(x^2+y^2+z^2))` | embedded resolution | 19.8 | none |
| 219 | t3-sheets-33 | `(t-(y^2))*(t-(x*y))*(t-(y*z+x^3))` | embedded resolution | 19.8 | none |
| 220 | t3-sheets-34 | `(t-(y^2))*(t-(x^2+y^2))*(t-(x^2+z^3))` | embedded resolution | 19.8 | none |
| 221 | t3-sheets-35 | `(t-(y^2))*(t-(x^2+y^2))*(t-(x^2-y*z))` | embedded resolution | 19.8 | none |
| 222 | t3-sheets-36 | `(t-(y^2))*(t-(x^2+y^2))*(t-(y*z+x^3))` | embedded resolution | 19.8 | none |
| 223 | t3-sheets-37 | `(t-(y^2))*(t-(x^2+y^2+z^2))*(t-(x^2+z^3))` | embedded resolution | 19.7 | none |
| 224 | t3-sheets-38 | `(t-(y^2))*(t-(x^2-y*z))*(t-(x^2+z^3))` | embedded resolution | 19.7 | none |
| 225 | t3-sheets-39 | `(t-(z^2))*(t-(x*y*z))*(t-(x^2+z^3))` | embedded resolution | 19.6 | none |
| 226 | t3-sheets-4 | `t*(t-(x^2+y^2+z^2))*(t-(x^2+z^3))` | embedded resolution | 19.7 | none |
| 227 | t3-sheets-6 | `t*(t-(z^2))*(t-(x^2+y^2+z^2))` | embedded resolution | 19.6 | none |
| 228 | t3-sheets-7 | `(t-(x))*(t-(x*y))*(t-(x^2+y^2+z^2))` | embedded resolution | 19.8 | none |
| 229 | t3-sheets-8 | `(t-(x))*(t-(x*y))*(t-(x^2-y*z))` | embedded resolution | 19.8 | none |
| 230 | t3-sheets-9 | `(t-(x))*(t-(x^2))*(t-(x*y*z))` | embedded resolution | 19.8 | none |
| 231 | t3-union-10 | `(x^2+y^3+z^3+t^4)*(t-z^2)` | embedded resolution | 19.9 | none |
| 232 | t3-union-12 | `(x^2+y^2+z^2+t^3)*(x^2-y^2+z^3+t^2)` | embedded resolution | 19.8 | none |
| 233 | t3-union-2 | `(x^2+y^2+z^2+t^3)*(t-y^2)` | intrinsic resolution | 18.9 | embedded resolution 1.0 |
| 234 | t3-union-3 | `(x*y+z^3+t^3)*(z-x^2-y^2)` | intrinsic resolution | 18.4 | embedded resolution 1.4 |
| 235 | t3-union-4 | `(x^2+y^3+z^3+t^3)*(t-x*y)` | embedded resolution | 19.9 | none |
| 236 | t3-union-5 | `(x^2+y^2+z^3+t^3)*(x-z^2)` | intrinsic resolution | 19.5 | embedded resolution 0.3 |
| 237 | t3-union-6 | `(x*y-z*t)*(t-x^2-y^2)` | embedded resolution | 19.9 | none |
| 238 | t3-union-8 | `(x^2+y^2+z^2+t^2)*(x^2+2*y^2+3*z^2+4*t^2)` | intrinsic resolution | 8.5 | embedded resolution 11.4 |
| 239 | t3-union-9 | `(x*y-z^2-t^3)*(x*y-z^3-t^2)` | embedded resolution | 19.8 | none |
| 240 | t3-chain-1112325 | `x*y+y*z^2+z^3*t^2+t^5` | embedded resolution | 19.9 | none |
| 241 | t3-chain-1121324 | `x*y+y^2*z+z^3*t^2+t^4` | embedded resolution | 19.8 | none |
| 242 | t3-chain-1132225 | `x*y+y^3*z^2+z^2*t^2+t^5` | embedded resolution | 19.8 | none |
| 243 | t3-chain-1132323 | `x*y+y^3*z^2+z^3*t^2+t^3` | embedded resolution | 19.9 | none |
| 244 | t3-chain-1212123 | `x*y^2+y*z^2+z*t^2+t^3` | embedded resolution | 19.8 | none |
| 245 | t3-chain-1212214 | `x*y^2+y*z^2+z^2*t+t^4` | embedded resolution | 19.8 | none |
| 246 | t3-chain-1221324 | `x*y^2+y^2*z+z^3*t^2+t^4` | embedded resolution | 19.8 | none |
| 247 | t3-chain-1222224 | `x*y^2+y^2*z^2+z^2*t^2+t^4` | embedded resolution | 19.8 | none |
| 248 | t3-chain-1231223 | `x*y^2+y^3*z+z^2*t^2+t^3` | embedded resolution | 19.9 | none |
| 249 | t3-chain-1231315 | `x*y^2+y^3*z+z^3*t+t^5` | embedded resolution | 19.8 | none |
| 250 | t3-chain-1232314 | `x*y^2+y^3*z^2+z^3*t+t^4` | embedded resolution | 19.9 | none |
| 251 | t3-chain-2111223 | `x^2*y+y*z+z^2*t^2+t^3` | embedded resolution | 19.8 | none |
| 252 | t3-chain-2122125 | `x^2*y+y^2*z^2+z*t^2+t^5` | embedded resolution | 19.8 | none |
| 253 | t3-chain-2122222 | `x^2*y+y^2*z^2+z^2*t^2+t^2` | embedded resolution | 19.8 | none |
| 254 | t3-chain-2122225 | `x^2*y+y^2*z^2+z^2*t^2+t^5` | embedded resolution | 19.8 | none |
| 255 | t3-chain-2122314 | `x^2*y+y^2*z^2+z^3*t+t^4` | embedded resolution | 19.9 | none |
| 256 | t3-chain-2132312 | `x^2*y+y^3*z^2+z^3*t+t^2` | embedded resolution | 19.8 | none |
| 257 | t3-chain-2132325 | `x^2*y+y^3*z^2+z^3*t^2+t^5` | embedded resolution | 19.9 | none |
| 258 | t3-chain-2211114 | `x^2*y^2+y*z+z*t+t^4` | embedded resolution | 19.2 | none |
| 259 | t3-chain-2212114 | `x^2*y^2+y*z^2+z*t+t^4` | embedded resolution | 19.8 | none |
| 260 | t3-chain-2222214 | `x^2*y^2+y^2*z^2+z^2*t+t^4` | embedded resolution | 19.8 | none |
| 261 | t3-chain-2231115 | `x^2*y^2+y^3*z+z*t+t^5` | embedded resolution | 19.8 | none |
| 262 | t3-chain-2231312 | `x^2*y^2+y^3*z+z^3*t+t^2` | embedded resolution | 19.8 | none |
| 263 | t3-chain-2232314 | `x^2*y^2+y^3*z^2+z^3*t+t^4` | embedded resolution | 19.8 | none |
| 264 | t3-chain-3132115 | `x^3*y+y^3*z^2+z*t+t^5` | embedded resolution | 19.8 | none |
| 265 | t3-chain-3211115 | `x^3*y^2+y*z+z*t+t^5` | embedded resolution | 19.9 | none |
| 266 | t3-chain-3211125 | `x^3*y^2+y*z+z*t^2+t^5` | embedded resolution | 19.6 | none |
| 267 | t3-chain-3211214 | `x^3*y^2+y*z+z^2*t+t^4` | embedded resolution | 19.9 | none |
| 268 | t3-chain-3211215 | `x^3*y^2+y*z+z^2*t+t^5` | embedded resolution | 19.6 | none |
| 269 | t3-chain-3211224 | `x^3*y^2+y*z+z^2*t^2+t^4` | embedded resolution | 19.9 | none |
| 270 | t3-chain-3211323 | `x^3*y^2+y*z+z^3*t^2+t^3` | embedded resolution | 19.8 | none |
| 271 | t3-chain-3211325 | `x^3*y^2+y*z+z^3*t^2+t^5` | embedded resolution | 19.8 | none |
| 272 | t3-chain-3212125 | `x^3*y^2+y*z^2+z*t^2+t^5` | embedded resolution | 19.9 | none |
| 273 | t3-chain-3212323 | `x^3*y^2+y*z^2+z^3*t^2+t^3` | embedded resolution | 19.7 | none |
| 274 | t3-chain-3221322 | `x^3*y^2+y^2*z+z^3*t^2+t^2` | embedded resolution | 19.8 | none |
| 275 | t3-chain-3231125 | `x^3*y^2+y^3*z+z*t^2+t^5` | embedded resolution | 19.8 | none |
| 276 | t3-chain-3232212 | `x^3*y^2+y^3*z^2+z^2*t+t^2` | embedded resolution | 19.8 | none |
| 277 | t3-newton-1 | `-2*y*z^2*t^3-y*z^3*t^3+3*x*y*z^3*t-x^3*y^3*t` | embedded resolution | 19.9 | none |
| 278 | t3-newton-100 | `3*z^2*t^2+3*y^2*z*t-x^3*y^2*z*t-2*x^3*y^2*z^3-x^4*z^2` | embedded resolution | 19.9 | none |
| 279 | t3-newton-105 | `z^4*t^2+2*y*z^3*t-2*x^2*y*z*t+2*x^2*y^2*t^3-2*x^2*y^2*z*t^2+3*x^2*y^2*z^3` | embedded resolution | 19.8 | none |
| 280 | t3-newton-110 | `3*y^2*z^3*t^2-2*y^3*z*t+2*x*z^3*t^4+x^2*y*z*t+3*x^3*y*z^3+3*x^3*y^3*t^2` | embedded resolution | 19.8 | none |
| 281 | t3-newton-115 | `3*y*z^3*t^2+3*x*y*t^2-2*x^2*t^4+x^2*y*z*t^3-x^2*y*z^4-2*x^4*t^3` | embedded resolution | 19.8 | none |
| 282 | t3-newton-122 | `-2*y*z^4*t^2-2*x^2*z^2+3*x^3*t^2+3*x^3*z*t+x^3*y*t^4+x^3*y*z^3` | embedded resolution | 19.9 | none |
| 283 | t3-newton-126 | `3*y*z^4*t^2-x*y^3*z^2*t^2+3*x^2*y^2*z^2*t-2*x^3*y*t^4` | intrinsic resolution | 19.5 | embedded resolution 0.3 |
| 284 | t3-newton-133 | `-2*y*z*t^4+3*y^4*z^2*t^2+3*x^2*z^3+3*x^4*y*t^2` | embedded resolution | 19.9 | none |
| 285 | t3-newton-137 | `-y^4*t^2+x*y*z^3*t^2-x*y^2*z^3+3*x^2*t^2-x^4*z^2` | embedded resolution | 19.8 | none |
| 286 | t3-newton-14 | `-y^3*z^2*t^2+3*x*z^4+x*y^2*z*t^3+3*x^2*y*t^2+3*x^3*y^3*z^2` | embedded resolution | 19.8 | none |
| 287 | t3-newton-146 | `x*y^3*t^3-x*y^3*t^4+x^3*z*t^2+3*x^4*y*z+3*x^4*y*z*t^2` | embedded resolution | 19.8 | none |
| 288 | t3-newton-150 | `-y^2*z^2-2*x*z^3*t^4-2*x^2*z*t^2+x^2*y^3*z^2` | embedded resolution | 19.7 | none |
| 289 | t3-newton-156 | `2*y^2*z*t+2*x*y*z*t^2+2*x^2*z*t+2*x^2*z^3-2*x^2*y^2*z^2*t^2+x^2*y^2*z^4` | embedded resolution | 19.8 | none |
| 290 | t3-newton-162 | `-2*x*y^2*t^4+x*y^2*z^4*t-2*x^2*y*t-x^2*y*z^4+x^2*y^3*z*t^2+x^3*y^2` | embedded resolution | 19.7 | none |
| 291 | t3-newton-170 | `-2*y^2*z^2+2*x*z^2*t^2-x*y^2*t^3+2*x*y^3*z*t^2+x^3*y^2*t^3-x^4*z^3` | embedded resolution | 19.5 | none |
| 292 | t3-newton-175 | `-y^3*t^2-x*z^2*t+3*x*y^2*z*t^2-x^2*y*z^4*t` | embedded resolution | 19.8 | none |
| 293 | t3-newton-179 | `y*z^3*t^2-y^2*z*t^3-y^3*z*t-2*x*y^2*z*t+3*x^3*z^2` | embedded resolution | 19.4 | none |
| 294 | t3-newton-184 | `3*y^2*t^2-y^2*z^3*t^2-y^3*z*t^3-x*y*t^3-2*x*y^3*z*t^3+x^2*y*z` | embedded resolution | 19.9 | none |
| 295 | t3-newton-190 | `y*z^3*t^2-y^2*z^2-y^2*z^4*t^2+2*x*y^2*z^2*t+3*x^3*y*z*t^2-2*x^4*y*z*t` | intrinsic resolution | 18.1 | embedded resolution 1.6 |
| 296 | t3-newton-196 | `-x*t^2+3*x*z*t^4-x*z^3+2*x*y^2*z^2*t^3+3*x^2*y^2*z*t^2+3*x^2*y^3*z*t` | intrinsic resolution | 19.6 | embedded resolution 0.3 |
| 297 | t3-newton-202 | `z^3*t-2*x*z^2*t^4+3*x*y*z*t^4+3*x^2*y^2*z^2*t^2` | pole-check replay | 18.6 | embedded resolution 0.4, intrinsic resolution 0.8 |
| 298 | t3-newton-207 | `t^4-x*y^3*z^3-x^2*t^3-x^2*y*z^3` | embedded resolution | 19.9 | none |
| 299 | t3-newton-212 | `2*z*t^2-2*y^2*z^3-2*y^2*z^4+3*x*y*t-2*x*y^4*t-2*x^2*y^3*t` | embedded resolution | 19.7 | none |
| 300 | t3-newton-217 | `-y*z^2*t+y^2*t+2*x^2*t^2+x^4*z^3-x^4*y*t-x^4*y^2` | embedded resolution | 19.8 | none |
| 301 | t3-newton-226 | `-z^3*t^4-2*x*y^3*z^3+2*x^2*t^3-2*x^4*y*z^2*t` | embedded resolution | 19.7 | none |
| 302 | t3-newton-23 | `3*z^4*t^2+2*y^3*z^2*t^3+3*y^3*z^3+3*x^2*y^3*t^2-x^3*y^2*z*t-x^4*y^2*z` | embedded resolution | 19.3 | none |
| 303 | t3-newton-230 | `-z^4*t^3+3*y^3*t^3-2*x*z^3*t^2-x*y^3*z^3*t-2*x^2*y*z*t^2-2*x^3*z^3*t^2` | embedded resolution | 19.9 | none |
| 304 | t3-newton-235 | `-2*y*z^2*t^3+x*y^2*z^4+x^2*y*t^3+3*x^2*y^4+x^3*y*t` | embedded resolution | 19.8 | none |
| 305 | t3-newton-239 | `2*z*t-2*y^3*t^4-2*x^2*z^2*t^3+3*x^2*z^3+3*x^2*y^2*t+x^4*y*z*t` | pole-check replay | 12.9 | embedded resolution 3.0, intrinsic resolution 3.8 |
| 306 | t3-newton-244 | `-2*z^2*t-2*z^2*t^2+x*y^2+2*x*y^4*z*t^2-x^2*z*t^3+3*x^3*y*t^4` | embedded resolution | 19.9 | none |
| 307 | t3-newton-248 | `y^3*t^2+3*x*y^3*z^2*t+3*x^2*y*z*t^3-x^2*y^2*t^2+3*x^2*y^3*z*t` | intrinsic resolution | 18.6 | embedded resolution 1.2 |
| 308 | t3-newton-259 | `y^2*z+3*y^3*z^3+x*y^2*z^4*t+x^3*z^4*t+x^3*y^3*t` | embedded resolution | 19.8 | none |
| 309 | t3-newton-263 | `-y*t^4+x*y^3*z^2*t^2+2*x^3*z*t^4-x^4*y*t+3*x^4*y^4` | embedded resolution | 19.8 | none |
| 310 | t3-newton-267 | `-y*z^2+y^3*t^2+y^3*z^2*t^3+x^3*z^2*t` | embedded resolution | 19.4 | none |
| 311 | t3-newton-275 | `3*x*y*z^3+x^2*y*t^4+2*x^2*y^2*z*t^3+2*x^3*z^4*t` | embedded resolution | 19.8 | none |
| 312 | t3-newton-283 | `2*y*z^3*t^2+2*x*y*z^2*t^3-2*x*y^2*t^4-x^2*y^4*z*t+2*x^4*y*t^3` | embedded resolution | 19.7 | none |
| 313 | t3-newton-293 | `y^3*z^3-2*x^2*z*t+2*x^2*z^3*t-2*x^2*z^4*t+2*x^2*y*z^2*t+3*x^4*z^3` | pole-check replay | 16.8 | embedded resolution 0.7, intrinsic resolution 1.9 |
| 314 | t3-newton-297 | `-2*y*z^2*t-y^2*z*t^3-x*y^2*z*t^2-2*x*y^3*z^3*t-2*x*y^4*z^2*t` | pole-check replay | 18.4 | embedded resolution 0.3, intrinsic resolution 1.2 |
| 315 | t3-newton-32 | `-2*x*z*t^2+2*x*y*z^3+3*x*y^4*z*t^2-2*x*y^4*z^3` | intrinsic resolution | 19.3 | embedded resolution 0.5 |
| 316 | t3-newton-40 | `2*y*t^4+3*y^4-2*x*y^2*z*t^2-2*x*y^3*t-x^2*y^4*z` | pole-check replay | 18.9 | embedded resolution 0.3, intrinsic resolution 0.6 |
| 317 | t3-newton-44 | `z^4*t-y^3*z+y^4*z^3*t+3*x*y*t-x*y*z^4*t^2` | embedded resolution | 19.8 | none |
| 318 | t3-newton-5 | `-2*y^2*t+y^3*z^2*t-x^2*y^2*z^2*t^2-2*x^3*z^4*t+3*x^3*y*z` | embedded resolution | 19.5 | none |
| 319 | t3-newton-53 | `2*y*z^4*t+3*y^4*t^2+2*x*y*t^2-2*x^2*z^4*t` | embedded resolution | 19.8 | none |
| 320 | t3-newton-60 | `3*y^3*z^2*t^3-2*y^4*z*t-x*y^3*z^2*t^2-x^2*z*t+3*x^3*z^3*t^2` | intrinsic resolution | 19.3 | embedded resolution 0.5 |
| 321 | t3-newton-65 | `3*x*z^3*t^4-2*x*y*z^2*t^3-2*x^3*z*t^4-2*x^3*y^2*z*t+2*x^4*t^3` | intrinsic resolution | 18.2 | embedded resolution 1.4 |
| 322 | t3-newton-69 | `-x*y*z*t^4-2*x^2*y*z*t-2*x^2*y^2*t^2-2*x^3*z*t^4+3*x^3*y*z*t+3*x^3*y*z^2*t^2` | embedded resolution | 19.9 | none |
| 323 | t3-newton-73 | `3*y^2*t^4+y^3*z^3+2*x*z^4*t^2+2*x^3*y*t^2` | embedded resolution | 19.7 | none |
| 324 | t3-newton-77 | `-2*z*t^4-2*y*z^3+2*x*y^4*t+3*x^2*z*t-x^2*y^2-x^3*z*t` | embedded resolution | 19.8 | none |
| 325 | t3-newton-83 | `-2*y*z*t^2+x*z^3*t^4+2*x*y^2*t^2+3*x^2*y^2*t-x^2*y^2*z^3*t-x^3*z^3*t^2` | embedded resolution | 19.9 | none |
| 326 | t3-newton-9 | `-t^2-z*t^2-z^2*t^2-2*z^3*t^2+2*x^2*y*z*t+x^4*z^3` | embedded resolution | 19.9 | none |
| 327 | t3-newton-92 | `z*t^4+2*y^3-x*z^2*t^4+2*x^2*y*z^2` | embedded resolution | 19.8 | none |
| 328 | t3-newton-96 | `-2*y^3*z^2-x*y*z^3*t+3*x*y^2*z^4*t-2*x^2*z*t^4-2*x^3*z^4*t` | embedded resolution | 19.8 | none |
| 329 | t3-join-nonreduced-x2cusp-d4 | `x^2*(y^2-x^3)+z^2*t+t^3` | embedded resolution | 19.4 | none |
| 330 | t3-join-nonreduced-x2cusp-z2t | `x^2*(y^2-x^3)+z^2*t` | embedded resolution | 19.8 | none |
| 331 | t3-join-nonreduced-x2cusp-z3t | `x^2*(y^2-x^3)+z^3*t` | embedded resolution | 19.9 | none |
| 332 | t3-join-nonreduced-x2y-d4 | `x^2*y+z^2*t+t^3` | embedded resolution | 19.8 | none |
| 333 | t3-join-nonreduced-x2yxy-e6 | `x^2*y*(x-y)+z^3+t^4` | embedded resolution | 19.2 | none |
| 334 | t3-join-nonreduced-x2yxy-z2t | `x^2*y*(x-y)+z^2*t` | embedded resolution | 19.7 | none |
| 335 | t3-join-nonreduced-x2yxy-z3t | `x^2*y*(x-y)+z^3*t` | embedded resolution | 19.8 | none |
| 336 | t3-join-nonreduced-x3cusp-d4 | `x^3*(y^2-x^3)+z^2*t+t^3` | embedded resolution | 19.7 | none |
| 337 | t3-join-nonreduced-x3cusp-z2t | `x^3*(y^2-x^3)+z^2*t` | embedded resolution | 19.7 | none |
| 338 | t3-join-nonreduced-x3cusp-z3t | `x^3*(y^2-x^3)+z^3*t` | embedded resolution | 19.8 | none |
| 339 | t3-join-nonreduced-xcusp2-a1 | `x*(y^2-x^3)^2+z^2+t^2` | embedded resolution | 19.7 | none |
| 340 | t3-join-nonreduced-xcusp2-a2 | `x*(y^2-x^3)^2+z^2+t^3` | embedded resolution | 19.9 | none |
| 341 | t3-join-nonreduced-xcusp2-a4 | `x*(y^2-x^3)^2+z^2+t^5` | embedded resolution | 19.8 | none |
| 342 | t3-join-nonreduced-xcusp2-e6 | `x*(y^2-x^3)^2+z^3+t^4` | embedded resolution | 19.8 | none |
| 343 | t3-join-nonreduced-xcusp2-z2t | `x*(y^2-x^3)^2+z^2*t` | embedded resolution | 19.5 | none |
| 344 | t3-join-nonreduced-xcusp2-z3t | `x*(y^2-x^3)^2+z^3*t` | embedded resolution | 19.9 | none |
| 345 | t3-join-nonreduced-xcusp2b-a4 | `x*(x^2-y^3)^2+z^2+t^5` | embedded resolution | 19.8 | none |
| 346 | t3-join-nonreduced-xcusp2b-d4 | `x*(x^2-y^3)^2+z^2*t+t^3` | embedded resolution | 19.6 | none |
| 347 | t3-join-nonreduced-xcusp2b-z2t | `x*(x^2-y^3)^2+z^2*t` | embedded resolution | 19.8 | none |
| 348 | t3-join-nonreduced-xcusp2b-z3t | `x*(x^2-y^3)^2+z^3*t` | embedded resolution | 19.8 | none |
| 349 | t3-join-nonreduced-xy2xy2-a1 | `x*y^2*(x-y)^2+z^2+t^2` | embedded resolution | 19.8 | none |
| 350 | t3-join-nonreduced-xy2xy2-a2 | `x*y^2*(x-y)^2+z^2+t^3` | embedded resolution | 19.8 | none |
| 351 | t3-join-nonreduced-xy2xy2-a4 | `x*y^2*(x-y)^2+z^2+t^5` | embedded resolution | 19.8 | none |
| 352 | t3-join-nonreduced-xy2xy2-e6 | `x*y^2*(x-y)^2+z^3+t^4` | embedded resolution | 19.8 | none |
| 353 | t3-join-nonreduced-xy2xy2-z2t | `x*y^2*(x-y)^2+z^2*t` | embedded resolution | 19.9 | none |
| 354 | t3-join-nonreduced-xy2xy2-z3t | `x*y^2*(x-y)^2+z^3*t` | embedded resolution | 19.8 | none |
| 355 | t3-suspension-arrangement-4-1-2 | `(y+3*z)*(x+2*y)*(2*x-y+z)*(x+2*y+3*z)+t^2` | embedded resolution | 19.7 | none |
| 356 | t3-suspension-arrangement-6-13-2 | `(x+2*y+3*z)*y*(x+3*y)*(2*x-y+z)*(x-y)*(2*x+y)+t^2` | embedded resolution | 19.8 | none |
| 357 | t3-suspension-arrangement-7-25-2 | `(x-y)*(y+z)*(y+3*z)*(x+y+2*z)*(2*x-y+z)*(x+2*z)*y+t^2` | embedded resolution | 19.8 | none |
| 358 | t3-suspension-arrangement-8-37-3 | `(x-y+z)*(x+y)*(x+y-z)*(x+2*y)*(y+z)*(y-z)*(x+y+z)*y+t^3` | embedded resolution | 19.7 | none |
| 359 | t3-suspension-arrangement-8-49-2 | `(x+2*y)*(y+3*z)*(x-y+z)*(x+3*y)*x*(x-2*y)*y*(-x+y+z)+t^2` | embedded resolution | 19.8 | none |
| 360 | t3-suspension-arrangement-9-61-2 | `(y+3*z)*(x+2*y)*z*(-x+y+z)*(x+y)*(x-z)*(x+2*y+3*z)*(x-2*y)*(x+2*z)+t^2` | embedded resolution | 19.8 | none |
| 361 | t3-suspension-arrangement-9-73-2 | `(x+z)*(y-z)*(x+y-z)*(y+z)*(x+y+2*z)*(x-y)*(x+y)*y*(x-z)+t^2` | embedded resolution | 19.8 | none |
| 362 | t3-suspension-arrangement-9-85-3 | `x*y*z*(x-y)*(x-z)*(y-z)*(x+y)*(x+z)*(y+z)+t^3` | embedded resolution | 19.9 | none |
| 363 | t3-suspension-chain-33114-3 | `x^3*y^3+y*z+z^4+t^3` | embedded resolution | 19.6 | none |
| 364 | t3-suspension-chain-43316-2 | `x^4*y^3+y^3*z+z^6+t^2` | embedded resolution | 19.6 | none |
| 365 | t3-suspension-cone-d5-x2y-1-2 | `z^2*x^2*y+y^5+x^4*y+t^2` | embedded resolution | 19.7 | none |
| 366 | t3-suspension-cone-d5-xy-1-b-2 | `z^3*x*y+y^5+x^4*y+z^2*(x^3+y^3)+t^2` | embedded resolution | 19.8 | none |
| 367 | t3-suspension-cone-d5-xyxy-4-b-2 | `z^2*x*y*(x+y)+x^2*y^3+x^5+z*(y^4)+t^2` | embedded resolution | 19.8 | none |
| 368 | t3-suspension-cone-tricuspidal-quartic-2 | `x^2*y^2+y^2*z^2+z^2*x^2-2*x*y*z*(x+y+z)+t^2` | embedded resolution | 19.8 | none |
| 369 | t3-suspension-cylinder-sheet-a4-y2-2 | `(y^2-x^5)*(z-y^2)+t^2` | embedded resolution | 19.7 | none |
| 370 | t3-suspension-cylinder-sheet-d5-xy-2 | `(x^2*y+y^4)*(z-x*y)+t^2` | embedded resolution | 19.8 | none |
| 371 | t3-suspension-cylinder-sheet-e6-x3-2 | `(y^3-x^4)*(z-x^3)+t^2` | embedded resolution | 19.8 | none |
| 372 | t3-suspension-cylinder-sheet-e8-x2y2-3 | `(y^3-x^5)*(z-(x^2+y^2))+t^3` | embedded resolution | 19.8 | none |
| 373 | t3-suspension-cylinder-sheet-tacnode-x2-2 | `(y^2-x^4)*(z-x^2)+t^2` | embedded resolution | 19.8 | none |
| 374 | t3-suspension-degenerate-a4-2-2-x-3 | `(y^2-x^5)^2+z^2*x+t^3` | embedded resolution | 19.8 | none |
| 375 | t3-suspension-degenerate-a6-2-2-x-3 | `(y^2-x^7)^2+z^2*x+t^3` | embedded resolution | 19.8 | none |
| 376 | t3-suspension-degenerate-cusp-2-2-x-2 | `(y^2-x^3)^2+z^2*x+t^2` | embedded resolution | 19.8 | none |
| 377 | t3-suspension-degenerate-d4-2-2-x-2 | `(x^3-y^3)^2+z^2*x+t^2` | embedded resolution | 19.8 | none |
| 378 | t3-suspension-degenerate-e6-2-2-x-2 | `(y^3-x^4)^2+z^2*x+t^2` | embedded resolution | 19.7 | none |
| 379 | t3-suspension-degenerate-e8-2-2-x-2 | `(y^3-x^5)^2+z^2*x+t^2` | embedded resolution | 19.9 | none |
| 380 | t3-suspension-degenerate-tacnode-2-2-x-2 | `(y^2-x^4)^2+z^2*x+t^2` | embedded resolution | 19.6 | none |
| 381 | t3-suspension-image-mond-b5-2 | `y^11+2*x^2*y^6+x^4*y-z^2+t^2` | embedded resolution | 19.8 | none |
| 382 | t3-suspension-image-mond-c6-3 | `x^12*y+2*x^7*y^2+x^2*y^3-z^2+t^3` | embedded resolution | 19.8 | none |
| 383 | t3-suspension-image-mond-h3-2 | `y^8+3*x*y^3*z+x^3*y-z^3+t^2` | embedded resolution | 19.9 | none |
| 384 | t3-suspension-image-mond-p3-5-2 | `-16*x^4*z+16*x^3*y^2+8*x^2*z^2-85*x*y^2*z+125*y^4-z^3+t^2` | embedded resolution | 19.8 | none |
| 385 | t3-suspension-image-mond-s2-2 | `x^6*y+2*x^3*y^2+y^3-z^2+t^2` | embedded resolution | 19.7 | none |
| 386 | t3-suspension-image-quadruple-5-2 | `x^8*y-2*x^4*y^2+4*x^2*y*z^2-z^4+y^3+t^2` | embedded resolution | 19.8 | none |
| 387 | t3-suspension-image-triple-10-2 | `x^6*y+x^3*y^2+3*x^3*y*z+3*x^2*y^3+3*x^2*y^2*z+3*x*y^4+y^5-z^3+t^2` | embedded resolution | 19.8 | none |
| 388 | t3-suspension-image-triple-5-2 | `x^6*y+3*x^2*y^2*z+y^5-z^3+t^2` | embedded resolution | 19.8 | none |
| 389 | t3-suspension-modulus-z18-1-3 | `x^3*y+x*y^6+z*y^9+t^3` | embedded resolution | 19.9 | none |
| 390 | t3-suspension-quasi-ordinary-02-32-2 | `x^6*y^4-2*x^3*y^2*z^4-12*x^3*y^3*z^2+z^8-2*x^3*y^4-4*y*z^6+6*y^2*z^4-4*y^3*z^2+y^4+t^2` | embedded resolution | 19.8 | none |
| 391 | t3-suspension-quasi-ordinary-22-32-2 | `x^6*y^4-2*x^5*y^4-12*x^4*y^3*z^2-2*x^3*y^2*z^4+x^4*y^4-4*x^3*y^3*z^2+6*x^2*y^2*z^4-4*x*y*z^6+z^8+t^2` | embedded resolution | 19.8 | none |
| 392 | t3-suspension-quasi-ordinary-22-34-3 | `x^6*y^8-2*x^5*y^6-12*x^4*y^5*z^2-2*x^3*y^4*z^4+x^4*y^4-4*x^3*y^3*z^2+6*x^2*y^2*z^4-4*x*y*z^6+z^8+t^3` | embedded resolution | 19.8 | none |
| 393 | t3-suspension-quasi-ordinary-24-35-2 | `x^6*y^10-2*x^5*y^9-12*x^4*y^7*z^2+x^4*y^8-2*x^3*y^5*z^4-4*x^3*y^6*z^2+6*x^2*y^4*z^4-4*x*y^2*z^6+z^8+t^2` | embedded resolution | 19.8 | none |
| 394 | t3-suspension-quasi-ordinary-24-55-2 | `x^10*y^10-2*x^7*y^9-12*x^6*y^7*z^2-2*x^5*y^5*z^4+x^4*y^8-4*x^3*y^6*z^2+6*x^2*y^4*z^4-4*x*y^2*z^6+z^8+t^2` | embedded resolution | 19.8 | none |
| 395 | t3-suspension-quasi-ordinary-62-63-3 | `x^12*y^6-2*x^12*y^5+x^12*y^4-12*x^9*y^4*z^2-4*x^9*y^3*z^2-2*x^6*y^3*z^4+6*x^6*y^2*z^4-4*x^3*y*z^6+z^8+t^3` | embedded resolution | 19.8 | none |
| 396 | t3-suspension-ruled-3-5-5-2-3 | `x*y*(x-2*y)+z^2*(x^2*y)+t^3` | intrinsic resolution | 17.7 | embedded resolution 2.1 |
| 397 | t3-suspension-ruled-5-1-5-1-3 | `x*y*(x-y)*(x+y)*(x-2*y)+z*(x^5)+t^3` | embedded resolution | 19.8 | none |
| 398 | t3-suspension-ruled-jump-4-3-2-4-2 | `x*y*(x-y)*(x-2*y)+z*(x^3+y^3)+t^2` | embedded resolution | 19.8 | none |
| 399 | t3-suspension-ruled-jump-5-4-1-3-2 | `x*y*(x-y)*(x+y)*(x-2*y)+z*(x*y*(x^2+y^2))+t^2` | embedded resolution | 19.8 | none |
| 400 | t3-suspension-sheets-3-1-2 | `(z-(-x^2))*(z-(x*y))*(z-(x+y^2))+t^2` | embedded resolution | 19.8 | none |
| 401 | t3-suspension-sheets-3-17-2 | `(z-(x^2))*(z-(y^2))*(z-(x*y+x^3))+t^2` | embedded resolution | 19.8 | none |
| 402 | t3-suspension-sheets-4-113-3 | `(z-(y))*(z-(2*x^2))*(z-(x+y^2))*(z-(x*y+x^3))+t^3` | embedded resolution | 19.8 | none |
| 403 | t3-suspension-sheets-4-33-2 | `(z-(-x^2))*(z-(x^2+y^2))*(z-(x*y))*(z-(x^3))+t^2` | embedded resolution | 19.8 | none |
| 404 | t3-suspension-sheets-4-49-3 | `z*(z-(x^2))*(z-(-x^2))*(z-(x^2-y^2))+t^3` | embedded resolution | 19.9 | none |
| 405 | t3-suspension-sheets-4-65-2 | `z*(z-(y))*(z-(x^2))*(z-(y^2-x^3))+t^2` | embedded resolution | 19.8 | none |
| 406 | t3-suspension-sheets-4-81-2 | `(z-(x))*(z-(x^2+y^2))*(z-(x*y+x^3))*(z-(y^2-x^3))+t^2` | embedded resolution | 19.8 | none |
| 407 | t3-suspension-sheets-4-97-2 | `(z-(x^2))*(z-(x^3))*(z-(2*x^2))*(z-(x*y+x^3))+t^2` | embedded resolution | 19.8 | none |
| 408 | t3-suspension-steiner-222-sum-m1-2 | `(x*y)^2+(y*z)^2+(z*x)^2-x*y*z*(x+y+z)+t^2` | intrinsic resolution | 18.0 | embedded resolution 1.8 |

## Errors (108)

Errors by step: embedded resolution 106, record assembly 2. The diagnostic omits the opening sentence about the singular tangent cone when the solver gave one.

### Surfaces (71)

| # | ID | Equation | Step | Diagnostic |
| ---: | --- | --- | --- | --- |
| 1 | s2-sheets-3-16 | `(z-(x^2))*(z-(x^3))*(z-(x^2+y^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 8 candidates (7 rejected, 1 undecided). |
| 2 | s2-sheets-3-8 | `z*(z-(x^2+y^3))*(z-(x*y+x^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 7 candidates (6 rejected, 1 undecided). |
| 3 | s2-sheets-4-108 | `(z-(y))*(z-(-x^2))*(z-(x*y))*(z-(x^2-y^2))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The successive blowup search returned no certified atlas. The general search checked 11 candidates (10 rejected, 1 undecided). |
| 4 | s2-sheets-4-116 | `(z-(y))*(z-(x^2+y^2))*(z-(x*y))*(z-(x^2-y^2))` | embedded resolution | The Newton search returned no certified atlas. The successive blowup search returned no certified atlas. The general search checked 10 candidates (9 rejected, 1 undecided). |
| 5 | s2-sheets-4-125 | `(z-(y^2))*(z-(x^2+y^2))*(z-(x*y))*(z-(x^2-y^2))` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 10 candidates (9 rejected, 1 undecided). |
| 6 | s2-sheets-4-130 | `(z-(y^3))*(z-(x^2+y^3))*(z-(x^2-y^2))*(z-(x*y+x^3))` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 9 candidates (8 rejected, 1 undecided). |
| 7 | s2-sheets-4-32 | `(z-(-x^2))*(z-(x*y))*(z-(y^3))*(z-(x^2-y^2))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 11 candidates (10 rejected, 1 undecided). |
| 8 | s2-sheets-4-33 | `(z-(-x^2))*(z-(x^2+y^2))*(z-(x*y))*(z-(x^3))` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 11 candidates (10 rejected, 1 undecided). |
| 9 | s2-sheets-4-35 | `(z-(-x^2))*(z-(x^2+y^2))*(z-(y^3))*(z-(x^2-y^2))` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 9 candidates (8 rejected, 1 undecided). |
| 10 | s2-sheets-4-39 | `z*(z-(-x^2))*(z-(x*y))*(z-(y^2-x^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 12 candidates (11 rejected, 1 undecided). |
| 11 | s2-sheets-4-46 | `z*(z-(x*y))*(z-(x+y^2))*(z-(x*y+x^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The successive blowup search returned no certified atlas. The general search checked 11 candidates (10 rejected, 1 undecided). |
| 12 | s2-sheets-4-48 | `z*(z-(x+y^2))*(z-(x*y+x^3))*(z-(y^2-x^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The successive blowup search returned no certified atlas. The general search checked 10 candidates (9 rejected, 1 undecided). |
| 13 | s2-sheets-4-53 | `z*(z-(x^2+y^2))*(z-(x^2+y^3))*(z-(y^2-x^3))` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 9 candidates (8 rejected, 1 undecided). |
| 14 | s2-sheets-4-54 | `z*(z-(x^2+y^2))*(z-(x^3))*(z-(x^2-y^2))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 11 candidates (10 rejected, 1 undecided). |
| 15 | s2-sheets-4-55 | `z*(z-(x^2+y^2))*(z-(y^3))*(z-(x+y^2))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The successive blowup search returned no certified atlas. The general search checked 11 candidates (10 rejected, 1 undecided). |
| 16 | s2-sheets-4-57 | `z*(z-(x^2+y^3))*(z-(x*y+x^3))*(z-(y^2-x^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 10 candidates (9 rejected, 1 undecided). |
| 17 | s2-sheets-4-59 | `z*(z-(x^3))*(z-(y^3))*(z-(2*x^2))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 13 candidates (12 rejected, 1 undecided). |
| 18 | s2-sheets-4-60 | `z*(z-(x^3))*(z-(y^3))*(z-(x*y+x^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 13 candidates (12 rejected, 1 undecided). |
| 19 | s2-sheets-4-61 | `z*(z-(x^3))*(z-(y^3))*(z-(y^2-x^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 13 candidates (12 rejected, 1 undecided). |
| 20 | s2-sheets-4-64 | `z*(z-(y))*(z-(x^2))*(z-(x^2+y^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The successive blowup search returned no certified atlas. The general search checked 12 candidates (11 rejected, 1 undecided). |
| 21 | s2-sheets-4-65 | `z*(z-(y))*(z-(x^2))*(z-(y^2-x^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The successive blowup search returned no certified atlas. The general search checked 12 candidates (11 rejected, 1 undecided). |
| 22 | s2-sheets-4-66 | `z*(z-(y))*(z-(x^2+y^2))*(z-(y^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The successive blowup search returned no certified atlas. The general search checked 11 candidates (10 rejected, 1 undecided). |
| 23 | s2-sheets-4-68 | `z*(z-(y))*(z-(y^3))*(z-(x*y+x^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The successive blowup search returned no certified atlas. The general search checked 12 candidates (11 rejected, 1 undecided). |
| 24 | s2-sheets-4-71 | `z*(z-(y^2))*(z-(x^3))*(z-(y^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 13 candidates (12 rejected, 1 undecided). |
| 25 | s2-sheets-4-72 | `z*(z-(y^3))*(z-(x^2+y^3))*(z-(x*y+x^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 12 candidates (11 rejected, 1 undecided). |
| 26 | s2-sheets-4-76 | `(z-(x))*(z-(x*y))*(z-(x^2+y^3))*(z-(x+y^2))` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 10 candidates (9 rejected, 1 undecided). |
| 27 | s2-sheets-4-77 | `(z-(x))*(z-(x*y))*(z-(x^3))*(z-(x+y^2))` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 10 candidates (9 rejected, 1 undecided). |
| 28 | s2-sheets-4-78 | `(z-(x))*(z-(x*y))*(z-(y^3))*(z-(y^2-x^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 11 candidates (10 rejected, 1 undecided). |
| 29 | s2-sheets-4-79 | `(z-(x))*(z-(x^2))*(z-(x^2-y^2))*(z-(y^2-x^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 10 candidates (9 rejected, 1 undecided). |
| 30 | s2-sheets-4-84 | `(z-(x))*(z-(x^2+y^3))*(z-(x^2-y^2))*(z-(x*y+x^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 10 candidates (9 rejected, 1 undecided). |
| 31 | s2-sheets-4-88 | `(z-(x))*(z-(y))*(z-(y^3))*(z-(x*y+x^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 11 candidates (10 rejected, 1 undecided). |
| 32 | s2-sheets-4-89 | `(z-(x*y))*(z-(x^2-y^2))*(z-(x*y+x^3))*(z-(y^2-x^3))` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 10 candidates (9 rejected, 1 undecided). |
| 33 | s2-sheets-4-94 | `(z-(x^2))*(z-(x*y))*(z-(x^3))*(z-(x^2+y^3))` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 11 candidates (10 rejected, 1 undecided). |
| 34 | s2-sheets-4-95 | `(z-(x^2))*(z-(x^2+y^2))*(z-(2*x^2))*(z-(y^2-x^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. A Newton face could not be certified. The successive blowup search returned no certified atlas. The general search checked 11 candidates (10 rejected, 1 undecided). |
| 35 | s2-sheets-4-97 | `(z-(x^2))*(z-(x^3))*(z-(2*x^2))*(z-(x*y+x^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 11 candidates (9 rejected, 2 undecided). |
| 36 | s2-sheets-4-98 | `(z-(x^2))*(z-(y^2))*(z-(x*y))*(z-(y^3))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 12 candidates (11 rejected, 1 undecided). |
| 37 | s2-sheets-4-99 | `(z-(x^2))*(z-(y^2))*(z-(x^2+y^2))*(z-(x*y+x^3))` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. A Newton face could not be certified. The successive blowup search returned no certified atlas. The general search checked 10 candidates (9 rejected, 1 undecided). |
| 38 | s2-image-corank2-7 | `x^10-2*x^5*y^5+y^10-2*x^6*y-2*x^5*z^2-8*x^3*y^3*z-2*x*y^6-2*y^5*z^2+x^2*y^2-2*x*y*z^2+z^4` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 3 candidates (2 rejected, 1 undecided). |
| 39 | s2-image-corank2-8 | `z^9-3*x*y*z^6-5*z^8+3*x^2*y^2*z^3+7*x*y*z^5+10*z^7-x^3*y^3-2*x^2*y^2*z^2-3*x*y*z^4-10*z^6+x^5-3*x*y*z^3+y^5+5*…` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 3 candidates (2 rejected, 1 undecided). |
| 40 | s2-image-quadruple-11 | `x^8*y^2-4*x^5*y^3-x^4*y^3-4*x^4*y^2*z-2*x^4*y*z^2+2*x^2*y^4-4*x^2*y^3*z-4*x*y^2*z^2-y^5+z^4` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 5 candidates (4 rejected, 1 undecided). |
| 41 | s2-image-triple-10 | `x^6*y+x^3*y^2+3*x^3*y*z+3*x^2*y^3+3*x^2*y^2*z+3*x*y^4+y^5-z^3` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 3 candidates (2 rejected, 1 undecided). |
| 42 | s2-a4-section-a-b | `-16*x^6*z+4*x^5*y^2+72*x^5*y*z-108*x^5*z^2-16*x^4*y^3-108*x^5*z+27*x^4*y^2+630*x^4*y*z-825*x^4*z^2-144*x^3*y^3…` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 3 candidates (2 rejected, 1 undecided). |
| 43 | s2-a4-section-c-a | `16*x^7-4*x^5*y^2-72*x^5*y*z+108*x^5*z^2+16*x^3*y^3*z-128*x^6+144*x^4*y^2+560*x^4*y*z-900*x^4*z^2-27*x^2*y^4-63…` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 3 candidates (2 rejected, 1 undecided). |
| 44 | s2-a4-section-d-a | `108*x^7-72*x^5*y*z+16*x^4*y^3+16*x^4*z^3-4*x^3*y^2*z^2-900*x^5*z+825*x^4*y^2+560*x^3*y*z^2-630*x^2*y^3*z-128*x…` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 3 candidates (2 rejected, 1 undecided). |
| 45 | s2-a4-section-d-b2 | `108*x^5*y^4-72*x^4*y^3*z+16*x^3*y^5-900*x^3*y^4*z+825*x^2*y^6-3750*x*y^7+3125*y^8+16*x^4*z^3-4*x^3*y^2*z^2+560…` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 5 candidates (2 rejected, 3 undecided). |
| 46 | s2-a5-section-ab | `-1024*x^6*z+256*x^5*y^2-13824*x^3*z^3+43200*x^2*y^2*z^2-22500*x*y^4*z+3125*y^6-46656*z^5` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 3 candidates (2 rejected, 1 undecided). |
| 47 | s2-a5-section-ad | `729*x^6*z^2+108*x^4*y^3*z-8748*x^4*z^3-8640*x^2*y^3*z^2-1024*y^6*z+34992*x^2*z^4-13824*y^3*z^3-46656*z^5` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 6 candidates (5 rejected, 1 undecided). |
| 48 | s2-a5-section-bc | `-1024*x^6*z^3+108*x^5*y^4-192*x^4*y^2*z^2-13824*x^3*z^4+1500*x^2*y^4*z-32400*x*y^2*z^3+3125*y^6-46656*z^5` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 5 candidates (4 rejected, 1 undecided). |
| 49 | s2-caustic-e6-slice | `4*x^14*y^4-24*x^13*y^2*z^2+36*x^12*z^4-384*x^10*y^5+2412*x^9*y^3*z^2-2916*x^8*y*z^4+9216*x^6*y^6-46656*x^5*y^4…` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 5 candidates (5 rejected, 0 undecided). |
| 50 | s2-trans-e13-cusp-s | `(y^2-z^3)^3+(y^2-z^3)*x^5` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 6 candidates (6 rejected, 0 undecided). |
| 51 | s2-trans-w13-d5-s | `(y^2*z+z^4)^4+(y^2*z+z^4)*x^4` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 4 candidates (4 rejected, 0 undecided). |
| 52 | s2-trans-w13-e6-s | `(y^3-z^4)^4+(y^3-z^4)*x^4` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 3 candidates (3 rejected, 0 undecided). |
| 53 | s2-trans-z13-d4-s | `(y^3-z^3)^3*x+x^6` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 4 candidates (4 rejected, 0 undecided). |
| 54 | s2-trans-z13-d5-s | `(y^2*z+z^4)^3*x+x^6` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 6 candidates (6 rejected, 0 undecided). |
| 55 | s2-trans-z13-tacnode-s | `(y^2-z^4)^3*x+x^6` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 4 candidates (4 rejected, 0 undecided). |
| 56 | s2-space-4611-2-4 | `(y^2-x^3)^2+(z^2-x^4*y)^4` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 2 candidates (2 rejected, 0 undecided). |
| 57 | s2-space-4611-d4 | `(y^2-x^3)^2*(z^2-x^4*y)+(z^2-x^4*y)^3` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 3 candidates (3 rejected, 0 undecided). |
| 58 | s2-space-467-3-2 | `(y^2-x^3)^3+(z^2-x^2*y)^2` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 3 candidates (2 rejected, 1 undecided). |
| 59 | s2-space-469-2-4 | `(y^2-x^3)^2+(z^2-y^3)^4` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 3 candidates (2 rejected, 1 undecided). |
| 60 | s2-space-6910-2-3 | `(y^2-x^3)^2+(z^3-x^5)^3` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 2 candidates (2 rejected, 0 undecided). |
| 61 | s2-space-6910-2-x2 | `(y^2-x^3)^2+x*(z^3-x^5)^2` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 3 candidates (2 rejected, 1 undecided). |
| 62 | s2-space-6910-d4 | `(y^2-x^3)^2*(z^3-x^5)+(z^3-x^5)^3` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 3 candidates (3 rejected, 0 undecided). |
| 63 | s2-space-cone-cusp-2-3 | `(x*y-z^2)^2+(x^2-y^3)^3` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 3 candidates (2 rejected, 1 undecided). |
| 64 | s2-quasi-ordinary-22-52 | `x^10*y^4-2*x^7*y^4-12*x^6*y^3*z^2-2*x^5*y^2*z^4+x^4*y^4-4*x^3*y^3*z^2+6*x^2*y^2*z^4-4*x*y*z^6+z^8` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 7 candidates (6 rejected, 1 undecided). |
| 65 | s2-quasi-ordinary-62-65 | `x^12*y^10-2*x^12*y^7-12*x^9*y^6*z^2+x^12*y^4-2*x^6*y^5*z^4-4*x^9*y^3*z^2+6*x^6*y^2*z^4-4*x^3*y*z^6+z^8` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 4 candidates (4 rejected, 0 undecided). |
| 66 | s2-quasi-ordinary-62-92 | `x^18*y^4-2*x^15*y^4-12*x^12*y^3*z^2+x^12*y^4-2*x^9*y^2*z^4-4*x^9*y^3*z^2+6*x^6*y^2*z^4-4*x^3*y*z^6+z^8` | embedded resolution | The Newton search returned no certified atlas. A Newton face could not be certified. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 4 candidates (4 rejected, 0 undecided). |
| 67 | s2-developable-135 | `81*x^5*z^2-90*x^4*y^2*z+25*x^3*y^4-120*x^2*y*z^2+120*x*y^3*z-32*y^5+16*z^3` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 5 candidates (4 rejected, 1 undecided). |
| 68 | s2-developable-137 | `729*x^7*z^2-378*x^5*y^3*z+49*x^3*y^6-1134*x^4*y*z^2+420*x^2*y^4*z-54*y^7+336*x*y^2*z^2+32*z^3` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 5 candidates (4 rejected, 1 undecided). |
| 69 | s2-developable-147 | `-4096*x^7*z^3+5376*x^6*y^2*z^2-2352*x^5*y^4*z+343*x^4*y^6+6048*x^3*y*z^3-7182*x^2*y^3*z^2+3024*x*y^5*z-432*y^7…` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 5 candidates (4 rejected, 1 undecided). |
| 70 | s2-developable-257 | `-12500*x^7*z^3+5488*x^5*y^5+3360*x^4*y^4*z+1680*x^3*y^3*z^2+29295*x^2*y^2*z^3-12500*y^7-17010*x*y*z^4+2187*z^5` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 5 candidates (4 rejected, 1 undecided). |
| 71 | s2-cylinder-sheet-e8-x2y2 | `(y^3-x^5)*(z-(x^2+y^2))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The successive blowup search returned no certified atlas. The general search checked 6 candidates (6 rejected, 0 undecided). |

### Threefolds (37)

| # | ID | Equation | Step | Diagnostic |
| ---: | --- | --- | --- | --- |
| 1 | t3-superisolated-3a2 | `x*y*z-t^3+(x+y+z+t)^4` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 3 candidates (2 rejected, 1 undecided). |
| 2 | t3-chain4-3342 | `x^3*y+y^3*z+z^4*t+t^2` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 3 candidates (2 rejected, 1 undecided). |
| 3 | t3-image-corank2-5 | `x^2*y*z^2+2*x*y^3*z+y^5-y^2*t^2+2*y*z^2*t-z^4` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 7 candidates (6 rejected, 1 undecided). |
| 4 | t3-image-corank2-6 | `x^2*y^2-2*x^2*y*z+x^2*z^2-2*x*y^2*z-2*x*y*z^2-8*x*y*z*t-2*x*y*t^2-2*x*z*t^2+y^2*z^2-2*y*z*t^2+t^4` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 6 candidates (5 rejected, 1 undecided). |
| 5 | t3-image-double-10 | `t^2-z*(z+x^3+y^4)^2` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 3 candidates (2 rejected, 1 undecided). |
| 6 | t3-image-double-5 | `t^2-z*(z+x^3+y^3)^2` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 3 candidates (3 rejected, 0 undecided). |
| 7 | t3-image-double5-1 | `t^2-z*(z^2+x^2+y^2)^2` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 3 candidates (3 rejected, 0 undecided). |
| 8 | t3-image-double5-10 | `t^2-z*(z^2+x^3+y^4)^2` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 3 candidates (3 rejected, 0 undecided). |
| 9 | t3-image-double5-2 | `t^2-z*(z^2+x*y)^2` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 5 candidates (5 rejected, 0 undecided). |
| 10 | t3-image-double5-5 | `t^2-z*(z^2+x^3+y^3)^2` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 3 candidates (3 rejected, 0 undecided). |
| 11 | t3-image-double5-8 | `t^2-z*(z^2+x^2*y+y^3)^2` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 4 candidates (3 rejected, 1 undecided). |
| 12 | t3-cone-d4-x2y-3 | `t*(x^2*y)+z^4+x^3*z` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 7 candidates (7 rejected, 0 undecided). |
| 13 | t3-sheets-18 | `(t-(x^2))*(t-(x*y))*(t-(x^2+z^3))` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 9 candidates (8 rejected, 1 undecided). |
| 14 | t3-sheets-3 | `t*(t-(x^2+y^2))*(t-(x^2-y*z))` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 8 candidates (7 rejected, 1 undecided). |
| 15 | t3-sheets-5 | `t*(t-(z^2))*(t-(x*y*z))` | record assembly | Incomplete intrinsic geometry for x*y*z^3*t-x*y*z*t^2-z^2*t^2+t^3 |
| 16 | t3-union-11 | `(x*y-z*t)*(x*z-y*t)` | record assembly | Incomplete intrinsic geometry for x^2*y*z-x*y^2*t-x*z^2*t+y*z*t^2 |
| 17 | t3-chain-1232324 | `x*y^2+y^3*z^2+z^3*t^2+t^4` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 6 candidates (6 rejected, 0 undecided). |
| 18 | t3-chain-2112222 | `x^2*y+y*z^2+z^2*t^2+t^2` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 4 candidates (3 rejected, 1 undecided). |
| 19 | t3-chain-2212313 | `x^2*y^2+y*z^2+z^3*t+t^3` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 5 candidates (4 rejected, 1 undecided). |
| 20 | t3-chain-2212322 | `x^2*y^2+y*z^2+z^3*t^2+t^2` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 5 candidates (4 rejected, 1 undecided). |
| 21 | t3-chain-2221313 | `x^2*y^2+y^2*z+z^3*t+t^3` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 4 candidates (3 rejected, 1 undecided). |
| 22 | t3-newton-252 | `-2*y^2*z*t^3+x^2*z^4*t+2*x^3*y*t^3+x^3*y*z*t-2*x^4*y*t^3` | embedded resolution | The Newton search returned no certified atlas. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 11 candidates (10 rejected, 1 undecided). |
| 23 | t3-join-nonreduced-x2y2-d4 | `x^2*y^2+z^2*t+t^3` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 5 candidates (5 rejected, 0 undecided). |
| 24 | t3-join-nonreduced-x2yxy-a2 | `x^2*y*(x-y)+z^2+t^3` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 4 candidates (4 rejected, 0 undecided). |
| 25 | t3-join-nonreduced-x2yxy-a4 | `x^2*y*(x-y)+z^2+t^5` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 4 candidates (4 rejected, 0 undecided). |
| 26 | t3-join-nonreduced-x2yxy-d4 | `x^2*y*(x-y)+z^2*t+t^3` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 4 candidates (3 rejected, 1 undecided). |
| 27 | t3-join-nonreduced-xcusp2-d4 | `x*(y^2-x^3)^2+z^2*t+t^3` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 3 candidates (2 rejected, 1 undecided). |
| 28 | t3-join-nonreduced-xcusp2b-a2 | `x*(x^2-y^3)^2+z^2+t^3` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 3 candidates (3 rejected, 0 undecided). |
| 29 | t3-join-nonreduced-xcusp2b-e6 | `x*(x^2-y^3)^2+z^3+t^4` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 3 candidates (3 rejected, 0 undecided). |
| 30 | t3-join-nonreduced-xy2xy2-d4 | `x*y^2*(x-y)^2+z^2*t+t^3` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 4 candidates (3 rejected, 1 undecided). |
| 31 | t3-suspension-cylinder-sheet-cusp-plane-2 | `(y^2-x^3)*z+t^2` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 4 candidates (4 rejected, 0 undecided). |
| 32 | t3-suspension-degenerate-node-2-2-x-2 | `(y^2-x^2)^2+z^2*x+t^2` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 3 candidates (2 rejected, 1 undecided). |
| 33 | t3-suspension-image-triple-15-3 | `x^12*y+3*x^8*y^2+3*x^4*y^3+y^4-z^3+t^3` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 3 candidates (3 rejected, 0 undecided). |
| 34 | t3-suspension-quasi-ordinary-42-45-2 | `x^4*y^5+4*x^3*y^3*z-x^4*y^2+2*x^2*y*z^2-z^4+t^2` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 5 candidates (4 rejected, 1 undecided). |
| 35 | t3-suspension-ruled-3-1-2-1-2 | `x*y*(x-y)+z*(x*y*(x+y))+t^2` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 4 candidates (3 rejected, 1 undecided). |
| 36 | t3-suspension-ruled-3-2-5-2-2 | `x*y*(x+y)+z^2*(x^2*y)+t^2` | embedded resolution | The Newton search returned no certified atlas. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 4 candidates (3 rejected, 1 undecided). |
| 37 | t3-suspension-ruled-3-4-2-1-2 | `x^3+y^3+z*(x*y*(x+y))+t^2` | embedded resolution | The Newton search returned no certified atlas. A degenerate face needs repair on a fan with centres extending beyond the origin. The strict transform fails normal crossings along a curve of an orbit. The repeated-tangent search returned no certified atlas. The canonical smooth-centre rule returned no certified atlas. The general search checked 4 candidates (3 rejected, 1 undecided). |
