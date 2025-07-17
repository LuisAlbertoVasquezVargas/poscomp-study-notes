<!-- File: calculus/differentiation.md -->

# Differentiation of Real Functions

---

## Chain Rule

The chain rule allows you to compute the derivative of a composition of functions.

If:

$$
y = f(g(x))
$$

Then the derivative of y with respect to x is:

$$
\frac{dy}{dx} = f'(g(x)) \cdot g'(x)
$$

Or equivalently:

$$
\frac{d}{dx}f(g(x)) = f'(g(x)) \, g'(x)
$$

---

### Example

Find the derivative of y = sin(x²):

$$
\frac{d}{dx} \sin(x^2) = \cos(x^2) \cdot 2x
$$

Here:

$$
f(u) = \sin(u), \; f'(u) = \cos(u)
$$

$$
u = x^2, \; u' = 2x
$$

---
