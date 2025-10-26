---
title: Assignment 7
nav_order: 8
---

Question 1
==========

**Problem:** Given the joint pmf of (X, Y). Find the joint pmf of (U, V)
where $U=|X|, V=Y^2$. Evaluate E(X), E(Y), Var(X), Var(Y), Cov(X,Y),
$\rho_{X,Y}$. Also find E(U), E(V), Var(U), Var(V), Cov(U,V),
$\rho_{U,V}$.\
**Solution:**\
**1. Joint PMF Table (X, Y):**\

  $Y \setminus X$      -1       0        1
  ----------------- -------- -------- --------
  -2                 $1/6$    $1/12$   $1/6$
  1                  $1/6$    $1/12$   $1/6$
  2                  $1/12$     0      $1/12$

**2. Marginals and Moments for (X, Y):**\
$$p_X(-1) = 1/6 + 1/6 + 1/12 = 5/12$$
$$p_X(0) = 1/12 + 1/12 + 0 = 2/12 = 1/6$$
$$p_X(1) = 1/6 + 1/6 + 1/12 = 5/12$$
$$p_Y(-2) = 1/6 + 1/12 + 1/6 = 5/12$$
$$p_Y(1) = 1/6 + 1/12 + 1/6 = 5/12$$
$$p_Y(2) = 1/12 + 0 + 1/12 = 2/12 = 1/6$$
$$E(X) = (-1)(5/12) + 0(1/6) + 1(5/12) = 0$$
$$E(X^2) = (-1)^2(5/12) + 0^2(1/6) + 1^2(5/12) = 5/12 + 5/12 = 10/12 = 5/6$$
$$Var(X) = E(X^2) - [E(X)]^2 = 5/6 - 0^2 = 5/6$$
$$E(Y) = (-2)(5/12) + 1(5/12) + 2(1/6) = -10/12 + 5/12 + 4/12 = -1/12$$
$$E(Y^2) = (-2)^2(5/12) + 1^2(5/12) + 2^2(1/6) = (4)(5/12) + 5/12 + 4(2/12) = 20/12 + 5/12 + 8/12 = 33/12 = 11/4$$
$$Var(Y) = E(Y^2) - [E(Y)]^2 = 11/4 - (-1/12)^2 = 11/4 - 1/144 = (396-1)/144 = 395/144$$
$$E(XY) = \sum x y p(x,y) = (-1)(-2)(1/6) + (1)(-2)(1/6) + (-1)(1)(1/6) + (1)(1)(1/6) + (-1)(2)(1/12) + (1)(2)(1/12)$$
$$E(XY) = 2/6 - 2/6 - 1/6 + 1/6 - 2/12 + 2/12 = 0$$
$$\text{Cov}(X,Y) = E(XY) - E(X)E(Y) = 0 - (0)(-1/12) = 0$$
$$\rho_{X,Y} = 0$$
$$\boxed{ \begin{gathered} E(X)=0, Var(X)=5/6, E(Y)=-1/12, Var(Y)=395/144 \\ Cov(X,Y)=0, \rho_{X,Y}=0 \end{gathered} }$$

**3. Transformation (U, V):**\
$U=|X|, V=Y^2$. Possible values for U are $\{0, 1\}$. Possible values
for V are $\{(-2)^2, 1^2, 2^2\} = \{1, 4\}$.\
**Nice Trick: Summing Probabilities for Transformation** To find
$P(U=u, V=v)$, sum $P(X=x, Y=y)$ for all $(x,y)$ pairs that map to
$(u,v)$.\

-   $P(U=0, V=1)$: Only $(X=0, Y=1)$ maps here. $P(0,1) = 1/12$.

-   $P(U=0, V=4)$: Mapped from $(X=0, Y=-2)$ and $(X=0, Y=2)$.
    $P(0,-2)+P(0,2) = 1/12 + 0 = 1/12$.

-   $P(U=1, V=1)$: Mapped from $(X=-1, Y=1)$ and $(X=1, Y=1)$.
    $P(-1,1)+P(1,1) = 1/6 + 1/6 = 2/6 = 1/3$.

-   $P(U=1, V=4)$: Mapped from
    $(X=-1, Y=-2), (X=1, Y=-2), (X=-1, Y=2), (X=1, Y=2)$.
    $P(-1,-2)+P(1,-2)+P(-1,2)+P(1,2) = 1/6 + 1/6 + 1/12 + 1/12 = 2/6 + 2/12 = 1/3 + 1/6 = 1/2$.

**Joint PMF Table (U, V):**
$$\boxed{ \begin{array}{|l|cc|} \hline V \setminus U & 0 & 1 \\ \hline 1 & 1/12 & 4/12 \\ 4 & 1/12 & 6/12 \\ \hline \end{array} }$$

**4. Marginals and Moments for (U, V):**
$$p_U(0) = 1/12 + 1/12 = 2/12 = 1/6$$ $$p_U(1) = 1/3 + 1/2 = 5/6$$
$$p_V(1) = 1/12 + 1/3 = 5/12$$ $$p_V(4) = 1/12 + 1/2 = 7/12$$
$$E(U) = 0(1/6) + 1(5/6) = 5/6$$ $$E(U^2) = 0^2(1/6) + 1^2(5/6) = 5/6$$
$$Var(U) = E(U^2) - [E(U)]^2 = 5/6 - (5/6)^2 = 5/6 - 25/36 = (30-25)/36 = 5/36$$
$$E(V) = 1(5/12) + 4(7/12) = 5/12 + 28/12 = 33/12 = 11/4$$
$$E(V^2) = 1^2(5/12) + 4^2(7/12) = 5/12 + 16(7/12) = 5/12 + 112/12 = 117/12 = 39/4$$
$$Var(V) = E(V^2) - [E(V)]^2 = 39/4 - (11/4)^2 = 39/4 - 121/16 = (156-121)/16 = 35/16$$
$$E(UV) = \sum u v p(u,v) = 0(1)(1/12) + 0(4)(1/12) + 1(1)(1/3) + 1(4)(1/2) = 0 + 0 + 1/3 + 2 = 7/3$$
$$\text{Cov}(U,V) = E(UV) - E(U)E(V) = 7/3 - (5/6)(11/4) = 7/3 - 55/24 = (56-55)/24 = 1/24$$
$$\rho_{U,V} = \frac{\text{Cov}(U,V)}{\sqrt{Var(U)Var(V)}} = \frac{1/24}{\sqrt{(5/36)(35/16)}} = \frac{1/24}{\sqrt{175/(36 \cdot 16)}} = \frac{1/24}{(\sqrt{25 \cdot 7}) / (6 \cdot 4)} = \frac{1/24}{(5\sqrt{7})/24} = \frac{1}{5\sqrt{7}}$$
$$\boxed{ \begin{gathered} E(U)=5/6, Var(U)=5/36, E(V)=11/4, Var(V)=35/16 \\ Cov(U,V)=1/24, \rho_{U,V}=\frac{1}{5\sqrt{7}} \approx 0.0756 \end{gathered} }$$

Question 2
==========

**Problem:** Projectiles hit $(X,Y)$ where $X, Y \sim N(0,1)$
independently. For two projectiles $(X_1, Y_1)$ and $(X_2, Y_2)$, find
the distribution of $Z^2$, where Z is the distance between hits.\
**Solution:**\
$$Z^2 = (X_1-X_2)^2 + (Y_1-Y_2)^2$$ Let $U = X_1-X_2$ and
$W = Y_1-Y_2$.\
Since $X_1, X_2$ are i.i.d $N(0,1)$,
$U \sim N(0-0, 1^2+1^2) = N(0, 2)$.\
Similarly, since $Y_1, Y_2$ are i.i.d $N(0,1)$,
$W \sim N(0-0, 1^2+1^2) = N(0, 2)$.\
Also, U and W are independent because $(X_1, Y_1)$ and $(X_2, Y_2)$ are
independent pairs.\
So $$Z^2 = U^2 + W^2$$ Let $U' = U/\sqrt{2}$ and $W' = W/\sqrt{2}$. Then
$U', W' \sim N(0,1)$ independently.\
$$Z^2 = (\sqrt{2}U')^2 + (\sqrt{2}W')^2 = 2(U'^2 + W'^2)$$ **Concept:
Chi-Squared Distribution**\
The square of a standard normal variable follows a Chi-Squared
distribution with 1 degree of freedom ($\chi^2_1$). The sum of k
independent $\chi^2_1$ variables follows a $\chi^2_k$ distribution.\
Here, $U'^2 \sim \chi^2_1$ and $W'^2 \sim \chi^2_1$. Therefore,
$T = U'^2 + W'^2 \sim \chi^2_2$.\
The PDF of a $\chi^2_k$ distribution is
$$f(t; k) = \frac{1}{2^{k/2}\Gamma(k/2)} t^{k/2-1}e^{-t/2}\text{ for }t>0$$
For $k=2$,
$$f_T(t) = \frac{1}{2^{1}\Gamma(1)} t^{1-1}e^{-t/2} = \frac{1}{2}e^{-t/2}\text{ for }t>0$$
This is an Exponential distribution with parameter $\lambda = 1/2$ (or
mean $\theta=2$).\
We have $Z^2 = 2T$. We need to find the distribution of $Z^2$. Let
$V = Z^2$.\
**Nice Trick: Scaling an Exponential Variable**\
If $T \sim \text{Exp}(\lambda)$, then $aT \sim \text{Exp}(\lambda/a)$.
Here $T \sim \text{Exp}(1/2)$, so
$V = 2T \sim \text{Exp}((1/2)/2) = \text{Exp}(1/4)$.\
The PDF of V ($=Z^2$) is $$f_V(v) = \frac{1}{4}e^{-v/4}\text{ for }v>0$$
$$\boxed{ Z^2 \sim \text{Exponential}(\lambda=1/4), \quad f_{Z^2}(v) = \frac{1}{4}e^{-v/4}, v>0 }$$

Question 3
==========

**Problem:** $X_1, X_2$ are i.i.d $\text{Exp}(\lambda)$. Find joint and
marginal distributions of $Y_1=X_1/X_2$ and $Y_2=X_1+X_2$. Are they
independent?\
**Solution:**\
**Concept: Jacobian Transformation**\
1. **Joint PDF of $(X_1, X_2)$:**
$$f(x_1, x_2) = (\lambda e^{-\lambda x_1})(\lambda e^{-\lambda x_2}) = \lambda^2 e^{-\lambda(x_1+x_2)}\text{ for }x_1>0, x_2>0$$
2. **Inverse Transformation:** From
$$Y_2=X_1+X_2 \implies X_1 = Y_2-X_2$$ Substitute into
$$Y_1=X_1/X_2: Y_1 = (Y_2-X_2)/X_2 = Y_2/X_2 - 1$$
$$Y_1+1 = Y_2/X_2 \implies X_2 = \frac{Y_2}{1+Y_1}$$ Then
$$X_1 = Y_2 - X_2 = Y_2 - \frac{Y_2}{1+Y_1} = Y_2(1 - \frac{1}{1+Y_1}) = \frac{Y_1 Y_2}{1+Y_1}$$
$$Region: X_1>0, X_2>0 \implies Y_1>0, Y_2>0$$ 3. **Jacobian:**
$$J = \det \begin{pmatrix} \frac{\partial x_1}{\partial y_1} & \frac{\partial x_1}{\partial y_2} \\ \frac{\partial x_2}{\partial y_1} & \frac{\partial x_2}{\partial y_2} \end{pmatrix} = \det \begin{pmatrix} \frac{y_2(1+y_1) - y_1y_2}{(1+y_1)^2} & \frac{y_1}{1+y_1} \\ \frac{-y_2}{(1+y_1)^2} & \frac{1}{1+y_1} \end{pmatrix} = \det \begin{pmatrix} \frac{y_2}{(1+y_1)^2} & \frac{y_1}{1+y_1} \\ \frac{-y_2}{(1+y_1)^2} & \frac{1}{1+y_1} \end{pmatrix}$$
$$J = \frac{y_2}{(1+y_1)^3} - \frac{-y_1 y_2}{(1+y_1)^3} = \frac{y_2(1+y_1)}{(1+y_1)^3} = \frac{y_2}{(1+y_1)^2}$$
$$|J| = \frac{y_2}{(1+y_1)^2} (\text{since } y_1, y_2 > 0)$$ 4. **Joint
PDF of $(Y_1, Y_2)$:**
$$f_{Y_1,Y_2}(y_1, y_2) = f_{X_1,X_2}(x_1(y_1,y_2), x_2(y_1,y_2)) |J|$$
$$f_{Y_1,Y_2}(y_1, y_2) = \lambda^2 e^{-\lambda(x_1+x_2)} |J| = \lambda^2 e^{-\lambda y_2} \frac{y_2}{(1+y_1)^2}$$
$$\boxed{ f_{Y_1,Y_2}(y_1, y_2) = \frac{\lambda^2 y_2 e^{-\lambda y_2}}{(1+y_1)^2}, \quad y_1 > 0, y_2 > 0 }$$
5. **Marginals and Independence:**
$$f_{Y_1}(y_1) = \int_0^\infty \frac{\lambda^2 y_2 e^{-\lambda y_2}}{(1+y_1)^2} dy_2 = \frac{1}{(1+y_1)^2} \int_0^\infty \lambda^2 y_2 e^{-\lambda y_2} dy_2$$
The integral $\int_0^\infty \lambda^2 y_2 e^{-\lambda y_2} dy_2$ is
$\Gamma(2)=1! = 1$. *(Recognize it relates to the Gamma(2, $\lambda$)
distribution PDF).*
$$\boxed{ f_{Y_1}(y_1) = \frac{1}{(1+y_1)^2}, \quad y_1 > 0 }$$ (This is
related to F(2,2)).
$$f_{Y_2}(y_2) = \int_0^\infty \frac{\lambda^2 y_2 e^{-\lambda y_2}}{(1+y_1)^2} dy_1 = \lambda^2 y_2 e^{-\lambda y_2} \int_0^\infty \frac{1}{(1+y_1)^2} dy_1$$
$\int_0^\infty (1+y_1)^{-2} dy_1 = [-(1+y_1)^{-1}]_0^\infty = 0 - (-1) = 1$.
$$\boxed{ f_{Y_2}(y_2) = \lambda^2 y_2 e^{-\lambda y_2}, \quad y_2 > 0 }$$
(This is Gamma(2, $\lambda$)). Check independence:
$f_{Y_1}(y_1) f_{Y_2}(y_2) = \frac{1}{(1+y_1)^2} \cdot \lambda^2 y_2 e^{-\lambda y_2} = f_{Y_1,Y_2}(y_1, y_2)$.
$$\boxed{ \text{Yes, } Y_1 \text{ and } Y_2 \text{ are independent.} }$$

Question 4
==========

**Problem:** $X_1, X_2$ i.i.d $N(0,1)$. $Y_1=X_1^2+X_2^2, Y_2=X_1/X_2$.
Find joint and marginals of $Y_1, Y_2$. Are they independent?\
**Solution:**\
**Concept: Transformation involving ratios and sums of Normals**\
1. **Joint PDF of $(X_1, X_2)$:**
$$f(x_1, x_2) = \frac{1}{2\pi} e^{-(x_1^2+x_2^2)/2}$$ 2. **Inverse
Transformation:**\
From $$Y_2=X_1/X_2 \implies X_1 = Y_2 X_2$$ Substitute into
$$Y_1=X_1^2+X_2^2: Y_1 = (Y_2 X_2)^2 + X_2^2 = X_2^2(Y_2^2+1)$$
$$X_2^2 = \frac{Y_1}{1+Y_2^2} \implies X_2 = \pm \sqrt{\frac{Y_1}{1+Y_2^2}}$$
$$X_1 = Y_2 X_2 = \pm Y_2 \sqrt{\frac{Y_1}{1+Y_2^2}}$$
$$Region: X_1, X_2 \in (-\infty, \infty)Y_1=X_1^2+X_2^2 > 0\text{. }Y_2=X_1/X_2 \in (-\infty, \infty)$$
There are two inverse solutions corresponding to the signs of
$X_1, X_2$.\
3. **Jacobian:**\
$$J = \det \begin{pmatrix} \frac{\partial x_1}{\partial y_1} & \frac{\partial x_1}{\partial y_2} \\ \frac{\partial x_2}{\partial y_1} & \frac{\partial x_2}{\partial y_2} \end{pmatrix}$$
Calculating the partial derivatives (as done previously or via polar
coordinates trick):\
$|J| = \frac{1}{2(1+y_2^2)}$. This value is the same for both inverse
solutions.\
4. **Joint PDF of $(Y_1, Y_2)$:**\
$$f_{Y_1,Y_2}(y_1, y_2) = 2 \times f_{X_1,X_2}(x_1, x_2) |J| \textit{  (factor of 2 because there are two inverse solutions).}$$
$$f_{Y_1,Y_2}(y_1, y_2) = 2 \times \frac{1}{2\pi} e^{-(x_1^2+x_2^2)/2} \frac{1}{2(1+y_2^2)} = \frac{1}{2\pi(1+y_2^2)} e^{-y_1/2}$$
$$\boxed{ f_{Y_1,Y_2}(y_1, y_2) = \frac{1}{2\pi(1+y_2^2)} e^{-y_1/2}, \quad y_1 > 0, -\infty < y_2 < \infty }$$
5. **Marginals and Independence:**
$$f_{Y_1}(y_1) = \int_{-\infty}^\infty \frac{1}{2\pi(1+y_2^2)} e^{-y_1/2} dy_2 = \frac{e^{-y_1/2}}{2\pi} \int_{-\infty}^\infty \frac{1}{1+y_2^2} dy_2$$
$$\int_{-\infty}^\infty \frac{1}{1+y_2^2} dy_2 = [\arctan(y_2)]_{-\infty}^\infty = \pi$$
$$f_{Y_1}(y_1) = \frac{e^{-y_1/2}}{2\pi} \cdot \pi = \frac{1}{2}e^{-y_1/2}$$
$$\boxed{ f_{Y_1}(y_1) = \frac{1}{2}e^{-y_1/2}, y_1>0 \implies Y_1 \sim \text{Exp}(1/2) \text{ or } \chi^2_2 }$$
$$f_{Y_2}(y_2) = \int_0^\infty \frac{1}{2\pi(1+y_2^2)} e^{-y_1/2} dy_1 = \frac{1}{2\pi(1+y_2^2)} \int_0^\infty e^{-y_1/2} dy_1$$
$\int_0^\infty e^{-y_1/2} dy_1 = [-2e^{-y_1/2}]_0^\infty = 2$.
$$f_{Y_2}(y_2) = \frac{1}{2\pi(1+y_2^2)} \cdot 2 = \frac{1}{\pi(1+y_2^2)}$$
$$\boxed{ f_{Y_2}(y_2) = \frac{1}{\pi(1+y_2^2)}, -\infty < y_2 < \infty \implies Y_2 \sim \text{Cauchy}(0,1) }$$
Check independence:
$f_{Y_1}(y_1) f_{Y_2}(y_2) = (\frac{1}{2}e^{-y_1/2}) (\frac{1}{\pi(1+y_2^2)}) = \frac{1}{2\pi(1+y_2^2)} e^{-y_1/2} = f_{Y_1,Y_2}(y_1, y_2)$.
$$\boxed{ \text{Yes, } Y_1 \text{ and } Y_2 \text{ are independent.} }$$

Question 5
==========

**Problem:**
$X_1 \sim \text{Gamma}(n_1, \lambda), X_2 \sim \text{Gamma}(n_2, \lambda)$
independently. Find distributions of $Y_1 = \frac{X_1}{X_1+X_2}$ and
$Y_2 = X_1+X_2$. Are they independent?\
**Solution:**\
**Concept: Transformation of Gamma variables, Relation to Beta**\
1. **Joint PDF of $(X_1, X_2)$:**\
$$f(x_1, x_2) = \frac{\lambda^{n_1}}{\Gamma(n_1)} x_1^{n_1-1}e^{-\lambda x_1} \cdot \frac{\lambda^{n_2}}{\Gamma(n_2)} x_2^{n_2-1}e^{-\lambda x_2} = \frac{\lambda^{n_1+n_2}}{\Gamma(n_1)\Gamma(n_2)} x_1^{n_1-1}x_2^{n_2-1}e^{-\lambda(x_1+x_2)}$$
2. **Inverse Transformation:**\
$$X_1 = Y_1 Y_2$$ $$X_2 = Y_2(1-Y_1)$$
$$Region: X_1>0, X_2>0 \implies Y_1 Y_2 > 0, Y_2(1-Y_1) > 0$$ Since
$Y_2 = X_1+X_2 > 0$, we need $Y_1 > 0$ and $1-Y_1 > 0$, so
$0 < Y_1 < 1$. Also $Y_2>0$.\
3. **Jacobian:**
$$J = \det \begin{pmatrix} y_2 & y_1 \\ -y_2 & 1-y_1 \end{pmatrix} = y_2(1-y_1) - (-y_2)(y_1) = y_2$$
$|J|=y_2$.\
4. **Joint PDF of $(Y_1, Y_2)$:**\
$$f_{Y_1,Y_2}(y_1, y_2) = \frac{\lambda^{n_1+n_2}}{\Gamma(n_1)\Gamma(n_2)} (y_1y_2)^{n_1-1} (y_2(1-y_1))^{n_2-1} e^{-\lambda y_2} \cdot y_2$$
$$= \frac{\lambda^{n_1+n_2}}{\Gamma(n_1)\Gamma(n_2)} y_1^{n_1-1} (1-y_1)^{n_2-1} y_2^{n_1+n_2-1} e^{-\lambda y_2}$$
$$\boxed{ f_{Y_1,Y_2}(y_1, y_2) = \frac{\lambda^{n_1+n_2}}{\Gamma(n_1)\Gamma(n_2)} y_1^{n_1-1} (1-y_1)^{n_2-1} y_2^{n_1+n_2-1} e^{-\lambda y_2}, \quad 0<y_1<1, y_2>0 }$$
5. **Marginals and Independence:**\
Factor the joint PDF:\
$$f_{Y_1,Y_2}(y_1, y_2) = \left[ \frac{\Gamma(n_1+n_2)}{\Gamma(n_1)\Gamma(n_2)} y_1^{n_1-1} (1-y_1)^{n_2-1} \right] \cdot \left[ \frac{\lambda^{n_1+n_2}}{\Gamma(n_1+n_2)} y_2^{n_1+n_2-1} e^{-\lambda y_2} \right]$$
The first bracket is the PDF of a Beta distribution with parameters
$(n_1, n_2)$. The second bracket is the PDF of a Gamma distribution with
parameters $(n_1+n_2, \lambda)$.
$$\boxed{ Y_1 \sim \text{Beta}(n_1, n_2) }$$
$$\boxed{ Y_2 \sim \text{Gamma}(n_1+n_2, \lambda) }$$ Since
$f_{Y_1,Y_2}(y_1, y_2) = f_{Y_1}(y_1) f_{Y_2}(y_2)$, they are
independent.
$$\boxed{ \text{Yes, } Y_1 \text{ and } Y_2 \text{ are independent.} }$$

Question 6
==========

**Problem:** $X_1, ..., X_n$ i.i.d $\text{Exp}(1)$. Define
$Y_1=S_n, Y_2=S_{n-1}/S_n, ..., Y_n=S_1/S_2$ where
$S_k = \sum_{i=1}^k X_i$. Find joint and marginals. Independent?\
**Solution:**\
**Concept: Transformation of Order Statistics / Ratios**\
Inverse transformation leads to: $$X_1 = Y_1 Y_2 \dots Y_n$$
$$X_k = Y_1 \dots Y_{n-k+1} (1-Y_{n-k+2})\text{ for }k=2, ..., n-1$$
$$X_n = Y_1(1-Y_2)$$
$$Region: Y_1 > 0\text{ and }0 < Y_k < 1\text{ for }k=2, \dots, n$$
$$Jacobian: |J| = y_1^{n-1} y_2^{n-2} \dots y_{n-1}$$ Joint PDF of
$(X_1, ..., X_n)$ is $$f(x_1, ..., x_n) = e^{-\sum x_i} = e^{-S_n}$$
Joint PDF of
$$(Y_1, ..., Y_n:f_Y(y_1, ..., y_n) = e^{-y_1} |J| = y_1^{n-1} e^{-y_1} y_2^{n-2} \dots y_{n-1}$$
$$\boxed{ f_Y(y_1, ..., y_n) = y_1^{n-1} e^{-y_1} \cdot y_2^{n-2} \cdot y_3^{n-3} \dots y_{n-1}^1 \cdot 1, \quad y_1>0, 0<y_k<1 \text{ for } k=2..n }$$
**Marginals and Independence:**\
The joint PDF factors into:\
$$f(y_1) = \frac{1}{\Gamma(n)}y_1^{n-1}e^{-y_1}$$
$$(Y_1 \sim \text{Gamma}(n, 1))$$ (Normalizing constant $\Gamma(n)$
needed).\
$$f(y_k) = (n-k+1)y_k^{n-k}\text{ for }0<y_k<1$$
$$(Y_k \sim \text{Beta}(n-k+1, 1)\text{ for }k=2,..,n)$$. (Normalizing
constant $(n-k+1)$ needed, as $\int_0^1 y^{a-1} dy = 1/a$). Since the
joint PDF is the product of the marginals (after accounting for
constants), they are independent.
$$\boxed{ \text{Yes, they are independent.} }$$
$$\boxed{ \begin{gathered} Y_1 \sim \text{Gamma}(n, 1) \\ Y_k \sim \text{Beta}(n-k+1, 1) \text{ for } k=2, \dots, n \end{gathered} }$$

Question 7
==========

**Problem:** $Y_1=\ln X_1 \sim N(4,1)$, $Y_2=\ln X_2 \sim N(3,1)$,
$Y_3=\ln X_3 \sim N(2,0.5)$ independently. Find distribution and median
of $W=e^2 X_1^2 X_2^4 X_3^4$. Find L, R such that
$P(L \le W \le R)=0.90$.

**Solution:**\
**Concept: Log-Normal Distribution Properties**\
Consider $\ln W$:
$$\ln W = \ln(e^2 X_1^2 X_2^4 X_3^4) = 2 + 2\ln X_1 + 4\ln X_2 + 4\ln X_3 = 2 + 2Y_1 + 4Y_2 + 4Y_3$$
Since $Y_1, Y_2, Y_3$ are independent Normal variables, $\ln W$ is
Normal.
$$E[\ln W] = 2 + 2E[Y_1] + 4E[Y_2] + 4E[Y_3] = 2 + 2(4) + 4(3) + 4(2) = 2 + 8 + 12 + 8 = 30$$
$$Var(\ln W) = Var(2Y_1) + Var(4Y_2) + Var(4Y_3) = 4Var(Y_1) + 16Var(Y_2) + 16Var(Y_3)$$
$$Var(\ln W) = 4(1) + 16(1) + 16(0.5) = 4 + 16 + 8 = 28$$ So,
$\ln W \sim N(30, 28)$. W follows a Log-Normal distribution.
$$\boxed{ W \text{ is Log-Normally distributed with } \ln W \sim N(30, 28) }$$
**Median of W:** $P(W \le M) = 0.5 \implies P(\ln W \le \ln M) = 0.5$.
The median of a Normal distribution is its mean.
$\ln M = E[\ln W] = 30$. $$\boxed{ \text{Median of } W = e^{30} }$$
**Interval (L, R):**
$P(L \le W \le R) = 0.90 \implies P(\ln L \le \ln W \le \ln R) = 0.90$\
Let $Z = (\ln W - 30) / \sqrt{28}$. We need
$P(z_L \le Z \le z_R) = 0.90$. For a symmetric interval,
$z_L = -z_{0.05}$ and $z_R = z_{0.05} = 1.645$.
$\ln L = 30 - 1.645\sqrt{28}$. $\ln R = 30 + 1.645\sqrt{28}$.
$$\boxed{ L = e^{30 - 1.645\sqrt{28}}, \quad R = e^{30 + 1.645\sqrt{28}} }$$

Question 8
==========

**Problem:** BVN with
$f(x,y)=\frac{1}{\pi\sqrt{3}} \text{Exp}\{-\frac{2}{3}(x^2-xy+y^2)\}$.
Find $\rho$, $V(X-Y)$, $P(-1<X+Y<2)$.

**Solution:**\
**Concept: Identifying BVN Parameters from PDF**\
Compare the exponent
$$-\frac{2}{3}(x^2-xy+y^2)\text{ to }-\frac{1}{2(1-\rho^2)}[(\frac{x-\mu_X}{\sigma_X})^2 - 2\rho(\dots) + (\frac{y-\mu_Y}{\sigma_Y})^2]$$
$$\mu_X=0, \mu_Y=0$$ $$\frac{1}{2(1-\rho^2)\sigma_X^2} = \frac{2}{3}
\text{ , }\frac{1}{2(1-\rho^2)\sigma_Y^2} = \frac{2}{3}$$
$$\frac{2\rho}{2(1-\rho^2)\sigma_X\sigma_Y} = \frac{2}{3}$$
$$\text{Implies } \sigma_X^2 = \sigma_Y^2 = \sigma^2.(1-\rho^2)\sigma^2 = 3/4$$
$\frac{\rho}{(1-\rho^2)\sigma^2} = \frac{2}{3} \implies \frac{\rho}{3/4} = \frac{2}{3} \implies \rho = 1/2$.
$(1-(1/2)^2)\sigma^2 = 3/4 \implies (3/4)\sigma^2 = 3/4 \implies \sigma^2 = 1$.
Parameters: $\mu_X=0, \mu_Y=0, \sigma_X^2=1, \sigma_Y^2=1, \rho=1/2$.
$$\boxed{ \rho = 1/2 }$$ **$V(X-Y)$:**
$V(X-Y) = V(X) + V(Y) - 2\text{Cov}(X,Y) = 1 + 1 - 2\rho\sigma_X\sigma_Y = 1 + 1 - 2(1/2)(1)(1) = 1$.
$$\boxed{ V(X-Y) = 1 }$$ **$P(-1<X+Y<2)$:** Let $W=X+Y$. $E(W)=0$.
$$V(W)=V(X)+V(Y)+2\text{Cov}(X,Y) = 1+1+2(1/2)(1)(1)=3$$
$$W \sim N(0, 3)$$
$$P(-1<W<2) = P(\frac{-1}{\sqrt{3}} < Z < \frac{2}{\sqrt{3}}) = P(-0.577 < Z < 1.155) = \Phi(1.15) - \Phi(-0.58) = 0.8749 - 0.2810 = 0.5939$$
$$\boxed{ P(-1<X+Y<2) \approx 0.5939 }$$

Question 9
==========

**Problem:** Lengths $X \sim N(20, 0.03)$, $Y \sim N(14, 0.01)$,
independent. Total length $T=X+Y$. Find $P(33.6 < T < 34.4)$.\
**Solution:**\
**Concept: Sum of Independent Normal Variables**\
$$T = X+Y$$ $$E(T) = E(X) + E(Y) = 20 + 14 = 34$$
$$Var(T) = Var(X) + Var(Y) = 0.03 + 0.01 = 0.04$$
$$\sigma_T = \sqrt{0.04} = 0.2$$ $$T \sim N(34, 0.04)$$
$$P(33.6 < T < 34.4) = P(\frac{33.6 - 34}{0.2} < Z < \frac{34.4 - 34}{0.2}) = P(-2 < Z < 2)$$
$$= \Phi(2) - \Phi(-2) = 2\Phi(2) - 1 = 2(0.9772) - 1 = 0.9544$$
$$\boxed{ P(33.6 < T < 34.4) \approx 0.9544 }$$

Question 10
===========

**Problem:** $f(x,y)=\frac{1}{x^2y^2}$ for $x>1, y>1$. Find joint and
marginals of $U=XY, V=X/Y$.\
**Solution:**\
**Concept: Jacobian Transformation (Non-linear)**\
1. **Inverse Transformation:** $X = \sqrt{UV}, Y = \sqrt{U/V}$. Region
for (U, V): $U > \max(V, 1/V), V>0$.\
2. **Jacobian:** $|J| = \frac{1}{2V}$.\
3. **Joint PDF of $(U, V)$:**
$$f_{U,V}(u,v) = f_{X,Y}(x, y) |J| = \frac{1}{(UV)(U/V)} \frac{1}{2V} = \frac{1}{2u^2 v}$$
$$\boxed{ f_{U,V}(u,v) = \frac{1}{2u^2 v}, \quad u > \max(v, 1/v), v>0 }$$
4. **Marginals:**\
For a fixed $u>1\text{ , } 1/u < v < u$.
$$f_U(u) = \int_{1/u}^u \frac{1}{2u^2 v} dv = \frac{1}{2u^2} [\ln v]_{1/u}^u = \frac{1}{2u^2} (\ln u - \ln(1/u)) = \frac{\ln u}{u^2}$$
$$\boxed{ f_U(u) = \frac{\ln u}{u^2}, \quad u>1 }$$ For $f_V(v)$: If
$v \ge 1$, then $u > v$.
$$\int_v^\infty \frac{1}{2u^2 v} du = \frac{1}{2v} [-\frac{1}{u}]_v^\infty = \frac{1}{2v^2}$$.\
If $0 < v < 1$, then $u > 1/v$.
$$\int_{1/v}^\infty \frac{1}{2u^2 v} du = \frac{1}{2v} [-\frac{1}{u}]_{1/v}^\infty = \frac{1}{2}$$
$$\boxed{ f_V(v) = \begin{cases} 1/2 & 0 < v < 1 \\ 1/(2v^2) & v \ge 1 \end{cases} }$$
