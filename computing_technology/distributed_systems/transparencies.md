<!-- File: distributed_systems/transparencies.md -->

# 🧩 Transparencies in Distributed Systems

In distributed systems, **transparency** refers to hiding the complexity of the system from users and applications. Ideally, distributed systems should appear as a **single coherent system**, regardless of the underlying distribution of resources and processes.

---

## ✅ Key Types of Transparency

| Type                      | Description                                                                             |
| ------------------------- | --------------------------------------------------------------------------------------- |
| **Access**                | Users/applications interact with resources the same way, regardless of location.        |
| **Location**              | Hides the physical location of resources.                                               |
| **Migration**             | Hides that resources may move to different locations.                                   |
| **Replication**           | Hides the presence of multiple replicas, making the system appear as a single resource. |
| **Concurrency**           | Hides that resources may be shared among multiple users.                                |
| **Failure**               | Hides failure and recovery of resources.                                                |
| **Persistence**           | Hides whether a resource is in volatile memory or on disk.                              |
| **Scaling (Scalability)** | Refers to the system’s ability to grow smoothly, not a transparency per se.             |

---

## 🧠 Explanation of Key Transparency Types

### 1. Concurrency Transparency

* Hides the fact that multiple processes run **concurrently** and may interact with shared resources.
* Ensures that concurrent access **does not lead to inconsistencies**.

### 2. Migration Transparency

* Allows a resource to move from one location to another **without affecting ongoing operations** accessing it.

### 3. Replication Transparency

* **Definition:** The system can maintain **multiple copies of a resource** to improve performance and availability, but users or applications are **unaware** of the replication.
* Users perceive the resource as a **single instance**.
* Ensures consistency and hides replication complexity.

### 4. Relocation Transparency

* Enables a resource to move to a **different physical location**.
* Usually occurs **offline** (while the resource is not being accessed).

### 5. Access Transparency

* Guarantees that **local and remote resources are accessed in the same way**.
* Users or applications **do not need to know** if a resource is local or remote.
* **Note:** Location hiding is specifically **location transparency**, a subtype of access transparency.

---

## ❌ Common Misconceptions

* **Access vs Location:** Access hides the method of interaction, location hides position.
* **Migration vs Relocation:** Migration can happen online, relocation usually offline.
* **Concurrency:** Focuses on simultaneous usage, not replication.
* **Failure, Persistence, Scalability:** Related to reliability, memory, or system growth, not transparency.

---
