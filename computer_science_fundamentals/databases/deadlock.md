<!-- File: databases/deadlock.md -->

# 🛑 Deadlocks in Databases

A **deadlock** occurs when two or more transactions are waiting for each other in a **circular chain**, creating a situation where none of them can proceed.

---

## 🔁 Deadlock Condition

A deadlock arises when **all** of the following four conditions hold simultaneously:

1. **Mutual Exclusion** – A resource can be held by only one transaction at a time.
2. **Hold and Wait** – Transactions holding resources can request new ones.
3. **No Preemption** – Resources cannot be forcibly taken from a transaction.
4. **Circular Wait** – A cycle of transactions exists, each waiting for the next.

> Example: T₁ waits for T₂, T₂ waits for T₃, ..., Tₙ waits for T₁.

---

## 🔍 Deadlock Detection

### ✅ **Wait-for Graph (WFG)**

- **Type:** Detection protocol
- **How it works:**  
  - Each transaction is a **node**.  
  - An edge `Tᵢ → Tⱼ` means Tᵢ is waiting for a resource held by Tⱼ.  
  - A **cycle** in the graph = deadlock detected.
- **What happens next:** The system aborts one or more transactions to break the cycle.

> POSCOMP-style tip: WFG is the **only** strategy in the multiple-choice list that **detects** deadlock after it has occurred.

---

## 🚫 Deadlock Prevention Protocols

These strategies **prevent** deadlocks by denying one or more of the four deadlock conditions:

### 🕒 **Wait-Die**

- **Older** transaction waits; **younger** is aborted (dies).
- Enforces a consistent timestamp-based ordering.

### 💥 **Wound-Wait**

- **Older** transaction "wounds" (preempts) younger transactions by aborting them.
- Younger ones must wait if they want to access locked resources.

### 🚷 **No-Wait**

- A transaction that requests a resource must get it **immediately**, or it's **aborted**.

### ❗ **Cautious Wait**

- A transaction can wait **only** if the lock holder is not **waiting** for another lock.
- Avoids cycles from forming.

---

## 🧠 Summary Table

| Strategy        | Type       | Key Idea                             |
|-----------------|------------|--------------------------------------|
| Wait-for Graph  | Detection  | Detect cycles in wait-for graph      |
| Wait-Die        | Prevention | Older waits; younger dies            |
| Wound-Wait      | Prevention | Older wounds (preempts) younger      |
| No-Wait         | Prevention | Abort if can't acquire immediately   |
| Cautious Wait   | Prevention | Wait only if lock holder isn’t waiting |

---
