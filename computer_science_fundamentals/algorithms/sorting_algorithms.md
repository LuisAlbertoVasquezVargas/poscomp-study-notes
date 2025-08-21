<!-- File: computer_science_fundamentals/algorithms/sorting_algorithms.md -->

# 🧩 Sorting Algorithms — Notes

---

## ✅ Overview

**Sorting algorithms** arrange elements of a list or array into a specific order, typically ascending or descending. They are fundamental for searching, data organization, and optimization.

Key factors to compare sorting algorithms:

* **Time complexity** (best, average, worst cases)
* **Space complexity**
* **Stability** (preserve order of equal elements)
* **Adaptivity** (benefit from existing order)

---

## 🔍 Common Comparison-Based Sorting Algorithms

### 1. **Selection Sort**

* **Idea:** Repeatedly selects the smallest element from the **unsorted part** and moves it to the **sorted part**.
* **Steps:**

  1. Find the smallest element in the unsorted portion.
  2. Swap it with the first unsorted element.
  3. Repeat until only one element remains.
* **Complexity:**

  * Best, Average, Worst: **O(n²)**
* **Space:** **O(1)** (in-place)
* **Stable:** ❌ No
* **Adaptive:** ❌ No
* **Pseudocode:**

  ```
  for i ← 0 to n-2:
      min_index ← i
      for j ← i+1 to n-1:
          if A[j] < A[min_index]:
              min_index ← j
      swap A[i] with A[min_index]
  ```

---

### 2. **Bubble Sort**

* **Idea:** Repeatedly compares adjacent elements and swaps them if they are in the wrong order. The largest element **bubbles up** to the end in each pass.
* **Steps:**

  1. Compare adjacent elements.
  2. Swap if out of order.
  3. After each pass, the largest element is in its correct position.
* **Complexity:**

  * Best: **O(n)** (if optimized with early stop)
  * Average, Worst: **O(n²)**
* **Space:** **O(1)** (in-place)
* **Stable:** ✅ Yes
* **Adaptive:** ✅ Yes (with early stop optimization)
* **Pseudocode:**

  ```
  for i ← 0 to n-2:
      swapped ← false
      for j ← 0 to n-2-i:
          if A[j] > A[j+1]:
              swap A[j], A[j+1]
              swapped ← true
      if not swapped:
          break
  ```

---

### 3. **Insertion Sort**

* **Idea:** Builds the sorted list incrementally by inserting each element into its correct position among previously sorted elements.
* **Steps:**

  1. Start with the second element; assume the first is sorted.
  2. Compare the current element with those in the sorted portion.
  3. Insert it in the correct position by shifting elements.
* **Complexity:**

  * Best: **O(n)** (already sorted)
  * Average, Worst: **O(n²)**
* **Space:** **O(1)** (in-place)
* **Stable:** ✅ Yes
* **Adaptive:** ✅ Yes
* **Pseudocode:**

  ```
  for i ← 1 to n-1:
      key ← A[i]
      j ← i - 1
      while j ≥ 0 and A[j] > key:
          A[j+1] ← A[j]
          j ← j - 1
      A[j+1] ← key
  ```

---

## ✅ Characteristics Summary Table

| Algorithm      | Time (Best) | Time (Worst) | Space | Stable | Adaptive |
| -------------- | ----------- | ------------ | ----- | ------ | -------- |
| Selection Sort | O(n²)       | O(n²)        | O(1)  | No     | No       |
| Bubble Sort    | O(n)        | O(n²)        | O(1)  | Yes    | Yes      |
| Insertion Sort | O(n)        | O(n²)        | O(1)  | Yes    | Yes      |

---

## 🔗 Related Algorithms

* **Shellsort:** Improves insertion sort using gap sequences.
* **Quicksort:** Divide-and-conquer with pivot-based partitioning.
* **Heapsort:** Uses a binary heap to efficiently extract max/min.
* **Merge Sort:** Divide-and-conquer using merging of sorted sublists.

---

