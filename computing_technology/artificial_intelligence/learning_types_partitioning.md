<!-- File: computing_technology/artificial_intelligence/learning_types_partitioning.md -->

# Learning Types and Partitioning – Artificial Intelligence

## Overview

* **AI/ML context**: Extract patterns or structure from data.
* **Learning types**:

  * **Supervised**: Uses labeled data.
  * **Unsupervised**: Works with unlabeled data; finds hidden structures.

## Unsupervised Learning

* **Goal**: Identify clusters or patterns without labels.
* **Tasks**:

  * Clustering
  * Association rules
  * Dimensionality reduction

## Partitioning Algorithms (Clustering)

* Divide dataset into clusters based on similarity.
* **Properties**:

  * No labeled data needed.
  * Each point → one cluster (fuzzy clustering allows overlap).
  * Number of clusters: predefined or auto-determined.

### Example: k-means

1. Initialize **k** centroids.
2. Assign points to nearest centroid.
3. Recalculate centroids.
4. Repeat until convergence.

* Applications: market segmentation, image compression.
* Sensitive to **k** and initial centroids.

## Other Artificial Intelligence / ML Algorithms

| Algorithm                      | Type               | Supervision  |
| ------------------------------ | ------------------ | ------------ |
| Apriori / FP-growth            | Association rules  | Unsupervised |
| Negative association mining    | Association rules  | Unsupervised |
| Sampling                       | Data preprocessing | N/A          |
| Decision tree (CART / FP-tree) | Classification     | Supervised   |

## Quick Summary

| Task           | Example       | Sup./Unsup.  | Output                    |
| -------------- | ------------- | ------------ | ------------------------- |
| Clustering     | k-means       | Unsupervised | Groups of similar points  |
| Association    | Apriori       | Unsupervised | Frequent itemsets / rules |
| Classification | Decision Tree | Supervised   | Predicted labels          |
| Sampling       | Random Sample | N/A          | Subset for analysis       |

**Key point:** k-means is the classic **unsupervised partitioning algorithm**.

---
