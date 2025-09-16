Question 1
==========

**Distribution Used:** Hypergeometric Distribution.

**Reasoning:** This problem involves sampling without replacement from a
finite population. The population consists of 7 judges, which is divided
into two distinct groups (4 who favor Ruby, 3 who favor Mini). We are
selecting a sample of 3 judges and are interested in the probability of
getting a specific number of judges from the first group.

**Solution:** Let $X$ be the number of judges in the panel of three who
favor Ruby. Ruby wins if she gets a majority of votes, which means $X$
must be 2 or 3. The total number of ways to choose 3 judges from a group
of 7 is $\binom{7}{3}$.

The number of ways to choose 2 judges who favor Ruby (from the 4
available) and 1 judge who favors Mini (from the 3 available) is:
$$\binom{4}{2}\binom{3}{1} = \frac{4!}{2!2!} \cdot \frac{3!}{1!2!} = 6 \cdot 3 = 18$$
The number of ways to choose 3 judges who favor Ruby (from the 4
available) and 0 who favor Mini is:
$$\binom{4}{3}\binom{3}{0} = \frac{4!}{3!1!} \cdot 1 = 4$$ The total
number of ways to form a panel of 3 from 7 is:
$$\binom{7}{3} = \frac{7!}{3!4!} = \frac{7 \cdot 6 \cdot 5}{3 \cdot 2 \cdot 1} = 35$$
The probability that Ruby wins is the sum of the probabilities of these
favorable outcomes:
$$P(\text{Ruby wins}) = P(X=2) + P(X=3) = \frac{\binom{4}{2}\binom{3}{1} + \binom{4}{3}}{\binom{7}{3}} = \frac{18 + 4}{35} = \frac{22}{35} \approx \boxed{0.6286}$$

Question 2
==========

**Distribution Used:** Binomial Distribution.

**Reasoning:** This scenario involves a fixed number of independent
trials ($n$ bombs dropped). Each trial has two possible outcomes (hit or
miss), and the probability of success (a hit) is constant for each trial
($p=0.5$). We are interested in the number of successes.

**Solution:** Let $n$ be the number of bombs that must be dropped. Let
$X$ be the number of successful hits. Given the probability of a single
hit is $p=0.5$. The target is destroyed if there are at least 2 hits.
The random variable $X$ follows a Binomial distribution,
$X \sim \text{Bin}(n, 0.5)$. We want to find the smallest $n$ such that
the probability of destroying the target is at least 99%, i.e.,
$P(X \ge 2) \ge 0.99$.

This is equivalent to $1 - P(X < 2) \ge 0.99$, which simplifies to
$P(X=0) + P(X=1) \le 0.01$. Using the Binomial probability mass function
$P(X=k) = \binom{n}{k}p^k(1-p)^{n-k}$:
$$\binom{n}{0}(0.5)^0(0.5)^n + \binom{n}{1}(0.5)^1(0.5)^{n-1} \le 0.01$$
$$(1)(0.5)^n + n(0.5)^n \le 0.01$$ $$(n+1)(0.5)^n \le 0.01$$ We can test
values of $n$:

-   For $n=8: (8+1)(0.5)^8 = 9 \cdot 0.00390625 = 0.035 > 0.01$

-   For $n=9: (9+1)(0.5)^9 = 10 \cdot 0.001953125 = 0.0195 > 0.01$

-   For $n=10: (10+1)(0.5)^{10} = 11 \cdot 0.0009765625 = 0.0107 > 0.01$

-   For
    $n=11: (11+1)(0.5)^{11} = 12 \cdot 0.00048828125 = 0.00586 \le 0.01$

The smallest integer value of $n$ that satisfies the condition is
$\boxed{n=11}$.

Question 3
==========

**Distribution Used:** Binomial Distribution.

**Reasoning:** We have a fixed number of independent items (3). Each
item can be either defective or not (two outcomes), with a constant
probability of being defective ($p=0.1$).

**Solution:** Let $X$ be the number of defective items in a sample of
three. $X$ follows a Binomial distribution with parameters $n=3$ and
$p=0.1$, i.e., $X \sim \text{Bin}(3, 0.1)$. We want to find the
probability that at most one item is defective, which is $P(X \le 1)$.
$$P(X \le 1) = P(X=0) + P(X=1)$$ Using the Binomial PMF:
$$P(X=0) = \binom{3}{0}(0.1)^0(0.9)^3 = 1 \cdot 1 \cdot (0.9)^3 = 0.729$$
$$P(X=1) = \binom{3}{1}(0.1)^1(0.9)^2 = 3 \cdot 0.1 \cdot 0.81 = 0.243$$
$$P(X \le 1) = 0.729 + 0.243 = \boxed{0.972}$$

Question 4
==========

**Distribution Used:** Binomial Distribution.

**Reasoning:** The question explicitly states that $X$ follows a
Binomial distribution. We use the properties of the mean and variance of
this distribution to find its parameters.

**Solution:** For a Binomial distribution, the mean is $\mu = np$ and
the variance is $\sigma^2 = npq$, where $q=1-p$. We are given: Mean
$np = 8$. Standard deviation $\sqrt{npq} = 2$, which implies variance
$npq = 4$.

We can solve for the parameters:
$$q = \frac{npq}{np} = \frac{4}{8} = 0.5$$ Since $p+q=1$, we have
$p = 1 - 0.5 = 0.5$. Now we find $n$:
$$np = 8 \implies n(0.5) = 8 \implies n = 16$$ So,
$X \sim \text{Bin}(16, 0.5)$. We need to find $P(X \ge 3)$.
$$P(X \ge 3) = 1 - P(X < 3) = 1 - [P(X=0) + P(X=1) + P(X=2)]$$ Calculate
the individual probabilities:
$$P(X=0) = \binom{16}{0}(0.5)^0(0.5)^{16} = (\frac{1}{2})^{16}$$
$$P(X=1) = \binom{16}{1}(0.5)^1(0.5)^{15} = 16 (\frac{1}{2})^{16}$$
$$P(X=2) = \binom{16}{2}(0.5)^2(0.5)^{14} = \frac{16 \cdot 15}{2} (\frac{1}{2})^{16} = 120 (\frac{1}{2})^{16}$$
$$P(X \ge 3) = 1 - \frac{1 + 16 + 120}{2^{16}} = 1 - \frac{137}{65536} = \frac{65399}{65536} \approx \boxed{0.9979}$$

Question 5
==========

**Distribution Used:** Binomial Distribution.

**Reasoning:** For an $n$-component system, each component functions
independently with probability $p$. The number of functioning components
follows a Binomial distribution.

**Solution:** Let $P_n$ be the probability that an $n$-component system
operates effectively. For a 3-component system, it operates if at least
$\lceil 3/2 \rceil = 2$ components function. Let
$X_3 \sim \text{Bin}(3, p)$.
$$P_3 = P(X_3 \ge 2) = P(X_3=2) + P(X_3=3) = \binom{3}{2}p^2(1-p) + \binom{3}{3}p^3 = 3p^2(1-p) + p^3 = 3p^2 - 2p^3$$
For a 5-component system, it operates if at least
$\lceil 5/2 \rceil = 3$ components function. Let
$X_5 \sim \text{Bin}(5, p)$. $$\begin{aligned}
P_5 &= P(X_5 \ge 3) = P(X_5=3) + P(X_5=4) + P(X_5=5) \\
&= \binom{5}{3}p^3(1-p)^2 + \binom{5}{4}p^4(1-p) + \binom{5}{5}p^5 \\
&= 10p^3(1-2p+p^2) + 5p^4(1-p) + p^5 \\
&= 10p^3 - 20p^4 + 10p^5 + 5p^4 - 5p^5 + p^5 \\
&= 6p^5 - 15p^4 + 10p^3\end{aligned}$$ We want to find the values of $p$
for which $P_5 > P_3$. $$6p^5 - 15p^4 + 10p^3 > 3p^2 - 2p^3$$ Since
$p \ne 0$, we can divide by $p^2$ (as $p=0$ makes both probabilities 0).
$$6p^3 - 15p^2 + 10p > 3 - 2p$$ $$6p^3 - 15p^2 + 12p - 3 > 0$$
$$2p^3 - 5p^2 + 4p - 1 > 0$$ We can factor this polynomial. Notice that
$p=1/2$ is a root:
$2(1/8)-5(1/4)+4(1/2)-1 = 1/4 - 5/4 + 2 - 1 = -1+1=0$. So $(p-1/2)$ or
$(2p-1)$ is a factor. $$(2p-1)(p^2 - 2p + 1) > 0$$ $$(2p-1)(p-1)^2 > 0$$
Since $(p-1)^2 \ge 0$ for all $p$ and we require $0 < p < 1$, the term
$(p-1)^2$ is always positive. Therefore, the inequality holds if
$2p-1 > 0$, which means $\boxed{p > 1/2}$. So, for $p \in (1/2, 1)$, the
5-component system is more reliable.

Question 6
==========

**Distribution Used:** Geometric Distribution.

**Reasoning:** The standard moment generating function (MGF) for a
geometric random variable $X$ (number of trials for the first success)
with success probability $p$ is $M_X(t) = \frac{pe^t}{1 - qe^t}$, where
$q=1-p$. The given MGF can be rearranged into this form.

**Solution:** The given MGF is $M_X(t) = \frac{2e^t}{7-5e^t}$. To match
the standard form, we divide the numerator and denominator by 7:
$$M_X(t) = \frac{(2/7)e^t}{1 - (5/7)e^t}$$ By comparison, we see this is
the MGF of a geometric distribution with success probability $p = 2/7$.
The probability of failure is $q = 1-p = 5/7$. We need to find
$P(X>7 | X>5)$. The geometric distribution has the memoryless property,
which states that for any integers $a, b > 0$:
$$P(X > a+b | X > a) = P(X > b)$$ Applying this property with $a=5$ and
$b=2$: $$P(X > 7 | X > 5) = P(X > 5+2 | X > 5) = P(X > 2)$$ The
probability that more than $k$ trials are needed is $P(X>k) = q^k$.
$$P(X > 2) = q^2 = (\frac{5}{7})^2 = \boxed{\frac{25}{49}}$$

Question 7
==========

**Distribution Used:** Binomial Distribution (twice).

**Reasoning:** First, the number of defective diskettes in a single pack
of 10 is modeled by a binomial distribution. Second, the number of packs
returned out of 3 is also modeled by a binomial distribution, where a
\"success\" is the event that a pack is returned.

**Solution:** **Step 1: Find the probability that a single pack is
returned.** Let $X$ be the number of defective diskettes in a pack of
10. The probability of a diskette being defective is 0.01. So,
$X \sim \text{Bin}(10, 0.01)$. A pack is returned if it contains more
than one defective diskette, i.e., if $X > 1$. Let $p_{return}$ be the
probability of returning a pack.
$$p_{return} = P(X > 1) = 1 - P(X \le 1) = 1 - [P(X=0) + P(X=1)]$$
$$P(X=0) = \binom{10}{0}(0.01)^0(0.99)^{10} = (0.99)^{10} \approx 0.90438$$
$$P(X=1) = \binom{10}{1}(0.01)^1(0.99)^{9} = 10(0.01)(0.99)^9 \approx 0.09135$$
$$p_{return} = 1 - (0.90438 + 0.09135) = 1 - 0.99573 = \boxed{0.00427}$$

**Step 2: Find the probability that at most one of three packs is
returned.** Let $Y$ be the number of packs returned out of 3. Now we
have a new binomial experiment with $n=3$ trials and success probability
$p = p_{return} = 0.00427$. So, $Y \sim \text{Bin}(3, 0.00427)$. We need
to find $P(Y \le 1) = P(Y=0) + P(Y=1)$.
$$P(Y=0) = \binom{3}{0}(0.00427)^0(1-0.00427)^3 = (0.99573)^3 \approx 0.98726$$
$$P(Y=1) = \binom{3}{1}(0.00427)^1(1-0.00427)^2 = 3(0.00427)(0.99573)^2 \approx 0.01270$$
$$P(Y \le 1) = 0.98726 + 0.01270 = \boxed{0.99996}$$

Question 8
==========

**Distribution Used:** Negative Binomial Distribution.

**Reasoning:** This problem involves repeating independent Bernoulli
trials until a fixed number of successes ($r=3$) is achieved. The random
variable $X$ is the total number of trials required. This is the
definition of a Negative Binomial distribution.

**Solution:** Let $X$ be the number of repetitions required to achieve
$r=3$ successful outcomes. The probability of success in a single trial
is $p=0.8$. Thus, $X$ follows a Negative Binomial distribution,
$X \sim \text{NB}(r=3, p=0.8)$. The probability mass function is
$P(X=k) = \binom{k-1}{r-1}p^r(1-p)^{k-r}$ for $k=r, r+1, \dots$. We need
to find the probability that at least 5 repetitions are required, i.e.,
$P(X \ge 5)$. $$P(X \ge 5) = 1 - P(X < 5) = 1 - [P(X=3) + P(X=4)]$$
Calculate the probabilities:
$$P(X=3) = \binom{3-1}{3-1}(0.8)^3(0.2)^{3-3} = \binom{2}{2}(0.8)^3 = 1 \cdot 0.512 = 0.512$$
$$P(X=4) = \binom{4-1}{3-1}(0.8)^3(0.2)^{4-3} = \binom{3}{2}(0.8)^3(0.2)^1 = 3 \cdot 0.512 \cdot 0.2 = 0.3072$$
$$P(X \ge 5) = 1 - (0.512 + 0.3072) = 1 - 0.8192 = \boxed{0.1808}$$

Question 9
==========

**Distribution Used:** Hypergeometric Distribution.

**Reasoning:** This is another example of sampling without replacement
from a finite population that contains two types of items (defective and
non-defective TVs).

**Solution:** Let $X$ be the number of defective TV sets in the sample.
The parameters for the Hypergeometric distribution are:

-   Population size, $N = 20$

-   Number of successes in the population (defective TVs), $K = 5$

-   Sample size, $n = 4$

We want to find the probability that the sample has exactly one
defective, $P(X=1)$. The Hypergeometric probability formula is
$P(X=k) = \frac{\binom{K}{k}\binom{N-K}{n-k}}{\binom{N}{n}}$.
$$P(X=1) = \frac{\binom{5}{1}\binom{20-5}{4-1}}{\binom{20}{4}} = \frac{\binom{5}{1}\binom{15}{3}}{\binom{20}{4}}$$
$$\binom{5}{1} = 5$$
$$\binom{15}{3} = \frac{15 \cdot 14 \cdot 13}{3 \cdot 2 \cdot 1} = 5 \cdot 7 \cdot 13 = 455$$
$$\binom{20}{4} = \frac{20 \cdot 19 \cdot 18 \cdot 17}{4 \cdot 3 \cdot 2 \cdot 1} = 5 \cdot 19 \cdot 3 \cdot 17 = 4845$$
$$P(X=1) = \frac{5 \cdot 455}{4845} = \frac{2275}{4845} = \boxed{\frac{455}{969} \approx 0.4696}$$

Question 10
===========

**Distribution Used:** Poisson Distribution.

**Reasoning:** The number of computers sold, $X$, is given to follow a
Poisson distribution. The profit, $Y$, is a transformation of this
random variable $X$.

**Solution:** The number of computers the store sells in a week is
$X \sim \text{Poisson}(\lambda=2)$. The profit is
$Y = 2000 \times \min(X, 10)$, since there are only 10 computers in
stock. The possible values for $Y$ are $2000j$ for
$j \in \{0, 1, 2, \ldots, 10\}$. The probability mass function of $X$ is
$P(X=k) = \frac{e^{-2}2^k}{k!}$.

For $j \in \{0, 1, \ldots, 9\}$, the profit is $Y=2000j$ if and only if
the number of computers sold is $X=j$.
$$P(Y = 2000j) = P(X=j) = \frac{e^{-2}2^j}{j!} \quad \text{for } j=0, 1, \ldots, 9$$
The profit is $Y=20000$ if the number of potential sales is 10 or more,
but the store can only sell its entire stock of 10.
$$P(Y = 20000) = P(X \ge 10) = \sum_{k=10}^{\infty} P(X=k) = 1 - \sum_{k=0}^{9} P(X=k)$$
So the probability distribution of $Y$ is: $$P(Y=y) = 
\begin{cases} 
\frac{e^{-2}2^{y/2000}}{(y/2000)!} & \text{if } y \in \{0, 2000, 4000, \ldots, 18000\} \\
1 - \sum_{k=0}^{9} \frac{e^{-2}2^k}{k!} & \text{if } y = 20000 \\
0 & \text{otherwise}
\end{cases}$$

Question 11
===========

**Distribution Used:** Poisson Distribution and Bayes' Theorem.

**Reasoning:** The number of colds follows a Poisson distribution with
one of two possible parameters. We are given prior probabilities for
which parameter is correct. After observing new data (no colds), we use
Bayes' Theorem to update our belief about which parameter is correct.

**Solution:** Let $B$ be the event that the drug is beneficial for an
individual. Let $B^C$ be the event that the drug has no effect. Let $X$
be the number of colds the individual contracts in a year.

We are given the following information:

-   Prior probabilities: $P(B) = 0.75$, $P(B^C) = 0.25$.

-   Conditional distributions: $X|B \sim \text{Poisson}(\lambda=2)$, and
    $X|B^C \sim \text{Poisson}(\lambda=3)$.

The individual has no cold, which is the event $X=0$. We want to find
the probability that the drug is beneficial given this evidence, i.e.,
$P(B|X=0)$.

Using Bayes' Theorem:
$$P(B|X=0) = \frac{P(X=0|B)P(B)}{P(X=0)} = \frac{P(X=0|B)P(B)}{P(X=0|B)P(B) + P(X=0|B^C)P(B^C)}$$
First, calculate the likelihoods from the Poisson PMF
$P(X=k|\lambda) = \frac{e^{-\lambda}\lambda^k}{k!}$:
$$P(X=0|B) = \frac{e^{-2}2^0}{0!} = e^{-2} \approx 0.1353$$
$$P(X=0|B^C) = \frac{e^{-3}3^0}{0!} = e^{-3} \approx 0.0498$$ Now,
substitute all values into Bayes' formula:
$$P(B|X=0) = \frac{(e^{-2})(0.75)}{(e^{-2})(0.75) + (e^{-3})(0.25)} = \frac{0.1353 \cdot 0.75}{0.1353 \cdot 0.75 + 0.0498 \cdot 0.25}$$
$$P(B|X=0) = \frac{0.1015}{0.1015 + 0.01245} = \frac{0.1015}{0.11395} \approx \boxed{0.8907}$$
It is highly likely (about 89% probability) that the drug is beneficial
for this individual.

Question 12
===========

**Distribution Used:** Poisson Distribution.

**Reasoning:** The Poisson distribution is used to model the number of
events (defects) occurring in a fixed interval of space (or time). The
average rate of defects is given for the whole area, and we can scale
this rate down to find the average rate for a smaller sub-area.

**Solution:** Let $X_{total}$ be the number of defects on the entire
chip. The average is given as 300. We can model this with a Poisson
distribution where the rate parameter for the whole chip is
$\lambda_{total} = 300$. We are interested in a randomly selected area
that comprises 2% of the total surface area. Assuming the defects are
uniformly distributed over the chip's surface, the rate for this smaller
area will be proportional to its size. Let $Y$ be the number of defects
in the 2% area. The new rate parameter is:
$$\lambda_{new} = \lambda_{total} \times 0.02 = 300 \times 0.02 = 6$$
So, $Y \sim \text{Poisson}(\lambda=6)$. We want to find the probability
that no more than 4 defects are found in this area, i.e., $P(Y \le 4)$.
$$P(Y \le 4) = P(Y=0) + P(Y=1) + P(Y=2) + P(Y=3) + P(Y=4)$$
$$P(Y \le 4) = \sum_{k=0}^{4} \frac{e^{-6}6^k}{k!} = e^{-6} \left( \frac{6^0}{0!} + \frac{6^1}{1!} + \frac{6^2}{2!} + \frac{6^3}{3!} + \frac{6^4}{4!} \right)$$
$$P(Y \le 4) = e^{-6} \left( 1 + 6 + \frac{36}{2} + \frac{216}{6} + \frac{1296}{24} \right) = e^{-6} (1 + 6 + 18 + 36 + 54) = 115 e^{-6}$$
Using $e^{-6} \approx 0.00247875$:
$$P(Y \le 4) \approx 115 \times 0.00247875 \approx \boxed{0.2851}$$

Question 13
===========

**Distribution Used:** Continuous Uniform Distribution (Geometric
Probability).

**Reasoning:** The arrival times are independent and uniformly
distributed over a fixed time interval. This is a classic geometric
probability problem where probabilities are found by comparing areas.

**Solution:** Let the time interval from 5 p.m. to 6 p.m. be represented
by $[0, 60]$ minutes. Let $X$ be the arrival time of the boy and $Y$ be
the arrival time of the girl. We have $X \sim U(0, 60)$ and
$Y \sim U(0, 60)$. The joint sample space is a square in the Cartesian
plane with vertices at (0,0), (60,0), (60,60), and (0,60). The area of
this sample space is $A_{total} = 60 \times 60 = 3600$.

They will meet if the absolute difference between their arrival times is
no more than 20 minutes. $$|X - Y| \le 20$$ This is equivalent to the
pair of inequalities:
$$-20 \le X - Y \le 20 \implies Y \le X + 20 \quad \text{and} \quad Y \ge X - 20$$
It is easier to calculate the area of the region where they do \*not\*
meet and subtract it from the total area. They do not meet if
$|X - Y| > 20$, which means:
$$Y > X + 20 \quad \text{or} \quad Y < X - 20$$ These two inequalities
define two triangular regions at the corners of our sample space square.

1.  The region $Y > X + 20$ is an upper-left triangle with vertices
    (0,20), (0,60), and (40,60). The base and height are both
    $60-20=40$. Area = $\frac{1}{2} \times 40 \times 40 = 800$.

2.  The region $Y < X - 20$ is a lower-right triangle with vertices
    (20,0), (60,0), and (60,40). The base and height are both
    $60-20=40$. Area = $\frac{1}{2} \times 40 \times 40 = 800$.

The total area where they do not meet is
$A_{no-meet} = 800 + 800 = 1600$. The area of the favorable region where
they do meet is
$A_{meet} = A_{total} - A_{no-meet} = 3600 - 1600 = 2000$. The
probability that they will meet is the ratio of the areas:
$$P(\text{meet}) = \frac{A_{meet}}{A_{total}} = \frac{2000}{3600} = \frac{20}{36} = \boxed{\frac{5}{9}}$$

Question 14
===========

**Distribution Used:** Discrete Uniform Distribution.

**Reasoning:** We need to identify the distribution by matching its MGF
to a known form. The MGF of a discrete uniform distribution on the
integers $\{1, 2, \dots, N\}$ is
$M_X(t) = \frac{e^t(e^{Nt}-1)}{N(e^t-1)}$.

**Solution:** The given MGF is:
$$M_X(t) = \frac{e^t(e^{10t}-1)}{10(e^t-1)}$$ This perfectly matches the
MGF of a discrete uniform distribution on $\{1, 2, \dots, N\}$ with
$N=10$. The variance of a discrete uniform random variable on the first
$N$ integers is given by the formula:
$$\text{Var}(X) = \frac{N^2 - 1}{12}$$ Substituting $N=10$:
$$\text{Var}(X) = \frac{10^2 - 1}{12} = \frac{99}{12} = \frac{33}{4} = \boxed{8.25}$$

Question 15
===========

**Distribution Used:** Continuous Uniform Distribution.

**Reasoning:** The low bid is explicitly defined as a continuous uniform
random variable. The problem requires maximizing an expected value,
which involves integrating the profit function against the probability
density function.

**Solution:** Let $X$ be the low bid for the job, with
$X \sim U(\frac{3}{4}C, 2C)$. The PDF of $X$ is
$f(x) = \frac{1}{2C - \frac{3}{4}C} = \frac{1}{\frac{5}{4}C} = \frac{4}{5C}$
for $x \in [\frac{3}{4}C, 2C]$. Let $b$ be the contractor's bid. The
contractor wins the job if his bid is the lowest, which means $b < X$
(assuming $X$ represents the lowest competing bid). The profit,
$P(b,X)$, is:
$$P(b,X) = \begin{cases} b-C & \text{if } b < X \text{ (wins the job)} \\ 0 & \text{if } b \ge X \text{ (loses the job)} \end{cases}$$
We want to maximize the expected profit, $g(b) = E[P(b,X)]$. The
contractor should only bid in the range where winning is possible, so
$b \in [\frac{3}{4}C, 2C]$.
$$g(b) = \int_{3C/4}^{2C} P(b,x) f(x) dx = \int_{b}^{2C} (b-C) \frac{4}{5C} dx$$
$$g(b) = (b-C) \frac{4}{5C} \int_{b}^{2C} dx = (b-C) \frac{4}{5C} [x]_b^{2C} = (b-C) \frac{4}{5C} (2C-b)$$
To find the maximum, we take the derivative with respect to $b$ and set
it to zero.
$$g(b) = \frac{4}{5C} (2Cb - b^2 - 2C^2 + Cb) = \frac{4}{5C} (-b^2 + 3Cb - 2C^2)$$
$$g'(b) = \frac{d}{db} \left[ \frac{4}{5C} (-b^2 + 3Cb - 2C^2) \right] = \frac{4}{5C}(-2b + 3C)$$
Set $g'(b) = 0$: $$-2b + 3C = 0 \implies b = \frac{3}{2}C$$ The second
derivative is $g''(b) = -\frac{8}{5C} < 0$, which confirms this is a
maximum. The bid that maximizes expected profit is $\boxed{b = 1.5C}$.

Question 16
===========

**Distributions Used:** Exponential, then Binomial.

**Reasoning:** The lifetime of a single bulb is modeled by an
exponential distribution. The number of bulbs from a set of 10 that are
still working after a certain time is a count of successes in 10
independent Bernoulli trials, which follows a Binomial distribution.

**Solution:** **Step 1: Find the probability a single bulb is working
after 100 hours.** Let $X$ be the lifetime of a bulb. $X$ is
exponentially distributed with a mean of 50 hours. Mean
$= 1/\lambda = 50$, so the rate parameter is $\lambda = 1/50$. The
probability that a single bulb works for more than 100 hours is
$p = P(X > 100)$. For an exponential distribution, the survival function
is $P(X > t) = e^{-\lambda t}$.
$$p = P(X > 100) = e^{-(1/50) \cdot 100} = e^{-2}$$

**Step 2: Use the Binomial distribution for the 10 bulbs.** Let $Y$ be
the number of bulbs working after 100 hours. We have 10 independent
bulbs, so $Y$ follows a Binomial distribution with $n=10$ and success
probability $p = e^{-2}$. $Y \sim \text{Bin}(10, e^{-2})$. We want the
probability that at least two bulbs are working, $P(Y \ge 2)$.
$$P(Y \ge 2) = 1 - P(Y < 2) = 1 - [P(Y=0) + P(Y=1)]$$ Using
$p=e^{-2} \approx 0.1353$ and $q=1-p \approx 0.8647$:
$$P(Y=0) = \binom{10}{0} p^0 q^{10} = (1-e^{-2})^{10} \approx (0.8647)^{10} \approx 0.2335$$
$$P(Y=1) = \binom{10}{1} p^1 q^9 = 10(e^{-2})(1-e^{-2})^9 \approx 10(0.1353)(0.8647)^9 \approx 0.3627$$
$$P(Y \ge 2) = 1 - (0.2335 + 0.3627) = 1 - 0.5962 = \boxed{0.4038}$$

Question 17
===========

**Distribution Used:** Exponential Distribution (in a mixture model).

**Reasoning:** The lifetime of a bulb follows one of two different
exponential distributions depending on its origin. We use the Law of
Total Probability to find the overall probability of survival for a
randomly selected bulb.

**Solution:** Let $A$ be the event that a bulb is from plant A, and $B$
be the event it is from plant B. Plant B produces three times as many
bulbs as A. If plant A produces $k$ bulbs, plant B produces $3k$ bulbs,
for a total of $4k$. The prior probabilities are:
$P(A) = \frac{k}{4k} = \frac{1}{4}$ and
$P(B) = \frac{3k}{4k} = \frac{3}{4}$.

Let $X$ be the lifetime of a bulb. For plant A: mean is 5 months, so
$\lambda_A = 1/5$. The survival function is $P(X>t|A) = e^{-t/5}$. For
plant B: mean is 2 months, so $\lambda_B = 1/2$. The survival function
is $P(X>t|B) = e^{-t/2}$.

We want to find the probability that a bulb purchased at random will
burn for at least 5 months, $P(X>5)$. Using the Law of Total
Probability: $$P(X>5) = P(X>5|A)P(A) + P(X>5|B)P(B)$$
$$P(X>5) = (e^{-5/5}) \cdot (\frac{1}{4}) + (e^{-5/2}) \cdot (\frac{3}{4})$$
$$P(X>5) = \frac{1}{4}e^{-1} + \frac{3}{4}e^{-2.5}$$ Using
$e^{-1} \approx 0.3679$ and $e^{-2.5} \approx 0.0821$:
$$P(X>5) \approx \frac{1}{4}(0.3679) + \frac{3}{4}(0.0821) = 0.091975 + 0.061575 = \boxed{0.15355}$$

Question 18
===========

**Distribution Used:** Exponential Distribution.

**Reasoning:** The motherboard's lifetime is modeled by an exponential
distribution. The profit is a piecewise function of this random
lifetime. The expected profit is found by integrating this profit
function against the lifetime's PDF.

**Solution:** Let $X$ be the lifetime (time to failure) of a motherboard
in years. The mean life is 2 years, so the rate parameter is
$\lambda = 1/2$ per year. The PDF of $X$ is $f(x) = \frac{1}{2}e^{-x/2}$
for $x > 0$. The guarantee period is 6 months, which is $0.5$ years.

The profit, let's call it $H(X)$, is a random variable that depends on
$X$:
$$H(x) = \begin{cases} 5000 - 2000 = 3000 & \text{if } X < 0.5 \text{ (fails within guarantee)} \\ 5000 & \text{if } X \ge 0.5 \text{ (does not fail within guarantee)} \end{cases}$$
The expected profit is $E[H(X)]$:
$$E[H(X)] = 3000 \cdot P(X < 0.5) + 5000 \cdot P(X \ge 0.5)$$ First, we
find the probabilities. For an exponential distribution, the CDF is
$P(X \le t) = 1 - e^{-\lambda t}$.
$$P(X < 0.5) = 1 - e^{-(1/2) \cdot 0.5} = 1 - e^{-1/4}$$
$$P(X \ge 0.5) = 1 - P(X < 0.5) = e^{-1/4}$$ Now, calculate the expected
profit:
$$E[H(X)] = 3000(1 - e^{-1/4}) + 5000(e^{-1/4}) = 3000 - 3000e^{-1/4} + 5000e^{-1/4} = 3000 + 2000e^{-1/4}$$
Using $e^{-1/4} \approx 0.7788$:
$$E[H(X)] \approx 3000 + 2000(0.7788) = 3000 + 1557.60 = \boxed{4557.60}$$
The expected profit is Rs. 4557.60.

Question 19
===========

**Distribution Used:** Exponential Distribution.

**Reasoning:** This is a problem about competing risks. The system fails
as soon as the \*first\* component fails. The minimum of independent
exponential random variables is itself an exponential random variable.
We need to find a conditional probability.

**Solution:** Let $X_i$ be the lifetime of component $i$, with
$X_i \sim \text{Exp}(\lambda_i)$. The system is a series system, so its
lifetime $X_{sys}$ is the minimum of the component lifetimes:
$X_{sys} = \min(X_1, X_2, \ldots, X_n)$. The lifetime of the system,
$X_{sys}$, is exponentially distributed with a rate parameter
$\lambda_{sys} = \sum_{i=1}^n \lambda_i$. The probability that the
system fails before time $t$ is
$P(X_{sys} \le t) = 1 - e^{-t \sum \lambda_i}$.

We want to find the probability that the failure was caused \*only\* by
component $j$, given that the system failed before time $t$. The event
\"failure caused only by component $j$\" is the event that component $j$
fails first, i.e., $X_j < X_i$ for all $i \ne j$. The probability that
component $j$ is the one that fails first is given by
$P(X_j = \min_i X_i) = \frac{\lambda_j}{\sum_i \lambda_i}$. This result
is independent of time. The question asks for
$P(\text{only component j fails before t} | \text{system fails before t})$.
The event \"only component j fails before t\" means $X_j \le t$ and
$X_i > t$ for all $i \ne j$. This interpretation seems incorrect for a
series system, as the system fails once the first component fails. A
better interpretation is: $P(X_j < \min_{i \ne j} X_i | X_{sys} \le t)$.
Since the event $X_j < \min_{i \ne j} X_i$ is independent of the time of
failure, this conditional probability is simply
$P(X_j < \min_{i \ne j} X_i)$.
$$P(\text{failure caused by j}) = \frac{\lambda_j}{\sum_{i=1}^n \lambda_i}$$
Note: The solution provided seems to calculate a different quantity.
Let's analyze it:
$\frac{(1-e^{-\lambda_j t})e^{-t \sum_{i\ne j}\lambda_i}}{1-e^{-t\sum \lambda_i}}$.
The numerator represents
$P(X_j \le t \text{ and } X_i > t \text{ for } i \ne j)$. This is the
probability that component j fails before t AND all other components
survive past t. This is not the definition of a series system failure.
However, if asked to follow the provided solution's logic, that would be
the answer. Based on standard theory, the time-independent result is
correct.

Question 20
===========

**Distributions Used:** Exponential, then Binomial.

**Reasoning:** This is analogous to question 16. The lifetime of a
single AC follows an exponential distribution. The number of ACs still
working after 100 hours, out of a set of 5, follows a Binomial
distribution.

**Solution:** **Step 1: Find the probability a single AC is working
after 100 hours.** Let $X$ be the lifetime of an AC. $X$ is
exponentially distributed with a mean of 100 hours. Mean
$= 1/\lambda = 100$, so the rate parameter is $\lambda = 1/100$. The
probability that a single AC works for more than 100 hours is
$p = P(X > 100)$.
$$p = P(X > 100) = e^{-\lambda t} = e^{-(1/100) \cdot 100} = e^{-1}$$

**Step 2: Use the Binomial distribution for the 5 ACs.** Let $Y$ be the
number of ACs working after 100 hours. We have 5 independent ACs, so $Y$
follows a Binomial distribution with $n=5$ and success probability
$p = e^{-1}$. $Y \sim \text{Bin}(5, e^{-1})$. We want the probability
that at least two ACs are in working condition, $P(Y \ge 2)$.
$$P(Y \ge 2) = 1 - P(Y < 2) = 1 - [P(Y=0) + P(Y=1)]$$ Using
$p=e^{-1} \approx 0.3679$ and $q=1-p \approx 0.6321$:
$$P(Y=0) = \binom{5}{0} p^0 q^5 = (1-e^{-1})^5 \approx (0.6321)^5 \approx 0.1003$$
$$P(Y=1) = \binom{5}{1} p^1 q^4 = 5(e^{-1})(1-e^{-1})^4 \approx 5(0.3679)(0.6321)^4 \approx 0.2952$$
$$P(Y \ge 2) = 1 - (0.1003 + 0.2952) = 1 - 0.3955 = \boxed{0.6045}$$

Question 21
===========

**Distribution Used:** Poisson Process / Gamma Distribution.

**Reasoning:** The time \*between\* arrivals is exponential, which
implies the \*number\* of arrivals in a given time period follows a
Poisson distribution. The time \*until the k-th arrival\* follows a
Gamma distribution. Let $T_k$ be the time of the $k$-th arrival.
$T_k = X_1 + X_2 + \dots + X_k$, where $X_i$ are the independent
inter-arrival times. Since $X_i \sim \text{Exp}(\lambda)$, their sum
$T_k$ follows a Gamma distribution with shape $k$ and rate $\lambda$.

**Solution:** The time between arrivals, $X$, is exponential with mean
10 minutes. Mean $= 1/\lambda = 10$, so the rate of arrivals is
$\lambda = 1/10$ customers per minute. The time until the 3rd customer
arrives, $T_3$, is the sum of three independent exponential random
variables, each with rate $\lambda = 1/10$. Thus, $T_3$ follows a Gamma
distribution with shape parameter $r=3$ and rate parameter
$\lambda=1/10$. The PDF of $T_3$ is
$f(t) = \frac{\lambda^r t^{r-1} e^{-\lambda t}}{\Gamma(r)} = \frac{(1/10)^3 t^2 e^{-t/10}}{2!}$
for $t>0$. We want to find the probability that the third customer
arrives within 15 minutes, $P(T_3 \le 15)$.
$$P(T_3 \le 15) = \int_0^{15} \frac{1}{2000} t^2 e^{-t/10} dt$$ An
alternative approach uses the relationship between the Gamma CDF and the
Poisson PMF: $P(T_r \le t) = P(N_t \ge r)$, where $N_t$ is the number of
arrivals in time $t$. Here, $N_t \sim \text{Poisson}(\lambda t)$. In our
case, $t=15$ minutes. The parameter for the Poisson distribution is
$\mu = \lambda t = (1/10) \cdot 15 = 1.5$. So we need to calculate
$P(N_{15} \ge 3)$, where $N_{15} \sim \text{Poisson}(1.5)$.
$$P(N_{15} \ge 3) = 1 - P(N_{15} < 3) = 1 - [P(N_{15}=0) + P(N_{15}=1) + P(N_{15}=2)]$$
$$P(N_{15}=0) = \frac{e^{-1.5}(1.5)^0}{0!} = e^{-1.5} \approx 0.2231$$
$$P(N_{15}=1) = \frac{e^{-1.5}(1.5)^1}{1!} = 1.5 e^{-1.5} \approx 0.3347$$
$$P(N_{15}=2) = \frac{e^{-1.5}(1.5)^2}{2!} = 1.125 e^{-1.5} \approx 0.2510$$
$$P(N_{15} \ge 3) = 1 - (0.2231 + 0.3347 + 0.2510) = 1 - 0.8088 =\boxed{0.1912}$$
\*Note: The solution provided gives $0.7769$, which is $1-e^{-1.5}$.
This would be the probability of the FIRST customer arriving in 15
minutes, not the third. There seems to be an error in the provided
solution key.\*

Question 22
===========

**Distribution Used:** Gamma Distribution.

**Reasoning:** The question explicitly states that the lead time follows
a Gamma distribution. We use the given mean and variance to determine
the distribution's parameters.

**Solution:** Let $X$ be the lead time. $X$ follows a Gamma distribution
with shape parameter $r$ and rate parameter $\lambda$. The mean is
$E[X] = r/\lambda$ and the variance is $\text{Var}(X) = r/\lambda^2$. We
are given: $E[X] = 20$ $\text{Var}(X) = 100$ (since standard deviation
is 10). From these, we can find the parameters:
$$\lambda = \frac{E[X]}{\text{Var}(X)} = \frac{20}{100} = \frac{1}{5}$$
$$r = \lambda \cdot E[X] = \frac{1}{5} \cdot 20 = 4$$ So,
$X \sim \text{Gamma}(r=4, \lambda=1/5)$. We want to find the probability
of receiving an order within 15 days, $P(X \le 15)$. We use the
relationship $P(X \le t) = P(N_t \ge r)$, where
$N_t \sim \text{Poisson}(\lambda t)$. Here $t=15$, so the Poisson
parameter is $\mu = \lambda t = (1/5) \cdot 15 = 3$. We need to
calculate $P(N_{15} \ge 4)$, where $N_{15} \sim \text{Poisson}(3)$.
$$P(N_{15} \ge 4) = 1 - [P(N_{15}=0) + P(N_{15}=1) + P(N_{15}=2) + P(N_{15}=3)]$$
$$P(N_{15} \ge 4) = 1 - e^{-3} \left( \frac{3^0}{0!} + \frac{3^1}{1!} + \frac{3^2}{2!} + \frac{3^3}{3!} \right)$$
$$P(N_{15} \ge 4) = 1 - e^{-3} \left( 1 + 3 + 4.5 + 4.5 \right) = 1 - 13e^{-3}$$
Using $e^{-3} \approx 0.049787$:
$$P(X \le 15) \approx 1 - 13(0.049787) = 1 - 0.64723 = \boxed{0.35277}$$

Question 23
===========

**Distribution Used:** Gamma Distribution and Bayes' Theorem.

**Reasoning:** The equipment's life follows one of two Gamma
distributions depending on the manufacturer. We use the mean and
variance to find the parameters for each. Then, given that a unit has
survived for 12 years, we use Bayes' Theorem to find the posterior
probability that it came from manufacturer A.

**Solution:** Let $A$ be the event the equipment is from manufacturer A,
and $B$ from B. Priors: $P(A) = 0.75$, $P(B) = 0.25$. Let $X$ be the
lifetime. For manufacturer A: $E[X] = r_A/\lambda_A = 4$,
$\text{Var}(X) = r_A/\lambda_A^2 = 8$. $\lambda_A = 4/8 = 1/2$.
$r_A = 4 \cdot \lambda_A = 2$. So,
$X|A \sim \text{Gamma}(r=2, \lambda=1/2)$.

For manufacturer B: $E[X] = r_B/\lambda_B = 2$,
$\text{Var}(X) = r_B/\lambda_B^2 = 4$. $\lambda_B = 2/4 = 1/2$.
$r_B = 2 \cdot \lambda_B = 1$. So,
$X|B \sim \text{Gamma}(r=1, \lambda=1/2)$, which is an Exponential
distribution.

We are given the event $E$ that a unit is working after 12 years, i.e.,
$X>12$. We want to find $P(A|X>12)$. Using Bayes' Theorem:
$$P(A|X>12) = \frac{P(X>12|A)P(A)}{P(X>12|A)P(A) + P(X>12|B)P(B)}$$ We
need to calculate the survival probabilities $P(X>12)$ for each case.
For a Gamma distribution,
$P(X>t) = \sum_{k=0}^{r-1} \frac{e^{-\lambda t}(\lambda t)^k}{k!}$.
$P(X>12|A)$: Here $r=2, \lambda=1/2, t=12$. $\lambda t = 6$.
$$P(X>12|A) = e^{-6} \left( \frac{6^0}{0!} + \frac{6^1}{1!} \right) = e^{-6}(1+6) = 7e^{-6}$$
$P(X>12|B)$: Here $r=1, \lambda=1/2, t=12$. $\lambda t = 6$.
$$P(X>12|B) = e^{-6} \left( \frac{6^0}{0!} \right) = e^{-6}$$ Now
substitute into Bayes' formula:
$$P(A|X>12) = \frac{(7e^{-6})(0.75)}{(7e^{-6})(0.75) + (e^{-6})(0.25)} = \frac{7 \cdot 0.75}{7 \cdot 0.75 + 0.25} = \frac{5.25}{5.25 + 0.25} = \frac{5.25}{5.5} = \frac{21}{22} \approx \boxed{0.9545}$$
\*Note: The provided solution seems to have made an error in the final
calculation, resulting in $2e^{-6}$. The Bayesian probability should be
a value between 0 and 1.\*

Question 24
===========

**Distributions Used:** Exponential, Gamma, and Uniform (Mixture Model).

**Reasoning:** The printing time follows one of three different
distributions based on which printer is selected. We use the Law of
Total Probability to find the overall probability that a print job takes
less than one minute.

**Solution:** Let $I, II, III$ be the events that Printer I, II, or III
is used. Priors: $P(I)=0.3, P(II)=0.3, P(III)=0.4$. Let $X$ be the
printing time. We want to find $P(X < 1)$. Using the Law of Total
Probability:
$$P(X<1) = P(X<1|I)P(I) + P(X<1|II)P(II) + P(X<1|III)P(III)$$ **Printer
I:** $X|I \sim \text{Exp}(\text{mean}=3)$. So $\lambda_I = 1/3$.
$$P(X<1|I) = 1 - e^{-(1/3) \cdot 1} = 1 - e^{-1/3} \approx 1 - 0.7165 = 0.2835$$
**Printer II:**
$X|II \sim \text{Gamma}(\text{mean}=2, \text{variance}=2)$.
$E[X] = r/\lambda = 2$. $\text{Var}(X) = r/\lambda^2 = 2$.
$\lambda = 2/2 = 1$. $r = 2 \cdot \lambda = 2$. So
$X|II \sim \text{Gamma}(r=2, \lambda=1)$. $P(X<1|II) = P(N_1 \ge 2)$
where $N_1 \sim \text{Poisson}(\lambda t = 1\cdot 1 = 1)$.
$P(N_1 \ge 2) = 1 - [P(N_1=0) + P(N_1=1)] = 1 - e^{-1}(\frac{1^0}{0!} + \frac{1^1}{1!}) = 1 - 2e^{-1} \approx 1 - 2(0.3679) = 1 - 0.7358 = 0.2642$.
**Printer III:** $X|III \sim U(0, 4)$. The PDF is $f(x)=1/4$ for
$x \in [0,4]$.
$$P(X<1|III) = \int_0^1 \frac{1}{4} dx = \frac{1}{4} = 0.25$$ Now,
combine everything:
$$P(X<1) = (0.2835)(0.3) + (0.2642)(0.3) + (0.25)(0.4)$$
$$P(X<1) = 0.08505 + 0.07926 + 0.10 = \boxed{0.26431}$$

Question 25
===========

**Distribution Used:** Weibull Distribution.

**Reasoning:** The lifetime is explicitly modeled by a Weibull
distribution. We are given information about a conditional probability
of failure, which allows us to solve for the unknown parameter $\alpha$.

**Solution:** Let $X$ be the lifetime of a component.
$X \sim \text{Weibull}(\alpha, \beta)$ with $\beta=2$. The survival
function for a Weibull distribution is
$R(t) = P(X>t) = e^{-(\alpha t)^\beta}$. With $\beta=2$, this is
$R(t) = e^{-\alpha^2 t^2}$. Let's rename $\alpha^2$ to just $\alpha$ for
simplicity as in the solution hint, so $R(t) = e^{-\alpha t^2}$.

We are given that 15% of components that have lasted 90 hours fail
before 100 hours. This is a conditional probability:
$$P(X < 100 | X > 90) = 0.15$$ Using the formula
$P(A|B) = \frac{P(A \cap B)}{P(B)}$:
$$P(X < 100 | X > 90) = \frac{P(90 < X < 100)}{P(X > 90)} = \frac{P(X>90) - P(X>100)}{P(X>90)} = 1 - \frac{P(X>100)}{P(X>90)}$$
$$0.15 = 1 - \frac{e^{-\alpha (100)^2}}{e^{-\alpha (90)^2}} = 1 - e^{-\alpha(10000 - 8100)} = 1 - e^{-1900\alpha}$$
Now, we solve for $\alpha$: $$e^{-1900\alpha} = 1 - 0.15 = 0.85$$
$$-1900\alpha = \ln(0.85) \approx -0.1625$$
$$\alpha = \frac{-0.1625}{-1900} \approx 0.0000855$$ Now we need to
determine the probability that a component is working after 80 hours,
which is $P(X>80)$.
$$P(X > 80) = R(80) = e^{-\alpha (80)^2} = e^{-0.0000855 \cdot 6400}$$
$$P(X > 80) = e^{-0.5472} \approx \boxed{0.5786}$$
