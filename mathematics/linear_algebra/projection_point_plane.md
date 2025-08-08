<!-- File: linear_algebra/projection_point_plane.md -->

# Projection of a Point onto a Plane

## 🧮 Component Form

Given:

- A point **P** = $(x_0, y_0, z_0)$  
- A plane:  $a x + b y + c z + d = 0$  
  with normal vector **n** = $(a, b, c)$

We define:

- Scalar:

  $$
  t = \frac{a x_0 + b y_0 + c z_0 + d}{a^2 + b^2 + c^2}
  $$

- Vectors:

  $$
  \vec{p} = \begin{bmatrix} x_0 \\ y_0 \\ z_0 \end{bmatrix}, \quad
  \vec{n} = \begin{bmatrix} a \\ b \\ c \end{bmatrix}
  $$

Then the **orthogonal projection** of point **P** onto the plane is:

$$
\vec{p}_{\text{proj}} = \vec{p} - t \vec{n}
$$

Which in component form means:

$$
P' = (x_0, y_0, z_0) - t \cdot (a, b, c)
$$

Or explicitly:

$$
P' = \left( x_0 - a t,\;\; y_0 - b t,\;\; z_0 - c t \right)
$$

---

## 🧭 Pure Vector Form

Same idea, using inner product notation:

Let:

- $\vec{p}$ = position vector of the point  
- $\vec{n}$ = normal vector of the plane  
- $d$ = scalar from the plane equation $\, \vec{n} \cdot \vec{x} + d = 0$

Then:

$$
\vec{p}_{\text{proj}} = \vec{p} - \frac{\vec{n} \cdot \vec{p} + d}{\|\vec{n}\|^2} \vec{n}
$$

---

