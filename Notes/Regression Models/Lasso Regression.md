# [Lasso Regression]

**Type:** Supervised| **Task:** Regression| **Family: Model

---

## Introduction to [Lasso Regression]

- Lasso Regression works similarly to Linear Regression, except it applies L1 regularization.
- L1 regularization shrinks some coefficients exactly to zero and shrinks the remaining coefficients toward zero.
- As a result, features whose coefficients become zero are ignored during prediction.
- The strength of L1 regularization is controlled by the `alpha` parameter.


> **Intuition:** More regularized version of Ridge Regression.

---

## [Lasso alpha] (how [Alpha] affects L1 Regularization)

  
- **Smaller `alpha`** → Weaker regularization  
- **Larger `alpha`** → Stronger regularization  
  
---  
  
## Effect of Different `alpha` Values  
  
| Alpha | Regularization | Coefficient Shrinkage | Model Behavior |  
| ----- | -------------- | --------------------- | -------------- |  
| `0` | None | No shrinking | Equivalent to Linear Regression (may overfit) |  
| `0.1` | Weak | Some coefficients shrink slightly; a few may become `0` | Similar to Linear Regression |  
| `1.0` | Moderate (Default) | More coefficients become `0`; remaining coefficients shrink | Good balance between simplicity and performance |  
| `10` | Strong | Many coefficients become `0` | Performs feature selection; may underfit if too strong |  
| `100` | Very Strong | Most coefficients become `0` | Model may become too simple and underfit |  
  
---  
  
## Key Points  
  
- `alpha ↑` → Regularization ↑  
- `alpha ↑` → More coefficients become **exactly `0`**  
- `alpha ↑` → Remaining coefficients shrink toward `0`  
- `alpha ↑` → More features are removed from the model  
- `alpha ↑` → Simpler model  
- Very large `alpha` may cause **underfitting**.  
- `alpha = 0` removes regularization and makes Lasso behave like **Linear Regression**.  
  
---  
  
> **Rule to Remember**  
>  
> **Higher `alpha` = Stronger regularization = More coefficients become `0` = More feature selection = Simpler model.**  
  
> **Rule of Thumb:** Start with the default value (`alpha = 1.0`) and tune it using validation or cross-validation.



> **Rule of thumb: Start with the default value (`alpha = 1.0`).

---

## Math (light)

**[Formula name]:**

`[formula here]`

> **Why it matters:** _(One line on why this formula is relevant in practice)_

---

## Strength, Weakness and Parameters

### Parameters

- `[alpha]` — L1 Regularization

> ⚠️ **[Important gotcha or preprocessing note]**

### Strength

- Performs **automatic feature selection** by reducing some coefficients exactly to `0`.
- Helps reduce **overfitting** by applying L1 regularization.
- Produces a **simpler and more interpretable model** by using only the most important features.

### Weakness

- Can **underfit** if `alpha` is set too high.
- May remove **useful features** if regularization is too strong.
- May perform poorly when many features are highly correlated, as it tends to keep only one and ignore the others.

---

## When to Use

✅ Dataset has many features, feature selection is required, model is overfitting.

❌ All features are important, many features are highly correlated, relationship between features and target is highly non-linear.

---

## Personal Notes

_(your patterns, confusions, and "aha" moments here)_