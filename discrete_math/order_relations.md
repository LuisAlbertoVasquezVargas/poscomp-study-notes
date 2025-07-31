<!-- File: discrete_math/order_relations.md -->

# Relations: Conditions for Order Relations

---

## 🔸 Definitions and Conditions for Order Relations

Given a set $A$, a **binary relation** $R \subseteq A \times A$ is said to be:

### 1. **Reflexive**

$$
\forall a \in A, \quad (a, a) \in R
$$

Every element relates to itself.

> *Note:* The **irreflexive** property is the negation of reflexive; it means no element relates to itself.

---

### 2. **Symmetric**

$$
\forall a, b \in A, \quad (a, b) \in R \implies (b, a) \in R
$$

If $a$ relates to $b$, then $b$ relates to $a$.

---

### 3. **Antisymmetric (Intuitive Explanation)**

For a relation to be **antisymmetric**, it means:

> If $a$ relates to $b$ and $b$ relates to $a$, then $a$ and $b$ must be the same element.

In other words, *no two different elements relate to each other both ways.*

This can be seen as a "negation" of symmetry for distinct elements:

$$
\forall a, b \in A, \quad a \neq b \implies \neg\big( (a,b) \in R \wedge (b,a) \in R \big)
$$

---

### 4. **Transitive**

$$
\forall a, b, c \in A, \quad \big( (a, b) \in R \wedge (b, c) \in R \big) \implies (a, c) \in R
$$

If $a$ relates to $b$ and $b$ relates to $c$, then $a$ relates to $c$.

---

## 🔸 Types of Order Relations

### Partial Order

A relation $R$ on $A$ is a **partial order** if it is:

- Reflexive
- Antisymmetric (as explained above)
- Transitive

---

### Total (Linear) Order

A **total order** is a partial order $R$ where any two elements are comparable:

$$
\forall a, b \in A, \quad (a, b) \in R \quad \text{or} \quad (b, a) \in R
$$

---

### Strict Partial Order

A relation $R$ on $A$ is a **strict partial order** if it is:

- Irreflexive (negation of reflexive)
- Transitive
- Satisfies the antisymmetry condition implied by irreflexivity and transitivity

---

### Strict Total Order

A strict partial order that is also **total**:

$$
\forall a, b \in A, a \neq b, \quad (a, b) \in R \quad \text{or} \quad (b, a) \in R
$$

---

## 🔸 Summary Table

| Property      | Definition                                | Partial Order? | Total Order? | Strict Partial Order? | Strict Total Order? |
|---------------|-------------------------------------------|---------------|--------------|----------------------|---------------------|
| Reflexive     | $\forall a, (a,a) \in R$                  | Yes           | Yes          | No                   | No                  |
| Symmetric     | $\forall a,b, (a,b) \in R \implies (b,a) \in R$ | No            | No           | No                   | No                  |
| Antisymmetric (Intuitive) | No two distinct elements relate both ways: $\forall a,b, a \neq b \implies \neg\big( (a,b) \in R \wedge (b,a) \in R \big)$ | Yes | Yes | Yes | Yes |
| Transitive    | $\forall a,b,c, (a,b) \in R \wedge (b,c) \in R \implies (a,c) \in R$ | Yes           | Yes          | Yes                  | Yes                 |
| Totality      | $\forall a,b, (a,b) \in R \text{ or } (b,a) \in R$ | No            | Yes          | No                   | Yes                 |

---
