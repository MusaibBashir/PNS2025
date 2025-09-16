---
title: Distributions
nav_order: 7
---

  **Distribution**           **PMF / PDF**                                                            $\mathbf{E[X]}$                  $\mathbf{Var(X)}$                                         **MGF $M_X(t)$**                            **Standard case / Example**
  -------------------------- ------------------------------------------------------------------------ -------------------------------- --------------------------------------------------------- ------------------------------------------- -------------------------------------------------------------
  Bernoulli$(p)$             $P(X=1)=p,\;P(X=0)=1-p$                                                  $p$                              $p(1-p)$                                                  $1-p+pe^{t}$                                Single trial with success probability $p$ (e.g. coin flip).
  Binomial$(n,p)$            $\binom{n}{x}p^x(1-p)^{n-x},\; x=0,\dots,n$                              $np$                             $np(1-p)$                                                 $(1-p+pe^t)^n$                              Number of successes in $n$ independent Bernoulli trials.
  Hypergeometric$(N,K,n)$    $\dfrac{\binom{K}{x}\binom{N-K}{\,n-x}}{\binom{N}{n}}$                   $n\frac{K}{N}$                   $n\frac{K}{N}\Big(1-\frac{K}{N}\Big)\frac{N-n}{N-1}$      ---                                         Number of successes in $n$ draws *without replacement*.
  Negative Binomial$(r,p)$   $\binom{k+r-1}{k}(1-p)^k p^r,\;k=0,1,\dots$                              $\tfrac{r(1-p)}{p}$              $\tfrac{r(1-p)}{p^2}$                                     $\Big(\tfrac{p}{1-(1-p)e^t}\Big)^r$         Failures before $r$ successes.
  Geometric$(p)$             $p(1-p)^{k-1},\; k=1,2,\dots$                                            $\tfrac{1}{p}$                   $\tfrac{1-p}{p^2}$                                        $\tfrac{pe^t}{1-(1-p)e^t}$                  Trials until first success.
  Poisson$(\lambda)$         $\dfrac{e^{-\lambda}\lambda^x}{x!},\; x=0,1,\dots$                       $\lambda$                        $\lambda$                                                 $\exp(\lambda(e^t-1))$                      Counts of rare events in time/space.
  Uniform$(a,b)$ (cont.)     $\dfrac{1}{b-a},\; a<x<b$                                                $\tfrac{a+b}{2}$                 $\tfrac{(b-a)^2}{12}$                                     $\dfrac{e^{tb}-e^{ta}}{t(b-a)}$             Continuous uniform on interval $[a,b]$.
  Exponential$(\lambda)$     $\lambda e^{-\lambda x},\; x\ge0$                                        $\tfrac{1}{\lambda}$             $\tfrac{1}{\lambda^2}$                                    $\tfrac{\lambda}{\lambda-t},\; t<\lambda$   Time between Poisson arrivals.
  Normal$(\mu,\sigma^2)$     $\dfrac{1}{\sqrt{2\pi\sigma^2}} e^{-\tfrac{(x-\mu)^2}{2\sigma^2}}$       $\mu$                            $\sigma^2$                                                $\exp(\mu t+\tfrac{1}{2}\sigma^2t^2)$       Central Limit Theorem, measurement error.
  Gamma$(\alpha,\beta)$      $\dfrac{\beta^\alpha}{\Gamma(\alpha)} x^{\alpha-1} e^{-\beta x},\;x>0$   $\tfrac{\alpha}{\beta}$          $\tfrac{\alpha}{\beta^2}$                                 $\Big(\tfrac{\beta}{\beta-t}\Big)^\alpha$   Waiting time for $\alpha$-th Poisson event.
  Beta$(\alpha,\beta)$       $\dfrac{x^{\alpha-1}(1-x)^{\beta-1}}{B(\alpha,\beta)},\;0<x<1$           $\tfrac{\alpha}{\alpha+\beta}$   $\tfrac{\alpha\beta}{(\alpha+\beta)^2(\alpha+\beta+1)}$   ---                                         Models random probabilities; conjugate prior to Binomial.

  : Distributions with mean, variance, MGF, and examples

Relationships Between Distributions {#relationships-between-distributions .unnumbered}
===================================

-   **Binomial $\to$ Poisson:** If $n$ is large and $p$ is small such
    that $np=\lambda$ (fixed), then
    $$\text{Binomial}(n,p) \;\approx\; \text{Poisson}(\lambda).$$

-   **Poisson $\to$ Normal:** If $\lambda$ is large, then
    $$\text{Poisson}(\lambda) \;\approx\; N(\mu=\lambda, \sigma^2=\lambda).$$

-   **Binomial $\to$ Normal:** If $n$ is large, then
    $$\text{Binomial}(n,p) \;\approx\; N(np, np(1-p)).$$

-   **Geometric and Negative Binomial:** Geometric($p$) is a special
    case of Negative Binomial with $r=1$.

-   **Exponential and Gamma:** Sum of $k$ independent
    $\text{Exponential}(\lambda)$ random variables follows
    $$\text{Gamma}(k, 1/\lambda).$$

-   **Normal and $\chi^2$:** If $Z \sim N(0,1)$, then
    $Z^2 \sim \chi^2(1)$. More generally, the sum of squares of $k$
    independent $N(0,1)$ random variables gives $\chi^2(k)$.

-   **Gamma and Exponential:** Exponential($\lambda$) is a special case
    of Gamma with shape $k=1$.

-   **Beta and Binomial:** The Beta distribution is the *conjugate
    prior* of the Binomial distribution in Bayesian statistics.

-   **Central Limit Theorem (CLT):** The sum (or average) of i.i.d.
    random variables with finite variance converges in distribution to a
    Normal distribution as $n \to \infty$.

-   **Poisson process links:**

    -   Counts in fixed time $\to$ Poisson.

    -   Time between events $\to$ Exponential (Negative Exponential).

    -   Waiting time for $k$ events $\to$ Gamma.
