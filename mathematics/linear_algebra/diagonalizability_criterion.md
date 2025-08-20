<!-- File: mathematics/linear_algebra/diagonalizability_criterion.md -->

# Diagonalizability Criterion

---

## Definition

A matrix is **diagonalizable** if there exists an invertible matrix $P$ and a diagonal matrix $D$ such that:

$$
A = P D P^{-1}
$$

This means $A$ can be represented in a simpler form using a basis of eigenvectors.

---

## Diagonalizability with Distinct Roots

**Theorem:**
If an $n \times n$ matrix has $n$ **distinct roots of its characteristic polynomial** (i.e., $n$ distinct eigenvalues), it is **always diagonalizable**.

* Each root corresponds to a **one-dimensional eigenspace**.
* Eigenvectors corresponding to different roots are **linearly independent**.
* These eigenvectors form a basis for $\mathbb{R}^n$ and can be used as columns of $P$ to diagonalize $A$.

**Practical Steps:**

1. Compute the **characteristic polynomial**:

$$
p(\lambda) = \det(A - \lambda I)
$$

2. Solve

$$
p(\lambda) = 0
$$

for eigenvalues $\lambda$.

3. If there are $n$ distinct roots → the matrix is diagonalizable.

---

## Counterexample: Repeated Eigenvalues

A matrix can have repeated eigenvalues and still be diagonalizable.

**Example:**

$$
A = 
\begin{bmatrix}
0 & 1 & -2 \\
0 & 1 & 0 \\
1 & -1 & 3
\end{bmatrix}
$$

* Characteristic polynomial:

$$
p(\lambda) = -(\lambda - 1)^2(\lambda - 2)
$$

After computing eigenvectors, we can write the diagonalization as:

$$
P = 
\begin{bmatrix}
1 & 0 & 1 \\
0 & 1 & 1 \\
1 & 1 & 1
\end{bmatrix}, 
\quad
D = 
\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 2
\end{bmatrix}
$$

So we have:

$$
A = P D P^{-1}
$$

This shows $A$ is diagonalizable despite having a repeated eigenvalue.

---

## Summary

* **All roots of the characteristic polynomial are distinct → guaranteed diagonalizable**
* **Repeated roots can still allow diagonalizability**, depending on eigenvectors.
* A matrix is diagonalizable **iff** there exists a basis of eigenvectors such that

$$
A = P D P^{-1}
$$

---
