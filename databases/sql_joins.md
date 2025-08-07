<!-- File: databases/sql_joins.md -->

# 🔗 SQL Joins

SQL joins combine rows from two or more tables based on a related column.

---

## 1. INNER JOIN

Returns only rows that exist in **both** tables.

```sql
SELECT *
FROM A
INNER JOIN B ON A.id = B.a_id;
````

**Venn Diagram:**

```
   A ∩ B
┌───────────┐
│   A   B   │
│    ◉      │ ← Only the intersection
└───────────┘
```

---

## 2. OUTER JOINS

Returns matching and non-matching rows, padding missing data with `NULL`.

---

### a. LEFT JOIN (LEFT OUTER JOIN)

Returns all rows from **A**, and matched rows from **B**.

```sql
SELECT *
FROM A
LEFT JOIN B ON A.id = B.a_id;
```

**Venn Diagram:**

```
   A ⊃ (A ∩ B)
┌───────────┐
│ ◉───      │ ← All of A, including matches
└───────────┘
```

---

### b. RIGHT JOIN (RIGHT OUTER JOIN)

Returns all rows from **B**, and matched rows from **A**.

```sql
SELECT *
FROM A
RIGHT JOIN B ON A.id = B.a_id;
```

**Venn Diagram:**

```
   B ⊃ (A ∩ B)
┌───────────┐
│     ───◉  │ ← All of B, including matches
└───────────┘
```

---

### c. FULL JOIN (FULL OUTER JOIN)

Returns all rows from **both** tables, including unmatched rows from either.

```sql
SELECT *
FROM A
FULL JOIN B ON A.id = B.a_id;
```

**Venn Diagram:**

```
   A ∪ B
┌───────────┐
│ ◉───◉     │ ← Everything from A and B
└───────────┘
```

---

## 3. CROSS JOIN

Returns the Cartesian product: every row in **A** paired with every row in **B**.

```sql
SELECT *
FROM A
CROSS JOIN B;
```

**Venn Diagram:**

```
A × B = all combinations
If A = 3 rows, B = 4 rows → Result = 12 rows
```

---

## 4. SELF JOIN

A table joined to itself.

```sql
SELECT A.name, B.name
FROM Employees A
JOIN Employees B ON A.manager_id = B.id;
```

**Use case:** Hierarchies (e.g., manager → employee).

---


