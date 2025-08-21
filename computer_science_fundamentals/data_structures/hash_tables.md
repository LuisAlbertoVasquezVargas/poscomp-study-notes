<!-- File: computer_science_fundamentals/data_structures/hash_tables.md -->

# 🧩 Hash Tables

---

## 1. Overview

A **hash table** is a data structure that stores **key–value pairs** and provides efficient operations for:

* **Insertion**
* **Search**
* **Deletion**

Average time complexity is **O(1)**, assuming a good hash function and low load factor.

### Core Idea:

1. Compute an **index** using a **hash function** $h(k)$.
2. Place the key–value pair in the corresponding position in an **array**.
3. Handle **collisions** when two keys map to the same index.

---

## 2. Hash Function

A **hash function** $h(k)$ maps a key $k$ to an integer index in the range:

$$
0 \leq h(k) < m
$$

where $m$ is the table size.

### ✅ Good properties:

* Uniform distribution of keys.
* Low computational cost.
* Minimal collisions.

### ✅ Common methods:

* **Division method**:

  $$
  h(k) = k \bmod m
  $$

  (choose $m$ as a prime number far from powers of 2).

* **Multiplication method**:

  $$
  h(k) = \lfloor m \cdot ((k \cdot A) \bmod 1) \rfloor, \quad 0 < A < 1
  $$

---

## 3. Collision Resolution

When two keys hash to the same index (**collision**), use one of the following strategies:

### 3.1 **Chaining (Separate Chaining)**

* Each index holds a **linked list** (or dynamic array) of all elements that hash to that index.
* **Advantages**:

  * Easy to implement.
  * Allows more elements than $m$.
* **Disadvantages**:

  * Extra memory for pointers.
  * Performance may degrade if chains are long.

### 3.2 **Open Addressing**

* All elements are stored **inside the table**.
* On collision, probe for the next available position.

**Common probing strategies**:

* **Linear probing**:

  $$
  (h(k) + i) \bmod m
  $$
* **Quadratic probing**:

  $$
  (h(k) + c_1 i + c_2 i^2) \bmod m
  $$
* **Double hashing**:

  $$
  (h_1(k) + i \cdot h_2(k)) \bmod m
  $$

---

## 4. Load Factor

The **load factor** $\alpha$ is defined as:

$$
\alpha = \frac{n}{m}
$$

where:

* $n$ = number of elements stored
* $m$ = table size

A higher load factor increases the likelihood of collisions.
Most implementations **rehash** (resize the table) when $\alpha$ exceeds a threshold (e.g., 0.75).

---

## 5. Special Concepts

### ✅ Perfect Hashing

* A hash function with **no collisions**.
* **Minimal Perfect Hashing**:

  * Occurs when:

    $$
    m = n
    $$
  * No empty slots.
  * All lookups require **one access**.

### ✅ Linear Hashing

* A **dynamic hashing** method that gradually grows or shrinks the table to maintain an acceptable load factor.
* Does **not** relate to lexicographical ordering or single-access lookups.

---
