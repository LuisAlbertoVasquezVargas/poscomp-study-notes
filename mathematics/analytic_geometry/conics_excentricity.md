<!-- File: analytic_geometry/conics_excentricity.md -->

# Excentricity of Conic Sections

---

## 🔸 Definition

The **excentricity** (often denoted as $e$) of a conic section is a non-negative number that describes how "stretched" or "elongated" the conic is. It is a measure of the deviation of the conic from being circular.

---

## 🔸 Excentricity Values and Corresponding Conics

- **Circle**:  
  $$e = 0$$  
  A circle is a special ellipse with zero excentricity.

- **Ellipse**:  
  $$0 < e < 1$$  
  The ellipse is a closed curve where the sum of distances from any point on it to the two foci is constant.

- **Parabola**:  
  $$e = 1$$  
  A parabola is the set of points equidistant from a fixed point (focus) and a fixed line (directrix).

- **Hyperbola**:  
  $$e > 1$$  
  A hyperbola consists of two separate branches; the difference of distances from any point on the hyperbola to the two foci is constant.

---

## 🔸 Formal Definition of Excentricity for Ellipse and Hyperbola

Given:

- The distance from the center to each focus: $c$
- The length of the semi-major axis: $a$

The excentricity $e$ is defined as:

$$
e = \frac{c}{a}
$$

where:

- For an ellipse, $c < a$, so $e < 1$.
- For a hyperbola, $c > a$, so $e > 1$.

---

## 🔸 Relation Between Parameters of Ellipse

For an ellipse with semi-major axis $a$ and semi-minor axis $b$:

$$
c^2 = a^2 - b^2
$$

thus,

$$
e = \frac{\sqrt{a^2 - b^2}}{a}
$$

---

## 🔸 Relation Between Parameters of Hyperbola

For a hyperbola with semi-major axis $a$ and semi-minor axis $b$:

$$
c^2 = a^2 + b^2
$$

thus,

$$
e = \frac{\sqrt{a^2 + b^2}}{a}
$$

---

## 🔸 Summary Table

| Conic     | Excentricity $e$    | Condition on $a$, $b$, $c$       |
|-----------|---------------------|---------------------------------|
| Circle    | $0$                 | $a = b$, $c=0$                  |
| Ellipse   | $0 < e < 1$         | $c^2 = a^2 - b^2$, $a > b$     |
| Parabola  | $e = 1$             | Defined by focus-directrix setup|
| Hyperbola | $e > 1$             | $c^2 = a^2 + b^2$               |

---

