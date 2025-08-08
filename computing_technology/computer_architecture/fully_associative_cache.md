<!-- File: computer_architecture/fully_associative_cache.md -->

# The Fully Associative Cache

This document presents a clean and detailed model of the **fully associative cache**. It explains how memory blocks can be stored *anywhere* in the cache, the logic of searching and replacement, and contrasts it with direct mapping.

> ⚠️ **Important Convention**: Unless otherwise stated, **cache size** and **main memory size** refer only to the **data capacity** — *excluding* metadata like tags or valid bits.

---

## 1. Core Principles and Parameters

In a **fully associative cache**, **any** memory block can be placed in **any** cache line — no fixed mapping based on the address.

We define:

* `M`: number of **bits** in a memory address
* `C`: **cache size**, in bytes (data only)
* `B`: **block size**, in bytes

From this, we compute:

* `N = C / B`: number of cache lines
* `O = log2(B)`: offset bits
* `T = M - O`: tag bits (no index field)

---

## 2. Address Partitioning

The address is split into:

* **Offset**: selects the byte inside the block → `O = log2(B)`
* **Tag**: identifies the memory block → `T = M - O`

```plaintext
|         Tag (T bits)         |   Offset (O bits)   |
```

There’s no index: to determine if a block is present, the system must **search all valid lines** for a matching tag.

---

## 3. Example Setup

Assume:

* `M = 12` bits
* `C = 64` bytes
* `B = 8` bytes

Then:

* `N = 64 / 8 = 8` lines
* `O = log2(8) = 3` bits
* `T = 12 - 3 = 9` bits

Address layout:

```plaintext
|  Tag: 9 bits  |  Offset: 3 bits  |
```

---

## 4. Cache Structure (Cold Start)

Each line stores:

1. **Valid Bit** (1 bit)
2. **Tag Field** (9 bits)
3. **Data Field** (8 bytes)

### Initial Cache Table

| Line | Valid | Tag (9 bits) | Data (8 bytes)        |
| ---- | ----- | ------------ | --------------------- |
| 0    | 0     | ???          | \[byte 0]...\[byte 7] |
| 1    | 0     | ???          | \[byte 0]...\[byte 7] |
| 2    | 0     | ???          | \[byte 0]...\[byte 7] |
| ...  | ...   | ...          | ...                   |
| 7    | 0     | ???          | \[byte 0]...\[byte 7] |

---

## 5. Example Access

### Access: `0x5C2` (binary `0101 1100 0010`)

* Offset = `010` (byte 2)
* Tag = `010111000` (first 9 bits)

Search the **entire cache** for a valid line with tag `010111000`.

* If **found** → HIT → read byte 2
* If **not found** → MISS:

  * Choose a line (e.g. first empty, or via LRU policy)
  * Store block `0x5C0–0x5C7`
  * Set:

    * Valid = `1`
    * Tag = `010111000`

---

## 6. Replacement Policy

On a miss and a **full cache**, we must **evict** a block.

Common strategies:

* **Random**
* **FIFO** (first-in, first-out)
* **LRU** (least recently used) — most realistic but costly
* **LFU** (least frequently used)

Associative caches require **hardware support** for these policies.

---

## 7. Memory Mapping to Cache

There is **no fixed mapping**:

```plaintext
Any memory block → Any cache line
```

This gives **maximum flexibility**, but also **maximum search cost** (linear or parallel).

---

## 8. Physical vs Logical Size

### Logical Cache Size

Just the **data blocks**:
e.g., 8 lines × 8 bytes = `64 bytes`

### Physical Cache Size

We must include metadata:

* Valid bit: 1 per line
* Tag: 9 bits per line

Per line:

* Data: 8 bytes = 64 bits
* Tag: 9 bits
* Valid: 1 bit
  **Total = 74 bits per line**
  Total cache = `8 × 74 = 592 bits ≈ 74 bytes`

---

## 9. Summary Formula Reference

```plaintext
O = log2(B)
T = M - O
N = C / B
```

**Address layout:**

```plaintext
|  Tag (T bits)  |  Offset (O bits)  |
```

**Each cache line contains:**

```plaintext
|  Valid (1 bit)  |  Tag (T bits)  |  Data (B bytes)  |
```
