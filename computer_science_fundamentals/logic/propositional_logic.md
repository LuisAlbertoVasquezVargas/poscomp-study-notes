<!-- File: computer_science_fundamentals/logic/propositional_logic.md -->

# Propositional Logic

---

## Definition

Propositional Logic studies statements called **propositions**, which can be either **true (1)** or **false (0)**.

Logical connectives combine propositions to form new propositions.

The basic logical connectives are:

- **Negation** (NOT): ¬  
- **Conjunction** (AND): ∧  
- **Disjunction** (OR): ∨  
- **Implication** (IMPLIES): →  
- **Biconditional** (IF AND ONLY IF): ↔

---

## Truth Values

Each proposition `p` can take one of two truth values:

| Truth Value | Meaning |
|-------------|----------|
| 1           | True     |
| 0           | False    |

---

## Truth Tables for Basic Connectives

### Negation (NOT)

| p | ¬p |
|---|----|
| 1 | 0  |
| 0 | 1  |

---

### Conjunction (AND)

| p | q | p ∧ q |
|---|---|-------|
| 1 | 1 | 1     |
| 1 | 0 | 0     |
| 0 | 1 | 0     |
| 0 | 0 | 0     |

---

### Disjunction (OR)

| p | q | p ∨ q |
|---|---|-------|
| 1 | 1 | 1     |
| 1 | 0 | 1     |
| 0 | 1 | 1     |
| 0 | 0 | 0     |

---

### Implication (IMPLIES)

| p | q | p → q |
|---|---|-------|
| 1 | 1 | 1     |
| 1 | 0 | 0     |
| 0 | 1 | 1     |
| 0 | 0 | 1     |

---

### Biconditional (IF AND ONLY IF)

| p | q | p ↔ q |
|---|---|-------|
| 1 | 1 | 1     |
| 1 | 0 | 0     |
| 0 | 1 | 0     |
| 0 | 0 | 1     |

---

## Properties of Implication

Implication has several useful equivalences and relationships to other connectives:

1. **Implication as disjunction**  
   - `p → q ≡ ¬p ∨ q`  
   “If p then q” is equivalent to “not p or q”.

2. **Contrapositive**  
   - `p → q ≡ ¬q → ¬p`  
   An implication is logically equivalent to its contrapositive.

3. **Negation of implication**  
   - `¬(p → q) ≡ p ∧ ¬q`  
   Saying “it is not true that if p then q” means p is true and q is false.

4. **Relation to De Morgan–style transformations**  
   - Since `p → q ≡ ¬p ∨ q`, we can apply De Morgan’s laws when dealing with negations.  
   Example:  
   `¬(p → q) ≡ ¬(¬p ∨ q) ≡ p ∧ ¬q`.

5. **Tautologies involving implication**  
   - `p → p` is always true (reflexivity).  
   - `(p → q) ∧ (q → r) → (p → r)` is always true (transitivity).  

---

