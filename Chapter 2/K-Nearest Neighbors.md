# K-Nearest Neighbors (KNN)

**Type:** Supervised | **Task:** Classification + Regression | **Family:** Instance-based

---

## Introduction to KNeighborsClassifier

The model compares the nearest neighbors and classifies the data point's label with the majority of its neighbors.

> **Intuition:** No training happens. The algorithm memorizes the data and decides at prediction time.

---

## Decision Boundary (how the value of n affects it)

| Small `n`                           | Large `n`                            |
| ----------------------------------- | ------------------------------------ |
| Looks at very few neighbors         | Looks at many neighbors              |
| Very sensitive to individual points | Averages many points                 |
| Rough, complex decision boundary    | Smooth, simple decision boundary     |
| Fits noise and small details        | Ignores small but important patterns |
| Can **overfit**                     | Can **underfit**                     |

- **Small n** → rough decision boundary → overfitting
- **Large n** → smooth decision boundary → underfitting
- **n = all data points** → model predicts the same outcome every time (the majority class)

> **Rule of thumb:** Start with `n = √(total data points)` and tune from there.

---

## Introduction to KNeighborsRegressor

Works the same way, but instead of a majority vote it calculates the **average** of the neighbors to predict the value.

---

## Math (light)

Distance between two points is calculated using **Euclidean distance:**

`d = √((x₁−x₂)² + (y₁−y₂)² + ...)`

> **Why it matters:** Features with larger number ranges will dominate the distance calculation and make the model biased. Always scale your features before using KNN.

---

## Strength, Weakness and Parameters

### Parameters

Two main parameters to focus on:

- `n` — number of neighbors to compare
- `metric` — how you measure distance between two points (default: Euclidean)

> ⚠️ **Scaling is necessary.** If an algorithm compares distances between data points (like KNN), features with larger numerical ranges will otherwise dominate the distance calculation.

### Strength

- Easy to understand
- Gives reasonable performance with fewer adjustments
- Fast training

### Weakness

- Takes time for prediction
- Does not perform well with datasets with ≥ 100 features
- Performs badly with sparse datasets

---

## When to Use

✅ Small-to-medium datasets, non-linear boundaries, quick baseline  
❌ Large datasets (slow prediction), high-dimensional data, sparse data

---

## Personal Notes

_(your patterns, confusions, and "aha" moments here)_


