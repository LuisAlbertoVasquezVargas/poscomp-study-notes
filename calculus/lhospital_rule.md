<!-- File: calculus/lhospital_rule.md -->

# L’Hospital’s Rule and the $e^{\ln(x)}$ Trick

---

## 🔸 L’Hospital’s Rule: Overview

L’Hospital’s Rule helps evaluate limits of the form:

- $\frac{0}{0}$ (zero over zero)  
- $\frac{\infty}{\infty}$ (infinity over infinity)

Specifically, if

$\lim_{x \to a} f(x) = 0$ and $\lim_{x \to a} g(x) = 0$

or both limits tend to $\pm \infty$, and the derivatives $f'(x)$ and $g'(x)$ exist near $a$, then

$\displaystyle \lim_{x \to a} \frac{f(x)}{g(x)} = \lim_{x \to a} \frac{f'(x)}{g'(x)}$

provided the right-hand limit exists or is infinite.

---

## 🔸 Common Indeterminate Forms

Besides $\frac{0}{0}$ and $\frac{\infty}{\infty}$, other indeterminate forms include:

- $0 \times \infty$  
- $\infty - \infty$  
- $0^0$  
- $1^\infty$  
- $\infty^0$

L’Hospital’s Rule can often be applied after algebraic manipulation.

---

## 🔸 The $e^{\ln(x)}$ Trick

To handle indeterminate forms like $0^0$, $1^\infty$, or $\infty^0$, use the substitution:

$f(x)^{g(x)} = e^{g(x) \cdot \ln(f(x))}$

This transforms the original limit into an exponential limit:

$\displaystyle \lim_{x \to a} f(x)^{g(x)} = \lim_{x \to a} e^{g(x) \ln(f(x))} = e^{\lim_{x \to a} \big[g(x) \ln(f(x))\big]}$

Then focus on evaluating the exponent’s limit:

$L = \lim_{x \to a} g(x) \ln(f(x))$

If this limit is indeterminate (e.g., $0 \times (-\infty)$), rewrite it as a quotient to apply L’Hospital’s Rule:

- Convert $g(x) \ln(f(x))$ into $\frac{\ln(f(x))}{1/g(x)}$ or $\frac{g(x)}{1/\ln(f(x))}$, whichever is easier to handle.

---

## 🔸 Example

Evaluate:

$\displaystyle \lim_{x \to 0^+} x^x$

Rewrite using the trick:

$x^x = e^{x \ln(x)}$

Focus on the exponent:

$\displaystyle \lim_{x \to 0^+} x \ln(x)$

This is an indeterminate form $0 \times (-\infty)$.

Rewrite as:

$\displaystyle \lim_{x \to 0^+} \frac{\ln(x)}{1/x}$

Apply L’Hospital’s Rule:

$\displaystyle \lim_{x \to 0^+} \frac{\frac{1}{x}}{-\frac{1}{x^2}} = \lim_{x \to 0^+} -x = 0$

So the original limit is:

$\displaystyle \lim_{x \to 0^+} x^x = e^0 = 1$

---
