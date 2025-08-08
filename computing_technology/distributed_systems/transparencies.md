<!-- File: distributed_systems/transparencies.md -->

# 🧩 Transparencies in Distributed Systems

In distributed systems, **transparency** refers to hiding the complexity of the distributed nature of the system from users and applications. Ideally, distributed systems should appear as a **single coherent system**.

---

## ✅ Key Types of Transparency

| Type                 | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **Access**           | Hides differences in data representation and access methods.                |
| **Location**         | Hides where resources are located.                                          |
| **Migration**        | Hides that resources may move to different locations.                       |
| **Replication**      | Hides the presence of multiple replicas.                                    |
| **Concurrency**      | Hides that resources may be shared among multiple users.                    |
| **Failure**          | Hides failure and recovery of resources.                                    |
| **Persistence**      | Hides whether a resource is in volatile memory or on disk.                  |
| **Scaling (Scalability)** | Not a transparency itself, but refers to the system’s ability to grow smoothly. |

---

## 🔍 POSCOMP Question Example

> **Question 68 –**  
> Client programs should not know the file distribution. A single set of operations is provided for accessing local and remote files. Programs written to operate on local files are capable of accessing remote files without modification.  
>  
> What is the transparency requirement described for file services in distributed systems?

### ✅ Correct answer: **B) Access**

---

## 🧠 Explanation

- **Access Transparency**: Users/applications interact with files using the same API regardless of whether the file is local or remote.
- This reduces the need for custom code to handle different sources.
- The system **abstracts the differences** between local and remote operations.

---

## ❌ Why the Other Options Are Incorrect

- **A) Location**: Related to *where* resources are, but doesn’t guarantee uniform access methods.
- **C) Mobility**: Refers to movement of processes/resources, not uniform access.
- **D) Performance**: A system metric, not a transparency type.
- **E) Scalability**: Describes system capacity growth, not transparency.

---
