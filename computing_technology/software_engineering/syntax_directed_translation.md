Here’s a clean set of notes based on your content, formatted according to your coding/Markdown standards:

---

<!-- File: computing_technology/software_engineering/syntax_directed_translation.md -->

# Syntax-Directed Translation – Synthesized vs Inherited Attributes

## 1. Overview

**Syntax-directed translation** associates **semantic actions** with the productions of a grammar. Attributes can be:

* **Synthesized Attributes:**

  * Values are computed from the attributes of child nodes in the parse tree.
  * Information flows **up** the tree.

* **Inherited Attributes:**

  * Values are computed from parent or sibling nodes.
  * Information flows **down** or **across** the tree.

---

## 2. Example Grammar and Attribute Analysis

| Production         | Semantic Action         | Attribute Type |
| :----------------- | :---------------------- | :------------- |
| **1) L → E n**     | L.val = E.val           | Synthesized    |
| **2) E → E₁ + T**  | E.val = E₁.val + T.val  | Synthesized    |
| **3) E → T**       | E.val = T.val           | Synthesized    |
| **4) T → T₁ \* F** | T.val = T₁.val \* F.val | Synthesized    |
| **5) T → F**       | T.val = F.val           | Synthesized    |
| **6) F → (E)**     | F.val = E.val           | Synthesized    |
| **7) F → digit**   | F.val = digit.lexval    | Synthesized    |

---

## 3. Key Observations

* In all productions, **attributes of the left-hand side are calculated from the right-hand side**, making them **synthesized**.
* **Production 4** specifically:

  * T.val = T₁.val \* F.val → both **T.val** and **F.val** are synthesized.
* No inherited attributes appear in this set of semantic actions.

---

## 4. Summary

* **Synthesized attributes:** Pass information **up** from children → parent.
* **Inherited attributes:** Pass information **down or across** → from parent or siblings.
* In this grammar, all main attributes (L.val, E.val, T.val, F.val) are **synthesized**.

✅ **Important:** In production 4, T.val and F.val are synthesized.

---

If you want, I can also create a **compact visual diagram of the parse tree with synthesized attribute flow**, which makes it much easier to memorize for Poscomp-style exams. Do you want me to do that?
