<!-- File: computer_science_fundamentals/computing_theory/programming_language_paradigms.md -->

# 🖥️ Programming Language Paradigms — Notes

---

## ✅ Overview

A **programming paradigm** is a style or way of programming that defines the approach to solving problems using a programming language. Paradigms influence:

* **How programs are structured**
* **How instructions are expressed**
* **The underlying computational model**

Common paradigms include:

* **Imperative**
* **Declarative**
* (Others: Functional, Object-Oriented, Logic-based, etc.)

---

## 🔹 1. Imperative Paradigm

The **Imperative Programming Paradigm** focuses on **how** to perform a computation by explicitly describing **a sequence of commands that change the program’s state**.

### **Key Characteristics**

* **State Changes:** The program modifies variables and memory.
* **Sequential Execution:** Instructions are executed in order.
* **Control Structures:** Explicit (`if`, `while`, `for`, etc.).
* **Von Neumann Architecture:**

  * Based on the **Von Neumann model**, where:

    * Instructions and data share memory.
    * Execution is sequential.
* **Typing:**

  * Depends on the language (e.g., C is strongly typed, Python is dynamically typed).

### **Examples**

* C
* Pascal
* Java
* Python

---

## 🔹 2. Declarative Paradigm

The **Declarative Programming Paradigm** focuses on **what** the program should accomplish, rather than **how** to achieve it. It specifies the desired result without explicitly listing control flow steps.

### **Key Characteristics**

* **No Explicit State Change:** Emphasizes descriptions over state mutations.
* **Abstract Specification:** Defines the properties of the result.
* **Implicit Control Flow:** The system determines execution order.
* **Independent of Architecture:** Not tied to Von Neumann model.

### **Examples**

* SQL (query-based)
* Prolog (logic programming)
* Haskell (functional programming)

---

## 🔍 Imperative vs Declarative Paradigms

| **Aspect**                   | **Imperative**                               | **Declarative**                                           |
| ---------------------------- | -------------------------------------------- | --------------------------------------------------------- |
| **Focus**                    | *How* to perform operations (explicit steps) | *What* result is desired (abstract specification)         |
| **State Changes**            | Yes, explicitly modifies state               | No explicit state changes, describes properties of result |
| **Control Flow**             | Explicit (`if`, `for`, `while`)              | Implicit, handled by the underlying system                |
| **Examples**                 | C, Java, Python                              | SQL, Prolog, Haskell                                      |
| **Relation to Architecture** | Based on **Von Neumann model**               | Independent of hardware architecture                      |

---
