# Formal groups, height, and Morava K-theory

This is a **small algebraic entrance** to a larger stable-homotopy subject, not an attempt to draw a spectrum.

## 1. A formal group law is a rule for addition near an origin

Fix a commutative ring (R). A one-dimensional commutative formal group law is a power series
[
F(x,y)in R[[x,y]]
]
satisfying
[
F(x,0)=x,qquad F(0,y)=y,qquad F(x,y)=F(y,x),
]
[
F(F(x,y),z)=F(x,F(y,z)).
]
The variables are *formal*, or can be interpreted in suitable nilpotent/complete algebras. Plotting (F(x,y)) over real inputs is at most an analogy unless convergence has been established.

Two easy examples:
- additive: (F_a(x,y)=x+y);
- multiplicative: (F_m(x,y)=x+y+xy), equivalently (1+F_m(x,y)=(1+x)(1+y)).

Define the (k)-series recursively by
[
[0]_F(t)=0,qquad [k+1]_F(t)=F([k]_F(t),t).
]
In particular, ([p]_F) is (p)-fold addition at a chosen prime (p).

## 2. Characteristic (p) exposes a numerical notion: *height*

Work now over a field (k) of characteristic (p).
- For (F_a), ([p]_{F_a}(t)=pt=0). Its height is **infinite**.
- For (F_m), ([p]_{F_m}(t)=(1+t)^p-1=t^p). Its height is **1**.
- A Honda formal group of height **2** can be chosen over an appropriate characteristic-(p) field with ([p]_F(t)=t^{p^2}) in a suitable coordinate.

For a nonzero (p)-series over a field, height (n) is characterized by its leading term (a,t^{p^n}) with (a
e0). Height is invariant under change of formal-group coordinate, although individual coefficients are not.

For **(p=2)**, the three examples give ([2]_F(t)=0,;t^2,;t^4) respectively. The zeros at low degrees are mathematically significant; if we truncate at degree (3), we cannot distinguish height 2 from infinite height.

More detailed link: [nLab, height of a formal group](https://ncatlab.org/nlab/show/height+of+a+formal+group).

## 3. Why this leads toward Morava K-theory

For (ngeq1), a standard grading convention gives
[
pi_*K(n)congmathbb{F}_p[v_n,v_n^{-1}],
qquad |v_n|=2(p^n-1).
]
This is a ring of *graded homotopy coefficients*, not a numerical field in a pixel shader. For (p=2), the first three nonzero heights have periods (2,6,14). Height zero corresponds to rational ordinary homology under the usual convention.

The theories (K(n)) detect distinct periodic phenomena in stable homotopy theory. The chromatic tower of a spectrum (X) takes successive approximations (L_nX), with maps (L_nX	o L_{n-1}X), and has monochromatic layers
[
M_nX=operatorname{fib}(L_nX	o L_{n-1}X).
]
For finite (p)-local spectra, the chromatic convergence theorem reconstructs (X) from these approximations. A “layer” in a visualization is not an ordinary spatial layer or a frequency band in a signal.

**Notation hazard:** the Johnson–Wilson (E(n)) and the Lubin–Tate/Morava (E_n) are different constructions, even though their Bousfield classes at the same height agree in the usual context. The Lubin–Tate universal deformation ring for a height-(n) formal group over a suitable perfect field (k) is
[
W(k)[[u_1,ldots,u_{n-1}]].
]
Do not label either coefficient ring as the other without explanation.

References: [nLab Morava K-theory](https://ncatlab.org/nlab/show/Morava+K-theory), [Morava E-theory](https://ncatlab.org/nlab/show/Morava+E-theory), [chromatic tower](https://ncatlab.org/nlab/show/chromatic+tower), [Lubin–Tate theory](https://ncatlab.org/nlab/show/Lubin-Tate+theory).

## 4. A mathematical visualization with clear limits

An inspector can show for a chosen prime:
1. An editable *example family* of power-series coefficients truncated at degree (N).
2. The (p)-series, computed by **formal series arithmetic modulo (p)**.
3. A coefficient plot whose first nonzero degree identifies height **when the truncation is sufficiently long**.
4. A separate diagram of chromatic heights and homotopy coefficient periods.

**Invariants/tests:** formal identity, commutativity, associativity to the chosen truncation order; ([p]_{F_a}=0), ([p]_{F_m}=t^p), and period (2(p^n-1)). Coordinate changes may alter coefficients but must not change computed height.

**Avoid:** assigning (K(n)) a fabricated physical color, presenting supersingular curves as if “two holes” or “height 2” is their Euclidean dimension, or showing a single ordinary elliptic curve and calling it an entire generalized cohomology theory.
