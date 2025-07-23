<!-- File: probability/discrete_distributions.md -->

# Discrete Probability Distributions

TODO(luisvasquez): Add derivations for expectation and variance formulas.

---

## Definition

A discrete random variable X has a probability mass function (PMF)

$$
P(X = x_i) = p_i
$$

where xi are the possible values of X. The PMF satisfies the normalization condition

$$
\sum_i p_i = 1
$$

---

## Identities

### Mean

The mean (expected value) of X is

$$
\mu = E(X) = \sum_i x_i p_i
$$

---

### Second Moment

The second moment of X about the origin is

$$
E(X^2) = \sum_i x_i^2 p_i
$$

---

### Variance

The variance of X is defined as

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

### Probability of an Interval

For a ≤ b, the probability that X falls within [a, b] is

$$
P(a \leq X \leq b) = \sum_{x_i \in [a, b]} p_i
$$

---

### Law of the Unconscious Statistician

For any function g(X), the expected value of g(X) is

$$
E[g(X)] = \sum_i g(x_i) p_i
$$

---

## Examples

### Mean of a Die Roll

For X the outcome of a fair six-sided die:

$$
\mu = E(X) = \frac{1}{6}(1+2+3+4+5+6) = 3.5
$$

---

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
