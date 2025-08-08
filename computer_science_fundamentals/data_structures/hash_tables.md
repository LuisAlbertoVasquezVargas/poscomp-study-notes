<!-- File: computer_science_fundamentals/data_structures/hash_tables.md -->

# Hash Tables

## 1. Overview

A **hash table** is a data structure that stores key–value pairs and allows efficient **insertion**, **search**, and **deletion** operations, typically in **O(1)** average time.

The main idea:
1. Use a **hash function** to map a key to an **index** in an array.
2. Store the key–value pair at that index.
3. Handle collisions when multiple keys map to the same index.

---

## 2. Hash Function

- **Definition**: A function `h(k)` that maps a key `k` to an index in `[0, m-1]` (where `m` is the table size).
- **Good properties**:
  - Uniform distribution of keys.
  - Low computation cost.
  - Minimizes collisions.

### Common methods:
- **Division method**: `h(k) = k mod m` (choose `m` as a prime not too close to a power of 2).
- **Multiplication method**: `h(k) = ⌊ m * ( (k * A) mod 1 ) ⌋`, where `0 < A < 1`.

---

## 3. Collision Resolution

### 3.1 Chaining
- Each table index holds a linked list (or dynamic array) of entries with the same hash.
- **Advantages**:
  - Simple to implement.
  - Table can store more elements than its size `m`.
- **Disadvantages**:
  - Extra memory for pointers.
  - Performance degrades if chains grow long.

### 3.2 Open Addressing
- All elements are stored directly in the table.
- On collision, probe other positions until an empty slot is found.

**Common probing methods**:
1. **Linear probing**: Check `(h(k) + i) mod m`.
   - Simple but may cause clustering.
2. **Quadratic probing**: Check `(h(k) + c₁i + c₂i²) mod m`.
   - Reduces clustering.
3. **Double hashing**: Check `(h₁(k) + i * h₂(k)) mod m`.
   - Requires a second hash function.

---

## 4. Load Factor

- **Definition**: `α = n / m`
  - `n` = number of stored elements.
  - `m` = table size.
- A higher load factor increases the likelihood of collisions.
- Many implementations resize (rehash) when `α` exceeds a threshold (e.g., 0.75).

---

## 5. POSCOMP Tips

- **Average-case complexity**:
  - Search, insert, delete: O(1) when the load factor is small.
- **Worst-case complexity**:
  - O(n) when all keys collide (poor hash function or high load factor).
- **Differences from other structures**:
  - Unordered — no natural order of keys.
  - Trade-off: speed vs. memory.

---

