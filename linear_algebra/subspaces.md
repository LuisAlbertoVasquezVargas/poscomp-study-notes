<!-- File: linear_algebra/subspaces.md -->

# Vector Subspaces

---

## Definition

A **vector subspace** (or simply a **subspace**) of $ \mathbb{R}^n $ is a subset $ W \subseteq \mathbb{R}^n $ that satisfies the following three conditions:

1. **Zero Vector:** $ \vec{0} \in W $
2. **Closed under Addition:** If $ \vec{u}, \vec{v} \in W $, then $ \vec{u} + \vec{v} \in W $
3. **Closed under Scalar Multiplication:** If $ \vec{v} \in W $ and $ \alpha \in \mathbb{R} $, then $ \alpha \vec{v} \in W $

If all three hold, then $ W $ is a **vector subspace**.

---

## Examples

- The set $ \mathbb{R}^n $ itself is a subspace.
- The set $ \{ \vec{0} \} $ (only the zero vector) is a subspace.
- The set of all vectors of the form $ (x, 0, 0) \in \mathbb{R}^3 $ is a **line** subspace.
- The set of all vectors of the form $ (x, y, 0) \in \mathbb{R}^3 $ is a **plane** subspace.

---

## How to Check if a Set is a Subspace

Given a set $ W $ described by conditions or equations, verify:

1. $ \vec{0} \in W $
2. If $ \vec{u}, \vec{v} \in W $, then $ \vec{u} + \vec{v} \in W $
3. If $ \vec{v} \in W $ and $ \alpha \in \mathbb{R} $, then $ \alpha \vec{v} \in W $

These steps are often used in POSCOMP questions.

---

# Orthogonal Subspace

---

## Definition

Let $ W \subseteq \mathbb{R}^n $ be a subspace. The **orthogonal subspace** (also called the **orthogonal complement**) of $ W $, denoted by $ W^\perp $, is defined as:

$$
W^\perp = \{ \vec{v} \in \mathbb{R}^n \mid \vec{v} \cdot \vec{w} = 0 \text{ for all } \vec{w} \in W \}
$$

That is, $ W^\perp $ contains **all vectors orthogonal to every vector in** $ W $.

---

## Properties

- $ W^\perp $ is also a **subspace** of $ \mathbb{R}^n $.
- $ \dim(W) + \dim(W^\perp) = n $ (Fundamental Theorem of Orthogonality)
- $ (W^\perp)^\perp = W $

---

## Examples

1. Let $ W = \text{span} \{ (1, 0, 0) \} \subset \mathbb{R}^3 $

   Then:

   $$
   W^\perp = \{ (0, y, z) \in \mathbb{R}^3 \} = \text{plane } yOz
   $$

2. If $ W $ is the $xy$-plane in $ \mathbb{R}^3 $:

   $$
   W = \{ (x, y, 0) \}, \quad W^\perp = \text{span} \{ (0, 0, 1) \}
   $$

---

## How to Compute $ W^\perp $

Let $ W = \text{span} \{ \vec{v}_1, \vec{v}_2, \ldots \} $

To find $ W^\perp $, solve:

$$
\vec{x} \cdot \vec{v}_1 = 0,\quad
\vec{x} \cdot \vec{v}_2 = 0,\quad
\ldots
$$

This gives a **homogeneous linear system**, and its **solution set is the orthogonal complement**.

---

## Summary

- A **subspace** is a subset closed under addition and scalar multiplication, and contains $ \vec{0} $.
- The **orthogonal complement** $ W^\perp $ contains all vectors orthogonal to a subspace $ W $.
- $ W^\perp $ is a subspace, and its dimension satisfies $ \dim(W) + \dim(W^\perp) = n $.

