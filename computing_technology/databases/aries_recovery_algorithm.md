<!-- File: computing_technology/databases/aries_recovery_algorithm.md -->

# ARIES (Algorithm for Recovery and Isolation Exploiting Semantics) – Study Notes

## 1. ARIES Overview

* **Purpose:** Provides a recovery mechanism for database systems, ensuring atomicity and durability.
* **Key Principles:**

  1. **Write-ahead logging (WAL):** All updates are logged before being applied to the database.
  2. **Repeating history during REDO:** All changes are reapplied during REDO to restore the state before a crash.
  3. **Logging UNDO operations:** Uses **Compensation Log Records (CLRs)** to prevent redoing UNDO operations if a crash occurs during recovery.

---

## 2. Recovery Rules and Buffer Management

### 2.1 Steal / No-force Policy

* **Steal:** Dirty pages can be written to disk **before a transaction commits**.
* **No-force:** Committed transaction pages **do not need to be flushed immediately**.
* **Implication:** Allows flexible buffer management and improves performance.

### 2.2 Key Data Structures

1. **Transaction Table (TT):**

   * Tracks active transactions.
   * Contains:

     * Transaction ID (TID)
     * Status (Active / Committed / Aborted)
     * Last LSN of the transaction
   * ❌ Does **not** track dirty pages.

2. **Dirty Page Table (DPT):**

   * Tracks pages in the buffer cache that have been modified but not yet written to disk.
   * Contains:

     * Page ID
     * **RecLSN:** The LSN of the earliest log record affecting the page.

---

## 3. REDO and UNDO Operations

### 3.1 REDO

* Applied to **all updates that might not be reflected on disk**, including uncommitted transactions.
* Ensures the database **reaches the exact state it had in memory before a crash**.
* Conceptually: **“repeating history”**.

### 3.2 UNDO

* Applied to **transactions that were active but not committed at crash time**.
* **Compensation Log Records (CLRs):**

  * Each UNDO operation is logged.
  * Prevents redoing an UNDO operation if a crash occurs during recovery.
* Conceptually: **“reversing uncommitted changes”**.

---

## 4. Common Concepts in ARIES

| Concept                     | Explanation                                                                                                               |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| REDO applies to all updates | Ensures the database state in memory is restored, not limited to committed transactions.                                  |
| Steal / No-force policy     | Allows dirty pages to be written before commit (steal) and avoids forcing committed pages immediately to disk (no-force). |
| Logging UNDO operations     | CLRs record actions so that UNDO operations are not repeated after a crash.                                               |
| Tracking dirty pages        | Dirty pages are tracked in the **Dirty Page Table**, while the **Transaction Table** tracks active transactions.          |

---
