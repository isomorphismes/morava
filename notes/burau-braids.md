# Three-strand braid → Burau matrix (a concrete starting point)

Source: **Jack Morava and Dale Rolfsen**, [*Toward the group completion of the Burau representation*](https://arxiv.org/abs/1809.01994) (published in *Transactions of the AMS* 376 (2023), 1845–1865).

The following is a standard elementary example of the **reduced Burau representation**, not a reconstruction of the authors' full TQFT or group completion.

## 1. Two kinds of states to show side by side

The braid group on three strands is
\[
B_3=\langle \sigma_1,\sigma_2\mid
  \sigma_1\sigma_2\sigma_1=\sigma_2\sigma_1\sigma_2\rangle.
\]
The generators exchange adjacent strands with a specified over/under crossing; inverses exchange them in the opposite direction. The positive-generator convention must be displayed in the drawing.

Let \(t\) be an *invertible* indeterminate. In one common basis for the reduced Burau representation,
\[
\rho(\sigma_1)=A=
  \begin{pmatrix}-t&1\\0&1\end{pmatrix},
\qquad
\rho(\sigma_2)=B=
  \begin{pmatrix}1&0\\t&-t\end{pmatrix}.
\]
The matrices live in \(GL_2(\mathbb{Z}[t,t^{-1}])\), so both have determinant \(-t\).

Multiplication checks the braid relation exactly:
\[
ABA=BAB=
\begin{pmatrix}
 0&-t\\-t^2&0
\end{pmatrix}.
\]
The drawing can show the same braid expressed with two words, while the algebra panel shows two equal Laurent-polynomial matrices. This is a **genuine mathematical equality**, not merely a visual similarity.

At \(t=1\),
\[
A=\begin{pmatrix}-1&1\\0&1\end{pmatrix},\quad
B=\begin{pmatrix}1&0\\1&-1\end{pmatrix},
\quad ABA=\begin{pmatrix}0&-1\\-1&0\end{pmatrix}.
\]
Choosing \(t=1\) throws away braid information; an interactive tool should also let \(t\) remain formal, rather than silently treating this specialization as faithful.

Matrix conventions vary with the choice of basis, whether braids act on the left or right, and which crossing is positive. Match the chosen drawing convention to the matrices and record it.

Cross-check for these matrix conventions: [*Discrete Representations of the Braid Groups*, §2.2.4](https://escholarship.org/uc/item/4vf3d9v1) and [a second description of reduced Burau matrices](https://go.owu.edu/~chjackso/Papers/thesis.pdf).

## 2. Screen behavior worth specifying

Three simultaneous views:
- Three colored strands; tapping a generator adds one explicit crossing, with under-strand occluded.
- A braid word with a visible cursor and inverse symbols.
- Its symbolic \(2\times2\) matrix, recomputed exactly from the word (or a small chosen numeric specialization).

Tap **σ₁**, **σ₂**, **σ₁⁻¹**, **σ₂⁻¹**. Each valid nontrivial edit must alter the displayed word **and** the braid picture; display the algebraic result even if a chosen representation loses information at a special value of \(t\). Support undo and application of the braid relation to a selected consecutive triple.

The rendering should carry its own visible response tests: event → changed braid word → changed geometry/matrix or an explicit reason why the mathematical object is equivalent. A successful event dispatch by itself is not evidence of user-visible change.

## 3. Mathematical test cases

- \(ABA=BAB\) as exact Laurent-polynomial matrices.
- \(AA^{-1}=I\) and \(BB^{-1}=I\).
- \(\det(\rho(\beta))=(-t)^{w(\beta)}\), where \(w\) is the exponent sum / writhe of the braid word.
- A braid relation should preserve its represented matrix and closed-braid isotopy class, although the *displayed word* changes.
- Do **not** infer equality of braids from equality of specialized numerical matrices.

This gives a bridge to the separate [swap](https://github.com/isomorphismes/swap) project if that repository's conventions and source model are compatible. Morava and Rolfsen's group-completion / TQFT construction is a later reading path, not a feature that follows just from drawing braids.
