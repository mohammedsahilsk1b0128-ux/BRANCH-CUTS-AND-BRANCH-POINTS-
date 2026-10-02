# Branch Points & Branch Cuts

Detailed, mathematical notes on multivalued analytic functions: monodromy, Riemann surfaces, types of branch points, cut structure, discontinuities, and contour integration.

**Contents**
1. Multivalued functions and analytic continuation
2. Worked model: $z^{1/2}$ and its Riemann surface
3. Formal definitions and monodromy
4. Choice of cut and discontinuity
5. Classification of branch points
6. Several branch points: the general rule $(z-a)^\alpha (z-b)^\beta$
7. Explicit square-root functions and uniformization
8. Logarithmic cuts and standard discontinuities
9. Same point, different sheets: $\ln(1-z)/z$
10. Contour integration with cuts
11. Contour integral representations (Gamma, Legendre)
12. Table of standard functions
13. Exercises

---

## 1. Multivalued functions and analytic continuation

An analytic function $f(z)=w$ is a map $f:\ R\subset\hat{\mathbb C}\to R'\subset\hat{\mathbb C}$. It is **single-valued** if each $z$ gives exactly one $w$.

Many familiar maps are *many-to-one*:

| Function | Many-to-one behaviour |
|---|---|
| $z^N$ | $z e^{2\pi i j/N}\ (j=1,\dots,N)\mapsto$ same value |
| $e^{z}$ | $z+2\pi i n\mapsto$ same value |
| $\cos z,\ \sin z$ | periodic with period $2\pi$ |

Their **inverses** are *one-to-many*. These are the **multivalued functions**: $z^{1/N},\ \ln z,\ \arcsin z,\dots$

**Analytic continuation along a path.** Let $f_0$ be an analytic function element near $z_0$. Continuing $f_0$ analytically along a path $\gamma$ gives a function element $f_\gamma$ at the endpoint. If $\gamma$ is a **closed** loop, $f_\gamma$ need not equal $f_0$. This failure of a closed loop to return the same value is the origin of multivaluedness.

---

## 2. Worked model: $f(z)=z^{1/2}$

Write $z=re^{i\theta}$, so
$$
f(z)=r^{1/2}e^{i\theta/2}.
$$

- For $0\le\theta<2\pi$: $0\le\arg w<\pi$. **The whole $z$-plane is mapped onto the upper half $w$-plane only.**
- For $2\pi\le\theta<4\pi$: $f=r^{1/2}e^{i\theta/2}=e^{i\pi}\,r^{1/2}e^{i(\theta-2\pi)/2}=-\sqrt z$, which covers the lower half $w$-plane.

To cover the full $w$-plane, $\theta$ must range over $[0,4\pi)$, so the $z$-plane has to be covered **twice**. The two values $\pm\sqrt z$ are the two **branches** $f_I=+\sqrt z$ and $f_{II}=-\sqrt z$, with
$$
f_{II}(z)=-f_I(z).
$$

**Riemann surface.** Take two copies of the $z$-plane (sheets I, II), each slit along $[0,\infty)$. Glue the lower lip of the slit on I to the upper lip of the slit on II, and the lower lip of II to the upper lip of I. A path that encircles $0$ once in the positive sense passes from I to II, and going around again returns to I.

- On the plane, $z^{1/2}$ is **double-valued**.
- On the two-sheeted Riemann surface, $z^{1/2}$ is **single-valued**.
- Sheet I ($0\le\theta<2\pi$) is the **principal sheet**.

At $z=0$ and $z=\infty$, $f_I=f_{II}$ (both $=0$, respectively $=\infty$), so the sheets meet there. Since $\hat{\mathbb C}$ has only one point at infinity, these two points are the branch points, and the cut joins them.

---

## 3. Formal definitions and monodromy

Let $\gamma_{z_0}$ be a small positively oriented circle around $z_0$ that encloses no other singular point, and let $f_{\gamma}$ be the continuation of $f$ once around it.

> **Branch point.** $z_0$ is a branch point of $f$ if $f_{\gamma_{z_0}}\ne f$ (the function does not return to itself after one loop).
>
> **Monodromy.** The operation $f\mapsto f_{\gamma_{z_0}}$ is the monodromy of $f$ at $z_0$.
>
> **Order.** $z_0$ is an algebraic branch point of order $q$ if the loop must be traversed $q$ times to return to $f$, i.e. $(f_{\gamma})_{\gamma}\cdots =f$ after $q$ loops, not before.

**Local form (Puiseux expansion).** Near an algebraic branch point of order $q$,
$$
f(z)=\sum_{k\ge k_0} c_k\,(z-z_0)^{k/q},
$$
a power series in $(z-z_0)^{1/q}$. Under one loop, $(z-z_0)^{1/q}\to e^{2\pi i/q}(z-z_0)^{1/q}$.

**Facts.**
1. A closed loop around exactly **one** branch point does not return $f$ to its original value. On the Riemann surface the path is not closed: it ends on a different sheet.
2. A loop around **no** branch point leaves $f$ unchanged. Example: a small circle around $z=2$ for $z^{1/2}$. Here $\arg z$ increases to a maximum and decreases back to its starting value without winding, so $f$ returns to itself and $z=2$ is **not** a branch point.
3. **A function cannot have exactly one branch point.** A branch cut joins two branch points, so the minimum is two (counting $\infty$).
4. To obtain a truly closed contour you must encircle branch points as many times as needed to return to the **starting sheet**.

---

## 4. Choice of cut and discontinuity

The cut can run along **any curve** joining the branch points, and approaching $z=0$ from any direction is allowed. For $z^{1/2}$ the positive real axis is the usual choice because it is simplest. What matters is that the **phase just above and just below the cut is specified**, so that the jump can be computed. The choice of cut also fixes the range of the argument.

**Cut on $[0,\infty)$, with $0\le\theta<2\pi$ (sheet I):**

| Location | $\theta$ | $\arg\sqrt z$ |
|---|---|---|
| just above positive real axis | $0$ | $0$ |
| negative real axis | $\pi$ | $\pi/2$ |
| just below positive real axis | $2\pi$ | $\pi$ |

**Continuity across the cut** (this is the gluing rule):
$$
\lim_{\epsilon\to0}f_I(x-i\epsilon)=\lim_{\epsilon\to0}f_{II}(x+i\epsilon),\qquad x>0 .
$$

**Discontinuity** (jump across the cut):
$$
\operatorname{disc}f(x)\;\overset{\text{def}}{=}\;\lim_{\epsilon\to0}\big[f_I(x+i\epsilon)-f_I(x-i\epsilon)\big]
=\lim_{\epsilon\to0}\big[f_I(x+i\epsilon)-f_{II}(x+i\epsilon)\big]
=\sqrt x-(-\sqrt x)=2\sqrt x .
$$

**General power.** For $f=z^\alpha$ with cut on $[0,\infty)$ and $0\le\theta<2\pi$: above $f=x^\alpha$, below $f=x^\alpha e^{2\pi i\alpha}$, so
$$
\operatorname{disc}z^\alpha=x^\alpha\big(1-e^{2\pi i\alpha}\big).
$$
Check: $\alpha=\tfrac12$ gives $x^{1/2}(1-e^{i\pi})=2\sqrt x$ ✓.

**Different cut, different phases.** If the cut is instead taken along the positive imaginary axis ($\tfrac\pi2\le\theta<\tfrac{5\pi}{2}$), then $\arg\sqrt z=\pi/4$ just to the left of the axis and $5\pi/4$ just to the right, and the jump is across the imaginary axis. *(Exercise: compute the discontinuity there.)*

---

## 5. Classification of branch points

Consider $f(z)=z^{\alpha}$ and $f(z)=\ln z$, with branch points at $z=0,\infty$. After $n$ positive loops around the origin:
$$
z^\alpha\to e^{2\pi i n\alpha}z^\alpha,\qquad \ln z\to\ln z+2\pi i n .
$$

### (i) Algebraic branch point — $f=z^{p/q}$
$p,q\in\mathbb Z$, coprime, $p\ne0$, $q>0$.

- Monodromy factor per loop: $e^{2\pi i p/q}$, which is a primitive $q$-th root of unity.
- It returns to $1$ only after $q$ loops, so the Riemann surface has exactly **$q$ sheets**.
- Crossing the cut moves you one sheet down. Crossing it on the lowest sheet takes you back to the top.
- $z^{1/2}$: 2 sheets. $z^{1/3}$: 3 sheets, since each turn shifts the phase by $2\pi/3$ and $\theta\in[0,6\pi)$ is needed to cover the $w$-plane.
- $z^N$ ($N\in\mathbb Z$) has **no** branch point.

### (ii) Winding point — $f=z^{\alpha}$, $\alpha$ irrational (or non-rational in general)
- $e^{2\pi i n\alpha}\ne1$ for every integer $n\ne0$, so we **never** return to the top sheet.
- The Riemann surface has **infinitely many sheets**, labelled by $n\in\mathbb Z$.
- On sheet $n$, $\theta$ ranges over $2\pi n\le\theta<2\pi(n+1)$ (principal sheet: $n=0$).

### (iii) Logarithmic branch point — $f=\ln z$
- Branch points at $z=0,\infty$, infinitely many sheets.
- On sheet $n$:
$$
\ln z=\ln r+i\theta+2\pi n i,\qquad 0\le\theta<2\pi,\ n\in\mathbb Z .
$$
- $\ln1=0$ **only on the principal sheet**; on sheet $n$, $\ln1=2\pi n i$.

**Summary of sheet counts**

| Type | Example | Sheets | Monodromy |
|---|---|---|---|
| Algebraic | $z^{p/q}$ | $q$ | multiplication by $e^{2\pi i p/q}$ |
| Winding | $z^{\alpha}$ | $\infty$ | multiplication by $e^{2\pi i\alpha}$ |
| Logarithmic | $\ln z$ | $\infty$ | addition of $2\pi i$ |

---

## 6. Several branch points: the rule for $(z-a)^\alpha(z-b)^\beta$

Take $f(z)=(z-a)^{\alpha}(z-b)^{\beta}$ with $a\ne b$ finite.

**Monodromy** (positive loop):

| Loop encircles | Factor |
|---|---|
| $a$ only | $e^{2\pi i\alpha}$ |
| $b$ only | $e^{2\pi i\beta}$ |
| $a$ and $b$ (large circle) | $e^{2\pi i(\alpha+\beta)}$ |

**Behaviour at infinity.** For large $|z|$, $f\sim z^{\alpha+\beta}$. Therefore:

$$
\boxed{\ z=\infty\ \text{is a branch point}\iff \alpha+\beta\notin\mathbb Z\ }
$$

(and $a$ is a branch point iff $\alpha\notin\mathbb Z$, $b$ iff $\beta\notin\mathbb Z$).

**Consequence for the cut.** If $\infty$ is *not* a branch point, the cut can be chosen as the **finite segment $[a,b]$**, since going around both $a$ and $b$ (a big loop) returns $f$ to itself. If $\infty$ is a branch point, the cut must run out to $\infty$.

| $f(z)$ | $\alpha+\beta$ | Branch points | Cut |
|---|---|---|---|
| $\dfrac{(z-a)^{1/2}}{(z-b)^{1/2}}$ | $0$ | $a,b$ | $[a,b]$ |
| $(z-a)^{1/2}(z-b)^{1/2}$ | $1$ | $a,b$ | $[a,b]$ |
| $\dfrac{(z-a)^{\alpha}}{(z-b)^{\alpha}}$, $\alpha\notin\mathbb Z$ | $0$ | $a,b$ | $[a,b]$ |
| $(z-a)^{\alpha}(z-b)^{\alpha}$, $2\alpha\notin\mathbb Z$ | $2\alpha$ | $a,b,\infty$ | runs to $\infty$ |

So for the product with equal exponents the cut is finite only when $2\alpha\in\mathbb Z$, which for non-integer $\alpha$ means $\alpha$ is a half-odd-integer.

**Regularity at $\infty$:**
- $\dfrac{(z-a)^{1/2}}{(z-b)^{1/2}}\to1$, so $\infty$ is regular.
- $(z-a)^{1/2}(z-b)^{1/2}\sim z$, so $\infty$ is not a branch point ($f$ is single-valued there, behaving like $z$).
- A generic $\alpha$ gives $z^{2\alpha}$, which is multivalued at $\infty$.

---

## 7. Explicit square-root function and uniformization

### 7.1 Phases for $f(z)=(z-a)^{1/2}(z-b)^{1/2}$, cut on $[a,b]$
The phases of the two factors **add**. Let $M=\sqrt{|z-a|\,|z-b|}$ and take $a<b$ real:

| Region on real axis | $\arg(z-a)^{1/2}$ | $\arg(z-b)^{1/2}$ | $\arg f$ | $f$ |
|---|---|---|---|---|
| $x>b$ | $0$ | $0$ | $0$ | $+M$ |
| $a<x<b$, just above | $0$ | $\pi/2$ | $\pi/2$ | $+iM$ |
| $a<x<b$, just below | $0$ | $3\pi/2$ | $3\pi/2$ | $-iM$ |
| $x<a$ | $\pi/2$ | $\pi/2$ | $\pi$ | $-M$ |

There is no jump to the right of $b$ or to the left of $a$, only across $(a,b)$:
$$
\operatorname{disc}f=2iM=2i\sqrt{(x-a)(b-x)},\qquad a<x<b .
$$

For the **ratio** $(z-a)^{1/2}/(z-b)^{1/2}$ the phases **subtract**. The jump is again only on $[a,b]$, and the square-root behaviour cancels for $x>b$ and $x<a$.

> More generally, for any non-integer $\alpha$, the argument of $(z-a)^\alpha/(z-b)^\alpha$ jumps only across $[a,b]$.
> The behaviour for $(z-a)^\alpha(z-b)^\alpha$ at $\alpha=\tfrac12$ (cut $[a,b]$) does **not** extend to other $\alpha$, because it relies on the accident $f\sim z^{2\alpha}=z$ being single-valued at $\infty$.

### 7.2 Uniformization (making the function single-valued)

For $z^{1/2}$ put $z=w^2$. Then $f=w$ is single-valued in the $w$-plane, and $w\mapsto -w$ exchanges the two sheets. **The Riemann surface of $z^{1/2}$ is the $w$-plane itself.**

For $\sqrt{(z-a)(z-b)}$ use the Joukowski-type map. Let $m=\tfrac{a+b}{2}$, $h=\tfrac{b-a}{2}$, and
$$
z=m+\frac h2\Big(u+\frac1u\Big).
$$
Then
$$
(z-a)(z-b)=(z-m)^2-h^2=\frac{h^2}{4}\Big(u-\frac1u\Big)^2
\quad\Longrightarrow\quad
\sqrt{(z-a)(z-b)}=\frac h2\Big(u-\frac1u\Big).
$$
This is single-valued in $u$. The unit circle $|u|=1$ maps onto the cut $[a,b]$ (traversed twice, once from each lip), and the two sheets correspond to $|u|>1$ and $|u|<1$. So the Riemann surface is a sphere (genus $0$).

*Remark.* For $y^2=\prod_{j=1}^{2g+2}(z-z_j)$ the Riemann surface has genus $g$, by the Riemann–Hurwitz formula $2-2g=2\cdot2-(2g+2)$. Four branch points give $g=1$ (a torus, elliptic functions).

---

## 8. Logarithmic cuts and standard discontinuities

**Cut on $[0,\infty)$, $0\le\theta<2\pi$:** above the cut $\ln z=\ln x$, below it $\ln z=\ln x+2\pi i$, so
$$
\operatorname{disc}\ln z=-2\pi i\qquad(x>0).
$$

**Principal logarithm $\operatorname{Ln}z$** (cut on $(-\infty,0]$, $-\pi<\theta\le\pi$): above the negative axis $\operatorname{Ln}x=\ln|x|+i\pi$, below it $\ln|x|-i\pi$, so
$$
\operatorname{disc}\operatorname{Ln}z=+2\pi i\qquad(x<0).
$$

**Two logarithmic branch points joined by a finite cut.**
$$
\ln\frac{z-a}{z-b}\quad\text{has branch points }a,b,\ \text{cut }[a,b],\ \text{and is regular at }\infty\ (\to0).
$$
The monodromy is $\pm2\pi i$ (loop around $a$ alone gives $+2\pi i$, around $b$ alone gives $-2\pi i$, around both gives $0$, which is why $\infty$ is regular).

**Example: the Legendre function of the second kind, $n=0$.**
$$
Q_0(z)=\tfrac12\ln\frac{z+1}{z-1},\qquad\text{cut }[-1,1].
$$
For $-1<x<1$ (principal arguments in $(-\pi,\pi)$): above, $\arg(z-1)=\pi$, so $Q_0=\tfrac12\ln\frac{1+x}{1-x}-\tfrac{i\pi}2$. Below, $\arg(z-1)=-\pi$, so $Q_0=\tfrac12\ln\frac{1+x}{1-x}+\tfrac{i\pi}2$. Hence
$$
\operatorname{disc}Q_0(x)=-i\pi,\qquad-1<x<1 .
$$

**Cut for $\ln(1-z)$ (principal branch):** branch points at $z=1,\infty$, cut $[1,\infty)$. For $x>1$ above the axis $1-z=(1-x)-i\epsilon$ has argument $-\pi$, below it $+\pi$, so $\operatorname{disc}\ln(1-z)=-2\pi i$.

---

## 9. Same point, different sheets: $f(z)=\dfrac{\ln(1-z)}{z}$

- Logarithmic branch points at $z=1$ and $z=\infty$.
- **Principal sheet** ($\ln1=0$): near $z=0$,
$$
\ln(1-z)=-z-\tfrac{z^2}{2}-\cdots\ \Rightarrow\ f(z)=-1-\tfrac z2-\cdots,
$$
so the simple pole of $1/z$ is cancelled by the simple zero of $\ln(1-z)$. $z=0$ is only a **removable** singularity.
- **Sheet $n\ne0$:** $\ln(1-z)=2\pi n i+\ln(1-z)\big|_{\rm principal}$, so $\ln(1-z)\to2\pi ni\ne0$ at $z=0$ and
$$
f(z)\sim\frac{2\pi n i}{z},
$$
a **simple pole with residue $2\pi n i$** at $z=0$.

> The nature of a singularity can depend on the sheet.

---

## 10. Contour integration in the presence of branch cuts

Cauchy's theorem and the residue theorem require a **closed** contour on the Riemann surface. A path that goes around a branch point once ends on another sheet, so it is **not** closed. There are three strategies:

1. **Avoid crossing the cut.** Use contours that enclose at most one branch point and do not cross the cut.
2. **Enclose several branch points, or the same one several times,** until $f$ returns to its starting value.
3. **Hug the cut** with a hairpin/keyhole contour and express the integral through $\operatorname{disc}f$.

### 10.1 Integral around a finite cut
**Claim.** $\displaystyle\int_a^b\frac{dx}{\sqrt{(x-a)(b-x)}}=\pi$, independent of $a,b$.

Let $F(z)=\big[(z-a)(z-b)\big]^{-1/2}$, with cut $[a,b]$ and $F\sim1/z$ at $\infty$.

- Large circle: $\oint_{|z|=R}F\,dz\to2\pi i$ (because $F\sim1/z$).
- By Cauchy, this equals the integral on a contour hugging the cut. From §7.1, $F(x+i0)=\dfrac{1}{iM}=-\dfrac iM$ and $F(x-i0)=+\dfrac iM$, where $M=\sqrt{(x-a)(b-x)}$.
- Going counter-clockwise (below the cut from $a$ to $b$, above it from $b$ to $a$):
$$
\oint F\,dz=\int_a^b\frac iM\,dx-\int_a^b\Big(-\frac iM\Big)dx=2i\int_a^b\frac{dx}{M}.
$$
Setting $2i\int_a^b dx/M=2\pi i$ gives $\displaystyle\int_a^b\frac{dx}{M}=\pi$ ✓ (also checked by $x=m+h\cos\varphi$, giving $\int_0^\pi d\varphi=\pi$).

### 10.2 Rational integrals via $\ln z$ (hairpin/keyhole trick)
**Problem.** $I=\displaystyle\int_0^\infty\frac{p(x)}{q(x)}\,dx$ where
(i) $\deg q\ge\deg p+2$ (so the integrand decays at least like $1/x^2$), and (ii) $q$ has no zeros on $x\ge0$.

**Method.** Use the cut of $\ln z$ along $[0,\infty)$ with $0<\arg z<2\pi$. Above the cut $\ln z=\ln x$, below it $\ln z=\ln x+2\pi i$. Integrate $p(z)\ln z/q(z)$ over the keyhole contour (above the axis out to $R$, big circle counter-clockwise, back below the axis, small circle clockwise). The arcs vanish (the integrand is $O(\ln R/R)$ on the big circle). Then
$$
\oint\frac{p\ln z}{q}\,dz=\int_0^\infty\frac{p\ln x}{q}dx-\int_0^\infty\frac{p(\ln x+2\pi i)}{q}dx=-2\pi i\,I .
$$
By the residue theorem the left side is $2\pi i\sum\operatorname{Res}$, hence
$$
\boxed{\ I=-\sum_{\text{poles of }q}\operatorname{Res}\Big[\frac{p(z)\ln z}{q(z)}\Big]\ ,\qquad 0<\arg z<2\pi\ }
$$

**Check:** $I=\int_0^\infty\frac{dx}{x^2+1}$. Poles at $z=i$ ($\ln i=\tfrac{i\pi}2$) and $z=-i$ ($\ln(-i)=\tfrac{3i\pi}2$):
$$
\operatorname{Res}_{i}=\frac{i\pi/2}{2i}=\frac\pi4,\qquad
\operatorname{Res}_{-i}=\frac{3i\pi/2}{-2i}=-\frac{3\pi}4,
\qquad
I=-\Big(\frac\pi4-\frac{3\pi}4\Big)=\frac\pi2\ \checkmark
$$

### 10.3 Keyhole for fractional powers
**Claim.** For $0<s<1$,
$$
\int_0^\infty\frac{x^{s-1}}{1+x}\,dx=\frac{\pi}{\sin\pi s}.
$$
Take $f(z)=\dfrac{z^{s-1}}{1+z}$, cut on $[0,\infty)$, $0<\arg z<2\pi$.

- Above the cut: $f=\dfrac{x^{s-1}}{1+x}$. Below the cut: $f=\dfrac{e^{2\pi i(s-1)}x^{s-1}}{1+x}=\dfrac{e^{2\pi is}x^{s-1}}{1+x}$.
- Arcs: the big arc is $O(R^{s-1})\to0$ and the small arc is $O(\epsilon^{s})\to0$ for $0<s<1$.
- Keyhole contour: $\oint f\,dz=(1-e^{2\pi is})\,J$, where $J$ is the desired integral.
- Residue at $z=-1=e^{i\pi}$: $(e^{i\pi})^{s-1}=-e^{i\pi s}$, so $\oint f\,dz=2\pi i\,(-e^{i\pi s})$.

$$
J=\frac{-2\pi i\,e^{i\pi s}}{1-e^{2\pi is}}=\frac{-2\pi i}{e^{-i\pi s}-e^{i\pi s}}=\frac{-2\pi i}{-2i\sin\pi s}=\frac\pi{\sin\pi s}\ \checkmark
$$

**Corollary.** Putting $u=x^n$,
$$
\int_0^\infty\frac{dx}{x^n+1}=\frac\pi n\csc\frac\pi n\qquad(n=2,3,\dots).
$$

### 10.4 Rectangular contour around the cut $[0,1]$
For $0<p<1$ and $Q(z)$ rational with no poles on $[0,1]$, let $f(z)=z^{1-p}(1-z)^{p}Q(z)$ with branch points $z=0,1$ and cut $[0,1]$. Take a thin rectangle $\Gamma$ (height $\pm\epsilon$) around the cut. The vertical sides vanish as $\epsilon\to0$, so
$$
\oint_\Gamma f\,dz=\int_0^1\big[f(x-i\epsilon)-f(x+i\epsilon)\big]dx=-\int_0^1\operatorname{disc}f(x)\,dx .
$$
Because the two lips differ only by a phase factor, $\operatorname{disc}f$ is a constant multiple of $x^{1-p}(1-x)^pQ(x)$. This converts the contour integral into the real integral $\int_0^1x^{1-p}(1-x)^pQ(x)\,dx$, up to a factor of the form $1/\sin\pi p$.

---

## 11. Contour integral representations

### 11.1 Gamma function (Hankel-type contour)
For $\operatorname{Re}z>0$: $\Gamma(z)=\int_0^\infty t^{z-1}e^{-t}\,dt$.

The factor $t^{z-1}$ has branch points at $t=0,\infty$, with the cut on the positive $t$-axis. Its phase is $0$ just above the cut and $2\pi z$ just below (since $e^{-2\pi i}=1$).

Let $C$ come in from $\infty$ to $\epsilon$ just **below** the cut, circle the origin in the **negative** sense, and run out from $\epsilon$ to $\infty$ just **above** the cut. Then for $\operatorname{Re}z>0$ the small arc vanishes and
$$
\int_C t^{z-1}e^{-t}\,dt=\underbrace{-e^{2\pi iz}\Gamma(z)}_{\text{lower lip, }\infty\to0}+\underbrace{\Gamma(z)}_{\text{upper lip, }0\to\infty}=(1-e^{2\pi iz})\,\Gamma(z).
$$
Since $C$ avoids $t=0$ it can be deformed away from the origin, so the contour integral is defined for **all finite $z$**. Hence
$$
\boxed{\ \Gamma(z)=\frac{1}{1-e^{2\pi iz}}\int_C t^{z-1}e^{-t}\,dt\qquad\text{for all }z\ }
$$
This is a **meromorphic** function of $z$ on the whole plane. The factor $1/(1-e^{2\pi iz})$ has simple poles at every integer. At $z=1,2,3,\dots$ the contour integral vanishes (the integrand is single-valued, so the two lips cancel), leaving finite values; at $z=0,-1,-2,\dots$ the poles survive, giving the known poles of $\Gamma$.

*Note.* $C$ may be straightened, but both ends must go to $\operatorname{Re}t\to+\infty$ so that $e^{-t}$ ensures convergence. We cannot close the contour with a large circle here.

### 11.2 Legendre functions $P_\nu(z)$, $Q_\nu(z)$
For non-integer $\nu$, $P_\nu(z)$ is no longer a polynomial.

- $P_\nu(z)$: branch points at $z=-1$ and $\infty$; by convention the cut runs from $-1$ to $-\infty$ along the real axis.
- $Q_\nu(z)$: branch points at $z=1,-1,\infty$; by convention the cut runs from $1$ through $-1$ to $-\infty$.
- For $\nu=n$ an integer, $P_n$ is a polynomial (no cut) and $Q_n(z)$ has logarithmic branch points at $\pm1$, with the cut $[-1,1]$ (see §8 for $Q_0$).

---

## 12. Reference table

| Function | Branch points | Typical cut | Sheets | $\operatorname{disc}$ across cut |
|---|---|---|---|---|
| $z^{1/2}$ | $0,\infty$ | $[0,\infty)$ | 2 | $2\sqrt x$ |
| $z^{1/3}$ | $0,\infty$ | $[0,\infty)$ | 3 | $x^{1/3}\big(1-e^{2\pi i/3}\big)$ |
| $z^{p/q}$ | $0,\infty$ | $[0,\infty)$ | $q$ | $x^{p/q}\big(1-e^{2\pi ip/q}\big)$ |
| $z^\alpha$, $\alpha$ irrational | $0,\infty$ | $[0,\infty)$ | $\infty$ | $x^{\alpha}\big(1-e^{2\pi i\alpha}\big)$ |
| $\ln z$ ($0\le\theta<2\pi$) | $0,\infty$ | $[0,\infty)$ | $\infty$ | $-2\pi i$ |
| $\operatorname{Ln}z$ (principal) | $0,\infty$ | $(-\infty,0]$ | $\infty$ | $+2\pi i$ |
| $\ln(1-z)$ | $1,\infty$ | $[1,\infty)$ | $\infty$ | $-2\pi i$ |
| $\sqrt{(z-a)(z-b)}$ | $a,b$ | $[a,b]$ | 2 | $2i\sqrt{(x-a)(b-x)}$ |
| $\sqrt{z^2-1}$ | $\pm1$ | $[-1,1]$ | 2 | $2i\sqrt{1-x^2}$ |
| $\sqrt{\dfrac{z-a}{z-b}}$ | $a,b$ | $[a,b]$ | 2 | $-2i\sqrt{\dfrac{x-a}{b-x}}$ |
| $\ln\dfrac{z-a}{z-b}$ | $a,b$ | $[a,b]$ | $\infty$ | $\pm2\pi i$ |
| $Q_0(z)=\tfrac12\ln\frac{z+1}{z-1}$ | $\pm1$ | $[-1,1]$ | $\infty$ | $-i\pi$ |
| $(z-a)^\alpha(z-b)^\alpha$ | $a,b,\infty$ ($2\alpha\notin\mathbb Z$) | to $\infty$ | depends on $\alpha$ | — |

*(Signs of the discontinuity depend on the chosen cut and on the sign convention $\operatorname{disc}f=f(x+i0)-f(x-i0)$.)*

---

## 13. Exercises

1. For $f(z)=z^{1/2}$ with the cut on the **positive imaginary axis**, find the phases on both sides of the cut and the discontinuity.
2. For $f(z)=(z-a)^\alpha(z-b)^{-\alpha}$, show that the argument of $f$ jumps only across $[a,b]$, and compute $\operatorname{disc}f$.
3. Prove that $\displaystyle\int_0^\infty\frac{dx}{x^n+1}=\frac\pi n\csc\frac\pi n$ using the keyhole contour.
4. Show that $\displaystyle\oint_{|z|=2}\frac{dz}{\sqrt{1+z+z^2}}=2\pi i$. (Hint: find the cut joining the two roots and use the behaviour at $\infty$.)
5. Show that $\Gamma(n)=(n-1)!$ is recovered from the Hankel representation for positive integers $n$, and find the residue of $\Gamma$ at $z=-n$.
6. Verify that $\ln(1-z)/z$ has a simple pole at $z=0$ on every sheet except the principal one, and find the residue on sheet $n$.

---

*References: V. Balakrishnan, "Mathematical Physics" (Springer, 2020), Ch. 26; handwritten complex-analysis lecture notes.*
