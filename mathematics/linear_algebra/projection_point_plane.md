<!-- File: mathematics/linear_algebra/projection_point_plane.md -->

# Projection of a Point onto a Plane or Subspace

## ✅ General Formula for Projection onto a Subspace

If a subspace $W \subseteq \mathbb{R}^n$ is spanned by linearly independent vectors (columns of $A$), then the **projection matrix** is:

$$
P_W = A (A^T A)^{-1} A^T
$$

For any vector $x \in \mathbb{R}^n$, the projection is:

$$
x_{\text{proj}} = P_W \, x
$$

---

## ▶ Special Case: Projection onto a Line (1D Subspace)

If $W = \mathrm{span}(u)$ for some nonzero vector $u$, then:

$$
P = \frac{u\,u^T}{u^T u}
$$

*(This is the general formula with $A = u$.)*

---

## 🔍 Auxiliary: Projection onto a Plane from a Point and Normal Vector

For a plane

$$
a x + b y + c z + d = 0,
$$

with normal

$$
n = \begin{bmatrix} a \\ b \\ c \end{bmatrix},
$$

and a point

$$
p = \begin{bmatrix} x_0 \\ y_0 \\ z_0 \end{bmatrix},
$$

the projection of $p$ onto the plane is:

$$
p_{\text{proj}} = p - \frac{n^T p + d}{n^T n}\,n.
$$

This is handy when the plane is given in normal form rather than by a spanning set.

---

## ✅ Summary Table (Matrix Perspective)

| **Subspace Type**    | **Projection Matrix Formula**   |
| -------------------- | ------------------------------- |
| General subspace $W$ | $P = A (A^T A)^{-1} A^T$        |
| Line (1D case)       | $P = \dfrac{u\,u^T}{u^T u}$     |
| Plane (via normal)   | $P = I - \dfrac{n\,n^T}{n^T n}$ |
