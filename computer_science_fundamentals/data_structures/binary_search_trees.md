<!-- File: computer_science_fundamentals/data_structures/binary_search_trees.md -->

# Binary Search Trees (BST)

## 1. Overview

A **Binary Search Tree (BST)** is a binary tree data structure where each node contains a **key** and satisfies the **BST property**:

- For every node:
  - Keys in the **left subtree** are **less than** the node’s key.
  - Keys in the **right subtree** are **greater than** the node’s key.

This property allows **efficient search, insertion, and deletion** in average **O(log n)** time.

---

## 2. Basic Operations

### 2.1 Search
- Compare the target key with the current node:
  - If equal → found.
  - If smaller → search left subtree.
  - If larger → search right subtree.
- **Complexity**:  
  - Average case: O(log n) (balanced tree).  
  - Worst case: O(n) (degenerate tree).

### 2.2 Insertion
1. Search for the correct position following the BST property.
2. Insert the new node as a leaf.
3. No balancing is done in plain BST.

### 2.3 Deletion
Three cases:
1. **Node is a leaf** → Remove it directly.
2. **Node has one child** → Replace the node with its child.
3. **Node has two children** → Replace the node with its **inorder successor** (smallest key in right subtree) or **inorder predecessor** (largest key in left subtree).

---

## 3. Traversals

- **Inorder (LNR)**: Left → Node → Right → Produces sorted keys.
- **Preorder (NLR)**: Node → Left → Right.
- **Postorder (LRN)**: Left → Right → Node.

---

## 4. Limitations

- **Degeneration**: If keys are inserted in sorted order, the tree becomes a linked list, degrading performance to O(n).
- **Solution**: Use **self-balancing BSTs** like AVL trees, Red-Black trees, or Splay trees.

---

## 5. POSCOMP Tips

- BST property ensures **inorder traversal** outputs a sorted sequence.
- Be ready to compute height, number of comparisons, and perform a manual insertion/deletion.
- For balanced BSTs, operations are O(log n); for skewed BSTs, worst case is O(n).

---
