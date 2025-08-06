<!-- File: computer_architecture/cache_hit_miss.md -->

# 🗂️ Cache Memory: Hit and Miss Formulas

Cache memory improves performance by storing frequently accessed data close to the CPU. Understanding hit and miss rates is key to analyzing cache effectiveness.

---

## 🔎 Definitions

- **Cache Hit:** The requested data is found in the cache.
- **Cache Miss:** The requested data is not found in the cache, requiring access to slower main memory.

---

## 🎯 Key Formulas

### Hit Rate (HR)

The probability that a memory access finds the data in cache:

```

HR = (Number of Cache Hits) / (Total Number of Memory Accesses)

```

or

```

HR = Hits / Accesses

```

### Miss Rate (MR)

The probability that a memory access does **not** find the data in cache:

```

MR = (Number of Cache Misses) / (Total Number of Memory Accesses)

```

or

```

MR = Misses / Accesses

```

---

## 📊 Relationship Between Hit and Miss Rates

```

HR + MR = 1

```

Because every access is either a hit or a miss.

---

## ⏳ Average Memory Access Time (AMAT)

To evaluate overall performance, AMAT is calculated as:

```

AMAT = (HR × Cache Access Time) + (MR × (Cache Access Time + Memory Access Time))

```

where:

- **Cache Access Time:** Time to access data if it's in cache.
- **Memory Access Time:** Time to access main memory (usually much larger).

---

## 🔄 Example

If:

- Cache access time = 1 ns
- Memory access time = 100 ns
- Hit rate = 0.95

Then:

```

AMAT = 0.95 × 1 ns + 0.05 × (1 ns + 100 ns) = 0.95 + 5.05 = 6 ns

```

---

## 📌 Summary

| Metric           | Formula                                 | Meaning                           |
|------------------|-----------------------------------------|---------------------------------|
| Hit Rate (HR)    | Hits / Accesses                         | Likelihood data is in cache     |
| Miss Rate (MR)   | Misses / Accesses                       | Likelihood data is not in cache |
| Average Memory Access Time (AMAT) | HR × Cache Time + MR × (Cache Time + Memory Time) | Expected time per memory access |

---

