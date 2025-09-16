---
title: Assignment 1
nav_order: 2
---

Question 1
==========

**Problem:** If 7 balls are placed at random into 7 cells, find the
probability that exactly one cell remains empty.

**Solution:** First, we determine the total number of ways to place 7
balls into 7 cells. Since each ball can be placed in any of the 7 cells
independently, the total number of possible arrangements is $7^7$.

Next, we find the number of favorable arrangements where exactly one
cell is empty. This implies that one cell must contain two balls, and
the other five cells must each contain exactly one ball.

1.  **Choose the empty cell:** There are $\binom{7}{1} = 7$ ways to
    choose which cell will be empty.

2.  **Choose the cell with two balls:** From the remaining 6 cells, we
    must choose one to contain two balls. There are $\binom{6}{1} = 6$
    ways.

3.  **Choose the two balls:** From the 7 available balls, we need to
    choose the two that will be placed together. This can be done in
    $\binom{7}{2} = \frac{7 \times 6}{2} = 21$ ways.

4.  **Arrange the remaining balls:** We have 5 balls left to be placed
    in the remaining 5 cells, with one ball per cell. The number of ways
    to do this is $5! = 120$.

The total number of favorable outcomes is the product of these steps:
$$\text{Favorable ways} = \binom{7}{1} \times \binom{6}{1} \times \binom{7}{2} \times 5! = 7 \times 6 \times 21 \times 120 = 105,840$$
The probability is the ratio of favorable outcomes to the total number
of outcomes:
$$P(\text{exactly one empty cell}) = \frac{105,840}{7^7} = \frac{105,840}{823,543} \approx 0.1285$$
$$\boxed{ P(\text{exactly one empty cell}) \approx 0.1285 }$$

Question 2
==========

**Problem:** Let event E be independent of events F, $F\cup G$ and
$F\cap G$. Show that E is independent of G.

**Solution:** We are given the following from the definition of
independence:

1.  $P(E \cap F) = P(E)P(F)$

2.  $P(E \cap (F \cup G)) = P(E)P(F \cup G)$

3.  $P(E \cap (F \cap G)) = P(E)P(F \cap G)$

We want to show that $P(E \cap G) = P(E)P(G)$. We start with the second
given condition: $$P(E \cap (F \cup G)) = P(E)P(F \cup G)$$ Using the
distributive property for the left side and the addition rule for the
right side:
$$P((E \cap F) \cup (E \cap G)) = P(E)[P(F) + P(G) - P(F \cap G)]$$
Applying the addition rule to the left side:
$$P(E \cap F) + P(E \cap G) - P(E \cap F \cap G) = P(E)P(F) + P(E)P(G) - P(E)P(F \cap G)$$
Now, we substitute our known independencies (1) and (3) into this
equation:
$$P(E)P(F) + P(E \cap G) - P(E)P(F \cap G) = P(E)P(F) + P(E)P(G) - P(E)P(F \cap G)$$
We can cancel the term $P(E)P(F)$ from both sides, and add the term
$P(E)P(F \cap G)$ to both sides, which also cancels out. This leaves us
with the desired result: $$\boxed{ P(E \cap G) = P(E)P(G) }$$ Thus, E is
independent of G.

Question 3
==========

**Problem:** A pair of dice is rolled until a sum of 4 or an odd sum
appears. Find the probability that a 4 appears first.

**Solution:** Let A be the event that the sum is 4. The outcomes for A
are $\{(1,3), (2,2), (3,1)\}$. So, $P(A) = \frac{3}{36} = \frac{1}{12}$.
Let B be the event that the sum is odd. An odd sum occurs if one die is
even and the other is odd. There are $3 \times 3 = 9$ (even, odd) pairs
and $3 \times 3 = 9$ (odd, even) pairs. So,
$P(B) = \frac{18}{36} = \frac{1}{2}$. The game stops when either A or B
occurs. Since A and B are mutually exclusive, the probability of the
game stopping on any given roll is
$P(A \cup B) = P(A) + P(B) = \frac{1}{12} + \frac{1}{2} = \frac{7}{12}$.
The probability that the game does not stop on a roll is
$1 - \frac{7}{12} = \frac{5}{12}$. For a 4 to appear first, it must
appear on a roll where the game stops. The probability of this is the
probability of A given that the game stopped (A or B occurred).
$$P(\text{4 appears first}) = P(A | A \cup B) = \frac{P(A \cap (A \cup B))}{P(A \cup B)} = \frac{P(A)}{P(A \cup B)}$$
$$P(\text{4 appears first}) = \frac{1/12}{7/12} = \frac{1}{7}$$
$$\boxed{ P(\text{4 appears first}) = \frac{1}{7} }$$

Question 4
==========

**Problem:** 50% of faculty own a desktop, 25

**Solution:** Let D be the event that a faculty member owns a desktop,
and L be the event they own a laptop. We are given: $P(D) = 0.50$,
$P(L) = 0.25$, and $P(D \cap L) = 0.10$. We want to find the probability
of the symmetric difference, which is owning one type of computer but
not the other. This can be expressed as $P(D \cup L) - P(D \cap L)$.
First, find $P(D \cup L)$:
$$P(D \cup L) = P(D) + P(L) - P(D \cap L) = 0.50 + 0.25 - 0.10 = 0.65$$
The probability of owning a desktop or a laptop but not both is:
$$P(\text{one but not both}) = P(D \cup L) - P(D \cap L) = 0.65 - 0.10 = 0.55$$
Alternatively, this is
$P(D) + P(L) - 2P(D \cap L) = 0.50 + 0.25 - 2(0.10) = 0.75 - 0.20 = 0.55$.
$$\boxed{ P(\text{owns one but not both}) = 0.55 }$$

Question 5
==========

**Problem:** 20% of people are smokers. The probability of death from
lung cancer for a smoker is 10 times that for a non-smoker. The overall
probability of death from lung cancer is 0.006. What is the probability
of death from lung cancer for a smoker?

**Solution:** Let S be the event that a person is a smoker, and C be the
event of death due to lung cancer. We are given:
$P(S) = 0.20 \implies P(S^c) = 0.80$. $P(C) = 0.006$.
$P(C|S) = 10 \times P(C|S^c)$. Let $\alpha = P(C|S^c)$. Then
$P(C|S) = 10\alpha$. We need to find $10\alpha$. Using the Law of Total
Probability: $$P(C) = P(C|S)P(S) + P(C|S^c)P(S^c)$$
$$0.006 = (10\alpha)(0.20) + (\alpha)(0.80)$$
$$0.006 = 2\alpha + 0.8\alpha = 2.8\alpha$$
$$\alpha = \frac{0.006}{2.8} \approx 0.002143$$ The probability of death
due to lung cancer given that a person is a smoker is
$P(C|S) = 10\alpha$.
$$P(C|S) = 10 \times \frac{0.006}{2.8} = \frac{0.06}{2.8} \approx 0.0214$$
$$\boxed{ P(\text{death from lung cancer | smoker}) \approx 0.0214 }$$

Question 6
==========

**Problem:** Two balls are drawn with replacement from a box with n
balls marked 1 to n. Find the probability that the numbers are
consecutive integers (order ignored).

**Solution:** The total number of outcomes when drawing two balls with
replacement is $n \times n = n^2$. We are looking for pairs of draws
$(a,b)$ where $|a-b|=1$. We can count the favorable ordered pairs:

-   If the first ball drawn is 1, the second must be 2. (1 pair: (1,2))

-   If the first ball drawn is n, the second must be n-1. (1 pair:
    (n,n-1))

-   If the first ball drawn is $i$, where $1 < i < n$, the second can be
    $i-1$ or $i+1$. There are $n-2$ such values for $i$, each providing
    2 pairs. This gives $2(n-2)$ pairs.

The total number of favorable ordered pairs is
$1 + 1 + 2(n-2) = 2 + 2n - 4 = 2n-2 = 2(n-1)$. The probability is the
ratio of favorable outcomes to the total number of outcomes.
$$P(\text{consecutive}) = \frac{2(n-1)}{n^2}$$
$$\boxed{ P(\text{consecutive}) = \frac{2(n-1)}{n^2} }$$

Question 7
==========

**Problem:** Given $P(A)<1$, $P(B)>0$ and $P(A|B)=1$. Determine
$P(B^C|A^C)$.

**Solution:** From the definition of conditional probability,
$P(A|B) = \frac{P(A \cap B)}{P(B)}$. Given $P(A|B)=1$, we have
$\frac{P(A \cap B)}{P(B)} = 1$, which implies $P(A \cap B) = P(B)$. This
means that the event B is a subset of the event A. We want to find
$P(B^c | A^c) = \frac{P(B^c \cap A^c)}{P(A^c)}$. By De Morgan's laws,
$B^c \cap A^c = (A \cup B)^c$. Since B is a subset of A, $A \cup B = A$.
Therefore, $(A \cup B)^c = A^c$. So, $P(B^c \cap A^c) = P(A^c)$.
Substituting this into the expression for conditional probability:
$$P(B^c | A^c) = \frac{P(A^c)}{P(A^c)} = 1$$ (This is valid because
$P(A)<1$ implies $P(A^c)>0$). $$\boxed{ P(B^c|A^c) = 1 }$$

Question 8
==========

**Problem:** If $P(A^c)=0.3$, $P(B)=0.4$, and $P(A\cap B^c)=0.5$, find
$P(B|A\cup B^c)$.

**Solution:** First, we list the probabilities we know or can derive:
$P(A^c)=0.3 \implies P(A)=1-0.3=0.7$.
$P(B)=0.4 \implies P(B^c)=1-0.4=0.6$. $P(A \cap B^c)=0.5$. We need to
find $P(B|A \cup B^c) = \frac{P(B \cap (A \cup B^c))}{P(A \cup B^c)}$.
Let's evaluate the numerator and denominator separately. **Numerator:**
Using the distributive property:
$P(B \cap (A \cup B^c)) = P((B \cap A) \cup (B \cap B^c)) = P(A \cap B) + P(\emptyset) = P(A \cap B)$.
We can find $P(A \cap B)$ from the relation
$P(A) = P(A \cap B) + P(A \cap B^c)$.
$0.7 = P(A \cap B) + 0.5 \implies P(A \cap B) = 0.2$. **Denominator:**
Using the addition rule:
$P(A \cup B^c) = P(A) + P(B^c) - P(A \cap B^c) = 0.7 + 0.6 - 0.5 = 0.8$.
Finally, we can calculate the conditional probability:
$$P(B|A \cup B^c) = \frac{0.2}{0.8} = \frac{1}{4} = 0.25$$
$$\boxed{ P(B|A \cup B^c) = 0.25 }$$

Question 9
==========

**Problem:** Given a trinary communication channel, find certain
probabilities.

**Solution:** Let $T_i$ be the event \"Digit i is transmitted\" and
$R_i$ be the event \"Digit i is received\". **Priors:** We are given
$P(T_3)=3P(T_1)$ and $P(T_2)=2P(T_1)$. Since $P(T_1)+P(T_2)+P(T_3)=1$,
we have $P(T_1)+2P(T_1)+3P(T_1)=1 \implies 6P(T_1)=1$. So,
$P(T_1)=1/6, P(T_2)=2/6, P(T_3)=3/6$. **Channel Probabilities (from
diagram):** $P(R_1|T_1)=1-\alpha$, $P(R_2|T_1)=\alpha/2$,
$P(R_3|T_1)=\alpha/2$. $P(R_2|T_2)=1-\beta$, $P(R_1|T_2)=\beta/2$,
$P(R_3|T_2)=\beta/2$. $P(R_3|T_3)=1-\gamma$, $P(R_1|T_3)=\gamma/2$,
$P(R_2|T_3)=\gamma/2$.

\(i\) **Probability $P(T_1|R_1)$:** Using Bayes' theorem:
$P(T_1|R_1) = \frac{P(R_1|T_1)P(T_1)}{P(R_1)}$.
$P(R_1) = \sum_{i=1}^3 P(R_1|T_i)P(T_i) = (1-\alpha)\frac{1}{6} + (\frac{\beta}{2})\frac{2}{6} + (\frac{\gamma}{2})\frac{3}{6} = \frac{1-\alpha+\beta+1.5\gamma}{6} = \frac{2-2\alpha+2\beta+3\gamma}{12}$.
$P(T_1|R_1) = \frac{(1-\alpha)/6}{(2-2\alpha+2\beta+3\gamma)/12} = \frac{2(1-\alpha)}{2-2\alpha+2\beta+3\gamma}$.
$$\boxed{ P(T_1|R_1) = \frac{2(1-\alpha)}{2(1-\alpha)+2\beta+3\gamma} }$$

\(ii\) **Probability of transmission error:**
$P(\text{error}) = 1 - P(\text{correct}) = 1 - \sum_{i=1}^3 P(R_i, T_i) = 1 - \sum_{i=1}^3 P(R_i|T_i)P(T_i)$.
$P(\text{correct}) = (1-\alpha)\frac{1}{6} + (1-\beta)\frac{2}{6} + (1-\gamma)\frac{3}{6} = \frac{1-\alpha+2-2\beta+3-3\gamma}{6} = \frac{6-\alpha-2\beta-3\gamma}{6}$.
$P(\text{error}) = 1 - \frac{6-\alpha-2\beta-3\gamma}{6} = \frac{\alpha+2\beta+3\gamma}{6}$.
$$\boxed{ P(\text{error}) = \frac{\alpha+2\beta+3\gamma}{6} }$$

\(iii\) **Probability of receiving digit i:** $P(R_1)$ was calculated in
part (i): $\frac{2-2\alpha+2\beta+3\gamma}{12}$.
$P(R_2) = \sum P(R_2|T_i)P(T_i) = (\frac{\alpha}{2})\frac{1}{6} + (1-\beta)\frac{2}{6} + (\frac{\gamma}{2})\frac{3}{6} = \frac{\alpha+4-4\beta+3\gamma}{12}$.
$P(R_3) = \sum P(R_3|T_i)P(T_i) = (\frac{\alpha}{2})\frac{1}{6} + (\frac{\beta}{2})\frac{2}{6} + (1-\gamma)\frac{3}{6} = \frac{\alpha+2\beta+6-6\gamma}{12}$.
$$\boxed{ P(R_1) = \frac{2-2\alpha+2\beta+3\gamma}{12}, P(R_2) = \frac{\alpha+4-4\beta+3\gamma}{12}, P(R_3) = \frac{\alpha+2\beta+6-6\gamma}{12} }$$

Question 10
===========

**Problem:** Which of the given statements is true?

**Solution:** (i) $P(A)=0.3, P(B)=0.7, P(A\cap B)=0.5$. This is
impossible, since $A \cap B \subseteq A$, which means $P(A \cap B)$
cannot be greater than $P(A)$. Here $0.5 > 0.3$. **False**.

\(ii\) $P(A)=0.5, P(A\cup B)=0.7$, A and B are independent, $P(B)=0.4$.
If A and B are independent, $P(A\cup B)=P(A)+P(B)-P(A)P(B)$. Let's
check:
$0.7 = 0.5 + 0.4 - (0.5)(0.4) \implies 0.7 = 0.9 - 0.2 \implies 0.7 = 0.7$.
This is consistent. **True**.

\(iii\) $P(A)=0.2, P(A\cup B)=0.9$, A and B are disjoint, $P(B)=0.6$. If
A and B are disjoint, $P(A\cup B) = P(A)+P(B)$. Let's check:
$0.9 = 0.2 + 0.6 \implies 0.9 = 0.8$. This is a contradiction.
**False**. $$\boxed{ \text{Statement (ii) is true.} }$$

Question 11
===========

**Problem:** Thirteen cards are distributed to each of four players.
What is the probability that player C has all four kings?

**Solution:** We consider the hand of player C. The total number of
possible 13-card hands for player C is $\binom{52}{13}$. For the event
to be favorable, player C's hand must contain all 4 kings and 9 other
cards from the remaining $52-4=48$ non-king cards. The number of ways to
form such a hand is $\binom{4}{4} \times \binom{48}{9}$. The probability
is the ratio of favorable hands to total possible hands:
$$P(\text{C has 4 kings}) = \frac{\binom{4}{4}\binom{48}{9}}{\binom{52}{13}} = \frac{1 \cdot \frac{48!}{9!39!}}{\frac{52!}{13!39!}} = \frac{48! \cdot 13!}{52! \cdot 9!} = \frac{13 \cdot 12 \cdot 11 \cdot 10}{52 \cdot 51 \cdot 50 \cdot 49}$$
$$= \frac{17160}{2082500} = \frac{11}{4165} \approx 0.00264$$
$$\boxed{ P(\text{C has 4 kings}) = \frac{11}{4165} }$$

Question 12
===========

**Problem:** A student takes 5 courses per semester for 4 semesters.
Probability of getting at least an 'A' in any course is 0.5. Find the
probability of getting all 'A's in at least one semester.

**Solution:** Let S be the event of success in a semester, which means
getting at least an 'A' in all 5 courses. The probability of getting at
least an 'A' in one course is $p=0.5$. Since grades are independent, the
probability of success in one semester is
$P(S) = (0.5)^5 = \frac{1}{32}$. The probability of failure in one
semester is $P(S^c) = 1 - \frac{1}{32} = \frac{31}{32}$. We have 4
semesters (4 independent trials). We want the probability of at least
one success. It is easier to calculate the complement: the probability
of zero successes (failure in all 4 semesters).
$$P(\text{failure in all 4 semesters}) = (P(S^c))^4 = \left(\frac{31}{32}\right)^4$$
The probability of at least one successful semester is:
$$P(\text{at least one S}) = 1 - P(\text{no S}) = 1 - \left(\frac{31}{32}\right)^4 \approx 1 - 0.8807 = 0.1193$$
$$\boxed{ P(\text{at least one semester with all A's}) = 1 - \left(\frac{31}{32}\right)^4 \approx 0.1193 }$$

Question 13
===========

**Problem:** If $P(A)>0$, show that
$P(A\cap B|A)\ge P(A\cap B|A\cup B)$.

**Solution:** We evaluate the left-hand side (LHS) and right-hand side
(RHS) separately. LHS:
$P(A \cap B|A) = \frac{P((A \cap B) \cap A)}{P(A)} = \frac{P(A \cap B)}{P(A)}$.
RHS:
$P(A \cap B|A \cup B) = \frac{P((A \cap B) \cap (A \cup B))}{P(A \cup B)} = \frac{P(A \cap B)}{P(A \cup B)}$.
The inequality we need to prove is:
$$\frac{P(A \cap B)}{P(A)} \ge \frac{P(A \cap B)}{P(A \cup B)}$$ This
inequality holds if $P(A \cap B) = 0$. If $P(A \cap B) > 0$, we can
divide by it, and the inequality becomes:
$$\frac{1}{P(A)} \ge \frac{1}{P(A \cup B)}$$ This is equivalent to
$P(A \cup B) \ge P(A)$. This is always true, because the event A is a
subset of the event $A \cup B$. Thus, the original statement is proven.
$$\boxed{ \text{The statement is proven as } P(A \cup B) \ge P(A) \text{ is always true.} }$$

Question 14
===========

**Problem:** Let A and B be random subsets of S=1,\...,n. Find
$P(|B|=i)$, $P(A \subset B | |B|=i)$, $P(A \subset B)$ and deduce
$P(A \cap B = \emptyset)$.

**Solution:** Total number of subsets of S is $2^n$. $P(|B|=i)$: The
number of subsets of size $i$ is $\binom{n}{i}$. Since B is chosen
equally likely, $P(|B|=i) = \frac{\binom{n}{i}}{2^n}$.
$P(A \subset B | |B|=i)$: Given that B is a specific subset of size $i$,
A must be one of the $2^i$ subsets of B. Since there are $2^n$ total
choices for A, the probability is $\frac{2^i}{2^n} = 2^{i-n}$.
$P(A \subset B)$: Using the law of total probability:
$$P(A \subset B) = \sum_{i=0}^n P(A \subset B | |B|=i)P(|B|=i) = \sum_{i=0}^n \frac{2^i}{2^n} \frac{\binom{n}{i}}{2^n} = \frac{1}{4^n} \sum_{i=0}^n \binom{n}{i} 2^i$$
Using the binomial theorem,
$\sum_{i=0}^n \binom{n}{i} 2^i = (1+2)^n = 3^n$.
$$P(A \subset B) = \frac{3^n}{4^n} = \left(\frac{3}{4}\right)^n$$
$P(A \cap B = \emptyset)$: This event is equivalent to
$A \subseteq B^c$. Since the choice of $B$ is random, the choice of its
complement $B^c$ is also random over all possible subsets. Therefore,
the problem is identical to finding $P(A \subset C)$ where C is a random
subset, which we just found.
$$\boxed{ P(|B|=i) = \frac{\binom{n}{i}}{2^n}, P(A \subset B | |B|=i) = \frac{2^i}{2^n}, P(A \subset B) = \left(\frac{3}{4}\right)^n, P(A \cap B = \emptyset) = \left(\frac{3}{4}\right)^n }$$

Question 15
===========

**Problem:** A test has 6 T/F and 4 multiple-choice questions. An
unprepared student guesses all answers. Find the probability of scoring
at least 8 marks.

**Solution:** Let $X$ be the score from the 6 T/F questions ($p=1/2$)
and $Y$ be the score from the 4 MC questions ($p=1/4$). We want
$P(X+Y \ge 8)$. The possible pairs $(X,Y)$ that sum to at least 8 are:
(4,4), (5,3), (5,4), (6,2), (6,3), (6,4). We sum the probabilities of
these independent events:\
$P(X=k) = \binom{6}{k}(1/2)^6$,
$P(Y=k) = \binom{4}{k}(1/4)^k(3/4)^{4-k}$.\
$P(X+Y \ge 8) = P(X=4)P(Y=4) + P(X=5)P(Y=3) + P(X=5)P(Y=4) + P(X=6)P(Y=2) + P(X=6)P(Y=3) + P(X=6)P(Y=4)$\
$= [\binom{6}{4}(\frac{1}{64})][\binom{4}{4}(\frac{1}{256})] + [\binom{6}{5}(\frac{1}{64})][\binom{4}{3}(\frac{12}{256})] + [\binom{6}{5}(\frac{1}{64})][\binom{4}{4}(\frac{1}{256})]$
$+ [\binom{6}{6}(\frac{1}{64})][\binom{4}{2}(\frac{54}{256})] + [\binom{6}{6}(\frac{1}{64})][\binom{4}{3}(\frac{12}{256})] + [\binom{6}{6}(\frac{1}{64})][\binom{4}{4}(\frac{1}{256})]$\
$= \frac{1}{16384} [ (15)(1) + (6)(12) + (6)(1) + (1)(54) + (1)(12) + (1)(1) ]$\
$= \frac{1}{16384} [ 15 + 72 + 6 + 54 + 12 + 1 ] = \frac{160}{16384} = \frac{5}{512}$.\
$$\boxed{ P(\text{score} \ge 8) = \frac{5}{512} \approx 0.00977 }$$

Question 16
===========

**Problem:** If 2n students qualify, and boys and girls are equally
likely, what is the probability that more girls qualify than boys?

**Solution:** Let $X$ be the number of girls who qualify among the $2n$
students. Each student is a girl with probability $0.5$. Thus,
$X \sim \text{Binomial}(2n, 0.5)$. We want to find $P(X > n)$. Let
$p = P(X>n)$, $q = P(X<n)$, and $r = P(X=n)$. We know $p+q+r=1$. For a
binomial distribution with $p=0.5$, the distribution is symmetric:
$P(X=k) = P(X=2n-k)$. Therefore,
$q = P(X<n) = \sum_{k=0}^{n-1} P(X=k) = \sum_{k=0}^{n-1} P(X=2n-k)$. Let
$j=2n-k$. The sum becomes $\sum_{j=n+1}^{2n} P(X=j) = P(X>n) = p$. Since
$p=q$, we have $2p+r=1$, which gives $p = \frac{1-r}{2}$. The term $r$
is $P(X=n) = \binom{2n}{n}(0.5)^{2n}$.
$$p = \frac{1 - \binom{2n}{n}(0.5)^{2n}}{2}$$
$$\boxed{ P(\text{more girls than boys}) = \frac{1}{2}\left(1 - \binom{2n}{n}\left(\frac{1}{2}\right)^{2n}\right) }$$

Question 17
===========

**Problem:** The hat-check problem (derangements). Find the probability
that no one gets their own hat, and the probability that at least one
person does.

**Solution:** This is a classic derangement problem. Let $D_n$ be the
number of ways n items can be arranged so that none are in their
original position. The total number of arrangements is $n!$. The
probability that no one gets their own hat is $P_0 = \frac{D_n}{n!}$.
The formula for $D_n$ can be derived using the principle of
inclusion-exclusion, and the probability is:
$$P(\text{no one gets own hat}) = \sum_{k=0}^n \frac{(-1)^k}{k!} = 1 - \frac{1}{1!} + \frac{1}{2!} - \dots + \frac{(-1)^n}{n!}$$
As $n \to \infty$, this series converges to $e^{-1}$. The probability
that at least one person gets their hat back is the complement of the
above event:
$$P(\text{at least one gets own hat}) = 1 - P(\text{no one gets own hat}) = 1 - \sum_{k=0}^n \frac{(-1)^k}{k!}$$
As $n \to \infty$, this probability converges to $1 - e^{-1}$.
$$\boxed{ P(\text{no match}) = \sum_{k=0}^n \frac{(-1)^k}{k!} \xrightarrow{n\to\infty} e^{-1}, \quad P(\text{at least one match}) = 1 - \sum_{k=0}^n \frac{(-1)^k}{k!} \xrightarrow{n\to\infty} 1-e^{-1} }$$

Question 18
===========

**Problem:** n balls are placed randomly in R boxes. What is the
probability that exactly k balls are placed in the first r boxes?

**Solution:** This scenario can be modeled as a sequence of $n$
independent trials. For each ball (trial), there are two outcomes: it
lands in one of the first $r$ boxes, or it does not. The probability of
a single ball landing in one of the first $r$ boxes is
$p = \frac{r}{R}$. The probability of it landing in one of the remaining
$R-r$ boxes is $1-p = 1 - \frac{r}{R}$. Let $X$ be the number of balls
that land in the first $r$ boxes. Then $X$ follows a Binomial
distribution with parameters $n$ and $p=r/R$. We want to find the
probability that $X=k$. Using the Binomial PMF:
$$P(X=k) = \binom{n}{k} p^k (1-p)^{n-k} = \binom{n}{k} \left(\frac{r}{R}\right)^k \left(1-\frac{r}{R}\right)^{n-k}$$
$$\boxed{ P(k \text{ balls in first } r \text{ boxes}) = \binom{n}{k}\left(\frac{r}{R}\right)^k\left(1-\frac{r}{R}\right)^{n-k} }$$

Question 19
===========

**Problem:** Choose 13 cards from a standard deck. What is the
probability of getting 3 red cards?

**Solution:** The total number of ways to choose 13 cards from a 52-card
deck is $\binom{52}{13}$. The deck has 26 red cards and 26 black cards.
A favorable hand consists of 3 red cards and $13-3=10$ black cards. The
number of ways to choose 3 red cards from 26 is $\binom{26}{3}$. The
number of ways to choose 10 black cards from 26 is $\binom{26}{10}$. The
total number of favorable hands is the product
$\binom{26}{3}\binom{26}{10}$. The probability is the ratio:
$$P(\text{3 red, 10 black}) = \frac{\binom{26}{3}\binom{26}{10}}{\binom{52}{13}}$$
$$\boxed{ P(\text{3 red cards}) = \frac{\binom{26}{3}\binom{26}{10}}{\binom{52}{13}} \approx 0.2117 }$$

Question 20
===========

**Problem:** Choose 13 cards. Find the probability of getting 3 clubs, 4
diamonds, 4 hearts, and 2 spades.

**Solution:** The total number of ways to choose 13 cards from 52 is
$\binom{52}{13}$. Each suit has 13 cards. We want a specific composition
for our hand. Number of ways to choose 3 clubs from 13: $\binom{13}{3}$.
Number of ways to choose 4 diamonds from 13: $\binom{13}{4}$. Number of
ways to choose 4 hearts from 13: $\binom{13}{4}$. Number of ways to
choose 2 spades from 13: $\binom{13}{2}$. The total number of favorable
hands is the product of these combinations.
$$P(\text{event}) = \frac{\binom{13}{3}\binom{13}{4}\binom{13}{4}\binom{13}{2}}{\binom{52}{13}}$$
$$\boxed{ P(\text{event}) = \frac{\binom{13}{3}\binom{13}{4}^2\binom{13}{2}}{\binom{52}{13}} \approx 0.00538 }$$

Question 21
===========

**Problem:** Choose 4 cards with replacement. Find the probability of
drawing (a) four distinct kings, (b) a queen each time.

**Solution:** The total number of outcomes when drawing 4 cards with
replacement is $52^4$. (a) **Four distinct kings:** This means drawing
the King of Spades, King of Hearts, King of Diamonds, and King of Clubs
in some order. There are 4 such cards. The number of ways to arrange
these 4 distinct cards is $4! = 24$.
$$P(\text{4 distinct kings}) = \frac{4!}{52^4} = \frac{24}{7,311,616} \approx 3.28 \times 10^{-6}$$
(b) **A queen each time:** There are 4 queens in the deck. The
probability of drawing a queen on any single draw is
$\frac{4}{52} = \frac{1}{13}$. Since the draws are independent (with
replacement), the probability of this happening 4 times in a row is:
$$P(\text{4 queens}) = \left(\frac{4}{52}\right)^4 = \left(\frac{1}{13}\right)^4 = \frac{1}{28,561} \approx 3.5 \times 10^{-5}$$
$$\boxed{ \text{(a)} \frac{4!}{52^4} \quad \text{(b)} \left(\frac{4}{52}\right)^4 }$$

Question 22
===========

**Problem:** n balls are distributed in n numbered boxes. What is the
probability that only the 1st box will remain empty?

**Solution:** Total number of arrangements is $n^n$. For the 1st box to
be the only empty box, all $n$ balls must be placed in the other $n-1$
boxes, with none of these $n-1$ boxes being empty. This implies that one
of these $n-1$ boxes must contain exactly 2 balls, while the other $n-2$
boxes contain 1 ball each.

1.  Choose which of the $n-1$ boxes (box 2 to n) will receive 2 balls:
    $\binom{n-1}{1}$ ways.

2.  Choose which 2 of the $n$ balls will go into that box:
    $\binom{n}{2}$ ways.

3.  Arrange the remaining $n-2$ balls in the remaining $n-2$ boxes (one
    per box): $(n-2)!$ ways.

Total favorable arrangements:
$\binom{n-1}{1}\binom{n}{2}(n-2)! = (n-1) \cdot \frac{n(n-1)}{2} \cdot (n-2)!$.
The probability is the ratio:
$$P(\text{only 1st empty}) = \frac{(n-1) \binom{n}{2} (n-2)!}{n^n} = \frac{(n-1) \frac{n(n-1)}{2} (n-2)!}{n^n}$$
$$\boxed{ P(\text{only 1st empty}) = \frac{(n-1)\binom{n}{2}(n-2)!}{n^n} }$$

Question 23
===========

**Problem:** A rumor spreads in a village of $n+1$ people. Find the
probability (a) it does not return to the originator, and (b) it is not
told to anyone who already knows it.

**Solution:** Assume that at each step, a person tells the rumor to one
of the $n$ other people at random. There is a sequence of $r$
transmissions. Total number of rumor paths: The originator has $n$
choices. Each subsequent person has $n$ choices. Total paths =
$n \times n^{r-1} = n^r$.

\(a\) **Rumor does not return to the originator:** The originator tells
one of $n$ people. For the subsequent $r-1$ steps, each person must
choose from the $n-1$ people who are not the originator. Favorable paths
= $n \times (n-1)^{r-1}$.
$$P(\text{not back to originator}) = \frac{n(n-1)^{r-1}}{n^r} = \left(\frac{n-1}{n}\right)^{r-1}$$
$$\boxed{ P(\text{a}) = \left(\frac{n-1}{n}\right)^{r-1} }$$

\(b\) **Rumor is not repeated to anyone:** This means the sequence of
$r+1$ people involved (originator + $r$ others) must all be distinct.
The originator tells person 1 (n choices). Person 1 must tell a new
person (n-1 choices available). Person 2 must tell a new person (n-2
choices available). \... Person r-1 must tell a new person (n-(r-1)
choices available). Favorable paths =
$n \times (n-1) \times (n-2) \times \dots \times (n-r+1) = P(n,r)$.
$$P(\text{no repeats}) = \frac{P(n,r)}{n^r} = \frac{n! / (n-r)!}{n^r}$$
$$\boxed{ P(\text{b}) = \frac{n(n-1)\dots(n-r+1)}{n^r} = \frac{_nP_r}{n^r} }$$
