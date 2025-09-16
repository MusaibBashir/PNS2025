---
title: Assignment 5
nav_order: 6
---

Question 1
==========

**Problem:** Let X be a continuous random variable with the density
function $f_X(x) = \frac{2(x+1)}{9}$ for $-1 < x < 2$. Find the density
function of $Y=X^2$.

**Solution:** We use the transformation method. The support of $X$ is
$(-1, 2)$, so the support of $Y=X^2$ is $[0, 4)$. We consider two cases
for the value of $y$.

**Case 1: $0 \le y < 1$** For a given value of $y$ in this range, there
are two inverse images from the transformation $y=x^2$:
$x_1 = -\sqrt{y}$ and $x_2 = \sqrt{y}$. Both of these values lie within
the support of $X$. The derivative of the inverse function is
$|\frac{dx}{dy}| = \frac{1}{2\sqrt{y}}$. The PDF of Y is given by:
$$f_Y(y) = f_X(x_1)\left|\frac{dx_1}{dy}\right| + f_X(x_2)\left|\frac{dx_2}{dy}\right|$$
$$f_Y(y) = \frac{2(-\sqrt{y}+1)}{9} \cdot \frac{1}{2\sqrt{y}} + \frac{2(\sqrt{y}+1)}{9} \cdot \frac{1}{2\sqrt{y}}$$
$$f_Y(y) = \frac{1}{9\sqrt{y}} (-\sqrt{y}+1+\sqrt{y}+1) = \frac{2}{9\sqrt{y}}$$

**Case 2: $1 \le y < 4$** For a value of $y$ in this range, there is
only one inverse image that lies in the support of $X$: $x = \sqrt{y}$
(since $-\sqrt{y}$ would be less than -1).
$$f_Y(y) = f_X(\sqrt{y})\left|\frac{dx}{dy}\right| = \frac{2(\sqrt{y}+1)}{9} \cdot \frac{1}{2\sqrt{y}} = \frac{\sqrt{y}+1}{9\sqrt{y}} = \frac{1}{9}\left(1 + \frac{1}{\sqrt{y}}\right)$$

Combining these results, the PDF of $Y$ is: $$\boxed{
f_Y(y) = 
\begin{cases} 
\frac{2}{9\sqrt{y}} & 0 \le y < 1 \\
\frac{1}{9}\left(1 + \frac{1}{\sqrt{y}}\right) & 1 \le y < 4 \\
0 & \text{otherwise}
\end{cases}
}$$

Question 2
==========

**Problem:** Let X be a continuous random variable with the density
$f_X(x)=\begin{cases}\frac{x}{2}&0<x\le1\\ \frac{1}{2}&1<x\le2\\ \frac{3-x}{2}&2<x<3\end{cases}$.
Find the density of $Y=(X-\frac{3}{2})^{2}$.

**Solution:** The transformation is $Y = (X - 3/2)^2$. The support of
$X$ is $(0, 3)$, so the support of $(X-3/2)$ is $(-3/2, 3/2)$, and the
support of $Y$ is $[0, 9/4)$. The inverse transformation gives
$X - 3/2 = \pm\sqrt{Y}$, so $x = \frac{3}{2} \pm \sqrt{y}$. The Jacobian
is $|\frac{dx}{dy}| = \frac{1}{2\sqrt{y}}$.

**Case 1: $0 \le y \le 1/4$** The inverse images are
$x_1 = \frac{3}{2} - \sqrt{y}$ and $x_2 = \frac{3}{2} + \sqrt{y}$. For
$y \in [0, 1/4]$, both $x_1$ and $x_2$ fall in the interval $[1, 2]$,
where $f_X(x) = 1/2$.
$$f_Y(y) = f_X(x_1)\left|\frac{dx}{dy}\right| + f_X(x_2)\left|\frac{dx}{dy}\right| = \frac{1}{2} \cdot \frac{1}{2\sqrt{y}} + \frac{1}{2} \cdot \frac{1}{2\sqrt{y}} = \frac{1}{2\sqrt{y}}$$

**Case 2: $1/4 < y < 9/4$** The inverse images
$x_1 = \frac{3}{2} - \sqrt{y}$ and $x_2 = \frac{3}{2} + \sqrt{y}$ fall
outside the interval $[1, 2]$. Specifically, $x_1 \in (0, 1)$ and
$x_2 \in (2, 3)$. For $x_1$,
$f_X(x_1) = x_1/2 = \frac{1}{2}(\frac{3}{2} - \sqrt{y})$. For $x_2$,
$f_X(x_2) = (3-x_2)/2 = \frac{1}{2}(3 - (\frac{3}{2} + \sqrt{y})) = \frac{1}{2}(\frac{3}{2} - \sqrt{y})$.
$$f_Y(y) = \left[\frac{1}{2}\left(\frac{3}{2}-\sqrt{y}\right)\right]\frac{1}{2\sqrt{y}} + \left[\frac{1}{2}\left(\frac{3}{2}-\sqrt{y}\right)\right]\frac{1}{2\sqrt{y}} = 2 \cdot \frac{\frac{3}{2}-\sqrt{y}}{4\sqrt{y}} = \frac{3}{4\sqrt{y}} - \frac{1}{2}$$

The complete PDF for Y is: $$\boxed{
f_Y(y) = 
\begin{cases} 
\frac{1}{2\sqrt{y}} & 0 \le y \le 1/4 \\
\frac{3}{4\sqrt{y}} - \frac{1}{2} & 1/4 < y < 9/4 \\
0 & \text{otherwise}
\end{cases}
}$$

Question 3
==========

**Problem:** Let X be a random variable with the density function
$f_X(x) = \frac{2x}{\pi^2}$ for $0 < x < \pi$. Find the distribution of
$Y=\sin(X)$.

**Solution:** The transformation is $Y=\sin(X)$. Since $X \in (0, \pi)$,
the support of $Y$ is $(0, 1]$. For any $y \in (0, 1)$, there are two
inverse images in the support of X: $x_1 = \arcsin(y)$ and
$x_2 = \pi - \arcsin(y)$. The derivative is
$\frac{dx}{dy} = \frac{1}{\sqrt{1-y^2}}$. So,
$|\frac{dx_1}{dy}| = \frac{1}{\sqrt{1-y^2}}$ and
$|\frac{dx_2}{dy}| = |-\frac{1}{\sqrt{1-y^2}}| = \frac{1}{\sqrt{1-y^2}}$.
The PDF of Y is:
$$f_Y(y) = f_X(x_1)\left|\frac{dx_1}{dy}\right| + f_X(x_2)\left|\frac{dx_2}{dy}\right|$$
$$f_Y(y) = \frac{2(\arcsin y)}{\pi^2} \cdot \frac{1}{\sqrt{1-y^2}} + \frac{2(\pi - \arcsin y)}{\pi^2} \cdot \frac{1}{\sqrt{1-y^2}}$$
$$f_Y(y) = \frac{2}{\pi^2\sqrt{1-y^2}}(\arcsin y + \pi - \arcsin y) = \frac{2\pi}{\pi^2\sqrt{1-y^2}}$$
$$\boxed{
f_Y(y) = 
\begin{cases} 
\frac{2}{\pi\sqrt{1-y^2}} & 0 < y \le 1 \\
0 & \text{otherwise}
\end{cases}
}$$

Question 4
==========

**Problem:** Let $X \sim Bin(n, p)$. Find the p.m.f. of (a) $Y_1=3X+4$;
(b) $Y_2=X-3$; (c) $Y_3=X^2+2$; (d) $Y_4=\sqrt{X}$.

**Solution:** The PMF of X is $P(X=k) = \binom{n}{k}p^k(1-p)^{n-k}$ for
$k \in \{0, 1, \dots, n\}$. We use the direct method for discrete
transformations.

\(a\) $Y_1=3X+4$: The inverse is $X = (Y_1-4)/3$. The support for $Y_1$
is $\{4, 7, 10, \dots, 3n+4\}$.
$$\boxed{ P(Y_1=y) = \binom{n}{(y-4)/3}p^{(y-4)/3}(1-p)^{n-(y-4)/3}, \quad y \in \{4, 7, \dots, 3n+4\} }$$

\(b\) $Y_2=X-3$: The inverse is $X = Y_2+3$. The support for $Y_2$ is
$\{-3, -2, \dots, n-3\}$.
$$\boxed{ P(Y_2=y) = \binom{n}{y+3}p^{y+3}(1-p)^{n-y-3}, \quad y \in \{-3, -2, \dots, n-3\} }$$

\(c\) $Y_3=X^2+2$: The inverse is $X = \sqrt{Y_3-2}$ (since $X \ge 0$).
The support for $Y_3$ is $\{2, 3, 6, \dots, n^2+2\}$.
$$\boxed{ P(Y_3=y) = \binom{n}{\sqrt{y-2}}p^{\sqrt{y-2}}(1-p)^{n-\sqrt{y-2}}, \quad y \in \{k^2+2 | k=0, \dots, n\} }$$

\(d\) $Y_4=\sqrt{X}$: The inverse is $X = Y_4^2$. The support for $Y_4$
is $\{0, 1, \sqrt{2}, \dots, \sqrt{n}\}$.
$$\boxed{ P(Y_4=y) = \binom{n}{y^2}p^{y^2}(1-p)^{n-y^2}, \quad y \in \{\sqrt{k} | k=0, \dots, n\} }$$

Question 5
==========

**Problem:** Let $X \sim \text{Beta}(a,b)$. Find the distributions of
$Y_1 = 1-X$ and $Y_2 = \frac{1}{1+X}$.

**Solution:** The PDF of $X$ is
$f_X(x) = \frac{1}{B(a,b)}x^{a-1}(1-x)^{b-1}$ for $0 < x < 1$.

**For $Y_1 = 1-X$:** The support for $Y_1$ is $(0, 1)$. The inverse is
$X = 1-Y_1$. The Jacobian is $|\frac{dx}{dy_1}| = |-1| = 1$.
$$f_{Y_1}(y) = f_X(1-y) \cdot 1 = \frac{1}{B(a,b)}(1-y)^{a-1}(1-(1-y))^{b-1} = \frac{1}{B(a,b)}y^{b-1}(1-y)^{a-1}$$
This is the PDF of a Beta distribution with parameters swapped.
$$\boxed{ Y_1 \sim \text{Beta}(b, a) }$$

**For $Y_2 = \frac{1}{1+X}$:** The support for $Y_2$ is $(1/2, 1)$. The
inverse is $X = \frac{1}{Y_2} - 1 = \frac{1-Y_2}{Y_2}$. The Jacobian is
$|\frac{dx}{dy_2}| = |-\frac{1}{y_2^2}| = \frac{1}{y_2^2}$.
$$f_{Y_2}(y) = f_X\left(\frac{1-y}{y}\right)\left|\frac{dx}{dy}\right| = \frac{1}{B(a,b)}\left(\frac{1-y}{y}\right)^{a-1}\left(1-\frac{1-y}{y}\right)^{b-1} \frac{1}{y^2}$$
$$f_{Y_2}(y) = \frac{1}{B(a,b)}\frac{(1-y)^{a-1}}{y^{a-1}}\left(\frac{y-(1-y)}{y}\right)^{b-1} \frac{1}{y^2} = \frac{1}{B(a,b)}\frac{(1-y)^{a-1}(2y-1)^{b-1}}{y^{a-1}y^{b-1}y^2}$$
$$\boxed{ f_{Y_2}(y) = \frac{(1-y)^{a-1}(2y-1)^{b-1}}{B(a,b) y^{a+b}}, \quad \frac{1}{2} < y < 1 }$$

Question 6
==========

**Problem:** Let C be uniformly distributed over $(15, 21)$. Let
$F = \frac{9}{5}C+32$. Find the density of F.

**Solution:** The PDF of C is $f_C(c) = \frac{1}{21-15} = \frac{1}{6}$
for $15 < c < 21$. This is a linear transformation. First, find the
support of F. When $c=15, F = \frac{9}{5}(15)+32 = 59$. When
$c=21, F = \frac{9}{5}(21)+32 = 69.8$. So, $F \in (59, 69.8)$. The
inverse transformation is $C = \frac{5}{9}(F-32)$. The Jacobian is
$|\frac{dC}{dF}| = \frac{5}{9}$. The PDF of F is:
$$f_F(f) = f_C\left(\frac{5}{9}(f-32)\right) \left|\frac{dC}{dF}\right| = \frac{1}{6} \cdot \frac{5}{9} = \frac{5}{54}$$
Thus, F is also uniformly distributed.
$$\boxed{ f_F(f) = \frac{5}{54}, \quad 59 < f < 69.8 }$$

Question 7
==========

**Problem:** Let X have density $f_X(x)=cx^2e^{-bx^2}$ for $x>0$. Find
the density of kinetic energy $Y = \frac{1}{2}mX^2$.

**Solution:** The support of $X$ is $(0, \infty)$, so the support of $Y$
is also $(0, \infty)$. The transformation is one-to-one on the support
of X. Inverse transformation:
$X^2 = \frac{2Y}{m} \implies X = \sqrt{\frac{2Y}{m}}$ (since $x>0$).
Jacobian:
$\frac{dX}{dY} = \sqrt{\frac{2}{m}} \cdot \frac{1}{2\sqrt{Y}} = \frac{1}{\sqrt{2mY}}$.
The PDF of Y is:
$$f_Y(y) = f_X\left(\sqrt{\frac{2y}{m}}\right) \left|\frac{dX}{dY}\right| = c\left(\sqrt{\frac{2y}{m}}\right)^2 e^{-b(\sqrt{2y/m})^2} \cdot \frac{1}{\sqrt{2mY}}$$
$$f_Y(y) = c\left(\frac{2y}{m}\right) e^{-2by/m} \frac{1}{\sqrt{2m}\sqrt{y}} = \frac{2c}{m\sqrt{2m}} y^{1/2} e^{-2by/m}$$
$$\boxed{ f_Y(y) = \frac{\sqrt{2}c}{m^{3/2}} \sqrt{y} e^{-2by/m}, \quad y>0 }$$
This is a Gamma distribution, $Y \sim \text{Gamma}(k=3/2, \theta=m/2b)$.

Question 8
==========

**Problem:** Let X have the pdf
$f_X(x)=\begin{cases}\frac{x+1}{4}&-1<x\le1\\ \frac{3-x}{4}&1<x<3\end{cases}$.
Find the distribution of $Y=|X|$.

**Solution:** The support of $X$ is $(-1, 3)$, so the support for
$Y=|X|$ is $[0, 3)$. We use the CDF method:
$F_Y(y) = P(Y \le y) = P(-y \le X \le y) = \int_{-y}^y f_X(x)dx$.

**Case 1: $0 \le y \le 1$** The interval $(-y, y)$ is contained in
$(-1, 1)$, where $f_X(x) = (x+1)/4$.
$$F_Y(y) = \int_{-y}^y \frac{x+1}{4}dx = \frac{1}{4}\left[\frac{x^2}{2}+x\right]_{-y}^y = \frac{1}{4}\left[\left(\frac{y^2}{2}+y\right) - \left(\frac{y^2}{2}-y\right)\right] = \frac{2y}{4} = \frac{y}{2}$$
Differentiating gives the PDF:
$f_Y(y) = \frac{d}{dy}(\frac{y}{2}) = \frac{1}{2}$.

**Case 2: $1 < y < 3$** The interval is $(-y, y)$. Since $X$ cannot be
less than -1, the integral is from -1 to y.
$$F_Y(y) = \int_{-1}^y f_X(x)dx = \int_{-1}^1 \frac{x+1}{4}dx + \int_1^y \frac{3-x}{4}dx$$
$$F_Y(y) = \frac{1}{4}\left[\frac{x^2}{2}+x\right]_{-1}^1 + \frac{1}{4}\left[3x-\frac{x^2}{2}\right]_1^y = \frac{1}{2} + \frac{1}{4}\left[(3y-\frac{y^2}{2}) - (3-\frac{1}{2})\right] = \frac{3y}{4}-\frac{y^2}{8}-\frac{1}{8}$$
Differentiating gives the PDF:
$f_Y(y) = \frac{d}{dy}\left(\frac{3y}{4}-\frac{y^2}{8}-\frac{1}{8}\right) = \frac{3}{4} - \frac{y}{4} = \frac{3-y}{4}$.

The complete PDF for Y is: $$\boxed{
f_Y(y) = 
\begin{cases} 
\frac{1}{2} & 0 \le y \le 1 \\
\frac{3-y}{4} & 1 < y < 3 \\
0 & \text{otherwise}
\end{cases}
}$$

Question 9
==========

**Problem:** Let X be a standard normal random variable and
$Y = \begin{cases} \frac{\sqrt{X}}{2} & X \ge 0 \\ -\sqrt{|X|} & X < 0 \end{cases}$.
Find the pdf of Y.

**Solution:** **Concept: Transformation of Variables (Piecewise
Function)** We need to find the probability density function (PDF) of Y,
which is defined as a piecewise function of a standard normal random
variable X. We will use the change of variable method, applying it
separately to the two cases defined by the transformation. The general
formula for a one-to-one transformation $Y=g(X)$ is
$f_Y(y) = f_X(g^{-1}(y)) \left| \frac{d}{dy}g^{-1}(y) \right|$.

**1. Define the PDF of X:** X is a standard normal random variable, so
its PDF is:
$$f_X(x) = \frac{1}{\sqrt{2\pi}} e^{-x^2/2}, \quad -\infty < x < \infty$$

**2. Analyze the Transformation in Two Cases:** We handle the positive
and negative ranges of Y separately, as they correspond to different
parts of the transformation.

**Case 1: $y \ge 0$** A non-negative value of $y$ can only be produced
by the first part of the transformation, where $X \ge 0$. The
transformation is $Y = \frac{\sqrt{X}}{2}$.

-   **Inverse Transformation:** We solve for x in terms of y.
    $$y = \frac{\sqrt{x}}{2} \implies 2y = \sqrt{x} \implies x = (2y)^2 = 4y^2$$
    The inverse function is $x = g_1^{-1}(y) = 4y^2$.

-   **Jacobian:** We find the derivative of the inverse function.
    $$\frac{dx}{dy} = \frac{d}{dy}(4y^2) = 8y$$ The absolute value of
    the Jacobian is $|\frac{dx}{dy}| = |8y| = 8y$ (since $y \ge 0$).

-   **Apply Formula:** We substitute $x=4y^2$ into the PDF of X and
    multiply by the Jacobian.
    $$f_Y(y) = f_X(4y^2) \left| \frac{dx}{dy} \right| = \frac{1}{\sqrt{2\pi}} e^{-(4y^2)^2/2} \cdot (8y) = \frac{8y}{\sqrt{2\pi}} e^{-16y^4/2}$$
    $$f_Y(y) = \frac{8y}{\sqrt{2\pi}} e^{-8y^4}, \quad \text{for } y \ge 0$$

**Case 2: $y < 0$** A negative value of $y$ can only be produced by the
second part of the transformation, where $X < 0$. The transformation is
$Y = -\sqrt{|X|}$. Since $X < 0$, $|X| = -X$. So, $Y = -\sqrt{-X}$.

-   **Inverse Transformation:** We solve for x in terms of y.
    $$y = -\sqrt{-x} \implies -y = \sqrt{-x} \quad (\text{Note: } -y > 0, \text{ so this is valid})$$
    $$(-y)^2 = -x \implies y^2 = -x \implies x = -y^2$$ The inverse
    function is $x = g_2^{-1}(y) = -y^2$.

-   **Jacobian:** We find the derivative of the inverse function.
    $$\frac{dx}{dy} = \frac{d}{dy}(-y^2) = -2y$$ The absolute value of
    the Jacobian is $|\frac{dx}{dy}| = |-2y| = -2y$ (since $y < 0$,
    $-2y$ is positive).

-   **Apply Formula:** We substitute $x=-y^2$ into the PDF of X and
    multiply by the Jacobian.
    $$f_Y(y) = f_X(-y^2) \left| \frac{dx}{dy} \right| = \frac{1}{\sqrt{2\pi}} e^{-(-y^2)^2/2} \cdot (-2y)$$
    $$f_Y(y) = \frac{-2y}{\sqrt{2\pi}} e^{-y^4/2}, \quad \text{for } y < 0$$

**3. Combine the Results:** We combine the two pieces to form the
complete probability density function for Y. $$\boxed{
f_Y(y) = 
\begin{cases} 
\frac{-2y}{\sqrt{2\pi}}e^{-y^4/2} & y < 0 \\
\\
\frac{8y}{\sqrt{2\pi}}e^{-8y^4} & y \ge 0
\end{cases}
}$$

Question 10
===========

**Problem:** Let X be a discrete random variable. Find the distribution
of $Y=X^2$.

**Solution:** To find the PMF of $Y=X^2$, we sum the probabilities of
the values of $X$ that map to each value of $y$. The PMF of X,
$p_X(k)=P(X=k)$, is not clearly specified in the problem statement.
However, the general method is as follows: The possible values for $Y$
are the squares of the possible values of $X$. The PMF of $Y$, $p_Y(y)$,
is found by:
$$P(Y=y) = P(X^2=y) = P(X=\sqrt{y}) + P(X=-\sqrt{y}) \quad \text{for } y > 0$$
$$P(Y=0) = P(X=0)$$ For any value $y$ in the support of $Y$, its
probability is:
$$\boxed{ p_Y(y) = \begin{cases} p_X(0) & \text{if } y=0 \\ p_X(\sqrt{y}) + p_X(-\sqrt{y}) & \text{if } y=k^2 \text{ for integer } k>0 \\ 0 & \text{otherwise} \end{cases} }$$
The median of Y is the value $m$ such that $P(Y \le m) \ge 0.5$ and
$P(Y \ge m) \ge 0.5$. This would be found by calculating the CDF of Y
from its PMF and finding the point where it crosses 0.5.

Question 11
===========

**Problem:** Let X have p.d.f. $f_X(x) = k\sqrt{x}$ for $0<x<1$. Find
the pdf of $Y=\sqrt[4]{X}$.

**Solution:** First, we find the constant $k$ by ensuring the PDF
integrates to 1.
$$\int_0^1 k\sqrt{x} dx = k \left[\frac{x^{3/2}}{3/2}\right]_0^1 = k\frac{2}{3} = 1 \implies k = \frac{3}{2}$$
So, $f_X(x) = \frac{3}{2}\sqrt{x}$ for $0<x<1$. The transformation is
$Y = X^{1/4}$. The support of $Y$ is $(0, 1)$. The inverse is $X = Y^4$.
The Jacobian is $|\frac{dX}{dY}| = |4y^3| = 4y^3$. The PDF of Y is:
$$f_Y(y) = f_X(y^4)\left|\frac{dX}{dY}\right| = \left(\frac{3}{2}\sqrt{y^4}\right)(4y^3) = \frac{3}{2}y^2 \cdot 4y^3 = 6y^5$$
$$\boxed{
f_Y(y) = 
\begin{cases} 
6y^5 & 0 < y < 1 \\
0 & \text{otherwise}
\end{cases}
}$$

Question 12
===========

**Problem:** Let X follow a uniform distribution on $(-1, 1)$. Let
$Y=-2\log_e|X|$. Find $E(Y)$.

**Solution:** The PDF of $X$ is $f_X(x) = 1/2$ for $-1 < x < 1$. We find
the expected value of the function of X using the definition
$E[g(X)] = \int g(x)f_X(x)dx$.
$$E[Y] = E[-2\ln|X|] = \int_{-1}^1 (-2\ln|x|) \cdot \frac{1}{2} dx = -\int_{-1}^1 \ln|x| dx$$
Since $\ln|x|$ is an even function, we can write the integral as:
$$E[Y] = -2 \int_0^1 \ln(x) dx$$ We use integration by parts,
$\int u dv = uv - \int v du$. Let $u=\ln(x)$ and $dv=dx$. Then
$du = (1/x)dx$ and $v=x$.
$$\int \ln(x)dx = x\ln(x) - \int x \cdot \frac{1}{x} dx = x\ln(x) - x$$
Now we evaluate the definite integral:
$$E[Y] = -2 [x\ln(x) - x]_0^1 = -2\left( (1\ln(1)-1) - \lim_{x\to0^+}(x\ln(x)-x) \right)$$
The limit $\lim_{x\to0^+} x\ln(x)$ is 0 (can be shown with L'Hopital's
rule). So the expression evaluates to:
$$E[Y] = -2( (0-1) - (0-0) ) = -2(-1) = 2$$ $$\boxed{ E[Y] = 2 }$$
