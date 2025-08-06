<!-- File: computer_architecture/twos_complement.md -->

# ➕ Two's Complement Representation and Operations

This section covers the two's complement system for representing signed integers in binary, along with its operations and theoretical foundation in digital systems.

---

## 🧩 What is Two's Complement?

Two's complement is the standard method for representing **signed integers** in binary within digital systems. It allows addition, subtraction, and comparison to be performed using the same circuitry as for unsigned binary arithmetic.

In an `n`-bit system:
- Non-negative integers are represented identically to their binary (unsigned) form.
- Negative integers are encoded so that addition and subtraction work modulo `2ⁿ`.

---

## 🧮 Definition of Two's Complement (ca₂)

Let `n` be the number of bits. The two's complement representation function is defined as:

> Given an integer `x` in the range `−2^(n−1) ≤ x ≤ 2^(n−1) − 1`, then:

```

ca₂(x) = {
x,                       if x ≥ 0
invert(|x|) + 1,         if x < 0
}

```

Where:
- `invert(b)` flips all bits of the binary representation `b`.
- The addition `+1` is performed modulo `2ⁿ`.
- This encoding ensures correct representation of negative numbers in the `n`-bit binary space.

---

## 🤔 Relation to Programming Language Negation

In programming languages with two's complement integers (like C, C++, Python):

- The unary negation operator `-x` **already produces** the two's complement encoding of `-x`.
- Internally, the CPU implements `-x` as `invert(bin(x)) + 1`.
- Therefore, the **programming trick** to get the two's complement is:

```

ca₂(−x) ≡ -x

```

in the sense that the bit pattern stored for `-x` matches `invert(|x|) + 1`.

**Note:** Do **not** confuse this with the arithmetic expression `(-x) + 1`, which is not correct for encoding two's complement.

---

## ✅ Key Identity: x + ca₂(−x) = 2ⁿ (for nonzero x)

For all integers `x` with `1 ≤ |x| ≤ 2^(n−1)`, the two's complement satisfies:

```

x + ca₂(−x) = 2ⁿ

```

This means that for every nonzero integer `x`, the two's complement of `−x` is the unique value that, when added to `x`, yields zero modulo `2ⁿ`.

**Special case:** For `x = 0`,

```

0 + ca₂(−0) = 0 + 0 = 0 ≠ 2ⁿ

```

However, zero is its own additive inverse modulo `2ⁿ`, so it "passes" the modular arithmetic sense of being an inverse but does not satisfy the sum equaling `2ⁿ`.

---

## 📏 Range of Representable Integers

In an `n`-bit two's complement system, the representable integer range is:

```

−2^(n−1) to 2^(n−1) − 1

```

For example, in 8 bits:
- Minimum: −128 (`10000000`)
- Maximum: +127 (`01111111`)

---

## ➕ Addition and Subtraction

Two's complement allows **binary addition** to work uniformly:
- `x + y` is computed modulo `2ⁿ`.
- Subtraction is implemented as `x − y = x + ca₂(−y)`.

Example:
```

0100 (4)

* 1111 (−1)
  \= 0011 (3)

````

Overflow detection happens when two operands with the same sign produce a result with a different sign.

---

## 💻 Implementation Examples

### C-style example (8-bit signed integers)
```c
#include <stdint.h>
#include <stdio.h>

int main() {
    int8_t a = 5;
    int8_t neg_a = -a; // negation is implemented as invert + 1 internally
    printf("a = %d, binary: 0x%02X\n", a, (uint8_t)a);
    printf("-a = %d, binary: 0x%02X\n", neg_a, (uint8_t)neg_a);
    return 0;
}
````

**Expected output:**

```
a = 5, binary: 0x05
-a = -5, binary: 0xFB
```

---

### Python example (manual 8-bit two's complement)

```python
def ca2(x, n=8):
    mod = 1 << n
    if x >= 0:
        return x
    else:
        return (~(-x) + 1) & (mod - 1)

for x in [5, -5, 0]:
    print(f"{x}: two's complement = {ca2(x,8):08b}")
```

**Expected output:**

```
5: two's complement = 00000101
-5: two's complement = 11111011
0: two's complement = 00000000
```

---

## 📋 Summary Table

| Decimal | 8-bit Binary | Two’s Complement (ca₂) |
| ------- | ------------ | ---------------------- |
| +0      | 00000000     | 00000000               |
| +1      | 00000001     | 00000001               |
| +5      | 00000101     | 00000101               |
| −1      |              | 11111111               |
| −5      |              | 11111011               |
| −128    |              | 10000000               |
| +127    | 01111111     | 01111111               |

---

## 🧠 Properties

* `ca₂(x) = x` for all `x ≥ 0`
* `ca₂(−x) = invert(bin(x)) + 1`
* `−x` in programming languages corresponds to the two's complement encoding of `-x`
* Arithmetic works modulo `2ⁿ`
* Unique representation of zero
* `−(−x) = x` modulo `2ⁿ`

