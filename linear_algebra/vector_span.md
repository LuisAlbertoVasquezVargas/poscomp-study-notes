<!-- File: linear_algebra/vector_span.md -->

# Vector Span

---

## Definition

The **span** of a set of vectors is the set of all possible **linear combinations** of those vectors.

Given vectors $ \vec{v}_1, \vec{v}_2, \ldots, \vec{v}_n \in \mathbb{R}^m $, we define:

$$
\text{span}(\vec{v}_1, \vec{v}_2, \ldots, \vec{v}_n)
= \left\{ \sum_{i=1}^{n} \alpha_i \vec{v}_i \mid \alpha_i \in \mathbb{R} \right\}
= \text{span} \{ \vec{v}_1, \vec{v}_2, \ldots, \vec{v}_n \}
= [\vec{v}_1, \vec{v}_2, \ldots, \vec{v}_n]
$$

This set forms a **subspace** of $ \mathbb{R}^m $.

- The notation with **curly braces** $\text{span} \{ \cdot \}$ is standard in textbooks.
- The notation with **square brackets** $[\cdot]$ is often used in exams such as **POSCOMP**.
- All three notations are equivalent and refer to the **same subspace**.

---

## Intuition

- The span represents **all points** you can reach by **scaling and adding** the given vectors.
- It is the **smallest subspace** that contains those vectors.
- For a single nonzero vector in $ \mathbb{R}^2 $, the span is a line.
- For two linearly independent vectors in $ \mathbb{R}^3 $, the span is a plane.

---

## Examples

### 1. Span of one vector

Let $ \vec{v} = \begin{bmatrix} 2 \\ 3 \end{bmatrix} \in \mathbb{R}^2 $

$$
\text{span}(\vec{v}) = \{ \alpha \vec{v} \mid \alpha \in \mathbb{R} \}
$$

→ A **line** through the origin in the direction of $ \vec{v} $.

---

### 2. Span of two vectors

Let:

$$
\vec{v}_1 = \begin{bmatrix} 1 \\ 0 \end{bmatrix}, \quad
\vec{v}_2 = \begin{bmatrix} 0 \\ 1 \end{bmatrix}
$$

$$
\text{span}(\vec{v}_1, \vec{v}_2) = \left\{ \alpha \begin{bmatrix} 1 \\ 0 \end{bmatrix} + \beta \begin{bmatrix} 0 \\ 1 \end{bmatrix} \mid \alpha, \beta \in \mathbb{R} \right\} = \mathbb{R}^2
$$

---

## Geometric Interpretation

| Space          | # Independent Vectors | Span                      |
|----------------|------------------------|---------------------------|
| $ \mathbb{R}^2 $ | 1                      | Line                      |
| $ \mathbb{R}^2 $ | 2                      | Plane = $ \mathbb{R}^2 $  |
| $ \mathbb{R}^3 $ | 1                      | Line                      |
| $ \mathbb{R}^3 $ | 2                      | Plane                     |
| $ \mathbb{R}^3 $ | 3 (independent)        | $ \mathbb{R}^3 $          |

---

## Relation to Linear Dependence

- If the span of a set of vectors has **lower dimension** than the number of vectors, then some of them are **linearly dependent**.
- The **dimension** of the span = number of linearly **independent** vectors in the set.

---

## Checking if a Vector Is in the Span

To check if $ \vec{b} \in \text{span}(\vec{v}_1, \vec{v}_2, \ldots) $, solve the **linear system**:

$$
\alpha_1 \vec{v}_1 + \alpha_2 \vec{v}_2 + \cdots = \vec{b}
$$

If a solution exists, then $ \vec{b} \in \text{span}(\vec{v}_1, \vec{v}_2, \ldots) $.

---

## Summary

- Span = all linear combinations.
- Forms a vector subspace.
- Span can be a point (zero vector), line, plane, or full space.
- Notations:
  - $ \text{span}(\vec{v}_1, \vec{v}_2, \ldots) $
  - $ \text{span} \{ \vec{v}_1, \vec{v}_2, \ldots \} $
  - $ [\vec{v}_1, \vec{v}_2, \ldots] $ (common in POSCOMP)
