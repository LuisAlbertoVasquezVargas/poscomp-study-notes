<!-- File: mathematics/calculus/taylor_maclaurin_sqrt.md -->

# Taylor and Maclaurin Series — √n Approximation

---

## Taylor / Maclaurin Series

For a function `f(x)` infinitely differentiable at `x = a`:

```

f(x) ≈ f(a) + f'(a)(x-a) + f''(a)/2!·(x-a)^2 + f'''(a)/3!·(x-a)^3 + …

```

Maclaurin series is the special case `a = 0`.

---

## Square Root Approximation

To approximate √n:

1. Choose nearest perfect square `m²` such that n ≈ m²  
2. Write `n = m² + h`  
3. Use the expansion:

```

√(m² + h) ≈ m + h/(2m) − h²/(8 m³) + h³/(16 m^5) − …

```

- 2 terms: `m + h/(2m)` (quick estimate)  
- 3–4 terms: more precise  

---

## Example: √5

- m = 2, h = 1 → 5 = 2² + 1  

| Terms | Approximation  | Absolute error | Relative error % |
|-------|----------------|----------------|----------------|
| 2     | 2.25           | 0.013932       | 0.622%         |
| 3     | 2.234375       | −0.001693      | 0.076%         |
| 4     | 2.236328125    | 0.000260       | 0.012%         |

✅ Observations:

- 2 terms: rough estimate, good for multiple-choice  
- 3–4 terms: highly accurate  
- Method generalizes for √n near any perfect square

---
