<!-- File: networking/bit_length.md -->

# Bit Length in Data Transmission

## Concept

The **length of a bit** in a communication channel is the physical distance that one bit occupies on the transmission medium at any given moment.

---

## Formula for Bit Length

Given:

- Propagation velocity in the medium: **c** (e.g., speed of light in vacuum)
- Transmission rate: **b** bits per second

The time to transmit one bit is:

- **Time per bit** = 1 / b seconds

Therefore, the length of one bit is:

- **Bit length** = propagation velocity × time per bit = c / b

---

## Important Notes

- The packet size (in bytes) and channel length do **not** affect the bit length.
- Bit length depends solely on the propagation speed of the signal and the bit transmission rate.
- This metric is useful for understanding concepts like the **bandwidth-delay product** and for designing protocols sensitive to transmission delays.

---

## Summary

| Parameter           | Symbol | Unit          |
|---------------------|--------|---------------|
| Propagation velocity | c      | meters/second |
| Bit rate            | b      | bits/second   |
| Bit length          | c/b    | meters        |

---
