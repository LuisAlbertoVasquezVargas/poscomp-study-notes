<!-- File: computer_science_fundamentals/filesystems/free_space_management.md -->

# Free Space Management in Filesystems

---

## Definition

Free space management is the task of keeping track of which disk blocks are **free** and which are **allocated**.  
This ensures efficient allocation of blocks for new files, minimizing fragmentation and maintaining consistency.

---

## Methods

### 1. Bitmap (Bit Vector)
- One bit per block: `0 = free`, `1 = allocated`.
- Example: `11100100` → blocks 0,1,2,5 are used.
- ✅ Compact, easy to scan in memory.  
- ❌ May need to search for consecutive free blocks.  
- **Used in ext2/ext3/ext4.**

---

### 2. Linked List
- All free blocks chained together:
```

head → block 6 → block 7 → block 11 → ...

```
- ✅ Simple, no global array needed.  
- ❌ Slow to traverse; extra pointer overhead.  
- Rare in modern filesystems.

---

### 3. Grouping (Linked List of Lists)
- Improvement over linked list:  
Each free block stores **a list of many free block numbers** plus a pointer to the next list block.
- Abstract view: a **linked list of arrays of free block addresses**.
- Logic:
- If block size = `B` bytes, block address = `A` bytes.  
- Each group block can hold about `(B / A) - 1` addresses (one slot reserved for next pointer).  
- Example: 4 KB block, 4 B addresses → ~1023 free addresses per group.
- ✅ Faster allocation than simple linked list.  
- ❌ Some free blocks are temporarily used for metadata lists.  

---

### 4. Counting
- Stores free blocks as runs `(start, length)`.  
- Example: `(6,2), (11,5)` → blocks 6–7 and 11–15 are free.
- ✅ Very compact if disk has large contiguous free regions.  
- ❌ Inefficient if the disk is fragmented.  
- **Used in extent-based FS (e.g., NTFS, ext4 extents).**

---

## Comparison

| Method      | Structure              | Pros                        | Cons                        | Real Use |
|-------------|------------------------|-----------------------------|-----------------------------|----------|
| Bitmap      | Bit per block          | Compact, easy to scan       | Search for runs needed      | ext2–ext4 |
| Linked List | Pointer per block      | Simple                     | Slow, overhead              | Rare     |
| Grouping    | Linked list of arrays  | Faster batch allocations    | Uses free blocks as metadata | Classic  |
| Counting    | Runs of free blocks    | Very compact if contiguous  | Bad if fragmented           | NTFS, ext4 extents |

---
