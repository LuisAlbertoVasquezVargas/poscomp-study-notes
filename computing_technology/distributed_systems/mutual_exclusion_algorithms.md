<!-- File: distributed_systems/mutual_exclusion_algorithms.md -->

# Mutual Exclusion Algorithms in Distributed Systems

This section summarizes common mutual exclusion strategies in distributed systems, especially those relevant to the POSCOMP exam.

## 🧭 Centralized Mutual Exclusion ✅

- **Definition:** A designated coordinator controls access to the critical section.
- **How it works (3 messages total):**
  1. A process sends a **request** to the coordinator.
  2. The coordinator replies with a **permission** if the critical section is available.
  3. After executing, the process sends a **release** message to the coordinator.
- **Advantages:**
  - Simple and efficient (only 3 messages per entry/exit).
- **Disadvantages:**
  - The coordinator is a single point of failure.

## 🧱 Ricart-Agrawala Algorithm ❌

- **Definition:** A distributed algorithm based on timestamped request-reply messages.
- **Message Complexity:** 2(N−1) messages per entry (request + reply).
- **Features:**
  - No central coordinator.
  - Relies on total ordering via Lamport timestamps.

## 🔁 Token-Ring Algorithm ❌

- **Definition:** Processes are logically arranged in a ring; a token circulates.
- **Critical section access:** Only the process holding the token can enter.
- **Advantages:**
  - Fair and no starvation.
- **Disadvantages:**
  - Token loss requires regeneration.

## ⏱️ Lamport’s Timestamps ❌

- **Not a mutual exclusion algorithm per se.**
- **Purpose:** To totally order events in a distributed system.
- **Usage:** Often embedded in distributed algorithms (e.g., Ricart-Agrawala).

## 🔢 Vector Clocks ❌

- **Purpose:** Causality tracking in distributed systems.
- **Not directly used for mutual exclusion**, but important for event ordering in concurrent systems.

---

> The **centralized algorithm** is the only one among the options that meets the condition of using **exactly three messages** for entry and exit in the critical section.
