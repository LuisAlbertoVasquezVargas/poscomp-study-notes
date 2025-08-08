<!-- File: linear_programming/dual_formulation.md -->

# Dual of a Linear Programming Problem

## 🔁 What is the Dual?

Every linear programming problem (called the **primal**) has an associated **dual** problem. Solving the dual can provide bounds, sensitivity information, or even directly solve the primal under certain circumstances.

If the **primal** is a **maximization** problem with constraints of type ≤, the **dual** will be a **minimization** problem with constraints of type ≥, and vice versa.

---

## 📑 Standard Forms

### Primal in standard form:
```

Maximize:     cᵀx
Subject to:   Ax ≤ b
x ≥ 0

```

### Dual:
```

Minimize:     bᵀy
Subject to:   Aᵀy ≥ c
y ≥ 0

```

📝 Each **constraint in the primal** becomes a **variable in the dual** and vice versa.

---

## 🧠 Rules to Build the Dual

| Primal Constraint Type | Dual Variable Restriction |
|------------------------|---------------------------|
| `=`                   | Free (∈ ℝ)                |
| `≤`                   | ≥ 0                       |
| `≥`                   | ≤ 0                       |

| Primal Variable Restriction | Dual Constraint Type |
|-----------------------------|----------------------|
| `xᵢ ≥ 0`                    | `≥`                 |
| `xᵢ ≤ 0`                    | `≤`                 |
| `xᵢ ∈ ℝ`                    | `=`                 |

---

## ✅ Solving an Example — QUESTÃO 07

### Given Primal:

```

Maximize:     2x₁ + x₂
Subject to:
x₁ + x₂  = 4      → constraint 1
x₁       ≤ 3      → constraint 2
x₂       ≥ 2      → constraint 3
x₁, x₂ ≥ 0

```

### Step 1: Label and Interpret

- Objective: **Maximize**
- 3 constraints → dual will have **3 variables**: y₁, y₂, y₃
  - Constraint 1 is `=` → y₁ ∈ ℝ
  - Constraint 2 is `≤` → y₂ ≥ 0
  - Constraint 3 is `≥` → y₃ ≤ 0

### Step 2: Dual Objective

The RHS of the primal becomes the coefficients in the dual objective function:

```

Minimize: 4y₁ + 3y₂ + 2y₃

```

### Step 3: Build Dual Constraints

Each primal variable becomes a constraint in the dual.

#### For x₁ (coefficient in primal objective = 2):

Use the coefficients from each constraint for x₁:
- From constraint 1: 1
- From constraint 2: 1
- From constraint 3: 0

So: `y₁ + y₂ ≥ 2`

#### For x₂ (coefficient in primal objective = 1):

- From constraint 1: 1
- From constraint 2: 0
- From constraint 3: 1

So: `y₁ + y₃ ≥ 1`

### Step 4: Write Full Dual

```

Minimize:   4y₁ + 3y₂ + 2y₃
Subject to:
y₁ + y₂ ≥ 2
y₁ + y₃ ≥ 1
y₁ ∈ ℝ, y₂ ≥ 0, y₃ ≤ 0

```

### ✅ Correct Answer: **(E)**

---

## 🔄 Summary Table (Quick Dual Mapping)

| Primal            | Dual              |
|-------------------|-------------------|
| Maximize          | Minimize          |
| x variables       | y constraints     |
| Constraints       | Variables         |
| RHS of constraints → dual objective   |
| Primal var ≥ 0 → dual constraint ≥    |
| Primal constraint = → dual var free   |
| Primal constraint ≤ → dual var ≥ 0    |
| Primal constraint ≥ → dual var ≤ 0    |

---
