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

### 5. **Equivalence Relation**

A relation $R$ on a set $A$ is an **equivalence relation** if it satisfies all three of the following:

- **Reflexive**
- **Symmetric**
- **Transitive**

These properties allow elements of $A$ to be grouped into **equivalence classes**, forming a **partition** of the set.

> **Examples:**
> - "is equal to" on numbers
> - "has same remainder modulo $n$"
> - "has same birthday" on a group of people

---

## 🔸 Types of Order Relations

### Partial Order

A relation $R$ on $A$ is a **partial order** if it is:

- Reflexive
- Antisymmetric
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

- Irreflexive
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

| Property             | Definition                                                                          | Partial Order? | Total Order? | Strict Partial Order? | Strict Total Order? | Equivalence Relation? |
|----------------------|--------------------------------------------------------------------------------------|----------------|---------------|------------------------|----------------------|------------------------|
| Reflexive            | $\forall a, (a,a) \in R$                                                             | Yes            | Yes           | No                     | No                   | Yes                    |
| Symmetric            | $\forall a,b, (a,b) \in R \implies (b,a) \in R$                                     | No             | No            | No                     | No                   | Yes                    |
| Antisymmetric        | $\forall a \neq b, \neg\big((a,b) \in R \wedge (b,a) \in R\big)$                    | Yes            | Yes           | Yes                    | Yes                  | No                     |
| Transitive           | $\forall a,b,c, (a,b) \wedge (b,c) \implies (a,c)$                                  | Yes            | Yes           | Yes                    | Yes                  | Yes                    |
| Totality             | $\forall a,b, (a,b) \in R \text{ or } (b,a) \in R$                                  | No             | Yes           | No                     | Yes                  | No                     |
| Equivalence Relation | Reflexive, Symmetric, Transitive                                                    | No             | No            | No                     | No                   | Yes                    |

---
