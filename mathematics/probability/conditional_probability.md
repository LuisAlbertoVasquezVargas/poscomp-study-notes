<!-- File: probability/conditional_probability.md -->

# 📘 Conditional Probability and Bayes' Theorem

---

## 🔹 Conditional Probability

### **Definition**

The **conditional probability** of an event $A$ given that another event $B$ has occurred (assuming $P(B) > 0$) is:

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
$$

This represents the **likelihood of $A$ happening under the condition that $B$ is known to have occurred**.

---

### **Interpretation**

Think of the sample space being **restricted to $B$**. Then ask: *within that restricted space, what is the chance of $A$?*

---

### **Properties**

- **Multiplication Rule**:  
  $$
  P(A \cap B) = P(A \mid B) \cdot P(B)
  $$

- **Independence**:  
  If $A$ and $B$ are independent, then:  
  $$
  P(A \mid B) = P(A)
  $$

- **Asymmetry**:  
  $$
  P(A \mid B) \neq P(B \mid A) \quad \text{in general}
  $$

---

## 🔹 Bayes' Theorem

Bayes’ Theorem is a direct consequence of the definition of conditional probability. It allows us to **reverse the condition**, giving a way to compute $P(A \mid B)$ if $P(B \mid A)$ is known:

### **Formula**

$$
P(A \mid B) = \frac{P(B \mid A) \cdot P(A)}{P(B)}
$$

Where:
- $P(A)$ is the **prior** probability of $A$
- $P(B \mid A)$ is the **likelihood**
- $P(B)$ is the **evidence** (normalizing constant)
- $P(A \mid B)$ is the **posterior** probability

---

### **Expanded Denominator (Law of Total Probability)**

If $A_1, A_2, \dots, A_n$ are a **partition** of the sample space and are mutually exclusive:

$$
P(B) = \sum_{i=1}^n P(B \mid A_i) \cdot P(A_i)
$$

Then:

$$
P(A_k \mid B) = \frac{P(B \mid A_k) \cdot P(A_k)}{\sum_{i=1}^n P(B \mid A_i) \cdot P(A_i)}
$$

---

## 🔹 Diagrammatic Intuition

A **Venn diagram** can help:

- Circle $A$, circle $B$.
- The **overlap** = $A \cap B$
- $P(A \mid B)$ = relative size of the overlap within $B$.

For Bayes’ Theorem, imagine reversing the direction: going from $P(B \mid A)$ to $P(A \mid B)$.

---

## 🔹 Common Applications

- Medical diagnostics  
  (e.g., probability of disease given a positive test result)
- Spam detection (email classification)
- Risk assessment
- Machine learning (naive Bayes classifiers)

---

## 🔹 Example (from Previous Notes)

Let:
- $A$ = card is a heart  
- $B$ = card is red

Deck: 4 red cards (1 heart, 3 diamonds), 6 black cards

Then:

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)} = \frac{1/10}{4/10} = \frac{1}{4}
$$

---

## 🧠 Tip

Bayes' Theorem is often useful when:
- You know how likely $B$ is under different $A_i$ conditions
- You want to **infer** the probability of $A_i$ after observing $B$

---
