<!-- File: linear_algebra/diagonalizability_criterion.md -->

# Diagonalizability Criterion (Distinct Roots)

---

## Theorem

If an $n \times n$ matrix has $n$ **distinct roots** of its characteristic equation:

$$
\det(A - \lambda I) = 0
$$

then the matrix is **diagonalizable**.

This means there exists an invertible matrix $P$ and a diagonal matrix $D$ such that:

$$
A = P D P^{-1}
$$

---

## What This Means

- Solving $\det(A - \lambda I) = 0$ gives us special numbers called **eigenvalues**.
- If the equation has $n$ different (non-repeating) solutions, then the matrix can be simplified to a **diagonal form** through a change of basis.

---

## Practical Steps

To determine if a matrix is diagonalizable:

1. Compute the **characteristic polynomial**:

   $$
   \det(A - \lambda I)
   $$

2. Solve the equation:

   $$
   \det(A - \lambda I) = 0
   $$

3. If it has **$n$ distinct solutions**, the matrix is diagonalizable.

---

## Summary

A matrix is diagonalizable if it can be transformed into a diagonal matrix.  
This always happens when the characteristic equation has **$n$ distinct roots**.
