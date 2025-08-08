<!-- File: computer_science_fundamentals/databases/b_trees.md -->

# B-Trees and B* Trees

## 1. Overview

B-Trees and B* Trees are balanced multiway search trees widely used in **database systems** and **filesystems** to store and retrieve large amounts of data efficiently, especially when disk access is involved.

---

## 2. B-Trees

### Characteristics
- **Balanced**: All leaf nodes are at the same depth.
- **Order (m)**: Maximum number of children a node can have.
- **Node keys**: A node can have at most `m - 1` keys and at least `⌈m/2⌉ - 1` keys (except the root).
- **Search**: Works like binary search within a node, but each pointer leads to a subtree containing keys in a specific range.

### Operations
1. **Search**
   - Binary search inside the current node.
   - Follow the corresponding pointer if the key is not found.
   - O(logₘ n) complexity.
2. **Insertion**
   - Insert key into a leaf in sorted order.
   - If overflow occurs (more than `m - 1` keys), split the node and promote the median to the parent.
3. **Deletion**
   - Remove the key.
   - If underflow occurs (less than `⌈m/2⌉ - 1` keys), **borrow** from a sibling or **merge** nodes.

---

## 3. B* Trees

### Differences from B-Trees
- **Higher space utilization**: At least 2/3 full (vs. 1/2 for B-Trees).
- **Node splitting strategy**: Instead of splitting immediately on overflow, a B* Tree redistributes keys with a sibling.
  - Only if both the node and its sibling are full does a split occur.
- This results in fewer splits and more efficient use of space.

### Advantages
- Better disk access efficiency due to higher node fill factor.
- Reduced height compared to equivalent B-Trees.

---

## 4. POSCOMP Tips

- **Complexity**: Both B-Trees and B* Trees maintain **O(log n)** search, insertion, and deletion.
- **Difference from Binary Search Trees**:
  - Nodes can contain multiple keys.
  - Balanced by design — no need for rebalancing rotations like AVL or Red-Black Trees.
- **B+ Tree** (often confused in questions):
  - All keys are stored in leaves; internal nodes only store routing keys.
  - Leaves are linked for efficient range queries.

---

## 5. Visual Example (Order m = 4)

```

\[ 10 | 20 | 30 ]
/    |     |   &#x20;
<10  10–20  20–30 >30

```


