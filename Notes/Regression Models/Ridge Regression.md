# [Ridge Regression]

**Type:** Supervised | **Task:** Regression | **Family:** Model

---

## Introduction to [Ridge Regression]

When a linear model overfits Ridge Regression is used to generalize its performance.

- It adds a penalty for **large coefficients (absolute value)**.
- As a result, the coefficients of **all features** are shrunk toward zero, **but usually not exactly zero**.
- If a feature contributes **less** to making accurate predictions, its coefficient is shrunk **more**.
- If a feature contributes **more** to making accurate predictions, its coefficient is shrunk **less**.
- This helps reduce **overfitting** and improves the model's ability to generalize to new data.

> **Intuition:** Keep only the amount of each feature that is useful for prediction, while discouraging unnecessarily large coefficients.****

>**Note** :  The model adds penalty for each feature based on "If I reduce this coefficient, how much will my prediction accuracy decrease?"
>
>The model trades of training accuracy for overall generalized performance

---

## [Ridge Alpha parameter] (how [Alpha] affects L2 Regularization)
  
`alpha` controls the **strength of L2 regularization**.  
  
- **Smaller `alpha`** → Weaker regularization  
- **Larger `alpha`** → Stronger regularization  
  
---  
  
## Effect of Different `alpha` Values  
  
| Alpha | Regularization     | Coefficient Shrinkage              | Model Behavior                                |
| ----- | ------------------ | ---------------------------------- | --------------------------------------------- |
| `0`   | None               | No shrinking                       | Equivalent to Linear Regression (may overfit) |
| `0.1` | Weak               | Shrinks coefficients slightly      | Similar to Linear Regression                  |
| `1.0` | Moderate (Default) | Moderate shrinking                 | Good balance between bias and variance        |
| `10`  | Strong             | Shrinks coefficients significantly | Simpler model                                 |
| `100` | Very Strong        | Heavy shrinking                    | May underfit                                  |

## Key Points  
  
- `alpha ↑` → Regularization ↑  
- `alpha ↑` → Coefficients shrink more  
- `alpha ↑` → Simpler model  
- Very large `alpha` may cause **underfitting**.  
- `alpha = 0` removes regularization and makes Ridge behave like **Linear Regression**.  
  
---  
  
> **Rule to Remember**  
>  
> **Higher `alpha` = Stronger regularization = Smaller coefficients = Simpler model.**


> **Rule of thumb:** Start setting the value of alpha = 1.0(the default value). 

---


## Math (light)

**[Formula name]:**

`[formula here]`

> **Why it matters:** _(One line on why this formula is relevant in practice)_

---

## Strength, Weakness and Parameters

### Parameters

- `[alpha 1]` — [L2 Regulation]

### Strength

- Reduces **overfitting** by shrinking coefficients toward zero.
- Usually achieves **better test (generalization) performance** than Linear Regression, especially when the training dataset is small.
- Handles datasets with **many correlated features (multicollinearity)** more effectively than ordinary Linear Regression.

### Weakness

- Introduces a new hyperparameter (**`alpha`**) that must be chosen carefully.
- Does **not perform feature selection**; all features remain in the model because coefficients are rarely reduced exactly to zero.
- With **very large training datasets**, regularization becomes less important, and Ridge may offer little or no improvement over ordinary Linear Regression.

---

## When to Use

✅ **Use Ridge Regression when:**
- The dataset has **many features**, especially if some are correlated (multicollinearity).
- The model is **overfitting**, and you want better performance on unseen (test) data.
- You want to **keep all features** while reducing the impact of less important ones.

❌ **Avoid Ridge Regression when:**
- You want **automatic feature selection** (use Lasso instead, as it can reduce coefficients to exactly zero).
- You have **a very large amount of training data**, where ordinary Linear Regression may perform just as well.
- The relationship between features and the target is **highly non-linear**, since Ridge is still a linear model.

---

## Personal Notes

_(your patterns, confusions, and "aha" moments here)_

[[Lasso Regression]]

