<!-- File: distributed_systems/failure_models.md -->

# Failure Models in Distributed Systems

This section outlines common failure models in distributed systems, with definitions and examples relevant to typical POSCOMP-style questions.

## 🔧 Crash Failure (Falha por pane) ✅

- **Definition:** A crash failure occurs when a process or server **abruptly stops** and does not recover on its own. It was functioning correctly until the moment it stopped.
- **Example:** An operating system that suddenly stops responding, requiring a reboot.
- **Key point:** After a crash failure, the system does not produce any more output.

## 🚫 Omission Failure ❌

- **Definition:** A process or communication channel **fails to send or receive messages**.
- **Example:** A node receives a request but fails to send a response.
- **Key point:** The process is still running, but part of its communication is lost.

## ⏱️ Timing Failure ❌

- **Definition:** Responses from a process **arrive too early or too late**, violating expected timing constraints.
- **Example:** A system is expected to respond in 200ms but takes 800ms.
- **Key point:** The process functions but not within the time bounds of the system.

## 📤 Response Failure ❌

- **Definition:** The system **produces incorrect responses**.
- **Example:** A calculation node sends an incorrect result even though it responded on time.
- **Key point:** The structure and timing of communication are intact, but the content is wrong.

## 🌀 Arbitrary Failure (Byzantine) ❌

- **Definition:** The process behaves **unpredictably**, possibly sending corrupted or malicious output at any time.
- **Example:** A node sends misleading messages or collaborates with faulty nodes to deceive the system.
- **Key point:** This is the **most general and difficult** failure model to handle.

---

> These failure models are fundamental to reasoning about fault tolerance, reliability, and recovery strategies in distributed systems.

