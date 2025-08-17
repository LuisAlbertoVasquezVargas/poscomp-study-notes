<!-- File: linear_algebra/matrix_inverse.md -->

# Matrix Inverse via Gauss-Jordan Elimination

The **inverse of a matrix** `A` (denoted `A⁻¹`) is defined as the matrix that satisfies:

* `A A⁻¹ = I`
* `A⁻¹ A = I`

where `I` is the identity matrix of the same order. Only **square and nonsingular (det(A) ≠ 0)** matrices have inverses.

---

## Gauss-Jordan Elimination Method

Steps to compute `A⁻¹`:

1. Start with matrix `A` and the identity matrix `I`.
2. Form the augmented matrix `[A | I]`.
3. Apply elementary row operations to transform `A` into `I`.
4. The same operations applied to `I` will transform it into `A⁻¹`.
5. If you cannot reduce `A` to `I`, then `A` is singular (not invertible).

---

## Example

Let

```
A = [[2, 1],
     [5, 3]]
```

Form the augmented matrix:

```
[A | I] = [[2, 1 | 1, 0],
           [5, 3 | 0, 1]]
```

* Divide row 1 by 2 → `[1, 0.5 | 0.5, 0]`
* Subtract 5×row1 from row2 → `[0, 0.5 | -2.5, 1]`
* Multiply row2 by 2 → `[0, 1 | -5, 2]`
* Subtract 0.5×row2 from row1 → `[1, 0 | 3, -1]`

Result:

```
[I | A⁻¹] = [[1, 0 | 3, -1],
             [0, 1 | -5, 2]]
```

So

```
A⁻¹ = [[3, -1],
       [-5, 2]]
```

---


## Properties of Inverse Matrices

* `(A⁻¹)⁻¹ = A`
* `(AB)⁻¹ = B⁻¹ A⁻¹` (note the reversed order)
* `(Aᵀ)⁻¹ = (A⁻¹)ᵀ`
* If `A` is **orthogonal** (`AᵀA = I`), then `A⁻¹ = Aᵀ`
* If `A` is **symmetric** (`Aᵀ = A`), then `A⁻¹` is also symmetric (when it exists).

---

