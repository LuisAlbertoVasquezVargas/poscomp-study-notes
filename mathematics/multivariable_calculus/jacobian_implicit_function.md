<!-- File: multivariable_calculus/jacobian_implicit_function.md -->

# Jacobians and the Implicit Function Theorem

## 🧠 Definitions

### Total Derivative / Total Differential

Given a function $F(u, v, x, y)$ where $u = u(x,y)$, $v = v(x,y)$, the **total derivative** (or total differential) with respect to $x$ captures all ways $F$ changes as $x$ changes, including indirect effects through $u(x,y)$ and $v(x,y)$:

$$
\frac{dF}{dx} = \frac{\partial F}{\partial x} + \frac{\partial F}{\partial u} \frac{\partial u}{\partial x} + \frac{\partial F}{\partial v} \frac{\partial v}{\partial x}
$$

Here, $\frac{\partial F}{\partial x}$, $\frac{\partial F}{\partial u}$, and $\frac{\partial F}{\partial v}$ are **partial derivatives**, computed by treating all other independent variables as constants.

---

### Partial Derivative

The **partial derivative** of a function with respect to one variable holds all other variables **constant** (including implicitly dependent variables), e.g.,

$$
\frac{\partial F}{\partial x}
$$

is evaluated by treating $u$, $v$, and $y$ as constants.

---

### Jacobian Matrix

The **Jacobian matrix** of a vector function $\mathbf{F} = (F_1, F_2)$ with respect to variables $(u, v)$ is the matrix of **partial derivatives**:

$$
J_{(F_1, F_2)/(u, v)} =
\begin{bmatrix}
\frac{\partial F_1}{\partial u} & \frac{\partial F_1}{\partial v} \\
\frac{\partial F_2}{\partial u} & \frac{\partial F_2}{\partial v}
\end{bmatrix}
$$

Each entry is a **partial derivative**, holding $x, y$ fixed (treated as constants).

Similarly, the Jacobian matrix of the implicitly defined functions $u = u(x,y)$, $v = v(x,y)$ with respect to $(x,y)$ is:

$$
J_{(u, v)/(x, y)} =
\begin{bmatrix}
\frac{\partial u}{\partial x} & \frac{\partial u}{\partial y} \\
\frac{\partial v}{\partial x} & \frac{\partial v}{\partial y}
\end{bmatrix}
$$

---

### Notation note: $\frac{\partial (u,v)}{\partial (x,y)}$

This notation means the Jacobian matrix of the vector function $(u,v)$ with respect to $(x,y)$, explicitly:

$$
\frac{\partial (u,v)}{\partial (x,y)} =
\begin{bmatrix}
\frac{\partial u}{\partial x} & \frac{\partial u}{\partial y} \\
\frac{\partial v}{\partial x} & \frac{\partial v}{\partial y}
\end{bmatrix}
$$

---

## 📘 Theorem: Implicit Function Theorem (Simplified)

Consider the system

$$
\begin{cases}
F_1(x,y,u,v) = 0 \\
F_2(x,y,u,v) = 0
\end{cases}
$$

that implicitly defines $u = u(x,y)$ and $v = v(x,y)$.

If the Jacobian matrix with respect to $(u,v)$,

$$
J_{(F_1,F_2)/(u,v)} =
\begin{bmatrix}
\frac{\partial F_1}{\partial u} & \frac{\partial F_1}{\partial v} \\
\frac{\partial F_2}{\partial u} & \frac{\partial F_2}{\partial v}
\end{bmatrix}
$$

has **nonzero determinant** at a point,

$$
\det \left( J_{(F_1,F_2)/(u,v)} \right) \neq 0,
$$

then functions $u = u(x,y)$, $v = v(x,y)$ exist and are differentiable in a neighborhood of that point.

---

## 🧮 Jacobian via Total Differentiation

Starting from the implicit system

$$
\begin{cases}
F_1(x,y,u(x,y),v(x,y)) = 0 \\
F_2(x,y,u(x,y),v(x,y)) = 0
\end{cases}
$$

taking total differentials yields:

$$
\begin{cases}
dF_1 = \frac{\partial F_1}{\partial x} dx + \frac{\partial F_1}{\partial y} dy + \frac{\partial F_1}{\partial u} du + \frac{\partial F_1}{\partial v} dv = 0 \\
dF_2 = \frac{\partial F_2}{\partial x} dx + \frac{\partial F_2}{\partial y} dy + \frac{\partial F_2}{\partial u} du + \frac{\partial F_2}{\partial v} dv = 0
\end{cases}
$$

where

$$
du = \frac{\partial u}{\partial x} dx + \frac{\partial u}{\partial y} dy, \quad dv = \frac{\partial v}{\partial x} dx + \frac{\partial v}{\partial y} dy
$$

Substitute $du$ and $dv$ into total differentials and group terms by $dx$ and $dy$ to get linear systems for the unknown partial derivatives.

---

## 🧮 Matrix Jacobian Formula

The Jacobian matrix of $(u,v)$ with respect to $(x,y)$ satisfies

$$
\boxed{
\frac{\partial (u,v)}{\partial (x,y)} = - \left( \frac{\partial (F_1,F_2)}{\partial (u,v)} \right)^{-1} \left( \frac{\partial (F_1,F_2)}{\partial (x,y)} \right)
}
$$

---

## Scalar 1D Analogy (Parenthesized Fraction Style)

If $F(x,u) = 0$ implicitly defines $u = u(x)$, then

$$
\boxed{
\frac{du}{dx} = - \left( \frac{\partial F}{\partial u} \right)^{-1} \left( \frac{\partial F}{\partial x} \right) = - \frac{\frac{\partial F}{\partial x}}{\frac{\partial F}{\partial u}}
}
$$

---

## 🧩 Example: Finding Jacobian entries step-by-step

Given the implicit system

$$
\begin{cases}
F_1(x,y,u,v) = x e^{u} + y u - 1 = 0 \\
F_2(x,y,u,v) = 2 x^{2} v + y^{3} e^{u} - 1 = 0
\end{cases}
$$

where $u = u(x,y)$, $v = v(x,y)$, find

$$
J =
\begin{bmatrix}
\frac{\partial u}{\partial x} & \frac{\partial u}{\partial y} \\
\frac{\partial v}{\partial x} & \frac{\partial v}{\partial y}
\end{bmatrix}
$$

at the point $(x,y,u,v) = (1,1,0,0)$.

---

### Step 1: Write total differentials and substitute $du, dv$

$$
dF_1 = \frac{\partial F_1}{\partial x} dx + \frac{\partial F_1}{\partial y} dy + \frac{\partial F_1}{\partial u} du + \frac{\partial F_1}{\partial v} dv = 0
$$

$$
dF_2 = \frac{\partial F_2}{\partial x} dx + \frac{\partial F_2}{\partial y} dy + \frac{\partial F_2}{\partial u} du + \frac{\partial F_2}{\partial v} dv = 0
$$

with

$$
du = \frac{\partial u}{\partial x} dx + \frac{\partial u}{\partial y} dy, \quad dv = \frac{\partial v}{\partial x} dx + \frac{\partial v}{\partial y} dy
$$

---

### Step 2: Substitute and group by $dx, dy$

$$
\left(\frac{\partial F_1}{\partial x} + \frac{\partial F_1}{\partial u} \frac{\partial u}{\partial x} + \frac{\partial F_1}{\partial v} \frac{\partial v}{\partial x}\right) dx + \left(\frac{\partial F_1}{\partial y} + \frac{\partial F_1}{\partial u} \frac{\partial u}{\partial y} + \frac{\partial F_1}{\partial v} \frac{\partial v}{\partial y}\right) dy = 0
$$

$$
\left(\frac{\partial F_2}{\partial x} + \frac{\partial F_2}{\partial u} \frac{\partial u}{\partial x} + \frac{\partial F_2}{\partial v} \frac{\partial v}{\partial x}\right) dx + \left(\frac{\partial F_2}{\partial y} + \frac{\partial F_2}{\partial u} \frac{\partial u}{\partial y} + \frac{\partial F_2}{\partial v} \frac{\partial v}{\partial y}\right) dy = 0
$$

---

### Step 3: Set coefficients of $dx$ and $dy$ equal to zero

$$
\begin{cases}
\frac{\partial F_1}{\partial x} + \frac{\partial F_1}{\partial u} \frac{\partial u}{\partial x} + \frac{\partial F_1}{\partial v} \frac{\partial v}{\partial x} = 0 \\
\frac{\partial F_1}{\partial y} + \frac{\partial F_1}{\partial u} \frac{\partial u}{\partial y} + \frac{\partial F_1}{\partial v} \frac{\partial v}{\partial y} = 0 \\
\frac{\partial F_2}{\partial x} + \frac{\partial F_2}{\partial u} \frac{\partial u}{\partial x} + \frac{\partial F_2}{\partial v} \frac{\partial v}{\partial x} = 0 \\
\frac{\partial F_2}{\partial y} + \frac{\partial F_2}{\partial u} \frac{\partial u}{\partial y} + \frac{\partial F_2}{\partial v} \frac{\partial v}{\partial y} = 0
\end{cases}
$$

---

### Step 4: Evaluate partial derivatives at $(1,1,0,0)$

$$
\begin{aligned}
&\frac{\partial F_1}{\partial u} = x e^{u} + y = 1 + 1 = 2, \quad \frac{\partial F_1}{\partial v} = 0 \\
&\frac{\partial F_1}{\partial x} = e^{u} = 1, \quad \frac{\partial F_1}{\partial y} = u = 0 \\
&\frac{\partial F_2}{\partial u} = y^{3} e^{u} = 1, \quad \frac{\partial F_2}{\partial v} = 2 x^{2} = 2 \\
&\frac{\partial F_2}{\partial x} = 4 x v = 0, \quad \frac{\partial F_2}{\partial y} = 3 y^{2} e^{u} = 3
\end{aligned}
$$

---

### Step 5: Write system of equations

$$
\begin{cases}
1 + 2 \frac{\partial u}{\partial x} + 0 \cdot \frac{\partial v}{\partial x} = 0 \implies 2 \frac{\partial u}{\partial x} + 1 = 0 \\
0 + 2 \frac{\partial u}{\partial y} + 0 \cdot \frac{\partial v}{\partial y} = 0 \implies 2 \frac{\partial u}{\partial y} = 0 \\
0 + 1 \frac{\partial u}{\partial x} + 2 \frac{\partial v}{\partial x} = 0 \implies \frac{\partial u}{\partial x} + 2 \frac{\partial v}{\partial x} = 0 \\
3 + 1 \frac{\partial u}{\partial y} + 2 \frac{\partial v}{\partial y} = 0 \implies \frac{\partial u}{\partial y} + 2 \frac{\partial v}{\partial y} + 3 = 0
\end{cases}
$$

---

### Step 6: Solve system

$$
\begin{aligned}
&\frac{\partial u}{\partial y} = 0 \\
&\frac{\partial u}{\partial x} = -\frac{1}{2} \\
&-\frac{1}{2} + 2 \frac{\partial v}{\partial x} = 0 \implies \frac{\partial v}{\partial x} = \frac{1}{4} \\
&0 + 2 \frac{\partial v}{\partial y} + 3 = 0 \implies \frac{\partial v}{\partial y} = -\frac{3}{2}
\end{aligned}
$$

---

### Final Jacobian matrix

$$
J =
\begin{bmatrix}
\frac{\partial u}{\partial x} & \frac{\partial u}{\partial y} \\
\frac{\partial v}{\partial x} & \frac{\partial v}{\partial y}
\end{bmatrix} =
\begin{bmatrix}
-\frac{1}{2} & 0 \\
\frac{1}{4} & -\frac{3}{2}
\end{bmatrix}
$$

---

