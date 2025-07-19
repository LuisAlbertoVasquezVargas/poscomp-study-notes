<!-- File: software_engineering/uml_class_diagrams.md -->

# UML Class Diagrams

---

## Purpose

UML (Unified Modeling Language) class diagrams visually represent the structure of a system by showing classes, their attributes, methods, and relationships.

---

## Key Elements

- **Class**: Represented as a rectangle divided into three sections:  
  - Top: Class name  
  - Middle: Attributes (variables)  
  - Bottom: Methods (functions)

- **Attributes**: List with visibility, name, and type  
  - Example: `- age: int` (private attribute)  
  - Visibility symbols:  
    - `+` Public  
    - `-` Private  
    - `#` Protected

- **Methods**: Similar format to attributes, with parameters and return type  
  - Example: `+ getAge(): int`

---

## Relationships

| Type               | Notation                | Description                                         |
|--------------------|-------------------------|-----------------------------------------------------|
| **Association**     | Solid line              | General connection between classes                  |
| **Multiplicity**    | Numbers near association | Specifies number of instances (e.g., 1..*, 0..1)    |
| **Aggregation**     | Hollow diamond          | “Has-a” relationship, whole-part but parts can exist independently |
| **Composition**     | Filled diamond          | Strong “Has-a” relationship; parts depend on whole |
| **Inheritance**     | Solid line with hollow arrow | “Is-a” relationship (generalization)                |
| **Dependency**      | Dashed arrow            | One class depends on another temporarily            |

---

## Example

```

+------------------+
\|     Person       |
+------------------+
\| - name: String   |
\| - age: int       |
+------------------+
\| + getName(): String |
\| + getAge(): int    |
+------------------+

```
     ^
     |
```

+------------------+
\|    Student       |
+------------------+
\| - studentId: int |
+------------------+
\| + getId(): int   |
+------------------+

```

---

## Tips

- Use clear, consistent naming.
- Keep class responsibilities focused.
- Use multiplicity to clarify relationships.
- Use aggregation vs composition appropriately.

---
