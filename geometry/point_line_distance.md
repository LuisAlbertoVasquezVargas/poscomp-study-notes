<!-- File: geometry/point_line_distance.md -->

# Distance from a Point to a Line

This formula gives the shortest (perpendicular) distance from a point to a straight line in 2D.

---

## Formula

For a line:

$$
Ax + By + C = 0
$$

and a point P(x₀, y₀), the distance d from the point to the line is:

$$
d = \frac{|A x₀ + B y₀ + C|}{\sqrt{A^2 + B^2}}
$$

---

## Example

Find the distance from P(3, 4) to the line \(2x - 3y + 6 = 0\):

Substitute A=2, B=-3, C=6, x₀=3, y₀=4:

$$
d = \frac{|2(3) + (-3)(4) + 6|}{\sqrt{2^2 + (-3)^2}}
$$

$$
d = \frac{|6 - 12 + 6|}{\sqrt{4 + 9}}
$$

$$
d = \frac{|0|}{\sqrt{13}} = 0
$$

So the point lies **on the line**.

---
