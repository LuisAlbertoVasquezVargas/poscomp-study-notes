<!-- File: computing_technology/databases/timestamp_ordering.md -->

# Timestamp Ordering (TSO) in Concurrency Control

## 1. Overview

**Timestamp Ordering (TSO)** is a concurrency control technique used in database systems to ensure **conflict serializability**.
Each transaction receives a unique timestamp:

$ts(T)$

For each data item $x$, the system maintains:

* Last read timestamp: $r_{ts}(x)$
* Last write timestamp: $w_{ts}(x)$

---

## 2. Write Rule in TSO

When a transaction $T$ with timestamp $ts(T)$ issues a **write(x)**:

* **Abort Condition**

$$
ts(T) \le r_{ts}(x) \text{ OR } ts(T) \le w_{ts}(x)
$$

* **Success Condition**

$$
ts(T) > r_{ts}(x) \text{ AND } ts(T) > w_{ts}(x)
$$

---

## 3. Logical Formulation

Abort condition:

$$
(r_{ts}(x) > ts(T)) \text{ OR } (w_{ts}(x) > ts(T))
$$

Negation (success condition):

$$
\neg(r_{ts}(x) > ts(T)) \text{ AND } \neg(w_{ts}(x) > ts(T))
$$

which simplifies to:

$$
(ts(T) \ge r_{ts}(x)) \text{ AND } (ts(T) \ge w_{ts}(x))
$$

---

## 4. Key Takeaways

* TSO enforces a **global serial order** using timestamps.
* Every conflicting operation must respect timestamp order.
* If a transaction violates the order, it **aborts**.
* The write rule is stricter than the read rule because a write can invalidate prior reads or writes.

---

