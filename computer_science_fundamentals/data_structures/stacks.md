<!-- File: computer_science_fundamentals/data_structures/stacks.md -->

# Stacks

## 1. Overview

A **stack** is an abstract data type (ADT) that stores elements in a **Last-In, First-Out (LIFO)** order.

- **Push**: Insert an element at the top.
- **Pop**: Remove the element from the top.
- **Peek/Top**: Access the top element without removing it.

---

## 2. Characteristics

- Only the **top** element is accessible.
- Can be implemented using arrays or linked lists.
- Has a fixed capacity if array-based (unless dynamic resizing is implemented).

---

## 3. Operations

| Operation | Complexity |
|-----------|------------|
| Push      | O(1)       |
| Pop       | O(1)       |
| Peek      | O(1)       |

---

## 4. Applications

- Function call management (call stack).
- Undo/redo in applications.
- Parsing expressions (e.g., infix to postfix conversion).
- Depth-first search (DFS) in graphs.

---

## 5. POSCOMP Tips

- Be comfortable simulating a stack’s push/pop sequence.
- Remember LIFO ordering for tracking operations in algorithm traces.
- Stack overflow occurs when trying to push into a full stack (array-based without resizing).

---
