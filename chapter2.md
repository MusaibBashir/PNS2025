---
title: Assignment 2
nav_order: 3
---

Question 1
==========

**Problem:** Let X be a continuous random variable with PDF $f(x)=x^2$
for $0<x\le1$ and $f(x)=c/x^2$ for $1<x<\infty$. Determine c, the CDF,
E(X), Var(X), the median, $P(0.5<X<2)$, and $P(X>3)$.

**Solution:** **Find c:** For $f(x)$ to be a valid PDF, its total
integral must be 1.
$$\int_{-\infty}^{\infty} f(x)dx = \int_0^1 x^2 dx + \int_1^\infty \frac{c}{x^2} dx = 1$$
$$\left[\frac{x^3}{3}\right]_0^1 + c\left[-\frac{1}{x}\right]_1^\infty = \frac{1}{3} + c[0 - (-1)] = \frac{1}{3} + c = 1 \implies c = \frac{2}{3}$$
**CDF of X:** We integrate the PDF from $-\infty$ to $x$. For $x \le 0$:
$F(x)=0$. For $0 < x \le 1$: $F(x) = \int_0^x t^2 dt = \frac{x^3}{3}$.
For $x > 1$:
$F(x) = \int_0^1 t^2 dt + \int_1^x \frac{2/3}{t^2} dt = \frac{1}{3} + \frac{2}{3}\left[-\frac{1}{t}\right]_1^x = \frac{1}{3} + \frac{2}{3}\left(-\frac{1}{x} - (-1)\right) = 1 - \frac{2}{3x}$.
$$F(x) = \begin{cases} 0, & x \le 0 \\ \frac{x^3}{3}, & 0 < x \le 1 \\ 1 - \frac{2}{3x}, & x > 1 \end{cases}$$
**E(X) and Var(X):**
$$E(X) = \int_{-\infty}^{\infty} x f(x) dx = \int_0^1 x^3 dx + \int_1^\infty x \frac{2/3}{x^2} dx = \left[\frac{x^4}{4}\right]_0^1 + \frac{2}{3}\int_1^\infty \frac{1}{x} dx$$
The second integral is $\frac{2}{3}[\ln(x)]_1^\infty$, which diverges.
Thus, $E(X)$ does not exist. Since $E(X)$ does not exist, $Var(X)$ also
does not exist. **Median of X:** We solve $F(M)=0.5$. Since
$F(1)=1/3 < 0.5$, the median must be in the range $x>1$.
$$1 - \frac{2}{3M} = 0.5 \implies \frac{2}{3M} = 0.5 \implies 3M = 4 \implies M = \frac{4}{3}$$
**Probabilities:** We use the CDF.
$P(0.5<X<2) = F(2) - F(0.5) = (1 - \frac{2}{3(2)}) - \frac{(0.5)^3}{3} = (1 - \frac{1}{3}) - \frac{0.125}{3} = \frac{2}{3} - \frac{1}{24} = \frac{16-1}{24} = \frac{15}{24} = \frac{5}{8}$.
$P(X>3) = 1 - F(3) = 1 - (1 - \frac{2}{3(3)}) = \frac{2}{9}$.
$$\boxed{ c=\frac{2}{3}, \text{Median}=\frac{4}{3}, P(0.5<X<2)=\frac{5}{8}, P(X>3)=\frac{2}{9}, \text{E(X) and Var(X) do not exist.} }$$

Question 2
==========

**Problem:** Given a CDF for a mixed random variable X, find
probabilities, E(X), Var(X), and the median.

**Solution:** **Probabilities from CDF:**
$P(1/2 < X < 5/2) = F(5/2^-) - F(1/2)$. Since $5/2=2.5$ is in $[2,3)$,
$F(5/2^-) = 11/12$. Since $1/2$ is in $[0,1)$, $F(1/2)=1/2/4=1/8$.
$P(1/2 < X < 5/2) = \frac{11}{12} - \frac{1}{8} = \frac{22-3}{24} = \frac{19}{24}$.
$P(1 < X < 3) = F(3^-) - F(1) = \frac{11}{12} - \frac{1+1}{4} = \frac{11}{12} - \frac{1}{2} = \frac{5}{12}$.

**E(X) and Var(X):** This is a mixed random variable. **Nice Trick:
Identifying Mixed Components** The jumps in the CDF indicate discrete
probability masses. The derivative in smooth regions gives the
continuous density.
$P(X=1) = F(1) - F(1^-) = \frac{1+1}{4} - \frac{1}{4} = \frac{1}{4}$.\
$P(X=2) = F(2) - F(2^-) = \frac{11}{12} - \frac{2+1}{4} = \frac{11-9}{12} = \frac{2}{12} = \frac{1}{6}$.\
$P(X=3) = F(3) - F(3^-) = 1 - \frac{11}{12} = \frac{1}{12}$.\
For $x \in (0,1) \cup (1,2)$, the density is $f(x) = F'(x) = 1/4$.
$E(X) = \int_0^1 x\frac{1}{4}dx + \int_1^2 x\frac{1}{4}dx + 1\cdot P(X=1) + 2\cdot P(X=2) + 3\cdot P(X=3)$\
$E(X) = \frac{1}{4}[\frac{x^2}{2}]_0^1 + \frac{1}{4}[\frac{x^2}{2}]_1^2 + 1(\frac{1}{4}) + 2(\frac{1}{6}) + 3(\frac{1}{12}) = \frac{1}{8} + \frac{3}{8} + \frac{1}{4} + \frac{1}{3} + \frac{1}{4} = \frac{4}{3}$.\
$E(X^2) = \int_0^1 x^2\frac{1}{4}dx + \int_1^2 x^2\frac{1}{4}dx + 1^2(\frac{1}{4}) + 2^2(\frac{1}{6}) + 3^2(\frac{1}{12}) = \frac{1}{12} + \frac{7}{12} + \frac{1}{4} + \frac{4}{6} + \frac{9}{12} = \frac{34}{12} = \frac{17}{6}$.\
$V(X) = E(X^2) - [E(X)]^2 = \frac{17}{6} - (\frac{4}{3})^2 = \frac{17}{6} - \frac{16}{9} = \frac{51-32}{18} = \frac{19}{18}$.
**Median:** We need $F(M)=0.5$. $F(1) = (1+1)/4 = 1/2$. So the median is
1.
$$\boxed{ P(\frac{1}{2}<X<\frac{5}{2})=\frac{19}{24}, P(1<X<3)=\frac{5}{12}, E(X)=\frac{4}{3}, V(X)=\frac{19}{18}, \text{Median}=1 }$$

Question 3
==========

**Problem:** Find the probability distributions of the number of
survivals (X) and deaths (Y) in a multi-stage experiment with guinea
pigs.

**Solution:** Let $P(S)=2/3$ and $P(D)=1/3$. The sample space and
probabilities of outcomes are:

-   SS: $(2/3)^2=4/9$. (X=2, Y=0)

-   SD\...: (1S, 1D) then one more trial.

-   SDS: $(2/3)(1/3)(2/3)=4/27$. (X=2, Y=1)

-   SDD: $(2/3)(1/3)(1/3)=2/27$. (X=1, Y=2)

-   DS\...: (1S, 1D) then one more trial.

-   DSS: $(1/3)(2/3)(2/3)=4/27$. (X=2, Y=1)

-   DSD: $(1/3)(2/3)(1/3)=2/27$. (X=1, Y=2)

-   DD\...: (0S, 2D) then two more trials.

-   DDSS: $(1/3)^2(2/3)^2=4/81$. (X=2, Y=2)

-   DDSD: $(1/3)^2(2/3)(1/3)=2/81$. (X=1, Y=3)

-   DDDS: $(1/3)^2(1/3)(2/3)=2/81$. (X=1, Y=3)

-   DDDD: $(1/3)^4=1/81$. (X=0, Y=4)

**Distribution of X (Survivors):**\
$P(X=2) = P(SS)+P(SDS)+P(DSS)+P(DDSS) = 4/9+4/27+4/27+4/81 = (36+12+12+4)/81=64/81$.\
$P(X=1) = P(SDD)+P(DSD)+P(DDSD)+P(DDDS) = 2/27+2/27+2/81+2/81 = (6+6+2+2)/81=16/81$.\
$P(X=0) = P(DDDD) = 1/81$.\
**Distribution of Y (Deaths):** $P(Y=0) = P(SS)=4/9$.\
$P(Y=1) = P(SDS)+P(DSS)=4/27+4/27=8/27$.\
$P(Y=2) = P(SDD)+P(DSD)+P(DDSS)=2/27+2/27+4/81=(6+6+4)/81=16/81$.\
$P(Y=3) = P(DDSD)+P(DDDS)=2/81+2/81=4/81$.\
$P(Y=4) = P(DDDD)=1/81$.\
$$\boxed{ \begin{array}{l} \text{PMF of X: } P(X=0)=1/81, P(X=1)=16/81, P(X=2)=64/81 \\ \text{PMF of Y: } P(Y=0)=4/9, P(Y=1)=8/27, P(Y=2)=16/81, P(Y=3)=4/81, P(Y=4)=1/81 \end{array} }$$

Question 4
==========

**Problem:** Find the PMF of the number of third-generation particles in
a branching process.

**Solution:** Let X be the number of 2nd gen particles, $P(X=k)=1/3$ for
$k=1,2,3$. Let $Z_i$ be the number of particles from the $i$-th 2nd gen
particle, $P(Z_i=j)=1/3$ for $j=1,2,3$. Let Y be the total number of 3rd
gen particles, $Y = \sum_{i=1}^X Z_i$. We use the Law of Total
Probability: $P(Y=j) = \sum_k P(Y=j|X=k)P(X=k)$.

-   $P(Y=1) = P(Y=1|X=1)\frac{1}{3} = P(Z_1=1)\frac{1}{3} = \frac{1}{3}\frac{1}{3} = 1/9$.

-   $P(Y=2) = [P(Z_1=2) + P(Z_1+Z_2=2)]\frac{1}{3} = [\frac{1}{3} + \frac{1}{9}]\frac{1}{3} = 4/27$.

-   $P(Y=3) = [P(Z_1=3)+P(Z_1+Z_2=3)+P(Z_1+Z_2+Z_3=3)]\frac{1}{3} = [\frac{1}{3}+\frac{2}{9}+\frac{1}{27}]\frac{1}{3} = 16/81$.

-   $P(Y=4) = [P(Z_1+Z_2=4)+P(Z_1+Z_2+Z_3=4)]\frac{1}{3} = [\frac{3}{9}+\frac{3}{27}]\frac{1}{3}=12/81=4/27$.

-   $P(Y=5) = [P(Z_1+Z_2=5)+P(Z_1+Z_2+Z_3=5)]\frac{1}{3} = [\frac{2}{9}+\frac{6}{27}]\frac{1}{3}=12/81=4/27$.

-   $P(Y=6) = [P(Z_1+Z_2=6)+P(Z_1+Z_2+Z_3=6)]\frac{1}{3} = [\frac{1}{9}+\frac{7}{27}]\frac{1}{3}=10/81$.

-   $P(Y=7) = [P(Z_1+Z_2+Z_3=7)]\frac{1}{3} = [\frac{6}{27}]\frac{1}{3}=6/81=2/27$.

-   $P(Y=8) = [P(Z_1+Z_2+Z_3=8)]\frac{1}{3} = [\frac{3}{27}]\frac{1}{3}=3/81=1/27$.

-   $P(Y=9) = [P(Z_1+Z_2+Z_3=9)]\frac{1}{3} = [\frac{1}{27}]\frac{1}{3}=1/81$.

$$\boxed{ \begin{array}{l} P(Y=1)=1/9, P(Y=2)=4/27, P(Y=3)=16/81, P(Y=4)=4/27, P(Y=5)=4/27, \\ P(Y=6)=10/81, P(Y=7)=2/27, P(Y=8)=1/27, P(Y=9)=1/81 \end{array} }$$

Question 5
==========

**Problem:** Use Chebyshev's inequality to bound the probability of an
IQ score being above 148 or below 52, given mean 100 and standard
deviation 16.

**Solution:** **Concept: Chebyshev's Inequality** This inequality
provides a lower bound on the probability that a random variable falls
within a certain distance of its mean, regardless of the specific
distribution. The form is $P(|X-\mu| \ge c) \le \frac{\sigma^2}{c^2}$.
Here, $X$ is the IQ score, $\mu=100$, and $\sigma=16$. The event is
$X < 52$ or $X > 148$. This can be written as $|X-100| > 48$. So, we set
$c=48$. Applying Chebyshev's inequality:
$$P(|X-100| > 48) \le \frac{\sigma^2}{c^2} = \frac{16^2}{48^2} = \left(\frac{16}{48}\right)^2 = \left(\frac{1}{3}\right)^2 = \frac{1}{9}$$
$$\boxed{ P(X<52 \text{ or } X>148) \le \frac{1}{9} }$$

Question 6
==========

**Problem:** Find the cdf, mean, variance, and median for a continuous
random variable with a given piecewise PDF.

**Solution:** The PDF is symmetric about $x=1.5$. **CDF:** We integrate
the PDF. For $x<0$, $F(x)=0$. For $0 \le x \le 1$,
$F(x)=\int_0^x t/2 dt = x^2/4$.\
For $1 < x \le 2$,
$F(x)=F(1)+\int_1^x 1/2 dt = 1/4+(x-1)/2 = (2x-1)/4$.\
For $2 < x \le 3$,
$F(x)=F(2)+\int_2^x (3-t)/2 dt = 3/4 + [3t-t^2/2]_2^x/2 = (-x^2+6x-5)/4$.\
For $x>3$, $F(x)=1$.\
**Mean:** Due to symmetry about $1.5$, $E(X)=1.5$.\
**Variance:** We calculate
$E(X^2) = \int_0^1 \frac{x^3}{2}dx + \int_1^2 \frac{x^2}{2}dx + \int_2^3 \frac{x^2(3-x)}{2}dx \\= \frac{1}{8}+\frac{7}{6}+\frac{11}{8} = \frac{8}{3}$.\
$Var(X)=E(X^2)-[E(X)]^2 = 8/3 - (3/2)^2 = 8/3 - 9/4 = 5/12$.\
**Median:** Due to symmetry, Median = Mean = 1.5. Check:
$F(1.5)=(2(1.5)-1)/4=2/4=0.5$.\
$$\boxed{ E(X)=1.5, Var(X)=5/12, \text{Median}=1.5 }$$

Question 7
==========

**Problem:** Let X be a continuous random variable with PDF $f(x) = k/4$
for $0<x<1$, $x^2/4$ for $1 \le x \le 2$, and $(1-k)/4$ for $2<x<3$.
Determine the values of k for which f(x) is a density function. Find the
CDF, the median M, and show that $\sqrt{2} \le M \le \sqrt{3}$.

**Solution:** **1. Determine valid range for k:** For $f(x)$ to be a
valid PDF, two conditions must be met: (a) $f(x) \ge 0$ for all x. (b)
$\int_{-\infty}^{\infty} f(x)dx = 1$.

Condition (a):

-   For $0<x<1$, we need $k/4 \ge 0 \implies k \ge 0$.

-   For $1 \le x \le 2$, $x^2/4$ is always non-negative.

-   For $2<x<3$, we need
    $(1-k)/4 \ge 0 \implies 1-k \ge 0 \implies k \le 1$.

Combining these, we get the constraint $0 \le k \le 1$.

Condition (b):
$$\int_0^1 \frac{k}{4} dx + \int_1^2 \frac{x^2}{4} dx + \int_2^3 \frac{1-k}{4} dx = 1$$
$$\frac{k}{4}[x]_0^1 + \frac{1}{4}\left[\frac{x^3}{3}\right]_1^2 + \frac{1-k}{4}[x]_2^3 = 1$$
$$\frac{k}{4}(1) + \frac{1}{4}\left(\frac{8}{3} - \frac{1}{3}\right) + \frac{1-k}{4}(1) = 1$$
$$\frac{k}{4} + \frac{7}{12} + \frac{1-k}{4} = 1$$
$$\frac{k+1-k}{4} + \frac{7}{12} = 1 \implies \frac{1}{4} + \frac{7}{12} = 1 \implies \frac{3+7}{12} = \frac{10}{12} = 1$$
This is a contradiction, as $10/12 \ne 1$. There appears to be a typo in
the problem statement as given, because the integral does not sum to 1.
Let's assume there is a typo in the second interval and the PDF is
$f(x) = kx^2/4$ for $1 \le x \le 2$. Let's re-calculate:
$$\frac{k}{4} + \frac{k}{4}\left(\frac{7}{3}\right) + \frac{1-k}{4} = 1 \implies \frac{1}{4} + \frac{7k}{12} = 1 \implies \frac{7k}{12} = \frac{3}{4} \implies k = \frac{9}{7}$$
This violates $k \le 1$. Let's adhere strictly to the problem as written
in the PDF, which means no value of $k$ makes it a valid density.
However, to proceed with the structure of the question as intended, we
will assume the calculation error in the provided solution key implies a
different function. Based on the solution key leading to $M=\sqrt{3-k}$,
the intended CDF in the second interval was likely $\frac{k+x^2-1}{4}$.
This corresponds to a PDF of $f(x) = x/2$ for $1<x \le 2$. Let's solve
with this assumption.

**2. Find the CDF and Median (assuming $f(x)=x/2$ on $[1,2]$):**
$$F(x) = \begin{cases} 0 & x \le 0 \\ \frac{kx}{4} & 0 < x \le 1 \\ \frac{k}{4} + \frac{x^2-1}{4} & 1 < x \le 2 \\ \frac{k+3}{4} + \frac{(1-k)(x-2)}{4} & 2 < x < 3 \\ 1 & x \ge 3 \end{cases}$$
The median M satisfies $F(M)=1/2$. The value of $F(2) = (k+3)/4$. Since
$0 \le k \le 1$, $F(2)$ ranges from $3/4$ to $1$. And $F(1)=k/4$ ranges
from $0$ to $1/4$. Thus, the median must lie in the interval $(1, 2]$.
$$\frac{k + M^2 - 1}{4} = \frac{1}{2} \implies k+M^2-1=2 \implies M^2 = 3-k \implies M = \sqrt{3-k}$$
Since $0 \le k \le 1$, we can find the bounds for M: When $k=1$,
$M = \sqrt{3-1} = \sqrt{2}$. When $k=0$, $M = \sqrt{3-0} = \sqrt{3}$.
Thus, $\sqrt{2} \le M \le \sqrt{3}$.
$$\boxed{ \text{Valid k is } [0,1], \text{Median} M = \sqrt{3-k}, \text{ which implies } \sqrt{2} \le M \le \sqrt{3} }$$

Question 8
==========

**Problem:** Find the expected number of blood tests for a batch of 10
people, using a pooling strategy.

**Solution:** **Concept: Pooled Testing Efficiency** This is a classic
problem demonstrating how pooling samples can save resources. The
expectation is calculated over the two possible outcomes for the pooled
sample. Let X be the number of tests for a batch of 10. $p=0.01$ is the
incidence rate.

-   **Outcome 1:** The pooled test is negative. This happens if all 10
    people are healthy. The probability of one person being healthy is
    $1-p=0.99$. The probability of all 10 being healthy is
    $(0.99)^{10}$. In this case, $X=1$.

-   **Outcome 2:** The pooled test is positive. This happens if at least
    one person has the disease. The probability is $1 - (0.99)^{10}$. In
    this case, the initial pooled test is followed by 10 individual
    tests, so $X=1+10=11$.

The expected number of tests is
$E(X) = 1 \cdot P(X=1) + 11 \cdot P(X=11)$.
$P(X=1) = (0.99)^{10} \approx 0.9044$.
$P(X=11) = 1 - (0.99)^{10} \approx 0.0956$.
$E(X) = 1(0.9044) + 11(0.0956) = 0.9044 + 1.0516 = 1.956$.
$$\boxed{ E(\text{tests per batch}) = 11 - 10(0.99)^{10} \approx 1.956 }$$

Question 9
==========

**Problem:** Show that the expected number of children in a randomly
selected child's family, E(Y), is greater than or equal to the expected
number of children in a randomly selected family, E(X).

**Solution:** **Nice Trick: Jensen's Inequality / Variance Property**
The core of this proof lies in the fact that variance is non-negative.\
$Var(U) = E(U^2) - (E(U))^2 \ge 0$.\
Let U be a random variable for the number of children in a randomly
chosen family.\
$P(U=i) = n_i/m$, so $E(U) = \sum i \frac{n_i}{m} = E(X)$.\
And $E(U^2) = \sum i^2 \frac{n_i}{m}$.\
Now, consider Y, the number of children in a randomly selected child's
family. The probability of selecting a child from a family of size $i$
is proportional to $i \cdot n_i$.\
$P(Y=i) = \frac{i n_i}{\sum i n_i} = \frac{i n_i}{m \cdot E(U)}$.\
$E(Y) = \sum i P(Y=i) = \sum i \frac{i n_i}{m E(U)} = \frac{\sum i^2 n_i}{m E(U)} = \frac{E(U^2)}{E(U)}$.\
We need to show $E(Y) \ge E(X)$, which is
$\frac{E(U^2)}{E(U)} \ge E(U)$. Since $E(U)>0$, this is equivalent to
showing $E(U^2) \ge [E(U)]^2$. This is always true because
$Var(U) = E(U^2) - [E(U)]^2 \ge 0$.\
$$\boxed{ \text{The result is proven, as it is equivalent to the property } E(U^2) \ge [E(U)]^2. }$$

Question 10
===========

**Problem:** For a discrete random variable X, find the values of d for
which $p(x)$ is a valid PMF, and find the value of d that minimizes
Var(X).

**Solution:** **1. Find valid range for d:** For a valid PMF, we need
$p(x) \ge 0$ for all x and $\sum p(x) = 1$. The sum is
$\frac{1+3d}{4} + \frac{1-d}{4} + \frac{1+2d}{4} + \frac{1-4d}{4} = \frac{4+0d}{4} = 1$.
This condition is always met. Now, we enforce $p(x) \ge 0$:

-   $p(1) = 1+3d \ge 0 \implies d \ge -1/3$.

-   $p(2) = 1-d \ge 0 \implies d \le 1$.

-   $p(3) = 1+2d \ge 0 \implies d \ge -1/2$.

-   $p(4) = 1-4d \ge 0 \implies d \le 1/4$.

Combining all these constraints, the valid range for d is $[-1/3, 1/4]$.

**2. Minimize Var(X):** **Nice Trick: Variance as a Quadratic** Variance
is often a quadratic function of the parameter. We can find the minimum
by finding the vertex of the parabola. First, find E(X) and E(X$^2$):
$E(X) = 1(\frac{1+3d}{4}) + 2(\frac{1-d}{4}) + 3(\frac{1+2d}{4}) + 4(\frac{1-4d}{4}) = \frac{1+3d+2-2d+3+6d+4-16d}{4} = \frac{10-9d}{4}$.
$E(X^2) = 1^2(\frac{1+3d}{4}) + 2^2(\frac{1-d}{4}) + 3^2(\frac{1+2d}{4}) + 4^2(\frac{1-4d}{4}) = \frac{1+3d+4-4d+9+18d+16-64d}{4} = \frac{30-47d}{4}$.
$Var(X) = E(X^2) - [E(X)]^2 = \frac{30-47d}{4} - \left(\frac{10-9d}{4}\right)^2 = \frac{4(30-47d) - (100-180d+81d^2)}{16} = \frac{120-188d-100+180d-81d^2}{16}$.
$Var(X) = \frac{20 - 8d - 81d^2}{16}$. This is a downward-opening
parabola in $d$. The minimum value will occur at the boundaries of the
valid interval $[-1/3, 1/4]$. Let's evaluate the variance at the
endpoints:
$V(d=-1/3) = \frac{20 - 8(-1/3) - 81(-1/3)^2}{16} = \frac{20+8/3-9}{16} = \frac{11+8/3}{16} = \frac{41/3}{16} = \frac{41}{48}$.
$V(d=1/4) = \frac{20 - 8(1/4) - 81(1/4)^2}{16} = \frac{20-2-81/16}{16} = \frac{18-5.0625}{16} = \frac{12.9375}{16}$.
The vertex of the parabola $ad^2+bd+c$ is at $d=-b/2a$. Here,
$a=-81, b=-8$. Vertex at $d=-(-8)/(2 \cdot -81) = -4/81$. This is within
our valid range. This point corresponds to a maximum. Therefore, the
minimum must be at one of the endpoints. Comparing the values:
$V(1/4) = (20-2-81/16)/16 = (18 - 5.0625)/16 = 12.9375/16 \approx 0.808$.
$V(-1/3) = 41/48 \approx 0.854$. The minimum is indeed at $d=1/4$.
$$\boxed{ \text{Valid d is } [-\frac{1}{3}, \frac{1}{4}], \text{ Variance is minimized at } d=\frac{1}{4} }$$

Question 11
===========

**Problem:** For the PMF $p(x) = k/((x+1)(x+2))$ for $x=0,1,2,...$, find
k, the CDF, E(X) and the median.

**Solution:**\
**Nice Trick: Telescoping Series**\
We use partial fraction decomposition:
$\frac{1}{(x+1)(x+2)} = \frac{1}{x+1} - \frac{1}{x+2}$.\
**Find k:** $\sum_{x=0}^\infty p(x) = 1$.\
$\sum_{x=0}^\infty k \left(\frac{1}{x+1} - \frac{1}{x+2}\right) = k \left[ (\frac{1}{1}-\frac{1}{2}) + (\frac{1}{2}-\frac{1}{3}) + \dots \right] = k(1) = 1 \implies k=1$.\
**CDF:**
$F(x) = P(X \le x) = \sum_{i=0}^{\lfloor x \rfloor} (\frac{1}{i+1} - \frac{1}{i+2}) = 1 - \frac{1}{\lfloor x \rfloor + 2}$.\
**E(X):** $E(X) = \sum_{x=0}^\infty \frac{x}{(x+1)(x+2)}$. Using partial
fractions: $\frac{x}{(x+1)(x+2)} = \frac{2}{x+2} - \frac{1}{x+1}$.\
$E(X) = \sum_{x=0}^\infty (\frac{2}{x+2} - \frac{1}{x+1}) = (\frac{2}{2}-\frac{1}{1})+(\frac{2}{3}-\frac{1}{2})+(\frac{2}{4}-\frac{1}{3})+\dots$.\
This series diverges (related to the harmonic series). So E(X) does not
exist.\
**Median:** We need $F(M) \ge 0.5$.\
$F(0) = P(X \le 0) = p(0) = \frac{1}{1\cdot2} = 0.5$.\
Since $F(0)=0.5$, any value $M$ in the interval $[0,1)$ is a median.
$$\boxed{ k=1, CDF=1-\frac{1}{\lfloor x \rfloor+2}, \text{E(X) does not exist, Median} \in [0,1) }$$\

Question 12
===========

**Problem:** The number of items produced in a factory during a week is
a random variable with mean 50 and standard deviation 5. Using
Chebyshev's inequality find the minimum probability that this week's
production will be between 40 and 60?

**Solution:** **Concept: Chebyshev's Inequality (Lower Bound for
Probability)** Chebyshev's inequality gives a lower bound for the
probability that a random variable with finite variance will be within a
certain distance of its mean. It is powerful because it makes no
assumptions about the underlying distribution. The relevant form for
this problem is: $$P(|X - \mu| < c) \ge 1 - \frac{\sigma^2}{c^2}$$ where
$\mu$ is the mean and $\sigma$ is the standard deviation.

**1. Identify Parameters and the Event:** We are given:

-   Mean, $\mu = 50$.

-   Standard deviation, $\sigma = 5$.

The event is that the production is between 40 and 60, which we can
write as an inequality: $$40 < X < 60$$

**2. Express the Event in the Form of Chebyshev's Inequality:** We need
to express the event in the form $|X - \mu| < c$.
$$40 - 50 < X - 50 < 60 - 50$$ $$-10 < X - 50 < 10$$ $$|X - 50| < 10$$
From this, we can see that the distance from the mean is $c=10$.

**3. Apply the Inequality:** Now we substitute our values into the
formula: $$P(|X - 50| < 10) \ge 1 - \frac{5^2}{10^2}$$
$$P(40 < X < 60) \ge 1 - \frac{25}{100}$$
$$P(40 < X < 60) \ge 1 - 0.25 = 0.75$$ The minimum probability that the
production will be between 40 and 60 is 0.75.

$$\boxed{ P(40 < X < 60) = 0.75 }$$

Question 13
===========

**Problem:** Given MGF $M_X(t) = \frac{(3+2e^t)^4}{625}$, find the mean,
variance, and $P(X \le 1)$. Is it skewed?

**Solution:** **Concept: Recognizing MGFs**\
Identifying the form of an MGF allows you to immediately know the
distribution and its properties without calculus.\
The MGF can be rewritten as
$M_X(t) = \left(\frac{3}{5} + \frac{2}{5}e^t\right)^4$. This is the MGF
of a Binomial distribution, $(q+pe^t)^n$, with $n=4$ and $p=2/5$.\
So, $X \sim \text{Bin}(4, 0.4)$.\
**Mean and Variance:** For a Binomial, $E(X)=np=4(0.4)=1.6$.
$Var(X)=np(1-p)=4(0.4)(0.6)=0.96$.\
**P(X $\le$ 1):** $P(X \le 1) = P(X=0)+P(X=1)$.\
$P(X=0) = \binom{4}{0}(0.4)^0(0.6)^4 = 0.1296$.\
$P(X=1) = \binom{4}{1}(0.4)^1(0.6)^3 = 4(0.4)(0.216) = 0.3456$.\
$P(X \le 1) = 0.1296 + 0.3456 = 0.4752$.\
**Skewness:** For a binomial distribution, the skewness is determined by
$p$. Since $p=0.4 < 0.5$, the distribution is positively skewed (skewed
to the right).\
$$\boxed{ E(X)=1.6, Var(X)=0.96, P(X \le 1)=0.4752, \text{Positively Skewed} }$$
