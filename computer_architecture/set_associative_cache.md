<!-- File: computer_architecture/set_associative_cache.md -->

# The Set-Associative Cache

This document models the behavior and structure of a **set-associative cache**. It describes address partitioning, tag matching, replacement policies, and contrasts it with direct and fully associative caches.

> ⚠️ **Important Convention**: Unless otherwise stated, **cache size** and **main memory size** refer only to the **data capacity** — *excluding* metadata like tags, valid bits, or replacement bits.

---

## 1. Core Principles and Parameters

In a **set-associative cache**, each block of main memory maps to a **specific set**, but can be stored in **any line within that set**. It generalizes direct-mapped (1-way) and fully associative (N-way) caches.

We define:

- `M`: number of **bits** in a memory address  
- `C`: **cache size**, in bytes (data only)  
- `B`: **block size**, in bytes  
- `E`: number of **lines per set** (associativity)  

From this:

- `S = C / (B × E)`: number of sets  
- `O = log2(B)`: number of **offset bits**  
- `D = log2(S)`: number of **set index bits**  
- `T = M - D - O`: number of **tag bits**

---

## 2. Address Partitioning

Each memory address is split into:

- **Offset**: selects a byte within the block → `O = log2(B)`
- **Set index**: selects a set → `D = log2(S)`
- **Tag**: identifies which block is stored → `T = M - D - O`

**Address layout:**

```plaintext
|    Tag (T bits)   |  Set Index (D bits)  |  Offset (O bits)  |
````

---

## 3. Example Configuration

Assume:

* `M = 19` bits
* `C = 1024` bytes
* `B = 64` bytes
* `E = 4` (4-way set-associative)

Derived values:

* `S = 1024 / (64 × 4) = 4 sets`
* `O = log2(64) = 6` bits
* `D = log2(4) = 2` bits
* `T = 19 - 2 - 6 = 11` bits

**Address layout:**

```plaintext
|  Tag: 11 bits  |  Set Index: 2 bits  |  Offset: 6 bits  |
```

---

## 4. Cache Structure (Cold Start)

Each **set** contains `E` lines, each line has:

1. **Valid Bit** (1 bit)
2. **Tag Field** (T bits)
3. **Data Field** (B bytes)

### Set Table Example (Set 0)

| Line | Valid | Tag (11 bits) | Data (64 bytes)        |
| ---- | ----- | ------------- | ---------------------- |
| 0    | 0     | ???           | \[byte 0]...\[byte 63] |
| 1    | 0     | ???           | \[byte 0]...\[byte 63] |
| 2    | 0     | ???           | \[byte 0]...\[byte 63] |
| 3    | 0     | ???           | \[byte 0]...\[byte 63] |

---

## 5. Example Access

### Address: `0x52C8` (binary `0101 0010 1100 1000`)

Assuming the address splits as:

* Offset: last 6 bits
* Set Index: next 2 bits
* Tag: remaining bits

Breakdown:

* Offset: `001000` → byte 8 in block
* Set Index: `11` (set 3)
* Tag: `01010010100`

**Lookup:**

* Search all 4 lines in set 3:

  * If **valid bit = 1** and **tag matches** → **HIT**
  * Otherwise → **MISS**

On a miss, load block from memory into one of the lines in set 3 (e.g. first empty or LRU), and store:

* Valid = `1`
* Tag = `01010010100`
* Block data

---

## 6. Replacement Policies

If all lines in a set are valid, a **replacement policy** decides which line to evict:

* **Random** — simple, low hardware cost
* **FIFO** — evict the oldest inserted block
* **LRU** — evict the least recently used block
* **LFU** — evict the least frequently used

Associative caches require per-set tracking for these policies.

---

## 7. Memory Mapping to Sets

Each **block in memory** maps to a **single set**:

```plaintext
Set = (Block Number) mod (Number of Sets)
```

But within the set, it may be stored in **any line**.

Example:

```plaintext
Main Memory Block → Set

Block 0           → Set 0
Block 1           → Set 1
...
Block 4           → Set 0  (4 mod 4 = 0)
Block 5           → Set 1
```

---

## 8. Physical vs Logical Size

### Logical Size

Data-only size:

```plaintext
C = S × E × B
```

### Physical Size (with metadata)

Each line has:

* Valid bit: 1 bit
* Tag field: T bits
* Data: B bytes = 8B → 64 bits (for example)

Per line: `1 + T + (8 × B)` bits
Per set: `E × (1 + T + 8B)` bits
Total: `S × E × (1 + T + 8B)` bits

---

## 9. Summary Formula Reference

```plaintext
S = C / (B × E)
O = log2(B)
D = log2(S)
T = M - D - O
```

**Memory address layout:**

```plaintext
|  Tag (T bits)  |  Set Index (D bits)  |  Offset (O bits)  |
```

**Each cache line contains:**

```plaintext
|  Valid (1 bit)  |  Tag (T bits)  |  Data (B bytes)  |
```

**Mapping rule:**

```plaintext
Set = (Block Number) mod (Number of Sets)
```


https://www.youtube.com/watch?v=gr5M9CULUZw