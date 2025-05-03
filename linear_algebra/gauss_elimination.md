<!-- File: linear_algebra/gauss_elimination.md -->

# Gauss Elimination Method

---

## Key Idea

We want to solve a system of the form:

$$
A\vec{x} = \vec{b}
$$

To do that, we form the augmented matrix:

$$
[A \,|\, b]
$$

Then apply row operations until we get:

$$
[I \,|\, x]
$$

Where $I$ is the identity matrix and $x$ is the solution vector.

---

## Allowed Row Operations

- $R_i \leftrightarrow R_j$ (swap rows)  
- $R_i *= k$ (multiply row by scalar)  
- $R_i += k R_j$, $R_i -= k R_j$ (add/subtract row multiple)

---

## Example

Solve:

$$
\begin{aligned}
x + y + z &= 6 \\
2x + 3y + z &= 11 \\
x + 2y + 3z &= 13
\end{aligned}
$$

---

### Step 1: Augmented matrix

$$
\begin{bmatrix}
1 & 1 & 1 & \vert & 6 \\
2 & 3 & 1 & \vert & 11 \\
1 & 2 & 3 & \vert & 13 \\
\end{bmatrix}
$$

---

### Step 2: Eliminate below in column 1

$$
R_2 -= 2R_1 \\
R_3 -= R_1
$$

$$
\begin{bmatrix}
1 & 1 & 1 & \vert & 6 \\
0 & 1 & -1 & \vert & -1 \\
0 & 1 & 2 & \vert & 7 \\
\end{bmatrix}
$$

---

### Step 3: Eliminate below in column 2

$$
R_3 -= R_2
$$

$$
\begin{bmatrix}
1 & 1 & 1 & \vert & 6 \\
0 & 1 & -1 & \vert & -1 \\
0 & 0 & 3 & \vert & 8 \\
\end{bmatrix}
$$

---

### Step 4: Normalize third row

$$
R_3 *= \frac{1}{3}
$$

$$
\begin{bmatrix}
1 & 1 & 1 & \vert & 6 \\
0 & 1 & -1 & \vert & -1 \\
0 & 0 & 1 & \vert & \frac{8}{3} \\
\end{bmatrix}
$$

---

### Step 5: Eliminate above in column 3

$$
R_1 -= R_3 \\
R_2 += R_3
$$

$$
\begin{bmatrix}
1 & 1 & 0 & \vert & \frac{10}{3} \\
0 & 1 & 0 & \vert & \frac{5}{3} \\
0 & 0 & 1 & \vert & \frac{8}{3} \\
\end{bmatrix}
$$

---

### Step 6: Eliminate above in column 2

$$
R_1 -= R_2
$$

$$
\begin{bmatrix}
1 & 0 & 0 & \vert & \frac{5}{3} \\
0 & 1 & 0 & \vert & \frac{5}{3} \\
0 & 0 & 1 & \vert & \frac{8}{3} \\
\end{bmatrix}
$$

---

## Final Answer

$$
\boxed{
x = \frac{5}{3}, \quad
y = \frac{5}{3}, \quad
z = \frac{8}{3}
}
$$

---

## Sources

- [YouTube – Gaussian Elimination Overview](https://www.youtube.com/watch?v=JzhlfbVmXAE)
