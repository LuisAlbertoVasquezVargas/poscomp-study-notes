<!-- File: computing_technology/digital_logic/logic_gates.md -->

# Logic Gates

Logic gates are the basic building blocks of digital circuits. Each gate implements a Boolean function, mapping input bits to an output bit.

---

## 1. AND Gate

- **Symbol**: shaped like a **reflexed uppercase D**.  
- **Mnemonic**: think of "anD" → looks like a D.  
- **Operation**: output is 1 only if all inputs are 1.  

**Truth Table** (2 inputs):

| A | B | A AND B |
|---|---|---------|
| 0 | 0 |    0    |
| 0 | 1 |    0    |
| 1 | 0 |    0    |
| 1 | 1 |    1    |

---

## 2. OR Gate

- **Symbol**: resembles a **rounded D shape** (concave).  
- **Mnemonic**: "oR" → like a rounded D.  
- **Operation**: output is 1 if at least one input is 1.  

**Truth Table**:

| A | B | A OR B |
|---|---|--------|
| 0 | 0 |   0    |
| 0 | 1 |   1    |
| 1 | 0 |   1    |
| 1 | 1 |   1    |

---

## 3. NAND Gate

- **Definition**: NOT of AND.  
- **Symbol**: AND gate with a small inversion circle (bubble) at the output.  
- **Mnemonic**: "nanD" → same D shape as AND, just inverted.  
- **Operation**: output is 0 only if all inputs are 1.  

**Truth Table**:

| A | B | A NAND B |
|---|---|----------|
| 0 | 0 |    1     |
| 0 | 1 |    1     |
| 1 | 0 |    1     |
| 1 | 1 |    0     |

---

## 4. NOR Gate

- **Definition**: NOT of OR.  
- **Symbol**: OR gate with inversion bubble at the output.  
- **Operation**: output is 1 only if all inputs are 0.  

**Truth Table**:

| A | B | A NOR B |
|---|---|---------|
| 0 | 0 |    1    |
| 0 | 1 |    0    |
| 1 | 0 |    0    |
| 1 | 1 |    0    |

---

## 5. XOR Gate (Exclusive OR)

- **Symbol**: OR gate with an extra curved line at the input.  
- **Operation**: output is 1 if inputs are different.  

**Truth Table**:

| A | B | A XOR B |
|---|---|---------|
| 0 | 0 |    0    |
| 0 | 1 |    1    |
| 1 | 0 |    1    |
| 1 | 1 |    0    |

---

## 6. XNOR Gate (Exclusive NOR)

- **Definition**: NOT of XOR.  
- **Symbol**: XOR gate with inversion bubble at the output.  
- **Operation**: output is 1 if inputs are the same.  

**Truth Table**:

| A | B | A XNOR B |
|---|---|----------|
| 0 | 0 |    1     |
| 0 | 1 |    0     |
| 1 | 0 |    0     |
| 1 | 1 |    1     |

---

# Notes

- **Universal Gates**:  
  - NAND and NOR are universal gates — any Boolean function can be implemented using only NANDs or only NORs.  
- **Shape Mnemonic**:  
  - `anD`, `nanD`: shaped like an uppercase D (reflexed).  
  - `oR`, `noR`: rounded D shape.  
- **Inversion**: the small bubble (`•`) at the output indicates logical NOT.

---
