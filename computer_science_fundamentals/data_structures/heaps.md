<!-- File: computer_science_fundamentals/data_structures/heaps.md -->

# Heaps

## 1. Overview

A **heap** is a specialized tree-based data structure that satisfies the **heap property**:

- **Max-heap**: Every parent node’s key is **greater than or equal to** its children’s keys.
- **Min-heap**: Every parent node’s key is **less than or equal to** its children’s keys.

Heaps are commonly implemented as **arrays** for efficient storage.

---

## 2. Characteristics

- **Shape property**: Complete binary tree — all levels are full except possibly the last, which is filled from left to right.
- **Heap property**: Defined as max-heap or min-heap.
- **Index relationships** (array-based, 0-indexed):
  - Parent: `(i - 1) // 2`
  - Left child: `2*i + 1`
  - Right child: `2*i + 2`

---

## 3. Operations

| Operation        | Complexity |
|------------------|------------|
| Find max/min     | O(1)       |
| Insert           | O(log n)   |
| Extract max/min  | O(log n)   |
| Build heap       | O(n)       |

---

## 4. Applications

- **Priority queues**.
- **Heapsort** (O(n log n) sorting algorithm).
- Graph algorithms: Dijkstra’s and Prim’s.

---

## 5. POSCOMP Tips

- **Heap ≠ BST**: The heap property is only about parent-child relationships, not an inorder ordering of all nodes.
- Array representation is favored for efficiency and simplicity.
- Building a heap from an unsorted array is **O(n)**, not O(n log n).

---
