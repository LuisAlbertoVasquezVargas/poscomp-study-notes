<!-- File: artificial_intelligence/genetic_algorithms.md -->

# 🧬 Genetic Algorithms (GA) – Key Operators

Genetic Algorithms are inspired by natural selection and genetics, using a population of candidate solutions to solve optimization problems.

---

## 🔑 Main Operators in GA

| Operator    | Purpose                                        |
|-------------|------------------------------------------------|
| **Selection** | Chooses individuals from the current population for reproduction based on fitness. |
| **Crossover** | Combines parts of two parent chromosomes to create new offspring. |
| **Mutation**  | Randomly alters genes in an individual to introduce variation. |
| **Fitness Evaluation** | Measures how well each individual solves the problem. |
| **Elitism** | Preserves best individuals to the next generation. |

---

## 🔄 Crossover Operator

- **Role:** Generates new individuals (offspring) by recombining genetic material from two parents.
- **How it works:**  
  - Selects one or more crossover points in parent chromosomes.  
  - Swaps segments of genes between parents to form new chromosomes.
- **Purpose:**  
  - Explores new regions of the solution space.  
  - Promotes genetic diversity.  
  - Mimics biological reproduction.

---

## 🧠 Other Operators (For Context)

- **Selection:** Picks parents based on fitness, e.g., roulette wheel, tournament.
- **Mutation:** Introduces small random changes to genes to maintain diversity.
- **Fitness Function:** Evaluates how good a solution is.
- **Elitism:** Keeps top individuals unchanged into the next generation.

---

## 📌 POSCOMP Tip

- **Crossover = combining parent genes to create offspring.**
- Remember:  
  - Mutation = random gene modification  
  - Selection = choosing who reproduces  
  - Fitness = evaluation of solution quality

---
