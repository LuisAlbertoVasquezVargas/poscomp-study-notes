<!-- File: probability/conditional_probability.md -->

# 📘 Conditional Probability

---

## 🔹 Definition

The **conditional probability** of an event $A$ given that another event $B$ has occurred (with $P(B) > 0$) is defined by:

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
$$

It represents the **probability of $A$ occurring assuming $B$ is known to have occurred**.

---

## 🔹 Interpretation

Think of the sample space being **restricted to $B$**. Then we ask: *what is the probability of $A$ within that restricted space?*

---

## 🔹 Properties

- $P(A \mid B) \cdot P(B) = P(A \cap B)$
- If $A$ and $B$ are **independent**, then:
  $$
  P(A \mid B) = P(A)
  $$
- Symmetry does **not** hold in general:
  $$
  P(A \mid B) \neq P(B \mid A)
  $$

---

## 🔹 Common Use Cases

- Diagnostic tests (e.g., probability of a disease given a positive test)
- Sequential experiments
- Bayes’ Theorem (based on conditional probability)

---

## 🔹 Example

Suppose a deck has 4 red cards and 6 black cards. If one card is drawn at random and it's known to be red, what’s the probability it is a heart?

Let:
- $A$ = card is a heart
- $B$ = card is red

Then:

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)} = \frac{1/10}{4/10} = \frac{1}{4}
$$

---

## 🔹 Diagrammatic Intuition

In a Venn diagram:

- $P(A \cap B)$ = overlapping area
- $P(B)$ = area of $B$
- $P(A \mid B)$ = proportion of overlap within $B$

---
