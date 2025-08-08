<!-- File: digital_logic/multiplexer.md -->

# 🔀 Multiplexer (MUX)

A **multiplexer** is a combinational circuit that selects one input from multiple inputs and forwards it to a single output line based on control signals.

---

## 🧩 Definition

- A multiplexer routes one of `2^n` input lines to a single output line.
- The input selected depends on `n` **select lines**.
- Sometimes called a **data selector**.

---

## ⚙️ Structure

- Inputs: `2^n` data inputs (D0, D1, ..., D_(2^n−1))
- Select lines: `n` control bits (S0, S1, ..., S_(n−1))
- Output: single output `Y`

---

## 🧮 Function

The output `Y` equals the data input selected by the binary number on the select lines:

```

Y = D\_S

```

where `S` is the integer value represented by the select lines.

---

## 📐 Example: 4-to-1 Multiplexer

- Inputs: D0, D1, D2, D3
- Select lines: S1, S0 (2 bits)
- Output: Y

| S1 | S0 | Selected Input | Output Y |
|----|----|----------------|----------|
| 0  | 0  | D0             | D0       |
| 0  | 1  | D1             | D1       |
| 1  | 0  | D2             | D2       |
| 1  | 1  | D3             | D3       |

---

## 🛠️ Boolean Expression

For a 4-to-1 MUX:

```

Y = (¬S1 · ¬S0 · D0) + (¬S1 · S0 · D1) + (S1 · ¬S0 · D2) + (S1 · S0 · D3)

```

---

## 🔧 Applications

- Data routing and selection
- Implementing logic functions
- Resource sharing in hardware
- Building arithmetic circuits

---

## 📌 Summary

| Parameter         | Description                  |
|-------------------|------------------------------|
| Data Inputs       | `2^n` inputs                 |
| Select Lines      | `n` control bits             |
| Output            | Single line                  |
| Function          | Routes selected input to output |

---

