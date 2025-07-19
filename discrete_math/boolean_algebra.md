<!-- File: discrete_math/boolean_algebra.md -->

# Boolean Algebra Identities

---

## Basic Operations

- **AND**: A · B or simply AB  
- **OR**: A + B  
- **NOT**: ¬A or A'

---

## Fundamental Identities

$$
\begin{array}{ll}
\text{Identity Laws:} & A + 0 = A, \quad A \cdot 1 = A \\
\text{Null Laws:} & A + 1 = 1, \quad A \cdot 0 = 0 \\
\text{Idempotent Laws:} & A + A = A, \quad A \cdot A = A \\
\text{Complement Laws:} & A + \overline{A} = 1, \quad A \cdot \overline{A} = 0 \\
\text{Double Negation:} & \overline{\overline{A}} = A \\
\text{Commutative Laws:} & A + B = B + A, \quad A \cdot B = B \cdot A \\
\text{Associative Laws:} & (A + B) + C = A + (B + C), \quad (A \cdot B) \cdot C = A \cdot (B \cdot C) \\
\text{Distributive Laws:} & A \cdot (B + C) = AB + AC, \quad A + (B \cdot C) = (A + B)(A + C)
\end{array}
$$

---

## De Morgan's Laws

$$
\begin{aligned}
\overline{A \cdot B} &= \overline{A} + \overline{B} \\
\overline{A + B} &= \overline{A} \cdot \overline{B}
\end{aligned}
$$

---

## Absorption Laws

$$
\begin{aligned}
A + (A \cdot B) &= A \\
A \cdot (A + B) &= A
\end{aligned}
$$
