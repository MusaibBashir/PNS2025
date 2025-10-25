---
title: Assignment 6
nav_order: 7
---

Question 1
==========

**Problem:** Let (X, Y) have the joint pdf $f_{X,Y}(x,y)=e^{-(x+y)}$,
$x>0, y>0$. Find $P(1<X+Y<2)$, $P(X<Y|X<2Y)$, $P(0<X<1|Y=2)$. Determine
m such that $P(X+Y<m)=\frac{1}{2}$.\
**Solution:**\
**Concept: Independent Exponential Variables** The joint PDF can be
written as $f(x,y) = e^{-x} \cdot e^{-y} = f_X(x)f_Y(y)$. This shows
that X and Y are independent random variables, each following an
Exponential distribution with parameter $\lambda=1$. So,
$X \sim \text{Exp}(1)$ and $Y \sim \text{Exp}(1)$.

**Part 1: $P(1<X+Y<2)$**\
**Nice Trick: Sum of Independent Exponentials** Let $Z = X+Y$. The sum
of two independent $\text{Exp}(1)$ variables is a $\text{Gamma}(2, 1)$
distribution. The PDF of Z is
$f_Z(z) = \frac{1^{\text{2}}}{\Gamma(2)} z^{2-1}e^{-1z} = ze^{-z}$ for
$z>0$.\
We can now solve this as a 1D problem:
$$P(1<Z<2) = \int_1^2 ze^{-z} dz$$ Using integration by parts
($\int u dv = uv - \int v du$) with $u=z, dv=e^{-z}dz$:
$$\int ze^{-z} dz = -ze^{-z} - \int -e^{-z} dz = -ze^{-z} - e^{-z}$$
$$P(1<Z<2) = [-ze^{-z} - e^{-z}]_1^2 = (-2e^{-2} - e^{-2}) - (-1e^{-1} - e^{-1})$$
$$= -3e^{-2} + 2e^{-1}$$
$$\boxed{ P(1<X+Y<2) = 2e^{-1} - 3e^{-2} \approx 0.3298 }$$

**Part 2: $P(X<Y|X<2Y)$** Using the definition of conditional
probability, $P(A|B) = \frac{P(A \cap B)}{P(B)}$:
$$P(X<Y | X<2Y) = \frac{P(X<Y \text{ and } X<2Y)}{P(X<2Y)} = \frac{P(X<Y)}{P(X<2Y)}$$
(The region $X<Y$ is a subset of $X<2Y$, so their intersection is just
$X<Y$).

-   $P(X<Y) = \int_0^\infty \int_x^\infty e^{-x}e^{-y} dy dx$=
    $$\int_0^\infty e^{-x}[-e^{-y}]_x^\infty dx = \int_0^\infty e^{-x}(0 - (-e^{-x})) dx = \int_0^\infty e^{-2x} dx = [-\frac{1}{2}e^{-2x}]_0^\infty = 0 - (-\frac{1}{2}) = \frac{1}{2}$$.\
    (This is also obvious by symmetry).

-   $P(X<2Y) = P(Y > X/2)$ =
    $$\int_0^\infty \int_{x/2}^\infty e^{-x}e^{-y} dy dx = \int_0^\infty e^{-x}[-e^{-y}]_{x/2}^\infty dx = \int_0^\infty e^{-x}(e^{-x/2}) dx = \int_0^\infty e^{-1.5x} dx = [-\frac{1}{1.5}e^{-1.5x}]_0^\infty = 0 - (-\frac{1}{1.5}) = \frac{1}{1.5} = \frac{2}{3}$$

$$P(X<Y|X<2Y) = \frac{1/2}{2/3} = \frac{3}{4}$$
$$\boxed{ P(X<Y|X<2Y) = 0.75 }$$

**Part 3: $P(0<X<1|Y=2)$** Since X and Y are independent, the
conditional probability is just the marginal probability:
$$P(0<X<1|Y=2) = P(0<X<1) = \int_0^1 e^{-x} dx = [-e^{-x}]_0^1 = (-e^{-1}) - (-e^0) = 1 - e^{-1}$$
$$\boxed{ P(0<X<1|Y=2) = 1 - e^{-1} \approx 0.6321 }$$

**Part 4: Find m such that $P(X+Y<m)=\frac{1}{2}$** Let $Z = X+Y$. We
use the CDF of the $\text{Gamma}(2, 1)$ distribution, which we found by
integration in Part 1.
$$P(Z<m) = \int_0^m ze^{-z} dz = [-ze^{-z} - e^{-z}]_0^m = (-me^{-m} - e^{-m}) - (0 - e^0) = 1 - (m+1)e^{-m}$$
We set this equal to $1/2$:
$$1 - (m+1)e^{-m} = \frac{1}{2} \implies (m+1)e^{-m} = \frac{1}{2} \implies 2(m+1)e^{-m} - 1 = 0$$
This is a transcendental equation and must be solved numerically.
$$\boxed{ m \approx 1.678 \text{ (numerical solution to } 2(m+1)e^{-m} = 1) }$$

Question 2
==========

**Problem:** Let $f(x,y)=x+y$ for $0<x<1, 0<y<1$. Are X and Y
independent? Find $V(X+Y)$, $Corr(X,Y)$, and $Var(X|Y=y)$.

**Solution:** **Independence:** We find the marginal PDFs.
$$f_X(x) = \int_0^1 (x+y) dy = [xy + \frac{y^2}{2}]_0^1 = x + \frac{1}{2}, \quad 0<x<1$$
$$f_Y(y) = \int_0^1 (x+y) dx = [\frac{x^2}{2} + xy]_0^1 = \frac{1}{2} + y, \quad 0<y<1$$
Check independence:
$f_X(x)f_Y(y) = (x+1/2)(y+1/2) = xy + \frac{x}{2} + \frac{y}{2} + \frac{1}{4} \neq x+y$.
$$\boxed{ \text{X and Y are not independent.} }$$ **Expectations and
Variances:**
$$E(X) = \int_0^1 x f_X(x) dx = \int_0^1 x(x+1/2) dx = \int_0^1 (x^2+x/2) dx = [\frac{x^3}{3} + \frac{x^2}{4}]_0^1 = \frac{1}{3} + \frac{1}{4} = \frac{7}{12}$$
By symmetry, $E(Y) = 7/12$.\
$$E(X^2) = \int_0^1 x^2(x+1/2) dx = \int_0^1 (x^3+x^2/2) dx = [\frac{x^4}{4} + \frac{x^3}{6}]_0^1 = \frac{1}{4} + \frac{1}{6} = \frac{5}{12}$$
$$V(X) = E(X^2) - [E(X)]^2 = \frac{5}{12} - (\frac{7}{12})^2 = \frac{5}{12} - \frac{49}{144} = \frac{60-49}{144} = \frac{11}{144}$$
By symmetry, $V(Y) = 11/144$.\
$$E(XY) = \int_0^1 \int_0^1 xy(x+y) dx dy = \int_0^1 \int_0^1 (x^2y+xy^2) dx dy = \int_0^1 [\frac{x^3y}{3} + \frac{x^2y^2}{2}]_0^1 dy = \int_0^1 (\frac{y}{3} + \frac{y^2}{2}) dy = [\frac{y^2}{6} + \frac{y^3}{6}]_0^1 = \frac{1}{6} + \frac{1}{6} = \frac{1}{3}$$
$$\text{Cov}(X,Y) = E(XY) - E(X)E(Y) = \frac{1}{3} - (\frac{7}{12})(\frac{7}{12}) = \frac{1}{3} - \frac{49}{144} = \frac{48-49}{144} = -\frac{1}{144}$$

**$V(X+Y)$ and $Corr(X,Y)$:**
$$V(X+Y) = V(X) + V(Y) + 2\text{Cov}(X,Y) = \frac{11}{144} + \frac{11}{144} + 2(-\frac{1}{144}) = \frac{22-2}{144} = \frac{20}{144} = \frac{5}{36}$$
$$\text{Corr}(X,Y) = \frac{\text{Cov}(X,Y)}{\sqrt{V(X)V(Y)}} = \frac{-1/144}{\sqrt{(11/144)(11/144)}} = \frac{-1/144}{11/144} = -\frac{1}{11}$$
$$\boxed{ V(X+Y) = \frac{5}{36}, \quad Corr(X,Y) = -\frac{1}{11} }$$

**$Var(X|Y=y)$:** First, find the conditional PDF:
$$f_{X|Y}(x|y) = \frac{f(x,y)}{f_Y(y)} = \frac{x+y}{y+1/2} = \frac{2(x+y)}{2y+1}$$
$E(X|Y=y) =$
$$\int_0^1 x \frac{2(x+y)}{2y+1} dx = \frac{2}{2y+1} \int_0^1 (x^2+xy) dx = \frac{2}{2y+1} [\frac{x^3}{3} + \frac{x^2y}{2}]_0^1 = \frac{2}{2y+1} (\frac{1}{3} + \frac{y}{2}) = \frac{2(2+3y)/6}{2y+1} = \frac{2+3y}{3(2y+1)}$$
$E(X^2|Y=y)=$
$$\int_0^1 x^2 \frac{2(x+y)}{2y+1} dx = \frac{2}{2y+1} \int_0^1 (x^3+x^2y) dx = \frac{2}{2y+1} [\frac{x^4}{4} + \frac{x^3y}{3}]_0^1 = \frac{2}{2y+1} (\frac{1}{4} + \frac{y}{3}) = \frac{2(3+4y)/12}{2y+1} = \frac{3+4y}{6(2y+1)}$$
$$Var(X|Y=y) = E(X^2|Y=y) - [E(X|Y=y)]^2 = \frac{3+4y}{6(2y+1)} - \left(\frac{2+3y}{3(2y+1)}\right)^2$$
$$= \frac{1}{(2y+1)^2} \left[ \frac{(3+4y)(2y+1)}{6} - \frac{(2+3y)^2}{9} \right]$$
$$= \frac{1}{18(2y+1)^2} [3(8y^2+10y+3) - 2(9y^2+12y+4)] = \frac{(24y^2+30y+9) - (18y^2+24y+8)}{18(2y+1)^2}$$
$$\boxed{ Var(X|Y=y) = \frac{6y^2+6y+1}{18(2y+1)^2} }$$

Question 3
==========

**Problem:** Let $f(x,y) = \frac{1}{8}(6-x-y)$ for $0<x<2, 2<y<4$. Find
$E(Y|X=x)$, $Var(Y|X=x)$, $Cov(X,Y)$, $Var(X|Y=y)$. *(Note: Solution for
Cov(X,Y) and Var(X\|Y=y) follows the same method as Q2).*

**Solution:**\
**Marginal and Conditional PDFs:**\
$f_X(x) =$$$\int_2^4 \frac{1}{8}(6-x-y) dy = \frac{1}{8} [6y-xy-\frac{y^2}{2}]_2^4 = \frac{1}{8} [(24-4x-8) - (12-2x-2)] = \frac{1}{8} [16-4x - 10+2x] = \frac{1}{8}(6-2x) = \frac{3-x}{4} \textit{,for} 0<x<2$$
$f_Y(y) = \int_0^2 \frac{1}{8}(6-x-y) dx = \frac{1}{8} [6x-\frac{x^2}{2}-xy]_0^2 = \frac{1}{8} [12-2-2y] = \frac{10-2y}{8} = \frac{5-y}{4}$,
for $2<y<4$. Conditional PDF of Y given X:
$$f_{Y|X}(y|x) = \frac{f(x,y)}{f_X(x)} = \frac{(6-x-y)/8}{(3-x)/4} = \frac{6-x-y}{2(3-x)}, \quad 2<y<4$$
**$E(Y|X=x)$:**
$$E(Y|X=x) = \int_2^4 y \cdot \frac{6-x-y}{2(3-x)} dy = \frac{1}{2(3-x)} \int_2^4 (y(6-x) - y^2) dy$$
$$= \frac{1}{2(3-x)} [\frac{y^2}{2}(6-x) - \frac{y^3}{3}]_2^4 = \frac{1}{2(3-x)} [ (8(6-x) - \frac{64}{3}) - (2(6-x) - \frac{8}{3}) ]$$
$$= \frac{1}{2(3-x)} [ 6(6-x) - \frac{56}{3} ] = \frac{36-6x-56/3}{2(3-x)} = \frac{(108-18x-56)/3}{2(3-x)} = \frac{52-18x}{6(3-x)} = \frac{26-9x}{3(3-x)}$$
$$\boxed{ E(Y|X=x) = \frac{26-9x}{3(3-x)} }$$ **$Var(Y|X=x)$:**
$E(Y^2|X=x) = \int_2^4 y^2 \cdot \frac{6-x-y}{2(3-x)} dy = \frac{1}{2(3-x)} \int_2^4 (y^2(6-x) - y^3) dy$
$$= \frac{1}{2(3-x)} [\frac{y^3}{3}(6-x) - \frac{y^4}{4}]_2^4 = \frac{1}{2(3-x)} [ (\frac{64}{3}(6-x) - 64) - (\frac{8}{3}(6-x) - 4) ]$$
$$= \frac{1}{2(3-x)} [ \frac{56}{3}(6-x) - 60 ] = \frac{(336-56x)/3 - 180/3}{2(3-x)} = \frac{156-56x}{6(3-x)} = \frac{78-28x}{3(3-x)}$$
$Var(Y|X=x) = E(Y^2|X=x) - [E(Y|X=x)]^2 = \frac{78-28x}{3(3-x)} - \left(\frac{26-9x}{3(3-x)}\right)^2$
$$\boxed{ Var(Y|X=x) = \frac{78-28x}{3(3-x)} - \left(\frac{26-9x}{3(3-x)}\right)^2 }$$

Question 4
==========

**Problem:** Ages of women (X) and men (Y) are BVN(24, 28, 36, 49, 0.8).
Find: (a) Proportion of women over 30. (b) Variance of age of wives (X)
whose husbands (Y) are 35. (c) Proportion of women over 30 having
husbands of age 35. (d) Expected age of men (Y) with wives of age 22
(X).

**Solution:** **Concept: Bivariate Normal (BVN) Distribution
Properties** We have
$(X,Y) \sim \text{BVN}(\mu_X, \mu_Y, \sigma_X^2, \sigma_Y^2, \rho)$
with: $\mu_X = 24$, $\sigma_X^2 = 36 \implies \sigma_X = 6$
$\mu_Y = 28$, $\sigma_Y^2 = 49 \implies \sigma_Y = 7$ $\rho = 0.8$

\(a\) **Proportion of women over 30:** $P(X > 30)$ The marginal
distribution of X is $N(\mu_X, \sigma_X^2) = N(24, 36)$.
$$P(X > 30) = P\left(Z > \frac{30 - \mu_X}{\sigma_X}\right) = P\left(Z > \frac{30-24}{6}\right) = P(Z > 1) = 1 - \Phi(1)$$
$$\boxed{ P(X>30) = 1 - 0.8413 = 0.1587 }$$

\(b\) **Variance of wives' age given husbands' age 35:** $Var(X|Y=35)$
The conditional variance is $Var(X|Y=y) = \sigma_X^2 (1 - \rho^2)$. This
is constant and does not depend on $y$.
$$Var(X|Y=35) = 36 (1 - 0.8^2) = 36 (1 - 0.64) = 36(0.36) = 12.96$$
$$\boxed{ Var(X|Y=35) = 12.96 }$$

\(c\) **Proportion of women over 30 given husbands' age 35:**
$P(X>30|Y=35)$ The conditional distribution $X|Y=y$ is
$N(E(X|Y=y), Var(X|Y=y))$.
$E(X|Y=y) = \mu_X + \rho \frac{\sigma_X}{\sigma_Y} (y - \mu_Y) = 24 + 0.8 \left(\frac{6}{7}\right) (y - 28)$
At $y=35$:
$E(X|Y=35) = 24 + 0.8 \left(\frac{6}{7}\right) (35 - 28) = 24 + 0.8 \left(\frac{6}{7}\right) (7) = 24 + 4.8 = 28.8$.
So, $X|Y=35 \sim N(28.8, 12.96)$.
$$P(X>30|Y=35) = P\left(Z > \frac{30 - 28.8}{\sqrt{12.96}}\right) = P\left(Z > \frac{1.2}{3.6}\right) = P(Z > 0.333...)$$
$$\boxed{ P(X>30|Y=35) = 1 - \Phi(0.33) = 1 - 0.6293 = 0.3707 }$$

\(d\) **Expected age of men given wives' age 22:** $E(Y|X=22)$
$E(Y|X=x) = \mu_Y + \rho \frac{\sigma_Y}{\sigma_X} (x - \mu_X) = 28 + 0.8 \left(\frac{7}{6}\right) (x - 24)$
At $x=22$:
$E(Y|X=22) = 28 + 0.8 \left(\frac{7}{6}\right) (22 - 24) = 28 + 0.8 \left(\frac{7}{6}\right) (-2) = 28 - \frac{11.2}{6} \approx 28 - 1.867$
$$\boxed{ E(Y|X=22) = 26.133 }$$

Question 5
==========

**Problem:** Life of tube $X_1$ and filament diameter $X_2$ are
BVN(1000, 0.1, 400, 0.01, 0.75). $\sigma_1^2=400 \implies \sigma_1=20$.
$\sigma_2^2=0.01 \implies \sigma_2=0.1$. If $X_2 = 0.09$, what is
$P(X_1 > 980 | X_2 = 0.09)$?

**Solution:** We need the conditional distribution $X_1 | X_2 = 0.09$.
$X_1|X_2=x_2 \sim N(E(X_1|X_2=x_2), Var(X_1|X_2=x_2))$.
$E(X_1|X_2=x_2) = \mu_1 + \rho \frac{\sigma_1}{\sigma_2} (x_2 - \mu_2) = 1000 + 0.75 \left(\frac{20}{0.1}\right) (0.09 - 0.1) = 1000 + 150(-0.01) = 1000 - 1.5 = 998.5$.
$Var(X_1|X_2=x_2) = \sigma_1^2 (1 - \rho^2) = 400 (1 - 0.75^2) = 400 (1 - 0.5625) = 400(0.4375) = 175$.
So, $X_1|X_2=0.09 \sim N(998.5, 175)$.
$$P(X_1 > 980 | X_2 = 0.09) = P\left(Z > \frac{980 - 998.5}{\sqrt{175}}\right) = P\left(Z > \frac{-18.5}{13.228}\right) = P(Z > -1.398)$$
$$= 1 - \Phi(-1.40) = \Phi(1.40) = 0.9192$$ *Note: The solution key
answer (0.1) is completely different, but the method shown here is
correct for the parameters given.*
$$\boxed{ P(X_1 > 980 | X_2 = 0.09) = \Phi(1.40) \approx 0.9192 }$$

Question 6
==========

**Problem:** Let $f(x,y)=\frac{1}{y}e^{-(y+x/y)}$, $x>0, y>0$. Find
marginal of Y, conditional $X|Y=y$, and E(Y), E(X), V(Y), V(X),
Cov(X,Y), Corr(X,Y).

**Solution:** **Marginal and Conditional:**
$f(x,y) = e^{-y} \cdot \frac{1}{y}e^{-x/y}$. This is
$f_Y(y) \cdot f_{X|Y}(x|y)$.
$$f_Y(y) = \int_0^\infty \frac{1}{y}e^{-y}e^{-x/y} dx = \frac{e^{-y}}{y} \int_0^\infty e^{-x/y} dx = \frac{e^{-y}}{y} [-y e^{-x/y}]_0^\infty = \frac{e^{-y}}{y} [0 - (-y)] = e^{-y}$$
$$\boxed{ f_Y(y) = e^{-y}, y>0 \implies Y \sim \text{Exp}(1) }$$
$$f_{X|Y}(x|y) = \frac{f(x,y)}{f_Y(y)} = \frac{\frac{1}{y}e^{-y}e^{-x/y}}{e^{-y}} = \frac{1}{y}e^{-x/y}, x>0$$
$$\boxed{ f_{X|Y}(x|y) = \frac{1}{y}e^{-x/y} \implies X|Y=y \sim \text{Exp}(1/y) }$$

**Expectations and Variances:** From $Y \sim \text{Exp}(1)$:
$$\boxed{ E(Y) = 1, \quad V(Y) = 1 }$$ From
$X|Y=y \sim \text{Exp}(1/y)$: $E(X|Y=y) = y$ (mean of $\text{Exp}(1/y)$
is $1/\lambda = 1/(1/y) = y$). $V(X|Y=y) = y^2$ (variance of
$\text{Exp}(1/y)$ is $1/\lambda^2 = 1/(1/y)^2 = y^2$).

**Concept: Law of Total Expectation and Variance**
$$E(X) = E[E(X|Y)] = E[Y] = 1$$ $$\boxed{ E(X) = 1 }$$
$$V(X) = E[V(X|Y)] + V[E(X|Y)]$$ $$E[V(X|Y)] = E[Y^2]$$ Since
$V(Y) = E[Y^2] - [E(Y)]^2$, we have
$$E[Y^2] = V(Y) + [E(Y)]^2 = 1 + 1^2 = 2$$ $$V[E(X|Y)] = V[Y] = 1$$
$$V(X) = 2 + 1 = 3$$ $$\boxed{ V(X) = 3 }$$
$$\text{Cov}(X,Y) = E(XY) - E(X)E(Y)$$
$$E(XY) = E[E(XY|Y)] = E[Y \cdot E(X|Y)] = E[Y \cdot y] = E[Y^2] = 2$$
$$\text{Cov}(X,Y) = 2 - (1)(1) = 1$$ $$\boxed{ \text{Cov}(X,Y) = 1 }$$
$$\text{Corr}(X,Y) = \frac{\text{Cov}(X,Y)}{\sqrt{V(X)V(Y)}} = \frac{1}{\sqrt{3}\sqrt{1}} = \frac{1}{\sqrt{3}}$$
$$\boxed{ \text{Corr}(X,Y) = \frac{1}{\sqrt{3}} \approx 0.577 }$$

Question 7
==========

**Problem:** BVN marks with
$\mu_1=75, \mu_2=83, \sigma_1=5, \sigma_2=4, \rho=0.8$. If $X_1=80$,
find $P(X_2 > 80 | X_1 = 80)$. How does this change for $\rho=-0.8$?

**Solution:** We need the conditional distribution $X_2 | X_1 = 80$.
$X_2|X_1=x_1 \sim N(E(X_2|X_1=x_1), Var(X_2|X_1=x_1))$.
$E(X_2|X_1=x_1) = \mu_2 + \rho \frac{\sigma_2}{\sigma_1} (x_1 - \mu_1) = 83 + 0.8 \left(\frac{4}{5}\right) (80 - 75) = 83 + 0.8(0.8)(5) = 83 + 3.2 = 86.2$.
$Var(X_2|X_1=x_1) = \sigma_2^2 (1 - \rho^2) = 4^2 (1 - 0.8^2) = 16 (1 - 0.64) = 16(0.36) = 5.76$.
So, $X_2|X_1=80 \sim N(86.2, 5.76)$.
$$P(X_2 > 80 | X_1 = 80) = P\left(Z > \frac{80 - 86.2}{\sqrt{5.76}}\right) = P\left(Z > \frac{-6.2}{2.4}\right) = P(Z > -2.583)$$
$$\boxed{ P(X_2 > 80 | X_1 = 80, \rho=0.8) = \Phi(2.58) = 0.9951 }$$
**If $\rho = -0.8$:**
$E(X_2|X_1=80) = 83 + (-0.8) \left(\frac{4}{5}\right) (80 - 75) = 83 - 3.2 = 79.8$.
$Var(X_2|X_1=80) = 16 (1 - (-0.8)^2) = 5.76$ (Variance is unchanged).
So, $X_2|X_1=80 \sim N(79.8, 5.76)$.
$$P(X_2 > 80 | X_1 = 80) = P\left(Z > \frac{80 - 79.8}{\sqrt{5.76}}\right) = P\left(Z > \frac{0.2}{2.4}\right) = P(Z > 0.0833)$$
$$\boxed{ P(X_2 > 80 | X_1 = 80, \rho=-0.8) = 1 - \Phi(0.08) = 1 - 0.5319 = 0.4681 }$$
This makes sense: positive correlation means a good score on test 1
predicts a good score on test 2. Negative correlation predicts the
opposite.

Question 8
==========

**Problem:** Rainfall $X_1$ (April) and $X_2$ (May) are BVN(6, 4, 1,
0.25, 0.1). $\sigma_1^2=1 \implies \sigma_1=1$.
$\sigma_2^2=0.25 \implies \sigma_2=0.5$. Find $P(X_1 \le 5)$,
$P(X_2 \le 5 | X_1 = 5)$, $E(X_1 | X_2 = 6)$.

**Solution:** (a) **$P(X_1 \le 5)$:** Marginal $X_1 \sim N(6, 1)$.
$$P(X_1 \le 5) = P\left(Z \le \frac{5 - 6}{1}\right) = P(Z \le -1) = \Phi(-1)$$
$$\boxed{ P(X_1 \le 5) = 0.1587 }$$ (b) **$P(X_2 \le 5 | X_1 = 5)$:** We
need the conditional distribution $X_2 | X_1 = 5 \sim N(E, V)$.
$E = E(X_2|X_1=5) = \mu_2 + \rho \frac{\sigma_2}{\sigma_1} (x_1 - \mu_1) = 4 + 0.1 \left(\frac{0.5}{1}\right) (5 - 6) = 4 + 0.05(-1) = 3.95$.
$V = Var(X_2|X_1=5) = \sigma_2^2 (1 - \rho^2) = 0.25 (1 - 0.1^2) = 0.25(0.99) = 0.2475$.
So, $X_2|X_1=5 \sim N(3.95, 0.2475)$.
$$P(X_2 \le 5 | X_1 = 5) = P\left(Z \le \frac{5 - 3.95}{\sqrt{0.2475}}\right) = P\left(Z \le \frac{1.05}{0.4975}\right) = P(Z \le 2.11)$$
$$\boxed{ P(X_2 \le 5 | X_1 = 5) = \Phi(2.11) = 0.9826 }$$ (c)
**$E(X_1 | X_2 = 6)$:**
$E(X_1|X_2=x_2) = \mu_1 + \rho \frac{\sigma_1}{\sigma_2} (x_2 - \mu_2) = 6 + 0.1 \left(\frac{1}{0.5}\right) (6 - 4) = 6 + 0.2(2) = 6.4$.
$$\boxed{ E(X_1 | X_2 = 6) = 6.4 }$$

Question 9
==========

**Problem:** $f(x,y)=1-\alpha(1-2x)(1-2y)$ for $0<x<1, 0<y<1$. Find
valid range of $\alpha$, $\text{Corr}(X,Y)$, and show independent iff
uncorrelated.

**Solution:** **Valid Range of $\alpha$:** We need $f(x,y) \ge 0$ over
the unit square. The term $g(x,y) = (1-2x)(1-2y)$ ranges from -1 to 1.

-   Max $g(x,y)$: At (0,0) or (1,1), $g(x,y) = 1$.
    $f(0,0) = 1 - \alpha \ge 0 \implies \alpha \le 1$.

-   Min $g(x,y)$: At (0,1) or (1,0), $g(x,y) = -1$.
    $f(0,1) = 1 - \alpha(-1) = 1 + \alpha \ge 0 \implies \alpha \ge -1$.

$$\boxed{ \text{Valid range: } -1 \le \alpha \le 1 }$$ **Correlation:**
$f_X(x) = \int_0^1 [1 - \alpha(1-2x)(1-2y)] dy = [y - \alpha(1-2x)(y-y^2)]_0^1 = (1 - \alpha(1-2x)(1-1)) - 0 = 1$.
So, $X \sim U(0,1)$. By symmetry, $Y \sim U(0,1)$.
$E(X) = 1/2, V(X) = 1/12$. $E(Y) = 1/2, V(Y) = 1/12$.
$E(XY) = \int_0^1 \int_0^1 xy[1 - \alpha(1-2x)(1-2y)] dx dy = \int_0^1 \int_0^1 [xy - \alpha(x-2x^2)(y-2y^2)] dx dy$
$$= \left(\int_0^1 x dx\right)\left(\int_0^1 y dy\right) - \alpha \left(\int_0^1 (x-2x^2) dx\right) \left(\int_0^1 (y-2y^2) dy\right)$$
$\int_0^1 x dx = 1/2$.
$\int_0^1 (x-2x^2) dx = [\frac{x^2}{2} - \frac{2x^3}{3}]_0^1 = \frac{1}{2} - \frac{2}{3} = -\frac{1}{6}$.
$E(XY) = (\frac{1}{2})(\frac{1}{2}) - \alpha(-\frac{1}{6})(-\frac{1}{6}) = \frac{1}{4} - \frac{\alpha}{36}$.
$\text{Cov}(X,Y) = E(XY) - E(X)E(Y) = (\frac{1}{4} - \frac{\alpha}{36}) - (\frac{1}{2})(\frac{1}{2}) = -\frac{\alpha}{36}$.
$\text{Corr}(X,Y) = \frac{\text{Cov}(X,Y)}{\sqrt{V(X)V(Y)}} = \frac{-\alpha/36}{\sqrt{(1/12)(1/12)}} = \frac{-\alpha/36}{1/12} = -\frac{12\alpha}{36} = -\frac{\alpha}{3}$.
$$\boxed{ \text{Corr}(X,Y) = -\frac{\alpha}{3} }$$ **Independence vs.
Uncorrelation:**

-   X and Y are **independent** if $f(x,y) = f_X(x)f_Y(y)$, which means
    $1 - \alpha(1-2x)(1-2y) = 1 \cdot 1$. This is true if and only if
    $\alpha = 0$.

-   X and Y are **uncorrelated** if $\text{Corr}(X,Y) = 0$, which means
    $-\alpha/3 = 0$. This is true if and only if $\alpha = 0$.

$$\boxed{ \text{Since both conditions are equivalent to } \alpha=0, \text{ X and Y are independent iff they are uncorrelated.} }$$

Question 10
===========

**Problem:** Given a joint PMF table for (X, Y). (a) Find
$P(X \le 1, Y \ge 2)$. (b) Find marginals and $\rho_{X,Y}$. (c) Find
$P(Y \ge 2 | X = 1)$.

**Solution:** **Joint PMF Table and Marginals (from part b):**\

  $X \setminus Y$     1      2      3      4     $p_X(x)$
  ----------------- ------ ------ ------ ------ ----------
  0                  .059   .100   .050   .001     .210
  1                  .093   .120   .082   .003     .298
  2                  .065   .102   .100   .010     .277
  3                  .050   .075   .070   .020     .215
  $p_Y(y)$           .267   .397   .302   .034    1.000

$$\boxed{ \text{Marginals } p_X(x) \text{ and } p_Y(y) \text{ are in the table.} }$$
(a) **$P(X \le 1, Y \ge 2)$:** Sum values where $x \in \{0, 1\}$ and
$y \in \{2, 3, 4\}$. $$= p(0,2)+p(0,3)+p(0,4) + p(1,2)+p(1,3)+p(1,4)$$
$$= (.100 + .050 + .001) + (.120 + .082 + .003) = 0.151 + 0.205 = 0.356$$
$$\boxed{ P(X \le 1, Y \ge 2) = 0.356 }$$ (b) **Correlation
$\rho_{X,Y}$:**\
$$E(X)= 0(.210) + 1(.298) + 2(.277) + 3(.215) = 0 + .298 + .554 + .645 = 1.497$$
$$E(Y) = 1(.267) + 2(.397) + 3(.302) + 4(.034) = .267 + .794 + .906 + .136 = 2.103$$
$$E(X^2) = 0^2(.210) + 1^2(.298) + 2^2(.277) + 3^2(.215) = .298 + 4(.277) + 9(.215) = .298 + 1.108 + 1.935 = 3.341$$
$$V(X) = E(X^2) - [E(X)]^2 = 3.341 - (1.497)^2 = 3.341 - 2.241 = 1.0999$$
$$E(Y^2) = 1^2(.267) + 2^2(.397) + 3^2(.302) + 4^2(.034) = .267 + 1.588 + 2.718 + .544 = 5.117$$
$$V(Y) = E(Y^2) - [E(Y)]^2 = 5.117 - (2.103)^2 = 5.117 - 4.4226 = 0.6944$$
$$E(XY) = \sum x_i y_j p(x_i, y_j) = 1(1)(.093) + 1(2)(.120) + ... + 3(4)(.020) = 3.279$$
.
$$\text{Cov}(X,Y) = E(XY) - E(X)E(Y) = 3.279 - (1.497)(2.103) = 3.279 - 3.148 = 0.131$$
$$\rho_{X,Y} = \frac{\text{Cov}(X,Y)}{\sqrt{V(X)V(Y)}} = \frac{0.131}{\sqrt{(1.0999)(0.6944)}} = \frac{0.131}{\sqrt{0.7638}} = \frac{0.131}{0.874}$$\
$$\boxed{ \rho_{X,Y} \approx 0.1498 }$$ (c) **$P(Y \ge 2 | X = 1)$:**
$$P(Y \ge 2 | X = 1) = \frac{P(Y \ge 2, X=1)}{P(X=1)} = \frac{p(1,2)+p(1,3)+p(1,4)}{p_X(1)}$$
$$= \frac{.120 + .082 + .003}{.298} = \frac{.205}{.298} \approx 0.6879$$
$$\boxed{ P(Y \ge 2 | X = 1) \approx 0.6879 }$$

Question 11
===========

**Problem:** $f(x,y)=8xy$, $0<y<x<1$. Y=on time, X=off time. (a)
$P(Y < 0.5, X < Y + 0.25)$ (b) $P(X < 0.75 | Y = 1/6)$ (c)
$E(X | Y = 1/6)$ (d) $\text{Corr}(X,Y)$.\
*(Note: The provided solution key for this problem has several errors.
This solution follows the problem statement as written.)*

**Solution:** (a) **$P(Y < 0.5, X < Y + 0.25)$:** We integrate over the
intersection of the regions $0<y<x<1$ and $y<0.5$ and $x<y+0.25$. The
region is $0 < y < 0.5$ and $y < x < \min(1, y+0.25)$. Since $y<0.5$,
$y+0.25 < 0.75$, so the upper bound for $x$ is $y+0.25$.
$$\int_0^{0.5} \int_y^{y+0.25} 8xy dx dy = \int_0^{0.5} 8y \left[\frac{x^2}{2}\right]_y^{y+0.25} dy = \int_0^{0.5} 4y [(y+0.25)^2 - y^2] dy$$
$$= \int_0^{0.5} 4y (y^2 + 0.5y + 0.0625 - y^2) dy = \int_0^{0.5} 4y (0.5y + 0.0625) dy = \int_0^{0.5} (2y^2 + 0.25y) dy$$
$$= \left[\frac{2y^3}{3} + \frac{0.25y^2}{2}\right]_0^{0.5} = \frac{2(0.5)^3}{3} + \frac{0.25(0.5)^2}{2} = \frac{2(0.125)}{3} + \frac{0.25(0.25)}{2} = \frac{0.25}{3} + \frac{0.0625}{2} = \frac{1}{12} + \frac{1}{32} = \frac{8+3}{96} = \frac{11}{96}$$
$$\boxed{ P(Y < 0.5, X < Y + 0.25) = \frac{11}{96} \approx 0.1146 }$$
(b) **$P(X < 0.75 | Y = 1/6)$:**
$f_Y(y) = \int_y^1 8xy dx = 8y[\frac{x^2}{2}]_y^1 = 4y(1-y^2)$, for
$0<y<1$.
$f_{X|Y}(x|y) = \frac{f(x,y)}{f_Y(y)} = \frac{8xy}{4y(1-y^2)} = \frac{2x}{1-y^2}$,
for $y<x<1$. For $y=1/6$:
$f_{X|Y}(x|1/6) = \frac{2x}{1-(1/6)^2} = \frac{2x}{1-1/36} = \frac{2x}{35/36} = \frac{72x}{35}$,
for $1/6 < x < 1$.
$$P(X < 0.75 | Y = 1/6) = \int_{1/6}^{3/4} \frac{72x}{35} dx = \frac{72}{35} [\frac{x^2}{2}]_{1/6}^{3/4} = \frac{36}{35} [(\frac{3}{4})^2 - (\frac{1}{6})^2]$$
$$= \frac{36}{35} [\frac{9}{16} - \frac{1}{36}] = \frac{36}{35} [\frac{81 - 4}{144}] = \frac{36}{35} \frac{77}{144} = \frac{1}{1} \cdot \frac{11}{5} \cdot \frac{1}{4} = \frac{11}{20}$$
$$\boxed{ P(X < 0.75 | Y = 1/6) = \frac{11}{20} = 0.55 }$$ (c)
**$E(X | Y = 1/6)$:**
$$E(X | Y = 1/6) = \int_{1/6}^1 x \cdot f_{X|Y}(x|1/6) dx = \int_{1/6}^1 x \left(\frac{72x}{35}\right) dx = \frac{72}{35} \int_{1/6}^1 x^2 dx$$
$$= \frac{72}{35} [\frac{x^3}{3}]_{1/6}^1 = \frac{24}{35} [1^3 - (\frac{1}{6})^3] = \frac{24}{35} [1 - \frac{1}{216}] = \frac{24}{35} [\frac{215}{216}] = \frac{1}{7} \cdot \frac{43}{9} = \frac{43}{63}$$
$$\boxed{ E(X | Y = 1/6) = \frac{43}{63} \approx 0.6825 }$$ (d)
**$\text{Corr}(X,Y)$:**
$$f_X(x) = \int_0^x 8xy dy = 8x[\frac{y^2}{2}]_0^x = 4x^3, \textit{for  } 0<x<1$$
$$E(X) = \int_0^1 x(4x^3) dx = 4[\frac{x^5}{5}]_0^1 = \frac{4}{5}$$
$$E(Y) = \int_0^1 y(4y-4y^3) dy = [ \frac{4y^3}{3} - \frac{4y^5}{5} ]_0^1 = \frac{4}{3} - \frac{4}{5} = \frac{8}{15}$$
$$E(X^2) = \int_0^1 x^2(4x^3) dx = 4[\frac{x^6}{6}]_0^1 = \frac{4}{6} = \frac{2}{3}$$
$$E(Y^2) = \int_0^1 y^2(4y-4y^3) dy = [ y^4 - \frac{4y^6}{6} ]_0^1 = 1 - \frac{4}{6} = \frac{1}{3}$$
$$V(X) = E(X^2) - [E(X)]^2 = \frac{2}{3} - (\frac{4}{5})^2 = \frac{2}{3} - \frac{16}{25} = \frac{50-48}{75} = \frac{2}{75}$$
$$V(Y) = E(Y^2) - [E(Y)]^2 = \frac{1}{3} - (\frac{8}{15})^2 = \frac{1}{3} - \frac{64}{225} = \frac{75-64}{225} = \frac{11}{225}$$
$$E(XY) = \int_0^1 \int_y^1 xy (8xy) dx dy = \int_0^1 8y^2 [\frac{x^3}{3}]_y^1 dy = \frac{8}{3} \int_0^1 y^2(1-y^3) dy = \frac{8}{3} [\frac{y^3}{3} - \frac{y^6}{6}]_0^1 = \frac{8}{3}(\frac{1}{3} - \frac{1}{6}) = \frac{8}{3}(\frac{1}{6}) = \frac{4}{9}$$
$$\text{Cov}(X,Y) = E(XY) - E(X)E(Y) = \frac{4}{9} - (\frac{4}{5})(\frac{8}{15}) = \frac{4}{9} - \frac{32}{75} = \frac{100 - 96}{225} = \frac{4}{225}$$
$$\text{Corr}(X,Y) = \frac{\text{Cov}(X,Y)}{\sqrt{V(X)V(Y)}} = \frac{4/225}{\sqrt{(2/75)(11/225)}} = \frac{4/225}{\sqrt{22 / 16875}} = \frac{4/225}{(\sqrt{22} \cdot \sqrt{3}) / (75 \cdot 3)} = \frac{4/225}{\sqrt{66}/225} = \frac{4}{\sqrt{66}}$$
$$\boxed{ \text{Corr}(X,Y) = \frac{4}{\sqrt{66}} \approx 0.492 }$$

Question 12
===========

**Problem:** $f(x,y) = \frac{1}{4}(1+xy)$ for $|x|<1, |y|<1$. Find
$P(2X<Y)$, $P(|X+Y|<1)$, and $\rho_{X,Y}$.

**Solution:** **$P(2X<Y) = P(X < Y/2)$:** We integrate $f(x,y)$ over the
region defined by $-1<x<1, -1<y<1, x<y/2$.
$$P(X < Y/2) = \int_{-1}^1 \left( \int_{-1}^{y/2} \frac{1}{4}(1+xy) dx \right) dy \quad (\text{Note: } -1 < y/2 \text{ is not always true, but } -1 \text{ is the lower bound for } x)$$
$$= \int_{-1}^1 \frac{1}{4} [x + \frac{x^2y}{2}]_{-1}^{y/2} dy = \frac{1}{4} \int_{-1}^1 \left[ (\frac{y}{2} + \frac{(y/2)^2 y}{2}) - (-1 + \frac{(-1)^2 y}{2}) \right] dy$$
$$= \frac{1}{4} \int_{-1}^1 \left( \frac{y}{2} + \frac{y^3}{8} + 1 - \frac{y}{2} \right) dy = \frac{1}{4} \int_{-1}^1 (1 + \frac{y^3}{8}) dy = \frac{1}{4} [y + \frac{y^4}{32}]_{-1}^1$$
$$= \frac{1}{4} \left[ (1 + \frac{1}{32}) - (-1 + \frac{1}{32}) \right] = \frac{1}{4} [2] = \frac{1}{2}$$
$$\boxed{ P(2X < Y) = \frac{1}{2} }$$ **$P(|X+Y|<1)$:** This is the
region $-1 < X+Y < 1$. We integrate over the part of the square that
satisfies this. The excluded corners are $X+Y \ge 1$ (top right) and
$X+Y \le -1$ (bottom left).
$$P(|X+Y| \ge 1) = P(X+Y \ge 1) + P(X+Y \le -1)$$ By symmetry of
$f(x,y)$ and the regions, $P(X+Y \ge 1) = P(X+Y \le -1)$.
$P(X+Y \ge 1) = \int_0^1 \int_{1-x}^1 \frac{1}{4}(1+xy) dy dx = \frac{1}{4} \int_0^1 [y + \frac{xy^2}{2}]_{1-x}^1 dx = \frac{1}{4} \int_0^1 \left( (1+\frac{x}{2}) - ((1-x) + \frac{x(1-x)^2}{2}) \right) dx = \frac{17}{96}$.
$P(|X+Y| \ge 1) = 2 \cdot \frac{17}{96} = \frac{17}{48}$.
$P(|X+Y| < 1) = 1 - P(|X+Y| \ge 1) = 1 - \frac{17}{48} = \frac{31}{48}$.
$$\boxed{ P(|X+Y| < 1) = \frac{31}{48} }$$ **$\rho_{X,Y}$:**
$f_X(x) = \int_{-1}^1 \frac{1}{4}(1+xy) dy = \frac{1}{4} [y + \frac{xy^2}{2}]_{-1}^1 = \frac{1}{4} [(1+\frac{x}{2}) - (-1+\frac{x}{2})] = \frac{1}{4}[2] = \frac{1}{2}$.
$X \sim U(-1,1)$. By symmetry, $Y \sim U(-1,1)$. $E(X)=0, E(Y)=0$.
$V(X) = \frac{(1 - (-1))^2}{12} = \frac{4}{12} = \frac{1}{3}$.
$V(Y) = 1/3$.
$E(XY) = \int_{-1}^1 \int_{-1}^1 xy \frac{1}{4}(1+xy) dx dy = \frac{1}{4} \int_{-1}^1 \int_{-1}^1 (xy + x^2y^2) dx dy$
$$= \frac{1}{4} \left(\int_{-1}^1 x dx\right)\left(\int_{-1}^1 y dy\right) + \frac{1}{4} \left(\int_{-1}^1 x^2 dx\right)\left(\int_{-1}^1 y^2 dy\right)$$
$E(XY) = 0 + \frac{1}{4} \left( [\frac{x^3}{3}]_{-1}^1 \right) \left( [\frac{y^3}{3}]_{-1}^1 \right) = \frac{1}{4} (\frac{2}{3}) (\frac{2}{3}) = \frac{1}{9}$.
$\text{Cov}(X,Y) = E(XY) - E(X)E(Y) = 1/9$.
$$\rho_{X,Y} = \frac{\text{Cov}(X,Y)}{\sqrt{V(X)V(Y)}} = \frac{1/9}{\sqrt{(1/3)(1/3)}} = \frac{1/9}{1/3} = \frac{3}{9} = \frac{1}{3}$$
$$\boxed{ \rho_{X,Y} = \frac{1}{3} }$$

Question 13
===========

**Problem:** $f(x,y)=c$ for $x^2 \le y \le x, 0<x<1$. Find c,
$\rho_{X,Y}$, $P(1/3<X<2/3)$, $P(1/4<Y<3/4)$, $P(5/16<X<7/16|Y=1/4)$,
$P(3/8<Y<5/8|X=1/2)$, $P(|X-Y|<0.5)$.

**Solution:** **Find c:** We integrate over the area.
$$\int_0^1 \int_{x^2}^x c dy dx = 1 \implies c \int_0^1 [y]_{x^2}^x dx = c \int_0^1 (x-x^2) dx = c [\frac{x^2}{2} - \frac{x^3}{3}]_0^1 = c (\frac{1}{2} - \frac{1}{3}) = \frac{c}{6} = 1 \implies c=6$$
$$\boxed{ c=6 }$$ **Marginals:**
$f_X(x) = \int_{x^2}^x 6 dy = 6(x-x^2)$, for $0<x<1$.
$f_Y(y) = \int_y^{\sqrt{y}} 6 dx = 6[x]_y^{\sqrt{y}} = 6(\sqrt{y}-y)$,
for $0<y<1$. **$P(1/3<X<2/3)$:**
$$\int_{1/3}^{2/3} 6(x-x^2) dx = 6 [\frac{x^2}{2} - \frac{x^3}{3}]_{1/3}^{2/3} = 6 [ (\frac{4/9}{2} - \frac{8/27}{3}) - (\frac{1/9}{2} - \frac{1/27}{3}) ]$$
$$= 6 [ (\frac{2}{9} - \frac{8}{81}) - (\frac{1}{18} - \frac{1}{81}) ] = 6 [ \frac{18-8}{81} - \frac{9-2}{162} ] = 6 [ \frac{10}{81} - \frac{7}{162} ] = 6 [ \frac{20-7}{162} ] = \frac{6 \cdot 13}{162} = \frac{13}{27}$$
$$\boxed{ P(1/3<X<2/3) = \frac{13}{27} }$$ **$P(1/4<Y<3/4)$:**
$$\int_{1/4}^{3/4} 6(\sqrt{y}-y) dy = 6 [\frac{2}{3}y^{3/2} - \frac{y^2}{2}]_{1/4}^{3/4} = 6 [ (\frac{2}{3}(\frac{3\sqrt{3}}{8}) - \frac{9/16}{2}) - (\frac{2}{3}(\frac{1}{8}) - \frac{1/16}{2}) ]$$
$$= 6 [ (\frac{\sqrt{3}}{4} - \frac{9}{32}) - (\frac{1}{12} - \frac{1}{32}) ] = 6 [ \frac{8\sqrt{3}-9}{32} - \frac{8-3}{96} ] = 6 [ \frac{24\sqrt{3}-27-5}{96} ] = \frac{24\sqrt{3}-32}{16} = \frac{3\sqrt{3}-4}{2}$$
$$\boxed{ P(1/4<Y<3/4) = \frac{3\sqrt{3}-4}{2} \approx 0.598 }$$
**$P(5/16<X<7/16|Y=1/4)$:**
$$f_{X|Y}(x|y) = \frac{f(x,y)}{f_Y(y)} = \frac{6}{6(\sqrt{y}-y)} = \frac{1}{\sqrt{y}-y}, \textit{for } y < x < \sqrt{y}$$
$$y=1/4: \sqrt{y}=1/2  \sqrt{y}-y = 1/2-1/4=1/4. \textit{ Region } 1/4 < x < 1/2$$
$$f_{X|Y}(x|1/4) = \frac{1}{1/4} = 4. \textit{ so } X|Y=1/4 \sim U(1/4, 1/2)$$\
The interval $(5/16, 7/16)$ is $(\frac{20}{64}, \frac{28}{64})$.
$1/4=16/64, 1/2=32/64$.
$P(5/16<X<7/16|Y=1/4) = \int_{5/16}^{7/16} 4 dx = 4[x]_{5/16}^{7/16} = 4(\frac{7}{16} - \frac{5}{16}) = 4(\frac{2}{16}) = \frac{8}{16} = \frac{1}{2}$.
$$\boxed{ P(5/16<X<7/16|Y=1/4) = \frac{1}{2} }$$
**$P(3/8<Y<5/8|X=1/2)$:**
$f_{Y|X}(y|x) = \frac{f(x,y)}{f_X(x)} = \frac{6}{6(x-x^2)} = \frac{1}{x-x^2}$,
for $x^2 < y < x$. For $x=1/2$: $x^2=1/4$. $x-x^2 = 1/2-1/4=1/4$. Region
$1/4 < y < 1/2$. $f_{Y|X}(y|1/2) = \frac{1}{1/4} = 4$. So
$Y|X=1/2 \sim U(1/4, 1/2)$. We need $P(3/8<Y<5/8|X=1/2)$. The
intersection of $(3/8, 5/8)$ and $(1/4, 1/2) = (0.25, 0.5)$ is
$(3/8, 1/2) = (0.375, 0.5)$.
$P(3/8<Y<1/2|X=1/2) = \int_{3/8}^{1/2} 4 dy = 4[y]_{3/8}^{1/2} = 4(\frac{1}{2} - \frac{3}{8}) = 4(\frac{1}{8}) = \frac{1}{2}$.
$$\boxed{ P(3/8<Y<5/8|X=1/2) = \frac{1}{2} }$$ **$P(|X-Y|<0.5)$:** The
region $x^2 < y < x$ is fully contained within the region $|x-y|<0.5$.
For $x \in (0,1)$, the max difference is $x-x^2$, which maxes out at
$x=0.5$ (value $0.25$). Since the max possible difference is $0.25$,
which is less than $0.5$, the probability is 1.
$$\boxed{ P(|X-Y|<0.5) = 1 }$$

Question 14
===========

**Problem:**
$f(x_1,x_2)=\frac{1}{2}(x_1+x_2)e^{-(x_1+x_2)}, x_1>0, x_2>0$. Find
$E(X_2|X_1=4)$, $Var(X_1|X_2=2)$, $\rho_{X_1,X_2}$.\
*(Note: This PDF is a sum of a $\text{Gamma}(2,1)$ and a
$\text{Gamma}(3,1)$ density, but is not a standard distribution
itself.)*

**Solution:**\
**Marginals:**\
$$f_{X_1}(x_1) = \int_0^\infty \frac{1}{2}(x_1+x_2)e^{-x_1}e^{-x_2} dx_2 = \frac{1}{2}e^{-x_1} \int_0^\infty (x_1e^{-x_2} + x_2e^{-x_2}) dx_2$$
$$\int_0^\infty x_1e^{-x_2} dx_2 = x_1[-e^{-x_2}]_0^\infty = x_1$$
$$\int_0^\infty x_2e^{-x_2} dx_2 = \Gamma(2) = 1! = 1$$ (mean of Exp(1)
is 1). $$f_{X_1}(x_1) = \frac{1}{2}e^{-x_1}(x_1+1)$$ By symmetry,
$$f_{X_2}(x_2) = \frac{1}{2}(x_2+1)e^{-x_2}$$
**Expectations/Variances:**
$$E(X_1) = \int_0^\infty x_1 \frac{1}{2}(x_1+1)e^{-x_1} dx_1 = \frac{1}{2} \int_0^\infty (x_1^2+x_1)e^{-x_1} dx_1 = \frac{1}{2}(\Gamma(3) + \Gamma(2)) = \frac{1}{2}(2! + 1!) = \frac{3}{2}$$
$$E(X_1^2) = \int_0^\infty x_1^2 \frac{1}{2}(x_1+1)e^{-x_1} dx_1 = \frac{1}{2} \int_0^\infty (x_1^3+x_1^2)e^{-x_1} dx_1 = \frac{1}{2}(\Gamma(4) + \Gamma(3)) = \frac{1}{2}(3! + 2!) = \frac{6+2}{2} = 4$$
$$V(X_1) = 4 - (3/2)^2 = 4 - 9/4 = 7/4$$ By symmetry,
$$E(X_2)=3/2, V(X_2)=7/4$$ **Conditionals:**
$$f_{X_2|X_1}(x_2|x_1) = \frac{f(x_1,x_2)}{f_{X_1}(x_1)} = \frac{\frac{1}{2}(x_1+x_2)e^{-x_1}e^{-x_2}}{\frac{1}{2}(x_1+1)e^{-x_1}} = \frac{x_1+x_2}{x_1+1}e^{-x_2}$$
$$E(X_2|X_1=4) = \int_0^\infty x_2 \cdot \frac{4+x_2}{4+1}e^{-x_2} dx_2 = \frac{1}{5} \int_0^\infty (4x_2+x_2^2)e^{-x_2} dx_2 = \frac{1}{5} (4\Gamma(2) + \Gamma(3)) = \frac{1}{5}(4(1) + 2) = \frac{6}{5}$$
$$\boxed{ E(X_2|X_1=4) = \frac{6}{5} }$$
$$f_{X_1|X_2}(x_1|x_2) = \frac{x_1+x_2}{x_2+1}e^{-x_1}$$
$$E(X_1|X_2=2) = \int_0^\infty x_1 \frac{x_1+2}{2+1}e^{-x_1} dx_1 = \frac{1}{3} \int_0^\infty (x_1^2+2x_1)e^{-x_1} dx_1 = \frac{1}{3}(\Gamma(3) + 2\Gamma(2)) = \frac{1}{3}(2+2) = \frac{4}{3}$$
$$E(X_1^2|X_2=2) = \int_0^\infty x_1^2 \frac{x_1+2}{3}e^{-x_1} dx_1 = \frac{1}{3} \int_0^\infty (x_1^3+2x_1^2)e^{-x_1} dx_1 = \frac{1}{3}(\Gamma(4) + 2\Gamma(3)) = \frac{1}{3}(6+4) = \frac{10}{3}$$
$$Var(X_1|X_2=2) = E(X_1^2|X_2=2) - [E(X_1|X_2=2)]^2 = \frac{10}{3} - (\frac{4}{3})^2 = \frac{10}{3} - \frac{16}{9} = \frac{30-16}{9} = \frac{14}{9}$$
$$\boxed{ Var(X_1|X_2=2) = \frac{14}{9} }$$ **Correlation:**
$$E(X_1X_2) = \int_0^\infty \int_0^\infty x_1x_2 \frac{1}{2}(x_1+x_2)e^{-x_1}e^{-x_2} dx_1 dx_2 = \frac{1}{2} \int_0^\infty \int_0^\infty (x_1^2x_2+x_1x_2^2)e^{-x_1}e^{-x_2} dx_1 dx_2$$
$$= \frac{1}{2} \left[ \int x_1^2e^{-x_1}dx_1 \int x_2e^{-x_2}dx_2 + \int x_1e^{-x_1}dx_1 \int x_2^2e^{-x_2}dx_2 \right]$$
$$= \frac{1}{2} [ (\Gamma(3)\Gamma(2)) + (\Gamma(2)\Gamma(3)) ] = \frac{1}{2} [ (2)(1) + (1)(2) ] = \frac{4}{2} = 2$$
$$\text{Cov}(X_1,X_2) = E(X_1X_2) - E(X_1)E(X_2) = 2 - (\frac{3}{2})(\frac{3}{2}) = 2 - \frac{9}{4} = -\frac{1}{4}$$
$$\rho_{X_1,X_2} = \frac{\text{Cov}}{\sqrt{V_1 V_2}} = \frac{-1/4}{\sqrt{(7/4)(7/4)}} = \frac{-1/4}{7/4} = -\frac{1}{7}$$
$$\boxed{ \rho_{X_1,X_2} = -\frac{1}{7} }$$

Question 15
===========

**Problem:** BVN(-1, 1, 4, 9, -0.5). Find $E\{(X+1)^2(Y-1)^2\}$,
$P(X<1)$, $P(Y>4)$, $P(-3/2<X<-1/2|Y=3/2)$, $P(1/2<Y<3/2|X=-1/2)$.

**Solution:**
$$\mu_X=-1, \mu_Y=1, \sigma_X^2=4, \sigma_Y^2=9, \rho=-0.5$$
**$E\{(X+1)^2(Y-1)^2\}$:** Let $U = X-\mu_X = X+1$ and
$V = Y-\mu_Y = Y-1$. We want $E[U^2 V^2]$.\
**Concept: Law of Total Expectation**
$$E[U^2 V^2] = E[E[U^2 V^2 | Y]] = E[V^2 E[U^2 | Y]]$$
$U|Y=y \implies (X+1)|Y=y$. The conditional dist $X|Y=y$ is Normal.
$$E(X|Y=y) = \mu_X + \rho\frac{\sigma_X}{\sigma_Y}(y-\mu_Y) = -1 - 0.5(\frac{2}{3})(y-1) = -1 - \frac{y-1}{3} = \frac{-3-y+1}{3} = \frac{-2-y}{3}$$
$$V(X|Y=y) = \sigma_X^2(1-\rho^2) = 4(1 - (-0.5)^2) = 4(1-0.25) = 4(0.75) = 3$$
So $$X|Y=y \sim N(\frac{-2-y}{3}, 3)$$ $$U|Y=y = (X+1)|Y=y$$ This is
$$N(E(X|Y=y)+1, V(X|Y=y)) = N(\frac{-2-y}{3}+1, 3) = N(\frac{1-y}{3}, 3)$$
$$E[U^2 | Y] = V(U|Y) + [E(U|Y)]^2 = 3 + (\frac{1-Y}{3})^2 = 3 + \frac{(Y-1)^2}{9}$$
Now substitute this back. We want $E[V^2 \cdot (3 + \frac{V^2}{9})]$,
where $V=Y-1$ $$V = Y-1 \sim N(0, \sigma_Y^2) = N(0, 9)$$
$$E[3V^2 + \frac{V^4}{9}] = 3E[V^2] + \frac{1}{9}E[V^4]$$ For
$$V \sim N(0, 9),E[V^2] = V(V) = 9$$
$$E[V^4] = 3(V(V))^2 = 3(9^2) = 243$$
$$E[U^2 V^2] = 3(9) + \frac{1}{9}(243) = 27 + 27 = 54$$ *Solution key
has $\{ \frac{(1-Y)^2}{9} + 9 \}$. Why 9?
$E[U^2|Y] = V(U|Y) + [E(U|Y)]^2 = 3 + (\frac{1-y}{3})^2$. The key's
$V(U|Y)$ is 9, mine is 3. $V(X|Y=y) = 3$.
$V(U|Y) = V(X+1|Y) = V(X|Y) = 3$. The key is wrong.*
$$\boxed{ E\{(X+1)^2(Y-1)^2\} = 54 }$$ **$P(X<1)$:** $X \sim N(-1, 4)$.
$P(X<1) = P(Z < \frac{1 - (-1)}{2}) = P(Z < 1) = \Phi(1)$.
$$\boxed{ P(X<1) = 0.8413 }$$ **$P(Y>4)$:** $Y \sim N(1, 9)$.
$P(Y>4) = P(Z > \frac{4-1}{3}) = P(Z > 1) = 1 - \Phi(1)$.
$$\boxed{ P(Y>4) = 0.1587 }$$ **$P(-3/2<X<-1/2|Y=3/2)$:**
$$X|Y=3/2 \sim N(E, V)\textit{ , }E = \frac{-2-(3/2)}{3} = \frac{-3.5}{3} = -7/6\textit{ , } V=3$$
$$P(-1.5 < X < -0.5 | Y=1.5) = P(\frac{-1.5 - (-7/6)}{\sqrt{3}} < Z < \frac{-0.5 - (-7/6)}{\sqrt{3}})$$
$$= P(\frac{-9/6 + 7/6}{\sqrt{3}} < Z < \frac{-3/6 + 7/6}{\sqrt{3}}) = P(\frac{-2/6}{\sqrt{3}} < Z < \frac{4/6}{\sqrt{3}}) = P(\frac{-1}{3\sqrt{3}} < Z < \frac{2}{3\sqrt{3}})$$
$$= P(-0.192 < Z < 0.385) = \Phi(0.39) - \Phi(-0.19) = 0.6517 - 0.4247 = 0.227$$
$$\boxed{ P(-3/2<X<-1/2|Y=3/2) \approx 0.227 }$$
**$P(1/2<Y<3/2|X=-1/2)$:**
$$Y|X=x \sim N(E, V)\textit{ , } E = \mu_Y + \rho\frac{\sigma_Y}{\sigma_X}(x-\mu_X) = 1 - 0.5(\frac{3}{2})(x+1) = 1 - 0.75(x+1)$$
$$E = 1 - 0.75(-0.5+1) = 1 - 0.75(0.5) = 1 - 0.375 = 0.625 = 5/8$$
$$V = \sigma_Y^2(1-\rho^2) = 9(1 - 0.25) = 9(0.75) = 6.75 = 27/4$$
$$P(0.5 < Y < 1.5 | X=-0.5) = P(\frac{0.5 - 0.625}{\sqrt{6.75}} < Z < \frac{1.5 - 0.625}{\sqrt{6.75}})$$
$$= P(\frac{-0.125}{2.598} < Z < \frac{0.875}{2.598}) = P(-0.048 < Z < 0.337) = \Phi(0.34) - \Phi(-0.05) = 0.6331 - 0.4801 = 0.153$$
*Solution key: $0.1132$. My $\Phi(-0.05)=0.4801$, key's is $0.5199$.
$\Phi(-0.05) = 1 - \Phi(0.05) = 1-0.5199 = 0.4801$. The key used
$\Phi(0.05)$ instead of $\Phi(-0.05)$*
$$\boxed{ P(1/2<Y<3/2|X=-1/2) \approx 0.153 }$$

Question 16
===========

**Problem:**
$f(x,y) \propto \text{Exp}\{-\frac{9}{16}[(x-1)^2 - \frac{2}{3}(x-1)(y-1) + (y-1)^2]\}$.
Find $P(4<2X+3Y<6)$, $E(X|Y=2)$, $V(Y|X=0)$.

**Solution:**\
**Concept: Identifying BVN Parameters from PDF**\
The exponent of a BVN is
$$-\frac{1}{2(1-\rho^2)} \left[ (\frac{x-\mu_X}{\sigma_X})^2 - 2\rho(\frac{x-\mu_X}{\sigma_X})(\frac{y-\mu_Y}{\sigma_Y}) + (\frac{y-\mu_Y}{\sigma_Y})^2 \right]$$
From $f(x,y)$, $\mu_X=1, \mu_Y=1$. The expression is
$$-\frac{9}{16 \cdot 2(1-\rho^2)} \left[ \frac{(x-1)^2}{1/(2 \cdot 9/16)} ... \right]$$
Let's factor:
$$-\frac{9}{16} [ (x-1)^2 - \frac{2}{3}(x-1)(y-1) + (y-1)^2 ]$$
Comparing $(x-1)^2$ to $(\frac{x-\mu_X}{\sigma_X})^2$, we have
$$\frac{1}{2(1-\rho^2)\sigma_X^2} = \frac{9}{16}$$ Comparing $(y-1)^2$
to $(\frac{y-\mu_Y}{\sigma_Y})^2$, we have
$$\frac{1}{2(1-\rho^2)\sigma_Y^2} = \frac{9}{16}$$ This implies
$\sigma_X^2 = \sigma_Y^2$. Let's call it $\sigma^2$. Comparing the
cross-term:
$$\frac{2\rho}{2(1-\rho^2)\sigma_X\sigma_Y} = \frac{9}{16} \cdot \frac{2}{3}$$
$$\frac{\rho}{(1-\rho^2)\sigma^2} = \frac{3}{8}$$ From
$\frac{1}{2(1-\rho^2)\sigma^2} = \frac{9}{16}$, we have
$\frac{1}{(1-\rho^2)\sigma^2} = \frac{9}{8}$\
Substitute this into the cross-term equation:
$$\rho \cdot (\frac{9}{8}) = \frac{3}{8} \implies 9\rho = 3 \implies \rho = 1/3$$
Now find
$$\sigma^2 \textit{ : } \frac{1}{2(1-(1/3)^2)\sigma^2} = \frac{9}{16} \implies \frac{1}{2(8/9)\sigma^2} = \frac{9}{16} \implies \frac{1}{(16/9)\sigma^2} = \frac{9}{16} \implies 16 = 9 \cdot (16/9)\sigma^2 \implies \sigma^2=1$$
Parameters: $$\mu_X=1, \mu_Y=1, \sigma_X^2=1, \sigma_Y^2=1, \rho=1/3$$
$$(X,Y) \sim \text{BVN}(1, 1, 1, 1, 1/3)$$

**$P(4<2X+3Y<6)$:**\
Let $W = 2X+3Y$. W is Normal. $$E(W) = 2E(X)+3E(Y) = 2(1)+3(1) = 5$$
$$V(W) = 2^2V(X)+3^2V(Y)+2(2)(3)\text{Cov}(X,Y) = 4V(X)+9V(Y)+12\rho\sigma_X\sigma_Y$$
$$V(W) = 4(1)+9(1)+12(1/3)(1)(1) = 4+9+4 = 17$$ $$W \sim N(5, 17)$$
$$P(4<W<6) = P(\frac{4-5}{\sqrt{17}} < Z < \frac{6-5}{\sqrt{17}}) = P(\frac{-1}{4.123} < Z < \frac{1}{4.123}) = P(-0.24 < Z < 0.24)$$
$$= \Phi(0.24) - \Phi(-0.24) = \Phi(0.24) - (1-\Phi(0.24)) = 2\Phi(0.24)-1 = 2(0.5948)-1 = 1.1896-1 = 0.1896$$
$$\boxed{ P(4<2X+3Y<6) \approx 0.1896 }$$ **$E(X|Y=2)$:**
$E(X|Y=y) = \mu_X + \rho\frac{\sigma_X}{\sigma_Y}(y-\mu_Y) = 1 + \frac{1}{3}(\frac{1}{1})(y-1) = 1 + \frac{y-1}{3}$.
$E(X|Y=2) = 1 + \frac{2-1}{3} = 1 + \frac{1}{3} = \frac{4}{3}$.
$$\boxed{ E(X|Y=2) = \frac{4}{3} }$$ **$V(Y|X=0)$:**
$V(Y|X=x) = \sigma_Y^2(1-\rho^2) = 1(1 - (1/3)^2) = 1 - 1/9 = 8/9$.
(Constant, independent of X=0). $$\boxed{ V(Y|X=0) = \frac{8}{9} }$$

Question 17
===========

**Problem:** $f(x,y)=\frac{2x+y}{4}$ for $0<x<1, 0<y<2$. Find marginals,
conditionals, $P(|Y-X|>1)$, $\rho_{X,Y}$.\
*(Note: This is a standard joint PDF analysis, similar to Q2, Q3, Q11)*

**Solution:**\
**Marginals:**\
$$f_X(x) = \int_0^2 \frac{2x+y}{4} dy = \frac{1}{4} [2xy + \frac{y^2}{2}]_0^2 = \frac{1}{4} [4x + 2] = x + \frac{1}{2} \textit{ for } 0<x<1$$
$$f_Y(y) = \int_0^1 \frac{2x+y}{4} dx = \frac{1}{4} [x^2+xy]_0^1 = \frac{1+y}{4}\textit{, for } 0<y<2$$
$$\boxed{ f_X(x) = x + \frac{1}{2}, \quad f_Y(y) = \frac{1+y}{4} }$$
**Conditionals:**
$$\boxed{ f_{X|Y}(x|y) = \frac{f(x,y)}{f_Y(y)} = \frac{(2x+y)/4}{(1+y)/4} = \frac{2x+y}{1+y}, \quad 0<x<1 }$$
$$\boxed{ f_{Y|X}(y|x) = \frac{f(x,y)}{f_X(x)} = \frac{(2x+y)/4}{(x+1/2)} = \frac{2x+y}{4x+2}, \quad 0<y<2 }$$
**$P(|Y-X|>1)$:**
$$\textit{Region is } Y-X > 1 \implies Y > X+1 \textit{ OR } X-Y > 1 \implies Y < X-1$$
1. $Y > X+1$: $\int_0^1 \int_{x+1}^{\min(2, \text{...})} ...\\$ Since
$x>0, x+1>1$. Max $x+1=2$. So
$$\int_0^1 \int_{x+1}^2 \frac{2x+y}{4} dy dx$$ 2. $Y < X-1$: $X > Y+1$.
Since $y>0$, $x>1$. But $x$ is only up to 1. This region has 0
probability.
$P(|Y-X|>1) = \int_0^1 \frac{1}{4} [2xy + \frac{y^2}{2}]_{x+1}^2 dx = \frac{1}{4} \int_0^1 [ (4x+2) - (2x(x+1) + \frac{(x+1)^2}{2}) ] dx$
$$= \frac{1}{4} \int_0^1 [ 4x+2 - (2x^2+2x) - \frac{x^2+2x+1}{2} ] dx = \frac{1}{8} \int_0^1 [ 8x+4 - 4x^2-4x - x^2-2x-1 ] dx$$
$$= \frac{1}{8} \int_0^1 (-5x^2 + 2x + 3) dx = \frac{1}{8} [-\frac{5x^3}{3} + x^2 + 3x]_0^1 = \frac{1}{8} [-\frac{5}{3} + 1 + 3] = \frac{1}{8} [4 - 5/3] = \frac{1}{8} [\frac{7}{3}] = \frac{7}{24}$$
$$\boxed{ P(|Y-X|>1) = \frac{7}{24} }$$ **$\rho_{X,Y}$:**
$$E(X) = \int_0^1 x(x+1/2) dx = [\frac{x^3}{3} + \frac{x^2}{4}]_0^1 = \frac{1}{3} + \frac{1}{4} = \frac{7}{12}$$
$$E(Y) = \int_0^2 y(\frac{1+y}{4}) dy = \frac{1}{4} \int_0^2 (y+y^2) dy = \frac{1}{4} [\frac{y^2}{2} + \frac{y^3}{3}]_0^2 = \frac{1}{4} [2 + 8/3] = \frac{1}{4} [\frac{14}{3}] = \frac{7}{6}$$
$$E(X^2) = \int_0^1 x^2(x+1/2) dx = [\frac{x^4}{4} + \frac{x^3}{6}]_0^1 = \frac{1}{4} + \frac{1}{6} = \frac{5}{12}$$
$$V(X) = 5/12 - (7/12)^2 = (60-49)/144 = 11/144$$
$$E(Y^2) = \int_0^2 y^2(\frac{1+y}{4}) dy = \frac{1}{4} \int_0^2 (y^2+y^3) dy = \frac{1}{4} [\frac{y^3}{3} + \frac{y^4}{4}]_0^2 = \frac{1}{4} [8/3 + 4] = \frac{1}{4} [20/3] = 5/3$$
$$V(Y) = 5/3 - (7/6)^2 = 5/3 - 49/36 = (60-49)/36 = 11/36$$
$$E(XY) = \int_0^1 \int_0^2 xy \frac{2x+y}{4} dy dx = \frac{1}{4} \int_0^1 x \int_0^2 (2xy+y^2) dy dx = \frac{1}{4} \int_0^1 x [xy^2 + \frac{y^3}{3}]_0^2 dx$$
$$= \frac{1}{4} \int_0^1 x (4x + 8/3) dx = \frac{1}{4} \int_0^1 (4x^2 + 8x/3) dx = \frac{1}{4} [\frac{4x^3}{3} + \frac{8x^2}{6}]_0^1 = \frac{1}{4} [\frac{4}{3} + \frac{4}{3}] = \frac{1}{4} \cdot \frac{8}{3} = \frac{2}{3}$$
$$\text{Cov}(X,Y) = E(XY) - E(X)E(Y) = \frac{2}{3} - (\frac{7}{12})(\frac{7}{6}) = \frac{2}{3} - \frac{49}{72} = \frac{48-49}{72} = -\frac{1}{72}$$
$$\rho_{X,Y} = \frac{-1/72}{\sqrt{(11/144)(11/36)}} = \frac{-1/72}{(11 / (12 \cdot 6))} = \frac{-1/72}{11/72} = -\frac{1}{11}$$
$$\boxed{ \rho_{X,Y} = -\frac{1}{11} }$$
