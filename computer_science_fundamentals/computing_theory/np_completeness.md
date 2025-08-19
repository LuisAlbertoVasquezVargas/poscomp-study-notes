<!-- File: computer_science_fundamentals/computing_theory/np_completeness.md -->

# NP-Completeness and Complexity Classes

---

## 1. Class P

- **Definition**: The set of decision problems solvable **deterministically in polynomial time**.  
- **Properties**:
  - Efficiently solvable on classical computers.
  - If a problem is in P, its **complement is also in P**.
- **Examples**:
  - Checking if a path exists between two nodes in a graph (using BFS or DFS).  
  - Determining if a number is prime (using modern deterministic algorithms).  

---

## 2. Class NP

- **Definition**: The set of decision problems where a **proposed solution can be verified in polynomial time**.  
- **Properties**:
  - **P ⊆ NP**: Every problem solvable in P can also be verified in polynomial time.
  - Verification is usually easier than finding a solution.
- **Examples**:
  - Hamiltonian path: Given a proposed path, check if it visits every node exactly once.
  - Sudoku: Verifying a filled board is correct is polynomial-time, but solving from scratch can be hard.

---

## 3. NP-Complete Problems

- **Definition**: A problem X is NP-complete if:
  1. **X ∈ NP**  
  2. **Every problem in NP can be reduced to X in polynomial time**.
- **Intuition**: NP-complete problems are the “hardest” problems in NP.
- **Important Fact**: If any NP-complete problem can be solved in polynomial time, then **P = NP**.
- **Examples**:
  - Boolean satisfiability (SAT, 3-SAT)  
  - Hamiltonian cycle  
  - Traveling Salesman (decision version)  

---

## 4. Complementary Problems

- **Complement of a decision problem X**: Swap YES and NO answers for all instances.  
- **Fact**: If X ∈ P, then its complement is also in P ⊆ NP.  

---

## 5. Relationships Between Classes

- **Venn diagram (simplified)**:

```

   +----------------+
   |       NP       |
   |   +--------+   |
   |   |   P    |   |
   |   +--------+   |
   +----------------+

```

- **P** is fully contained in **NP**.  
- NP-complete problems are assumed to be outside P (if P ≠ NP).  
- **State of the art**: It is unknown whether P = NP, but most experts conjecture **P ≠ NP**.

---

## 6. Quick Reference Table

| Class          | Definition / Example                                           | Key Fact |
|----------------|---------------------------------------------------------------|----------|
| **P**          | Solvable in polynomial time (graph path, primality test)      | P ⊆ NP |
| **NP**         | Verifiable in polynomial time (Hamiltonian path, Sudoku)     | Verification easy |
| **NP-complete**| Hardest problems in NP (SAT, Hamiltonian cycle, TSP)         | If one ∈ P → P = NP |
| **Complement** | Swap YES/NO answers                                           | If X ∈ P → complement ∈ P ⊆ NP |
