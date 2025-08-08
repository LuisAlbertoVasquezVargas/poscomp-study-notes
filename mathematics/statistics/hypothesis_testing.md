<!-- File: statistics/hypothesis_testing.md -->

# Statistical Hypothesis Testing: Key Concepts and Decision Making

---

## 1. Purpose

Determine if sample data provides enough evidence to support a claim about a population parameter.

---

## 2. Hypotheses

- **Null Hypothesis ($H_0$):** Assumes no effect or difference.  
  Example: $H_0: \mu_A = \mu_B$ (means of systems A and B are equal).

- **Alternative Hypothesis ($H_a$):** What you want to prove.  
  Example: $H_a: \mu_A \neq \mu_B$ (means are different, two-tailed test).

---

## 3. Significance Level ($\alpha$)

- The threshold probability for rejecting $H_0$.  
- Common values: 0.05 (5%), 0.01 (1%).  
- Risk of Type I error: rejecting $H_0$ when it's true.

---

## 4. p-value

- Probability of observing data as extreme as (or more than) the sample, assuming $H_0$ is true.  
- **Small p-value (≤ $\alpha$):** Strong evidence against $H_0$ → reject $H_0$.  
- **Large p-value (> $\alpha$):** Weak evidence against $H_0$ → fail to reject $H_0$.

---

## 5. Decision Rule

| Condition                 | Action                       |
|---------------------------|------------------------------|
| $p \leq \alpha$           | Reject $H_0$ (significant)   |
| $p > \alpha$              | Fail to reject $H_0$ (not significant) |

---

## 6. Example Application

- Given: $\alpha = 0.05$, p-value = 0.2343  
- Compare: 0.2343 > 0.05  
- Decision: Fail to reject $H_0$.  
- Conclusion: No sufficient evidence to say the systems differ significantly.  
- Interpretation: The two systems are **not statistically distinct** at the 5% significance level.

---

## 7. Summary

1. Identify $\alpha$ and p-value.  
2. Compare p-value to $\alpha$.  
3. If p-value > $\alpha$, do **not** reject $H_0$.  
4. State conclusion clearly: No significant difference found.  
5. Choose answer accordingly.

---

