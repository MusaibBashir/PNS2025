---
title: Assignment 4
nav_order: 5
---

Question 1
==========

**Distribution/Concept Used:** Survival Analysis (Hazard Rate).\
**Reasoning:** The problem provides a mortality rate, which is a hazard
rate function $Z(t)$. The probability of survival is described by the
survival function $R(t)$, which can be derived from the hazard rate.
Conditional survival probability is then calculated from the survival
function.

**Solution:** The survival function $R(t) = P(\text{survival time} > t)$
is related to the hazard rate $Z(t)$ by:
$$R(t) = \exp\left(-\int_0^t Z(u)du\right)$$ Given $Z(t) = 0.5 + 2t$, we
first compute the integral:
$$\int_0^t (0.5 + 2u)du = \left[0.5u + u^2\right]_0^t = 0.5t + t^2$$ So,
the survival function is $R(t) = e^{-(0.5t + t^2)}$. We need to find the
probability that the child will survive to age 2, given that they have
survived to age 1. This is the conditional probability $P(T>2 | T>1)$.
$$P(T>2 | T>1) = \frac{P(T>2 \cap T>1)}{P(T>1)} = \frac{P(T>2)}{P(T>1)} = \frac{R(2)}{R(1)}$$
Now, we calculate $R(1)$ and $R(2)$:
$$R(1) = e^{-(0.5(1) + 1^2)} = e^{-1.5}$$
$$R(2) = e^{-(0.5(2) + 2^2)} = e^{-(1+4)} = e^{-5}$$ The conditional
probability is:
$$\frac{R(2)}{R(1)} = \frac{e^{-5}}{e^{-1.5}} = e^{-5 - (-1.5)} = e^{-3.5}$$
$$\boxed{ P(T>2|T>1) = e^{-3.5} \approx 0.0302 }$$

Question 2
==========

**Solution:** Let $X$ be the marks, with $X \sim N(\mu, \sigma^2)$. Let
$Z = (X-\mu)/\sigma \sim N(0,1)$. We are given: 1.
$P(X < 45) = 0.10 \implies P(Z < \frac{45-\mu}{\sigma}) = 0.10$. From
the Z-table, $\Phi(z)=0.10$ gives $z \approx -1.28$.
$$\frac{45-\mu}{\sigma} = -1.28 \quad (1)$$ 2.
$P(X > 75) = 0.05 \implies P(Z > \frac{75-\mu}{\sigma}) = 0.05 \implies P(Z \le \frac{75-\mu}{\sigma}) = 0.95$.
From the Z-table, $\Phi(z)=0.95$ gives $z \approx 1.645$.
$$\frac{75-\mu}{\sigma} = 1.645 \quad (2)$$ We have a system of two
linear equations: $45 - \mu = -1.28\sigma$ $75 - \mu = 1.645\sigma$
Subtracting the first from the second:
$(75-\mu) - (45-\mu) = 1.645\sigma - (-1.28\sigma) \implies 30 = 2.925\sigma \implies \sigma = \frac{30}{2.925} \approx 10.256$.
Substituting $\sigma$ back into (1):
$45 - \mu = -1.28(10.256) \implies 45 - \mu = -13.128 \implies \mu = 58.128$.

Now we find the percentages for first and second class. **First Class
(60% to 75%):**
$P(60 < X \le 75) = P(\frac{60-58.128}{10.256} < Z \le \frac{75-58.128}{10.256}) = P(0.18 < Z \le 1.645)$
$P(0.18 < Z \le 1.645) = \Phi(1.645) - \Phi(0.18) = 0.95 - 0.5714 = 0.3786$.
**Second Class (45% to 60%):**
$P(45 < X \le 60) = P(\frac{45-58.128}{10.256} < Z \le \frac{60-58.128}{10.256}) = P(-1.28 < Z \le 0.18)$
$P(-1.28 < Z \le 0.18) = \Phi(0.18) - \Phi(-1.28) = 0.5714 - 0.10 = 0.4714$.
$$\boxed{ \text{First Class: 37.86\%, Second Class: 47.14\%} }$$

Question 3
==========

**Solution:** Let $X$ be the diameter. We are given
$X \sim N(\mu=3, \sigma^2=0.005^2)$. The specifications are
$3.0 \pm 0.01$ cm, so the acceptable range is $(2.99, 3.01)$. A ball is
scrapped if its diameter is outside this range, i.e., $X < 2.99$ or
$X > 3.01$. First, find the probability that a ball is \*not\* scrapped:
$$P(2.99 < X < 3.01) = P\left(\frac{2.99 - 3}{0.005} < Z < \frac{3.01 - 3}{0.005}\right)$$
$$= P\left(\frac{-0.01}{0.005} < Z < \frac{0.01}{0.005}\right) = P(-2 < Z < 2)$$
$$= \Phi(2) - \Phi(-2) = \Phi(2) - (1-\Phi(2)) = 2\Phi(2) - 1$$ From the
Z-table, $\Phi(2) \approx 0.97725$.
$$P(\text{not scrapped}) = 2(0.97725) - 1 = 1.9545 - 1 = 0.9545$$ The
probability that a ball is scrapped is $1 - P(\text{not scrapped})$.
$$P(\text{scrapped}) = 1 - 0.9545 = 0.0455$$ On average, 4.55% of
manufactured balls will be scrapped.
$$\boxed{ \text{4.55\% of balls will be scrapped} }$$

Question 4
==========

**Solution:** Let $X$ be the width, with
$X \sim N(\mu=0.9, \sigma^2=0.003^2)$. Specification limits are
$0.9 \pm 0.005$, i.e., $(0.895, 0.905)$. **Part 1: Percentage of
defective forgings** A forging is defective if $X < 0.895$ or
$X > 0.905$. $$P(\text{defective}) = 1 - P(0.895 < X < 0.905)$$
$$= 1 - P\left(\frac{0.895 - 0.9}{0.003} < Z < \frac{0.905 - 0.9}{0.003}\right) = 1 - P(-1.67 < Z < 1.67)$$
$$= 1 - (2\Phi(1.67) - 1) = 2 - 2\Phi(1.67) = 2(1 - \Phi(1.67))$$ From
Z-table, $\Phi(1.67) \approx 0.9525$.
$$P(\text{defective}) = 2(1 - 0.9525) = 2(0.0475) = 0.095$$ The
percentage of defective forgings is 9.5%.

**Part 2: Maximum allowable value of $\sigma$** We need no more than 1
defective in 100, so $P(\text{defective}) \le 0.01$. This means
$P(\text{acceptable}) = P(0.895 < X < 0.905) \ge 0.99$.
$$P\left(\frac{0.895-0.9}{\sigma} < Z < \frac{0.905-0.9}{\sigma}\right) \ge 0.99$$
$$P\left(-\frac{0.005}{\sigma} < Z < \frac{0.005}{\sigma}\right) \ge 0.99$$
This implies
$\Phi\left(\frac{0.005}{\sigma}\right) - \Phi\left(-\frac{0.005}{\sigma}\right) \ge 0.99$,
which means $2\Phi\left(\frac{0.005}{\sigma}\right) - 1 \ge 0.99$.
$$\Phi\left(\frac{0.005}{\sigma}\right) \ge \frac{1.99}{2} = 0.995$$
From the Z-table, we find the z-value corresponding to a cumulative
probability of 0.995, which is $z \approx 2.575$.
$$\frac{0.005}{\sigma} \ge 2.575 \implies \sigma \le \frac{0.005}{2.575} \approx 0.00194$$
$$\boxed{ \text{Percentage defective: 9.5\%. Maximum allowable } \sigma: 0.00194 }$$

Question 5
==========

**Solution:** Let $X$ be the height in cm.
$X \sim N(\mu=200, \sigma^2=10^2)$. **Part 1: Greatest height jumped
with probability 0.95** We want to find a height $h_1$ such that
$P(X \le h_1) = 0.95$.
$$P\left(Z \le \frac{h_1 - 200}{10}\right) = 0.95$$ From the Z-table,
the z-value for a 0.95 cumulative probability is $z \approx 1.645$.
$$\frac{h_1 - 200}{10} = 1.645 \implies h_1 - 200 = 16.45 \implies h_1 = 216.45 \text{ cm}$$

**Part 2: Height cleared only 10% of the time** We want to find a height
$h_2$ such that $P(X > h_2) = 0.10$. This is equivalent to
$P(X \le h_2) = 0.90$.
$$P\left(Z \le \frac{h_2 - 200}{10}\right) = 0.90$$ From the Z-table,
the z-value for a 0.90 cumulative probability is $z \approx 1.28$.
$$\frac{h_2 - 200}{10} = 1.28 \implies h_2 - 200 = 12.8 \implies h_2 = 212.8 \text{ cm}$$
$$\boxed{ \text{Greatest height (0.95 prob): 216.45 cm. Height cleared 10\% of time: 212.8 cm} }$$

Question 6
==========

**Solution:** Let $X$ be the marks. $X \sim N(\mu=74, \sigma^2=62.41)$.
The standard deviation is $\sigma = \sqrt{62.41} = 7.9$. a) **Lowest
passing grade (lowest 10% fail):** Find grade $g_a$ such that
$P(X \le g_a) = 0.10$. $P(Z \le \frac{g_a-74}{7.9}) = 0.10$. The z-score
is $z \approx -1.28$.
$\frac{g_a-74}{7.9} = -1.28 \implies g_a = 74 - 1.28(7.9) = 74 - 10.112 = 63.888$.

b\) **Highest B (top 5% get A's):** Find grade $g_b$ such that
$P(X > g_b) = 0.05$. This is the minimum score for an A. The highest B
is just below this.
$P(Z > \frac{g_b-74}{7.9}) = 0.05 \implies P(Z \le \frac{g_b-74}{7.9}) = 0.95$.
The z-score is $z \approx 1.645$.
$\frac{g_b-74}{7.9} = 1.645 \implies g_b = 74 + 1.645(7.9) = 74 + 12.9955 = 86.9955$.

c\) **Lowest B (top 10% A's, next 25% B's):** The B range starts where
the top 35% of students begin. Find $g_c$ such that $P(X > g_c) = 0.35$.
$P(Z > \frac{g_c-74}{7.9}) = 0.35 \implies P(Z \le \frac{g_c-74}{7.9}) = 0.65$.
The z-score is $z \approx 0.385$.
$\frac{g_c-74}{7.9} = 0.385 \implies g_c = 74 + 0.385(7.9) = 74 + 3.0415 = 77.0415$.
$$\boxed{ \text{a) 63.89} \quad \text{b) 87.00} \quad \text{c) 77.04} }$$

Question 7
==========

**Solution:** Let $X \sim N(\mu, \sigma^2=1)$. The profit function
$G(X)$ is:
$$G(X) = \begin{cases} C_0 & 6 \le X \le 8 \\ -C_1 & X < 6 \\ -C_2 & X > 8 \end{cases}$$
The expected profit $E[G(X)]$ is:
$$E[G(X)] = C_0 P(6 \le X \le 8) - C_1 P(X < 6) - C_2 P(X > 8)$$ In
terms of the standard normal CDF $\Phi$:
$$E(\mu) = C_0[\Phi(8-\mu) - \Phi(6-\mu)] - C_1\Phi(6-\mu) - C_2[1-\Phi(8-\mu)]$$
$$E(\mu) = (C_0+C_2)\Phi(8-\mu) - (C_0+C_1)\Phi(6-\mu) - C_2$$ To
maximize, we take the derivative with respect to $\mu$ and set to zero.
Let $\phi(z)$ be the standard normal PDF.
$\frac{d}{d\mu}\Phi(z-\mu) = -\phi(z-\mu)$.
$$\frac{dE}{d\mu} = -(C_0+C_2)\phi(8-\mu) + (C_0+C_1)\phi(6-\mu) = 0$$
$$(C_0+C_1)\phi(6-\mu) = (C_0+C_2)\phi(8-\mu)$$
$$(C_0+C_1)\frac{1}{\sqrt{2\pi}}e^{-(6-\mu)^2/2} = (C_0+C_2)\frac{1}{\sqrt{2\pi}}e^{-(8-\mu)^2/2}$$
Taking the natural logarithm of both sides:
$$\ln(C_0+C_1) - \frac{(6-\mu)^2}{2} = \ln(C_0+C_2) - \frac{(8-\mu)^2}{2}$$
$$2\ln\left(\frac{C_0+C_1}{C_0+C_2}\right) = (6-\mu)^2 - (8-\mu)^2 = (36-12\mu+\mu^2) - (64-16\mu+\mu^2) = -28+4\mu$$
$$4\mu = 28 + 2\ln\left(\frac{C_0+C_1}{C_0+C_2}\right) \implies \mu = 7 + \frac{1}{2}\ln\left(\frac{C_0+C_1}{C_0+C_2}\right)$$
$$\boxed{ \mu = 7 + \frac{1}{2}\ln\left(\frac{C_1+C_0}{C_2+C_0}\right) }$$

Question 8
==========

**Distributions Used:** Normal, then Binomial. **Reasoning:** First, we
use the normal distribution to find the probability ($p$) that a single
randomly selected candidate meets the IQ criteria. Then, since we are
selecting four candidates independently, the number of candidates who
meet the criteria follows a binomial distribution.

**Solution:** Let $X$ be the IQ level, $X \sim N(\mu=90, \sigma^2=5^2)$.
**Part 1: Probability for one candidate** Find $p = P(85 < X < 95)$.
$$p = P\left(\frac{85-90}{5} < Z < \frac{95-90}{5}\right) = P(-1 < Z < 1) = 2\Phi(1)-1$$
Using $\Phi(1) \approx 0.8413$, we get $p = 2(0.8413) - 1 = 0.6826$.

**Part 2: Probability for four candidates** Let $Y$ be the number of
candidates (out of 4) with IQ between 85 and 95.
$Y \sim \text{Bin}(n=4, p=0.6826)$. We want to find $P(Y \ge 2)$.
$$P(Y \ge 2) = 1 - P(Y < 2) = 1 - [P(Y=0) + P(Y=1)]$$ Let
$q=1-p=0.3174$.
$$P(Y=0) = \binom{4}{0}p^0q^4 = (0.3174)^4 \approx 0.0101$$
$$P(Y=1) = \binom{4}{1}p^1q^3 = 4(0.6826)(0.3174)^3 \approx 0.0872$$
$$P(Y \ge 2) = 1 - (0.0101 + 0.0872) = 1 - 0.0973 = 0.9027$$
$$\boxed{ P(Y \ge 2) \approx 0.9027 }$$

Question 9
==========

**Distributions Used:** Binomial and Normal Approximation.
**Reasoning:** First, we calculate the probability ($p$) that a single
machine works for more than two years by integrating its PDF. The number
of machines working for more than two years ($Y$) follows a Binomial
distribution. Since the number of trials ($n=200$) is large, we can use
the normal approximation to the binomial distribution to calculate the
final probability.

**Solution:** Let $X$ be the time to failure. PDF is $f(x)=2/x^3$ for
$x>1$. **Step 1: Find p**
$p = P(X>2) = \int_2^\infty \frac{2}{x^3} dx = 2\left[-\frac{1}{2x^2}\right]_2^\infty = -\left[\frac{1}{x^2}\right]_2^\infty = -(0 - \frac{1}{4}) = \frac{1}{4} = 0.25$.

**Step 2: Binomial to Normal Approximation** Let $Y$ be the number of
machines working for more than 2 years.
$Y \sim \text{Bin}(n=200, p=0.25)$. Mean of Y:
$\mu = np = 200(0.25) = 50$. Variance of Y:
$\sigma^2 = np(1-p) = 200(0.25)(0.75) = 37.5$. Standard deviation:
$\sigma = \sqrt{37.5} \approx 6.124$. We use normal approximation
$Y \approx N(50, 37.5)$ to find $P(Y \ge 60)$. We apply continuity
correction.
$$P(Y \ge 60) \approx P(Y_{norm} > 59.5) = P\left(Z > \frac{59.5 - 50}{6.124}\right) = P(Z > 1.55)$$
$$= 1 - \Phi(1.55) = 1 - 0.9394 = 0.0606$$
$$\boxed{ P(Y \ge 60) \approx 0.0606 }$$

Question 10
===========

**Distribution Used:** Binomial and Normal Approximation. **Reasoning:**
The number of students who cannot solve the question is a binomial
random variable. Since the number of students ($n=200$) is large, we can
use the normal approximation with continuity correction.

**Solution:** Let $X$ be the number of students who \*cannot\* solve the
question. The probability of a student not solving it is $p=0.5$. So,
$X \sim \text{Bin}(n=200, p=0.5)$. Mean: $\mu = np = 200(0.5) = 100$.
Variance: $\sigma^2 = np(1-p) = 200(0.5)(0.5) = 50$. Standard deviation:
$\sigma = \sqrt{50} \approx 7.071$. We need to find $P(X \ge 110)$.
Using normal approximation with continuity correction:
$$P(X \ge 110) \approx P(X_{norm} > 109.5) = P\left(Z > \frac{109.5 - 100}{7.071}\right) = P(Z > 1.34)$$
$$= 1 - \Phi(1.34) = 1 - 0.9099 = 0.0901$$
$$\boxed{ P(X \ge 110) \approx 0.0901 }$$

Question 11
===========

**Distribution Used:** Poisson and Normal Approximation. **Reasoning:**
The number of arrivals in a fixed time interval in a Poisson process
follows a Poisson distribution. Since the rate parameter ($\lambda$) is
large, we can approximate this Poisson distribution with a normal
distribution, using continuity correction.

**Solution:** The rate of arrivals is 1 per 3 minutes, so
$\lambda_{min} = 1/3$ trains/minute. The time interval is from 2:00 p.m.
to 3:00 p.m., which is 60 minutes. The rate for this interval is
$\lambda = 60 \times (1/3) = 20$. Let $X$ be the number of trains in
this hour. $X \sim \text{Poisson}(\lambda=20)$. Since $\lambda=20$ is
large, we can use a normal approximation. For a Poisson,
$\mu=\lambda=20$ and $\sigma^2=\lambda=20$. So,
$\sigma = \sqrt{20} \approx 4.472$. We need to find
$P(17 \le X \le 25)$. Applying continuity correction:
$$P(17 \le X \le 25) \approx P(16.5 < X_{norm} < 25.5)$$
$$= P\left(\frac{16.5 - 20}{4.472} < Z < \frac{25.5 - 20}{4.472}\right) = P(-0.78 < Z < 1.23)$$
$$= \Phi(1.23) - \Phi(-0.78) = 0.8907 - (1 - \Phi(0.78)) = 0.8907 - (1 - 0.7823) = 0.8907 - 0.2177 = 0.673$$
$$\boxed{ P(17 \le X \le 25) \approx 0.673 }$$

Question 12
===========

**Distribution Used:** Log-normal Distribution. **Reasoning:** A
variable Y is log-normally distributed if $\ln(Y)$ is normally
distributed. We use this property to transform the problem into a
standard normal distribution problem.

**Solution:** Given $Y$ has a log-normal distribution with parameters
$\mu=0.8$ and $\sigma=0.1$. This means $X = \ln(Y)$ is normally
distributed with mean $\mu_X=0.8$ and standard deviation $\sigma_X=0.1$.
So, $X \sim N(0.8, 0.1^2)$. **Part 1: Probability** We want to find
$P(Y > 2.7)$. $$P(Y > 2.7) = P(\ln(Y) > \ln(2.7)) = P(X > 0.99326)$$
Standardize this:
$$P\left(Z > \frac{0.99326 - 0.8}{0.1}\right) = P(Z > 1.9326) \approx P(Z > 1.93)$$
$$= 1 - \Phi(1.93) = 1 - 0.9732 = 0.0268$$

**Part 2: Interval** We want to find values $y_1, y_2$ such that
$P(y_1 < Y < y_2) = 0.95$. This is equivalent to
$P(\ln(y_1) < \ln(Y) < \ln(y_2)) = 0.95$, or
$P(\ln(y_1) < X < \ln(y_2)) = 0.95$. For a normal distribution, the
symmetric interval containing 95% of the probability is
$(\mu_X - 1.96\sigma_X, \mu_X + 1.96\sigma_X)$. Lower bound for X:
$0.8 - 1.96(0.1) = 0.8 - 0.196 = 0.604$. Upper bound for X:
$0.8 + 1.96(0.1) = 0.8 + 0.196 = 0.996$. So,
$\ln(y_1) = 0.604 \implies y_1 = e^{0.604} \approx 1.8294$. And,
$\ln(y_2) = 0.996 \implies y_2 = e^{0.996} \approx 2.7074$.
$$\boxed{ P(Y>2.7) \approx 0.0268. \quad \text{95\% interval for Y is (1.829, 2.707)} }$$

Question 13
===========

**Distribution Used:** Beta Distribution. **Reasoning:** We are given
the mean and variance of a Beta distributed random variable. We can use
the formulas for the mean and variance to solve for the distribution's
parameters, $\alpha$ and $\beta$. Once the PDF is fully specified, we
can integrate it to find the required probability.

**Solution:** Let $X \sim \text{Beta}(\alpha, \beta)$. The PDF is
$f(x) = \frac{1}{B(\alpha, \beta)}x^{\alpha-1}(1-x)^{\beta-1}$. Mean:
$E[X] = \frac{\alpha}{\alpha+\beta} = \frac{2}{3}$. Variance:
$\text{Var}(X) = \frac{\alpha\beta}{(\alpha+\beta)^2(\alpha+\beta+1)} = \frac{1}{18}$.
From the mean, $3\alpha = 2(\alpha+\beta) \implies \alpha = 2\beta$.
Substitute this into the variance formula:
$$\frac{(2\beta)\beta}{(2\beta+\beta)^2(2\beta+\beta+1)} = \frac{2\beta^2}{(3\beta)^2(3\beta+1)} = \frac{2\beta^2}{9\beta^2(3\beta+1)} = \frac{2}{9(3\beta+1)} = \frac{1}{18}$$
$$36 = 9(3\beta+1) \implies 4 = 3\beta+1 \implies 3\beta=3 \implies \beta=1$$
Since $\alpha = 2\beta$, we have $\alpha=2$. So,
$X \sim \text{Beta}(2, 1)$. The PDF is
$f(x) = \frac{1}{B(2,1)}x^{2-1}(1-x)^{1-1} = \frac{x}{1/2} = 2x$ for
$0<x<1$. We need to find $P(0.2 < X < 0.5)$.
$$P(0.2 < X < 0.5) = \int_{0.2}^{0.5} 2x dx = [x^2]_{0.2}^{0.5} = (0.5)^2 - (0.2)^2 = 0.25 - 0.04 = 0.21$$
$$\boxed{ P(0.2 < X < 0.5) = 0.21 }$$

Question 14
===========

**Distribution Used:** Zero-Truncated Poisson Distribution.
**Reasoning:** We need to compute the expected value of a function of a
discrete random variable, $g(X) = 1/(1+X)$. This is done by summing
$g(x)P(X=x)$ over all possible values of $x$.

**Solution:** The PMF is
$P(X=x) = \frac{e^{-\lambda}\lambda^x}{x!(1-e^{-\lambda})}$ for
$x=1,2,3,\dots$. We want to find $E\left[\frac{1}{1+X}\right]$.
$$E\left[\frac{1}{1+X}\right] = \sum_{x=1}^{\infty} \frac{1}{1+x} P(X=x) = \sum_{x=1}^{\infty} \frac{1}{1+x} \frac{e^{-\lambda}\lambda^x}{x!(1-e^{-\lambda})}$$
$$= \frac{e^{-\lambda}}{1-e^{-\lambda}} \sum_{x=1}^{\infty} \frac{\lambda^x}{(x+1)!}$$
To evaluate the sum, we manipulate it to resemble the Taylor series for
$e^\lambda = \sum_{k=0}^\infty \frac{\lambda^k}{k!}$. Let $k=x+1$. When
$x=1, k=2$. The sum becomes:
$$\sum_{k=2}^{\infty} \frac{\lambda^{k-1}}{k!} = \frac{1}{\lambda} \sum_{k=2}^{\infty} \frac{\lambda^k}{k!}$$
The full series is
$e^\lambda = \frac{\lambda^0}{0!} + \frac{\lambda^1}{1!} + \sum_{k=2}^\infty \frac{\lambda^k}{k!} = 1 + \lambda + \sum_{k=2}^\infty \frac{\lambda^k}{k!}$.
So, $\sum_{k=2}^\infty \frac{\lambda^k}{k!} = e^\lambda - 1 - \lambda$.
Substituting this back:
$$E\left[\frac{1}{1+X}\right] = \frac{e^{-\lambda}}{1-e^{-\lambda}} \cdot \frac{1}{\lambda}(e^\lambda - 1 - \lambda) = \frac{e^{-\lambda}(e^\lambda - 1 - \lambda)}{\lambda(1-e^{-\lambda})} = \frac{1 - e^{-\lambda} - \lambda e^{-\lambda}}{\lambda(1-e^{-\lambda})}$$
$$\boxed{ E\left[\frac{1}{1+X}\right] = \frac{1 - e^{-\lambda} - \lambda e^{-\lambda}}{\lambda(1-e^{-\lambda})} }$$
