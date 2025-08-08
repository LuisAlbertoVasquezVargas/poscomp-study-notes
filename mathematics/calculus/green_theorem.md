<!-- File: calculus/green_theorem.md -->

# 📗 Green’s Theorem

---

## 🔹 Statement

Let $C$ be a positively oriented, piecewise-smooth, simple closed curve in the plane, and let $D$ be the region bounded by $C$. Suppose $P(x,y)$ and $Q(x,y)$ are functions with continuous partial derivatives on an open region containing $D$. Then:

$$
\oint_C (P \, dx + Q \, dy) = \iint_D \left( \frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} \right) dA
$$

---

## 🔹 Interpretation

Green’s theorem relates a **line integral** around a simple closed curve $C$ to a **double integral** over the region $D$ it encloses.

- The left side measures the circulation of the vector field $(P, Q)$ along the boundary $C$.
- The right side measures the curl (rotation) of the field inside $D$.

---

## 🔹 Conditions

- $C$ must be a simple (non-self-intersecting), closed, positively oriented curve.
- $P$ and $Q$ have continuous partial derivatives on an open region containing $D$.

---

## 🔹 Applications

- Calculating areas
- Computing circulation and flux in fluid flow
- Connecting line and double integrals in vector calculus

---

## 🔹 Example

For the vector field $F = (-y, x)$ and $C$ the unit circle, the circulation integral equals:

$$
\oint_C (-y\, dx + x\, dy) = 2\pi
$$

This matches the double integral over the unit disk of the curl:

$$
\iint_D \left( \frac{\partial x}{\partial x} - \frac{\partial (-y)}{\partial y} \right) dA = \iint_D (1 + 1) dA = 2 \times \pi \times 1^2 = 2\pi
$$

---

