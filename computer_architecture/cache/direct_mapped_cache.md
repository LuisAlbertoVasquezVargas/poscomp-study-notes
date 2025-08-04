<!-- File: computer_architecture/direct_mapped_cache.md -->

# The Direct-Mapped Cache

This document provides a comprehensive and self-contained model for a direct-mapped cache. It covers the logical principles, address partitioning, internal structure, and operational logic, incorporating key distinctions between the idealized model and physical reality.

> ⚠️ **Important Convention**: Unless otherwise stated, **cache size** and **main memory size** refer only to the **data capacity** — *excluding* metadata like tag and valid bits. That is, they represent the **payload**, not the full hardware footprint.

---

## 1. Core Principles and Parameters

A **direct-mapped cache** maps each block of main memory to **exactly one** cache line based on the address.

To define this system, we use:

- `M`: number of **bits** in a memory address  
- `C`: **cache size**, in bytes (data only)  
- `B`: **block size**, in bytes (data per line)  

Each cache line stores exactly one full memory block.

---

## 2. Address Partitioning

Each memory address is split into three fields:

- **Offset**: selects a byte within the block  
  `O = log2(B)`
- **Index**: selects the cache line  
  `I = log2(C / B)`
- **Tag**: identifies which memory block is stored  
  `T = M - I - O`

**Address layout:**

```plaintext
|  Tag (T bits)  |  Index (I bits)  |  Offset (O bits)  |
````

---

## 3. Worked Example

Assume the following configuration:

* `M = 12` bits
* `C = 64` bytes
* `B = 8` bytes

Derived values:

* `O = log2(8) = 3` bits
* `I = log2(64 / 8) = log2(8) = 3` bits
* `T = 12 - 3 - 3 = 6` bits

So the memory address splits as:

```plaintext
|  Tag: 6 bits  |  Index: 3 bits  |  Offset: 3 bits  |
```

---

## 4. Cache Structure (Cold Start)

Each cache line stores:

1. **Valid Bit** (1 bit)
2. **Tag Field** (6 bits)
3. **Data Field** (8 bytes = 64 bits)

### Initial Cache Table

| Index | Valid | Tag (6 bits) | Data (8 bytes)        |
| ----- | ----- | ------------ | --------------------- |
| `000` | 0     | ???          | \[byte 0]...\[byte 7] |
| `001` | 0     | ???          | \[byte 0]...\[byte 7] |
| `010` | 0     | ???          | \[byte 0]...\[byte 7] |
| `011` | 0     | ???          | \[byte 0]...\[byte 7] |
| `100` | 0     | ???          | \[byte 0]...\[byte 7] |
| `101` | 0     | ???          | \[byte 0]...\[byte 7] |
| `110` | 0     | ???          | \[byte 0]...\[byte 7] |
| `111` | 0     | ???          | \[byte 0]...\[byte 7] |

---

## 5. Example Accesses

### Access 1: `0x5C2` (binary `0101 1100 0010`)

* Offset: `010` → byte 2 within block
* Index:  `000` → cache line 0
* Tag:    `010111`

**Miss:**

* Valid bit at line 0 is `0`
* Fetch block `0x5C0–0x5C7` from main memory
* Store block in line 0, set:

  * Valid = `1`
  * Tag = `010111`

---

### Access 2: `0x5C4` (binary `0101 1100 0100`)

* Offset: `100`
* Index:  `000`
* Tag:    `010111`

**Hit:**

* Valid bit = `1`
* Tag matches → read byte 4 from data field

---

## 6. Memory Mapping to Cache

```plaintext
Main Memory Block     →    Cache Line

Block 0               →    Line 0   (Block 0, 8, 16, ...)
Block 1               →    Line 1   (Block 1, 9, 17, ...)
Block 2               →    Line 2   (Block 2, 10, 18, ...)
Block 3               →    Line 3   (...)
Block 4               →    Line 4
...
```

Each memory block maps using:

```plaintext
Line = (Block Number) mod (Number of Cache Lines)
```

---

## 7. Physical vs Logical Size

### Logical Cache Size

This is the **data-only** size:
e.g., 8 lines × 8 bytes = `64 bytes`

### Physical Cache Size

We must also include metadata:

* Valid bit: 1 per line
* Tag field: T bits per line

**Example line contents:**

* Data: 8 bytes = 64 bits
* Tag: 6 bits
* Valid: 1 bit

Total per line = 71 bits
Total cache: `8 × 71 = 568 bits ≈ 71 bytes`

---

## 8. Summary Formula Reference

```plaintext
O = log2(B)
I = log2(C / B)
T = M - I - O
```

**Memory address layout:**

```plaintext
|  Tag (T bits)  |  Index (I bits)  |  Offset (O bits)  |
```

**Each cache line contains:**

```plaintext
|  Valid (1 bit)  |  Tag (T bits)  |  Data (B bytes)  |
```

---
