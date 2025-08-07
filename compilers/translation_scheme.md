<!-- File: compilers/translation_scheme.md -->

# 🔄 Translation Schemes

In compiler design, a **translation scheme** is a way to define how syntactic constructs are connected to semantic actions. It is a formal mechanism used in **syntax-directed translation**.

---

## 🧱 What Is a Translation Scheme?

A **Translation Scheme** is a:

> **Context-Free Grammar (CFG)** where **semantic actions** are embedded in the right-hand side of production rules.

- The grammar still defines the **syntactic structure**.
- The actions define what should happen **during parsing** — such as:
  - Code generation
  - Building syntax trees
  - Updating symbol tables
  - Performing checks or transformations

---

## 🧠 Key Concepts

- **Semantic Actions**: Pieces of code (usually written in the target implementation language) inserted directly inside production rules.
- **Execution Timing**: These actions are triggered as the parser **recognizes** parts of the grammar.
- **Ties Syntax to Semantics**: Translation schemes help implement compilers that not only recognize structure but also **produce output** tied to that structure.

---

## 💬 Example (Illustrative Only)

```bnf
E → E '+' T { print('+') }
  | T

T → 'num' { print(num.value) }
````

This scheme would output the **postfix notation** of arithmetic expressions. The semantic actions (`print(...)`) are performed as the parser applies each production.

---

## 🔍 Use Cases

* **Intermediate code generation**
* **AST (Abstract Syntax Tree) construction**
* **Symbol table updates**
* **Type checking (when combined with attribute grammars)**

---

## 🛠 Difference vs. Other Compiler Concepts

| Concept                    | Description                                 |
| -------------------------- | ------------------------------------------- |
| Translation Scheme         | CFG + embedded semantic actions             |
| Syntax-Directed Definition | CFG + attributes + rules for computing them |
| Dependency Graph           | Shows how attributes depend on each other   |
| Type Checking              | Ensures semantic correctness of data types  |
| Error Recovery             | Handles parsing errors gracefully           |

---

## 📌 Summary

* Translation schemes allow **interleaving parsing and semantic processing**.
* They are a practical way to define **syntax-directed translation**.
* Widely used in the implementation of **bottom-up parsers** (e.g., LR) and **top-down parsers** (e.g., LL).

---
