# Visualization proposals: geometry first, abstractions second

**Question:** Which portions of Morava's work can be visualized faithfully, and which only have useful *analogies*? The answer varies sharply by subject.

| Starting object | Proposed interaction | What is honest | What must not be claimed |
| --- | --- | --- | --- |
| Formal group \(p\)-series | Prime \(p\), truncated polynomial coefficients, first nonzero exponent | A calculation of height for explicit formal laws | The plot is not a picture of a \(K(n)\)-local spectrum |
| \(B_3\) / Burau | Draw crossing words; show 2×2 Laurent-polynomial matrices | Exact braid relation and representation | Specializing \(t\) need not distinguish all braids |
| Circle acting on a sphere | Turn sphere, select an orbit, see quotient data | Orbits, fixed points, isotropy, quotient interval | The quotient interval is not the full quotient groupoid |
| Lagrangian correspondences | Move points from one phase plane to another; compose | Finite-dimensional symplectic maps give Lagrangian graphs | It is not yet the *stable* symplectic category |
| Quaternion anti-automorphism | Explore eight group elements and reverse products | Group multiplication and the anti-homomorphism identity | This is only Morava's proposed model of the myth formula |
| Stratified groupoid | Change orbit types and preserve incidence arrows | Explicit finite group actions / orbit categories | A graph of strata is not a universal \(\pi_0\) theorem |
| Chromatic tower | Prime/height selector; fiber/fracture-square schematic | Correct localization arrows and algebraic labels | Levels are not literal image-frequency bands or physical depths |

## Proposed first experiments

### A. Circle action, quotient *versus* groupoid

Take \(S^2=\{(x,y,z):x^2+y^2+z^2=1\}\) and let \(S^1\) rotate around the \(z\)-axis. A point at height \(z\) moves around a latitude circle. The **ordinary orbit space** is the interval \([-1,1]\), with coordinate \(z\).

But the action retains stabilizer information:
- For \(-1<z<1\), the stabilizer is trivial.
- At \(z=\pm1\), the poles are fixed by the **whole circle** \(S^1\).

Display the sphere, its orbit interval and the stabilizer for the selected point simultaneously. Two fixed ends with the same coarse local picture as ordinary endpoints now visibly carry extra group data. This is a straightforward entry to quotient **groupoids/stacks**, [*Theories of anything*](https://arxiv.org/abs/1202.0684) and Morava's [circle-symmetry/bubbling toy model](https://arxiv.org/abs/2407.00672).

An optional collapse animation can be introduced *after* the groupoid display is correct. In particular, the map \([S^2/S^1]\to [\mathrm{pt}/S^1]\) from equivariant geometry is **not** the same mathematical map as just squeezing the sphere's pixels to a point.

### B. Three-strand Burau laboratory

This is probably the quickest bridge to a device with touch input: colored over/under crossings next to exact small matrices. See [worked example](burau-braids.md). An animation of the words \(\sigma_1\sigma_2\sigma_1\) and \(\sigma_2\sigma_1\sigma_2\) realizes a true relation in \(B_3\). It connects naturally to configurations of unordered points in the plane and Morava–Rolfsen's TQFT approach.

### C. The formal-group height inspector

For \(p=2\), compare a formal additive law (\([2]=0\)), multiplicative law (\([2]=t^2\)), and a height-two Honda law (\([2]=t^4\)). Render coefficients indexed by degree, with the first nonzero one highlighted. A side panel can show why coefficient truncation can produce **unknown height**, rather than arbitrarily deciding it. See [formal-group notes](formal-groups.md).

The scientific diagram has *two independent axes*: prime \(p\) and height \(n\). A misleading attractive picture would be to equate them with visible hue and physical height. A defensible display instead labels values and shows known formulae. Link the conceptual story to work on spectra and to [Paul VanKoughnett's lectures repo](https://github.com/isomorphisms/VanKoughnett) as a possible follow-up.

### D. Symplectic correspondences

Start with the phase plane \((q,p)\) equipped with \(\omega=dq\wedge dp\). For two such planes, a symplectomorphism \(f\) has a Lagrangian graph
\[
\Gamma_f=\{(x,f(x))\}\subset (\overline{\mathbb R^2})\times\mathbb R^2.
\]
Select a point and watch its image under a rotation, shear, or translation that preserves \(\omega\); compose two maps and compare the graphs. All these are finite-dimensional **examples**, not a computational realization of the homotopy-theoretic stable category described by **Nitu Kitchloo and Jack Morava** ([paper](https://arxiv.org/abs/1212.6905)). The geometry nevertheless motivates why a correspondence can be a morphism.

### E. Quaternions and Lévi-Strauss

Show \(Q_8=\{\pm1,\pm i,\pm j,\pm k\}\). Give two selectable elements \(a,b\), multiply them, then show \((ab)^{-1}=b^{-1}a^{-1}\). The identity makes inversion an **anti**-automorphism: it reverses order. This is concrete, testable mathematics with a relation to a [2003 Morava paper](https://arxiv.org/abs/math/0306174), not a proof of a theory of myths.

### F. Composition diagrams and abstract levels

Only after the elementary models work, investigate:
- Chromatic fracture squares as *commutative diagrams with homotopy pullbacks*, rather than pictures of slices of an object.
- Lubin–Tate deformation parameters \(u_1,\ldots,u_{n-1}\) as coordinates on a formal deformation space, with an explicit truncation/adic precision slider.
- Quasi-symmetric functions / ordered compositions as a combinatorial entry to the [Cosmic Galois group paper](https://arxiv.org/abs/1108.4627). The finite compositions are visualizable; the cosmic Galois group is not produced by them.
- Cobordism with free circle actions, boundary 3-manifolds and 4D slices; the [1999 paper](https://arxiv.org/abs/math/9908070) and [2025 paper](https://arxiv.org/abs/2502.05983) should control the mathematical constraints.

## A design criterion

Each proposed display should state:
1. the **mathematical object** and its domain, including whether arithmetic is formal/p-adic/finite-field;
2. the **visible projection** to pixels or 3D mesh;
3. one **invariant** that survives camera motion and interaction;
4. a **counterexample or missing-information warning** when the projection forgets structure.

Avoid letting graphics decide the mathematics: the drawing should be a derived representation of the object, so repainting follows every mathematically relevant interaction. The converse is false: two distinct objects can produce the same projection; in that case give the user a second view or explicit warning.
