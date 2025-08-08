<!-- File: formal_languages/state_machines.md -->

# 🤖 State Machines and Regular Languages

This section covers the foundational concepts of finite state machines (FSMs), their types, and the main theoretical results concerning regular languages.

---

## 🧩 What is a Finite State Machine (FSM)?

A **finite state machine** is an abstract computational model that:
- Has a **finite set of states**
- Reads input symbols one at a time
- Transitions between states according to a **transition function**
- (In some variants) produces output or accepts/rejects input

FSMs are used to define and recognize **regular languages**.

---

## ⚙️ Types of Finite State Machines

### 1. **Deterministic Finite Automaton (DFA)**
- **Unique transition** per input symbol from each state.
- Can be defined as a tuple:  
  `M = (Q, Σ, δ, q₀, F)`  
  where:
  - `Q`: finite set of states  
  - `Σ`: input alphabet  
  - `δ`: transition function `δ: Q × Σ → Q`  
  - `q₀ ∈ Q`: initial state  
  - `F ⊆ Q`: set of accepting states

### 2. **Nondeterministic Finite Automaton (NFA)**
- **Multiple transitions** allowed per input symbol.
- Accepts if at least one path leads to an accepting state.
- Transition function: `δ: Q × Σ → 𝒫(Q)`
- Equivalent in power to DFA.

### 3. **ε-NFA (NFA with ε-transitions)**
- Like an NFA, but includes transitions that do not consume input.
- Also equivalent in power to DFA.

### 4. **Moore Machine**
- FSM with **output associated to states**.
- Output depends only on the current state.
- Can be defined as a 6-tuple with output function `λ: Q → Γ`.

### 5. **Mealy Machine**
- FSM with **output associated to transitions**.
- Output depends on both current state and input symbol.
- Output function: `λ: Q × Σ → Γ`.

---

## 📘 Theorems and Results on Regular Languages

### Closure Properties of Regular Languages
The class of regular languages is closed under:
- **Union**
- **Concatenation** (juxtaposition, e.g., `r₁r₂`)
- **Kleene star** (`r*`)
- **Intersection**
- **Complement**
- **Difference**
- **Reversal**
- **Homomorphism**
- **Inverse homomorphism**

### Myhill–Nerode Theorem
A language `L ⊆ Σ*` is regular if and only if the number of equivalence classes of the relation:

`x ≡_L y ⇔ ∀z ∈ Σ*, xz ∈ L ⇔ yz ∈ L`

is finite. This relation defines indistinguishability of strings with respect to `L`.

### Kleene’s Theorem (Equivalence between Regular Expressions and Finite Automata)
A language is regular if and only if it can be described by a regular expression, and equivalently if and only if it is recognized by a finite automaton (deterministic, nondeterministic, or ε-based). There are constructive conversions in both directions:
- From a regular expression to an equivalent automaton (e.g., Thompson’s construction yields an ε-NFA).
- From a finite automaton to a regular expression (e.g., state elimination or using Arden’s lemma).
- Nondeterministic automata can be transformed into deterministic ones via subset construction.

### Equivalence of Models
The following models recognize the same class of languages:
- **Deterministic Finite Automaton**
- **Nondeterministic Finite Automaton**
- **Nondeterministic Finite Automaton with ε-transitions**
- **Regular expressions**

---

## ✳️ Regular Expression Operations

A regular expression over an alphabet `Σ` is built using:
- **∅** (empty set)
- **ε** (empty string)
- **a**, for any `a ∈ Σ`
- **(r₁ ∪ r₂)** (union)
- **r₁r₂** (concatenation)
- **(r₁*)** (Kleene star)

These operations are sufficient to describe all regular languages.

---

## ✅ Summary

| Finite State Machine Type                   | Output | Transition Determinism | Recognizes Regular Languages? | Abbreviation |
|--------------------------------------------|--------|------------------------|-------------------------------|--------------|
| Deterministic Finite Automaton             | No     | Deterministic          | Yes                           | DFA          |
| Nondeterministic Finite Automaton          | No     | Nondeterministic       | Yes                           | NFA          |
| Nondeterministic Finite Automaton with ε   | No     | Nondeterministic + ε   | Yes                           | ε-NFA        |
| Moore Machine                               | Yes    | Deterministic          | No                            | —            |
| Mealy Machine                               | Yes    | Deterministic          | No                            | —            |

---
