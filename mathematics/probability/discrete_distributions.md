<!-- File: mathematics/probability/discrete_distributions.md -->

# Discrete Probability Distributions

---

## Definition

A discrete random variable $X$ has a probability mass function (PMF)

$$
P(X = x_i) = p_i
$$

where $x_i$ are the possible values of $X$.  
The PMF satisfies the normalization condition

$$
\sum_i p_i = 1
$$

---

## Identities

### Mean

The mean (expected value) of $X$ is

$$
\mu = E(X) = \sum_i x_i p_i
$$

### Second Moment

The second moment of $X$ about the origin is

$$
E(X^2) = \sum_i x_i^2 p_i
$$

### Variance

The variance of $X$ is defined as

$$
\sigma^2 = \mathrm{Var}(X) = E[(X - \mu)^2]
$$

Expanded form:

$$
\sigma^2 = E(X^2) - \mu^2
$$

That is,

$$
\sigma^2 = \left( \sum_i x_i^2 p_i \right) - \left( \sum_i x_i p_i \right)^2
$$

---

## Probability of an Interval

For $a \leq b$, the probability that $X$ falls within $[a, b]$ is

$$
P(a \leq X \leq b) = \sum_{x_i \in [a, b]} p_i
$$

---

## Law of the Unconscious Statistician

For any function $g(X)$, the expected value of $g(X)$ is

$$
E[g(X)] = \sum_i g(x_i) p_i
$$

---

## Examples

### Mean of a Die Roll

For $X$ the outcome of a fair six-sided die:

$$
\mu = E(X) = \frac{1}{6}(1+2+3+4+5+6) = 3.5
$$

### Variance of a Die Roll

$$
E(X^2) = \frac{1}{6}(1^2+2^2+3^2+4^2+5^2+6^2) = \frac{91}{6}
$$

$$
\sigma^2 = E(X^2) - \mu^2
$$

$$
\sigma^2 = \frac{91}{6} - (3.5)^2
$$

$$
\sigma^2 = \frac{35}{12}
$$

---

## Common Distributions

### Poisson Distribution

The **Poisson distribution** models the number of events that occur in a fixed interval of time or space, under the assumptions that events happen **independently** of each other and with a **constant average rate**.

#### Probability Mass Function

A discrete random variable **X** is said to follow a Poisson distribution with parameter  
$\lambda > 0$ if it has the probability mass function (PMF)

$$
P(X = k) = \frac{\lambda^{k} e^{-\lambda}}{k!}, \quad k = 0, 1, 2, \dots
$$

where  
- $k$ is the number of occurrences,  
- $e$ is Euler’s number ($\approx 2.71828$),  
- $k!$ is the factorial of $k$.  

#### Mean and Variance

The parameter $\lambda$ represents the **expected number of events** in the interval.  
A key property of the Poisson distribution is that both the mean and the variance are equal to $\lambda$:

$$
E[X] = \operatorname{Var}(X) = \lambda
$$

#### Interpretation

The Poisson distribution applies to systems with a **large number of possible events**, each of which has a **small probability of happening** in a short interval.  
Examples include:  
- the number of phone calls received per minute at a call center,  
- the number of typos on a printed page,  
- the number of cosmic rays hitting a detector in one second.  

#### Rate–time Form

If events occur at average rate $r$ per unit time, then in an interval of length $T$ the expected number of events is

$$
\lambda = rT
$$

so the distribution becomes

$$
P(\text{k events in interval T}) = \frac{(rT)^k e^{-rT}}{k!}.
$$

---

#### Derivation (Binomial → Poisson, using ε)

This derivation shows how the Poisson PMF arises as the limit of a Binomial distribution when the interval is split into many tiny, independent slots.

**Setup**

1. Fix the observation interval of length $T$ and a rate $r$ (events per unit time). Define
   $$
   \lambda = rT.
   $$
2. Split the interval into $n$ equal subintervals (slots) of length
   $$
   \varepsilon = \frac{T}{n}.
   $$
3. Assume:
   - each slot has probability $p_\varepsilon$ of containing exactly one event,
   - probability of two or more events in a single slot is negligible as $\varepsilon \to 0$,
   - slots are independent.

To match the rate $r$, set
$$
p_\varepsilon = r \varepsilon = \frac{\lambda}{n}.
$$

**Binomial model**

The total number of events in $[0,T]$ is then approximately Binomial$(n, p_\varepsilon)$:

$$
P(X = k) = \binom{n}{k} (p_\varepsilon)^k (1 - p_\varepsilon)^{\,n-k}
= \binom{n}{k} \left(\frac{\lambda}{n}\right)^k \left(1 - \frac{\lambda}{n}\right)^{\,n-k}.
$$

**Take the limit $n \to \infty$ (equivalently $\varepsilon \to 0$)**

For fixed $k$:

1. The combinatorial term:
   $$
   \binom{n}{k} \left(\frac{\lambda}{n}\right)^k
   = \frac{n(n-1)\cdots(n-k+1)}{k!} \left(\frac{\lambda}{n}\right)^k
   = \frac{\lambda^k}{k!}\prod_{j=0}^{k-1}\frac{n-j}{n}
   \longrightarrow \frac{\lambda^k}{k!},
   $$
   because each factor $(n-j)/n \to 1$.

2. The exponential term:
   $$
   \left(1 - \frac{\lambda}{n}\right)^{n} \longrightarrow e^{-\lambda}.
   $$

3. The remaining factor:
   $$
   \left(1 - \frac{\lambda}{n}\right)^{-k} \longrightarrow 1.
   $$

Combining these limits:

$$
\lim_{n\to\infty} P(X = k)
= \frac{\lambda^k}{k!} \, e^{-\lambda}
= \frac{\lambda^k e^{-\lambda}}{k!}.
$$

This is the Poisson PMF.

**Remarks**

- In the rate–time language, replace $\lambda$ by $rT$ to obtain
  $$
  P(X = k) = \frac{(rT)^k e^{-rT}}{k!}.
  $$
- The key scaling is $p_\varepsilon \approx r\varepsilon$: probability of one event in a short slot is proportional to slot length. Choosing $p_\varepsilon = 1/n$ would force a fixed mean 1, which is not the general situation.

---

### Geometric Distribution

The **Geometric distribution** models the number of Bernoulli trials needed to get the first success, where each trial has success probability $p$.

#### PMF

$$
P(X = k) = (1-p)^{k-1}p, \quad k = 1, 2, 3, \dots
$$

#### Mean and Variance

$$
\mu = E(X) = \frac{1}{p}
$$

$$
\sigma^2 = \mathrm{Var}(X) = \frac{1-p}{p^2}
$$

---

### Exponential Distribution

The **Exponential distribution** models the **time between consecutive events** in a Poisson process, i.e., events that occur independently at a **constant average rate**.

#### Probability Density Function (PDF)

A continuous random variable X follows an exponential distribution with **rate parameter λ > 0** if its probability density function is:

$$
f_X(x) = 
\begin{cases} 
\lambda e^{-\lambda x}, & x \ge 0 \\
0, & x < 0
\end{cases}
$$

where

* λ is the **rate parameter** (events per unit time),
* x is the **time until the next event**.

#### Cumulative Distribution Function (CDF)

The probability that X ≤ x is:

$$
F_X(x) = P(X \le x) = 1 - e^{-\lambda x}, \quad x \ge 0
$$

#### Mean and Variance

The expected value (mean) and variance are:

$$
E[X] = \frac{1}{\lambda}, \quad \mathrm{Var}(X) = \frac{1}{\lambda^2}
$$

**Derivation of the mean**:

$$
E[X] = \int_0^\infty x \lambda e^{-\lambda x} dx = \frac{1}{\lambda}
$$

#### Memoryless Property

The exponential distribution is **memoryless**:

$$
P(X > s + t \mid X > s) = P(X > t), \quad s \ge 0, t \ge 0
$$

#### Interpretation

The exponential distribution describes **waiting times** in a Poisson process. Examples:

* Time until the next phone call in a call center
* Time until a radioactive particle decays
* Time between arrivals at a bus stop

#### Relation to Poisson

If the number of events in an interval follows a Poisson distribution with rate λ, the **time until the first event** follows an exponential distribution with the same rate.

---
