<!-- File: mathematics/algorithm_analysis/asymptotic_notation.md -->

# Asymptotic Notation

---

## Definition

Asymptotic notation describes the **growth rate** of functions, typically used to analyze the running time or space complexity of algorithms, ignoring constant factors and lower-order terms.

We compare two functions **f(n)** and **g(n)** for large values of **n**.

---

## Big-O Notation (O)

**Definition:**
A function f(n) is in O(g(n)) if there exist constants c > 0 and n₀ ≥ 0 such that

$$
0 \;\le\; f(n) \;\le\; c \cdot g(n), \quad \forall n \ge n_{0}
$$

* **Interpretation:**

  * Big-O gives an **asymptotic upper bound** on the growth of f(n).
  * f(n) grows *at most as fast as* g(n), up to a constant factor.

* **Examples:**

$$
3n + 2 \;\in\; O(n), \quad (c = 4,\; n_{0} = 1)
$$

Merge Sort has running time

$$
O(n \log n)
$$

---

## Big-Omega Notation (Ω)

**Definition:**
A function f(n) is in Ω(g(n)) if there exist constants c > 0 and n₀ ≥ 0 such that

$$
0 \;\le\; c \cdot g(n) \;\le\; f(n), \quad \forall n \ge n_{0}
$$

* **Interpretation:**

  * Big-Omega gives an **asymptotic lower bound** on the growth of f(n).
  * f(n) grows *at least as fast as* g(n), up to a constant factor.

* **Examples:**

$$
5n^{2} + 3n \;\in\; \Omega(n^{2}), \quad (c = 5,\; n_{0} = 1)
$$

Any comparison-based sorting requires

$$
\Omega(n \log n)
$$

---

## Big-Theta Notation (Θ)

**Definition:**
A function f(n) is in Θ(g(n)) if there exist constants c₁, c₂ > 0 and n₀ ≥ 0 such that

$$
0 \;\le\; c_{1} \cdot g(n) \;\le\; f(n) \;\le\; c_{2} \cdot g(n),
\quad \forall n \ge n_{0}
$$

* **Interpretation:**

  * Big-Theta gives a **tight bound** on the growth of f(n).
  * f(n) grows *at the same rate as* g(n), up to constant factors.

* **Examples:**

$$
7n^{2} + 2n + 10 \;\in\; \Theta(n^{2}), \quad (c_{1} = 7,\; c_{2} = 8,\; n_{0} = 1)
$$

Merge Sort is

$$
\Theta(n \log n)
$$

---

## Summary of Usage

* **Big-O (O):** Upper bound (worst-case guarantee)
* **Big-Omega (Ω):** Lower bound (best-case guarantee)
* **Big-Theta (Θ):** Tight bound (asymptotically exact)

---
