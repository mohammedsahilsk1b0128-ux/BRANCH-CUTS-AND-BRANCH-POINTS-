# Contour Integrals in the Presence of Branch Points

**Added by:** Mohammed Sahil, 2026-10-02  
**Source:** Lecture notes, pages 8–16 (`Pg8-16.pdf`)

---

## 1. Contour Integration When Branch Points Are Present

**Statement:**

For a single-valued analytic function, contour integration can be handled using the usual Cauchy integral theorem and residue theorem. For a multivalued function, a contour that winds around a branch point may return to its starting point on a different Riemann sheet. In that case, the function does not return to its initial value, and the lifted path is not closed on the Riemann surface.

When applying contour integration to multivalued functions, adapt the contour so that the branch behaviour is handled explicitly.

Two strategies from the lecture are:

- If possible, choose a contour that avoids crossing branch cuts and encloses only one branch point.
- Alternatively, use a contour that encircles branch points and returns to the starting Riemann sheet, while explicitly accounting for the different values on the two sides of a branch cut.

**Derivation / justification (condensed):**

1. A branch point is a point around which analytic continuation can change the value of a multivalued function.
2. A loop in the complex plane may therefore fail to be a closed path on a single Riemann sheet.
3. The ordinary contour theorems require the function to be single-valued and analytic on the relevant region, apart from isolated poles in the residue-theorem setting.
4. Introduce a branch cut to make a chosen branch single-valued in the remaining domain.
5. Deform the contour around the cut. The contributions from the two banks of the cut must be evaluated using the limiting values from above and below.

**Worked example:**

For a function containing fractional powers such as
\[
f(z)=z^{1-\beta}(1-z)^\beta,
\]
the points \(z=0\) and \(z=1\) are branch points in general. A natural branch cut is the segment joining them, \(0\leq z\leq1\). A contour just above and below this segment lets us compare the two boundary values and calculate the discontinuity.

**Pitfalls / conditions to watch:**

- Do not apply the residue theorem directly as if a multivalued function were automatically single-valued.
- State the branch cut and the branch/argument convention.
- Keep track of contour orientation: the upper and lower banks are traversed in opposite directions.
- The value on the upper bank need not equal the value on the lower bank.

---

## 2. Discontinuity Across a Branch Cut

**Statement:**

For a branch cut along a real interval, define the discontinuity by
\[
\operatorname{disc}f(x)=f(x+i0)-f(x-i0),
\]
where \(f(x+i0)\) and \(f(x-i0)\) are the limiting values from above and below the cut.

For the multivalued factor
\[
g(z)=z^{1-\beta}(1-z)^\beta,\qquad 0<x<1,
\]
using arguments in the range \(0<\arg z<2\pi\) and \(0<\arg(z-1)<2\pi\), the boundary values are
\[
g(x+i0)=x^{1-\beta}(1-x)^\beta e^{i\pi\beta},
\]
\[
g(x-i0)=x^{1-\beta}(1-x)^\beta e^{-i\pi\beta}.
\]
Consequently,
\[
\boxed{\operatorname{disc}g(x)
=2i\sin(\pi\beta)\,x^{1-\beta}(1-x)^\beta.}
\]

If \(Q(z)\) is rational and has no poles on the interval \([0,1]\), then it is continuous across the cut, so the discontinuity of
\(f(z)=g(z)Q(z)\) is
\[
\boxed{\operatorname{disc}f(x)
=2i\sin(\pi\beta)\,x^{1-\beta}(1-x)^\beta Q(x).}
\]

**Derivation / justification (condensed):**

Write
\[
z=re^{i\theta},\qquad z-1=\rho e^{i\phi}.
\]
Then
\[
g(z)=r^{1-\beta}\rho^\beta
e^{i(1-\beta)\theta}e^{i\beta\phi}.
\]
As \(z\) approaches \(x\in(0,1)\), the arguments on the two sides of the cut give the phase factors \(e^{i\pi\beta}\) and \(e^{-i\pi\beta}\), respectively. Subtract:
\[
\begin{aligned}
\operatorname{disc}g(x)
&=x^{1-\beta}(1-x)^\beta
(e^{i\pi\beta}-e^{-i\pi\beta})\\
&=2i\sin(\pi\beta)x^{1-\beta}(1-x)^\beta.
\end{aligned}
\]
Multiplying by \(Q(x)\), which has the same limiting value on both sides, gives the result for \(f\).

**Worked example:**

For
\[
f(z)=z^{1-\beta}(1-z)^\beta Q(z),
\]
the upper-minus-lower discontinuity is
\[
\operatorname{disc}f(x)
=2i\sin(\pi\beta)x^{1-\beta}(1-x)^\beta Q(x).
\]
In the keyhole/rectangular contour around the cut, the two straight-bank integrals combine with a minus sign because they have opposite orientations. Thus, in the limiting contour,
\[
\oint_\Gamma f(z)\,dz
=-\int_0^1\operatorname{disc}f(x)\,dx,
\]
provided the small end pieces vanish and the contour is oriented as in the lecture.

**Pitfalls / conditions to watch:**

- The discontinuity convention here is upper value minus lower value. Some texts use the opposite convention.
- The sign in the final contour integral also depends on orientation.
- Do not include a factor \(Q\) in the phase calculation if it is single-valued and continuous across the cut; evaluate it simply as \(Q(x)\).
- The argument ranges must be used consistently.

---

## 3. Contour Formula for an Integral on \([0,1]\)

**Statement:**

For \(0<\beta<1\), and a rational function \(Q(z)\) with no poles on \(0\leq z\leq1\), the lecture obtains
\[
\boxed{
\int_0^1 x^{1-\beta}(1-x)^\beta Q(x)\,dx
=
\frac{1}{-2i\sin(\pi\beta)}
\oint_\Gamma z^{1-\beta}(z-1)^\beta Q(z)\,dz
}
\]
for the contour \(\Gamma\) surrounding the branch cut from \(0\) to \(1\), with the branch and orientation chosen as in the notes. Equivalently, the sign can be tracked by writing the contour integral as minus the integral of the upper-minus-lower discontinuity.

**Derivation / justification (condensed):**

1. The factors \(z^{1-\beta}\) and \((z-1)^\beta\) have branch points at \(0\) and \(1\).
2. Choose the segment \([0,1]\) as the branch cut and take a thin rectangular contour around it.
3. Split the contour into its four sides. As the rectangle becomes thin, the short vertical sides vanish under the stated endpoint conditions.
4. The upper and lower horizontal sides approach the two banks of the cut and are oppositely oriented.
5. Their difference is the discontinuity calculated in Result 2:
   \[
   2i\sin(\pi\beta)x^{1-\beta}(1-x)^\beta Q(x).
   \]
6. With the orientation used in the notes, the contour integral is the negative of the integral of this discontinuity. Rearranging gives the displayed formula.

**Worked example:**

Take \(Q(z)=1\). Then the branch-cut contour relates the contour integral of
\(z^{1-\beta}(z-1)^\beta\) to
\[
\int_0^1x^{1-\beta}(1-x)^\beta\,dx.
\]
The point of the method is that the real integral is recovered from the jump of the multivalued function across its branch cut.

**Pitfalls / conditions to watch:**

- The formula depends on the branch convention and contour orientation stated above.
- Endpoint contributions must vanish; this is ensured for the relevant powers when \(0<\beta<1\).
- \(Q\) must not have poles on the cut.
- Check whether the contour integral in a particular problem is written using \((z-1)^\beta\) or \((1-z)^\beta\); their phases differ.

---

## 4. Keyhole Contour Evaluation of a Standard Improper Integral

**Statement:**

For
\[
0<\beta<1,
\]
the improper integral
\[
I=\int_0^\infty\frac{x^{\beta-1}}{1+x}\,dx
\]
has the value
\[
\boxed{I=\frac{\pi}{\sin(\pi\beta)}.}
\]

**Derivation / justification (condensed):**

Consider
\[
f(z)=\frac{z^{\beta-1}}{1+z}.
\]
The factor \(z^{\beta-1}\) is multivalued, with branch points at \(0\) and \(\infty\). Choose the principal branch \(0\leq\arg z<2\pi\), with the positive real axis as the branch cut. Use a keyhole contour consisting of:

- the upper bank of the positive real axis, from a small radius to a large radius;
- a large circle of radius \(R\);
- the lower bank, returning towards the origin;
- a small circle of radius \(\varepsilon\) around the origin.

The only pole inside the contour is the simple pole at \(z=-1\). Its residue is
\[
\operatorname{Res}_{z=-1}\frac{z^{\beta-1}}{1+z}
=(-1)^{\beta-1}
=e^{i\pi(\beta-1)}
=-e^{i\pi\beta},
\]
using the chosen argument \(\arg(-1)=\pi\).

The upper-bank contribution tends to \(I\). On the lower bank, the argument has increased by \(2\pi\), so the factor \(z^{\beta-1}\) acquires the multiplier \(e^{2\pi i(\beta-1)}=e^{2\pi i\beta}\), and the orientation is reversed. Thus the two straight portions contribute
\[
(1-e^{2\pi i\beta})I.
\]

The large-circle contribution vanishes as \(R\to\infty\), because the integrand is of order \(R^{\beta-2}\) and the arc length is of order \(R\), giving order \(R^{\beta-1}\to0\) when \(\beta<1\).

The small-circle contribution vanishes as \(\varepsilon\to0\), because it is of order \(\varepsilon^\beta\to0\) when \(\beta>0\).

By the residue theorem,
\[
(1-e^{2\pi i\beta})I
=2\pi i(-e^{i\pi\beta}).
\]
Therefore
\[
I=\frac{-2\pi i e^{i\pi\beta}}{1-e^{2\pi i\beta}}
=\frac{\pi}{\sin(\pi\beta)}.
\]

**Worked example:**

For \(\beta=\tfrac12\),
\[
I=\int_0^\infty\frac{x^{-1/2}}{1+x}\,dx
=\frac{\pi}{\sin(\pi/2)}
=\boxed{\pi}.
\]

**Pitfalls / conditions to watch:**

- Both conditions \(0<\beta<1\) are needed: \(\beta>0\) controls convergence near zero, and \(\beta<1\) controls convergence at infinity.
- The lower bank has the opposite orientation to the upper bank.
- The phase multiplier on the lower bank depends on the branch choice.
- The large and small circular arcs must be shown to vanish; they cannot simply be discarded.
- The pole at \(z=-1\) is a simple pole and must be included in the residue sum.

---

## 5. Evaluation of an Integral with Two Square-Root Branch Points

**Statement:**

For real \(a<b\),
\[
\boxed{
\int_a^b\frac{dx}{\sqrt{(b-x)(x-a)}}=\pi.
}
\]

The integrand can be represented by the multivalued complex function
\[
f(z)=(z-a)^{-1/2}(z-b)^{-1/2},
\]
which has branch points at \(z=a\) and \(z=b\). Choose the segment \([a,b]\) as the branch cut.

**Derivation / justification (condensed):**

Use a contour that surrounds the branch cut \([a,b]\). On the two banks of the cut, the square-root factors have different phases.

For \(a<x<b\), the magnitudes of the two factors give
\[
|f(x)|=\frac{1}{\sqrt{(x-a)(b-x)}}.
\]
With the branch convention in the notes, the phases on the two sides differ by a factor that makes the difference of the boundary values equal to
\[
f(x+i0)-f(x-i0)
=-2i\,|f(x)|.
\]
Because the banks are oppositely oriented, their combined contribution is
\[
2i\int_a^b\frac{dx}{\sqrt{(b-x)(x-a)}}=2iI.
\]

The contour can be expanded to a large circle. At infinity,
\[
f(z)=(z-a)^{-1/2}(z-b)^{-1/2}
\sim \frac{1}{z}.
\]
Hence the large-circle integral tends to
\[
\int_0^{2\pi} i\,d\theta=2\pi i.
\]
Equating the two contour evaluations gives
\[
2iI=2\pi i
\quad\Longrightarrow\quad
\boxed{I=\pi}.
\]

**Worked example:**

Choose \(a=0\) and \(b=4\):
\[
\int_0^4\frac{dx}{\sqrt{(4-x)x}}=\pi.
\]
The result is independent of the interval length: changing \(a\) and \(b\) does not change the value, provided \(a<b\).

**Pitfalls / conditions to watch:**

- The branch points are at both endpoints \(a\) and \(b\).
- The branch cut is the interval joining the two branch points.
- The phase on each bank must be evaluated using the chosen branch. The sign of the discontinuity depends on which bank is subtracted from which.
- Small detours around the branch points must vanish in the limiting process.
- At infinity, \(f(z)\sim1/z\), so the large-circle integral does not vanish; it tends to \(2\pi i\).

---

## Quick Reference

| Topic | Key result |
|---|---|
| Discontinuity across the cut | \(\operatorname{disc}g(x)=2i\sin(\pi\beta)x^{1-\beta}(1-x)^\beta\) |
| Standard improper integral | \(\displaystyle\int_0^\infty\frac{x^{\beta-1}}{1+x}\,dx=\frac{\pi}{\sin(\pi\beta)},\quad 0<\beta<1\) |
| Two square-root branch points | \(\displaystyle\int_a^b\frac{dx}{\sqrt{(b-x)(x-a)}}=\pi,\quad a<b\) |

## General Checklist for These Problems

- [ ] Identify all branch points.
- [ ] Choose and state a branch cut.
- [ ] State the argument range for each multivalued factor.
- [ ] Draw or describe the contour and its orientation.
- [ ] Calculate the upper and lower boundary values on the cut.
- [ ] Form the discontinuity with a clearly stated convention.
- [ ] Check whether the small-circle and large-circle contributions vanish or survive.
- [ ] Apply Cauchy's theorem or the residue theorem only after accounting for branch behaviour.
- [ ] Check convergence conditions at all endpoints and at infinity.
